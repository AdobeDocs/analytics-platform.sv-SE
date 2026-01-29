---
title: Caveats
description: Caveats for BI-tillägget i olika BI-verktyg i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Caveats


Var och en av de BI-verktyg som stöds har några kavattningar i arbetet med Customer Journey Analytics BI-tillägget.

+++ BI-verktyg

>[!BEGINTABS]

>[!TAB Power BI Desktop]

* Power BI Desktop Advanced datumintervallfiltrering är exklusiv.  För slutdatumet måste du välja ett som är efter dagen som du vill rapportera på. Exempel: **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL and before]** `1/2/2023`.
* Power BI Skrivbord är som standard **[!UICONTROL Import]** när du skapar en anslutning. Kontrollera att du använder **[!UICONTROL Direct Query]**.
* Power BI Desktop visar dataomvandlingar via Power Query.  Power Query fungerar i första hand med Import-typanslutningar så många omformningar som du använder som datum- eller strängfunktioner ger ett felmeddelande om att du måste växla till en Import-typanslutning.  Om du behöver omforma data vid frågetillfället bör du använda härledda dimensioner och mätvärden så att Power BI inte behöver göra själva omformningarna.
* Power BI Desktop förstår inte hur typkolumner för datum och tid ska hanteras. Därför stöds inte **[!UICONTROL daterange*X *]**-dimensioner som **[!UICONTROL daterangehour]**&#x200B;och **[!UICONTROL daterangeminute]**.
* Power BI Desktop försöker som standard skapa flera anslutningar med hjälp av fler sessioner i frågetjänsten.  Gå till Power BI-inställningarna för ditt projekt och inaktivera parallella frågor.
* Power BI Desktop sköter all sortering och begränsning på klientsidan. Power BI Desktop har också olika semantik för toppfiltrering av *X* som innehåller bundna värden. Du kan alltså inte skapa samma sortering och begränsning som i Analysis Workspace.
* I tidigare versioner av Power BI Desktop, oktober 2024-versionen, bryts PostgreSQL-datakällor. Se till att du använder den version som omnämns i den här artikeln.

>[!TAB Skrivbord för Tablet PC]

* Datumfiltreringen för Tableu är exklusiv. För slutdatumet måste du välja ett som är efter dagen som du vill rapportera på.
* När du lägger till ett datum- eller datum-/tidsmått som **[!UICONTROL Daterangemonth]** på raderna i ett blad, radbryts fältet i en **[!UICONTROL YEAR()]**-funktion.  För att få det du vill ha måste du markera dimensionen och välja den datumfunktion du vill använda i listrutan.  Ändra till exempel **[!UICONTROL Year]** till **[!UICONTROL Month]** när du försöker använda **[!UICONTROL Daterangemonth]**.
* Det är inte uppenbart att resultaten begränsas till de övre *X* i skrivbordet i Tableu. Du kan begränsa resultaten explicit eller använda ett beräkningsfält och funktionen **[!UICONTROL INDEX()]**.  Om du lägger till ett översta *X*-filter i en dimension genereras komplex SQL med hjälp av en inre koppling som inte stöds.

>[!TAB Sökare]

* Looker har ett maximalt antal anslutningar per nod som måste vara mellan 5 och 100.  Du kan inte ange värdet 1.  Den här inställningen innebär att en Looker-anslutning alltid använder minst 5 av de tillgängliga frågetjänstsessionerna.
* Med Looker kan du skapa ett projekt med en vy som baseras på en Customer Journey Analytics datavy. Looker skapar sedan en modell baserad på de mått och mätvärden som är tillgängliga i datavyn med LookerML.  Den här projektvyn uppdateras inte automatiskt så att den matchar källan.  Om du ändrar eller lägger till mått, mått, beräknade värden eller segment i CJA datavy visas inte dessa ändringar automatiskt i Looker.  Du måste uppdatera projektvyn manuellt eller skapa ett nytt projekt.
* Uppslagets användarupplevelse i datum- eller datum-/tidsfält som **[!UICONTROL Daterange Date]** eller **[!UICONTROL Daterangeday Date]** är förvirrande.
* Lookers datumintervall är exklusivt i stället för inkluderande.  **[!UICONTROL until (before)]** är grått, så du kanske missar den aspekten.  För slutdagen måste du välja en som ligger efter den dag du vill rapportera på.
* Looker behandlar inte automatiskt mätvärden.  När du väljer ett mätvärde försöker Looker som standard att behandla mätvärdet som en dimension i frågan.  Om du vill behandla en mätmetod som en mätmetod måste du skapa ett anpassat fält enligt bilden ovan. Som genväg kan du välja **[!UICONTROL ⋮]**, markera **[!UICONTROL Aggregate]** och sedan välja **[!UICONTROL Sum]**.

>[!TAB Jupyter-anteckningsbok]

* Den största skillnaden för Jupyter Notebook är att verktyget inte har något dra och släpp-gränssnitt som andra BI-verktyg. Du kan skapa bra bilder, men du måste skriva kod för att uppnå detta.

>[!TAB RStudio]

* R-distributionen fungerar med ett platt schema så alternativet **[!UICONTROL FLATTEN]** krävs.
* Huvudkavatten för RStudio är att verktyget inte har ett dra och släpp-användargränssnitt som andra BI-verktyg. Du kan skapa bra bilder, men du måste skriva kod för att uppnå detta.

>[!ENDTABS]

+++
