---
description: Faktorer som påverkar arbetsytans prestanda och optimeringar som du kan göra
title: Analysis Workspace prestandafaktorer och optimering
feature: FAQ
exl-id: ad00e476-6f19-462b-ba53-d72ddd949802
source-git-commit: a546c52d2a686c38f7a9a23e0c541568c2918495
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 0%

---

# Optimera [!UICONTROL Analysis Workspace] prestanda

Olika faktorer kan påverka prestanda i ett projekt inom Analysis Workspace. Det är viktigt att du vet vad dessa medarbetare är innan du börjar bygga ett projekt, så att du kan planera och bygga projektet på det optimala sättet. Den här sidan innehåller en lista med faktorer som påverkar prestanda och optimeringar som du kan göra för att få bästa prestanda i Analysis Workspace.

## [!UICONTROL Help] > [!UICONTROL Performance] i Analysis Workspace

Under **Analysis Workspace > [!UICONTROL Help] >[!UICONTROL Performance]** kan du se faktorer som påverkar projektets prestanda, t.ex. nätverk, webbläsare och projektfaktorer. Du får bäst resultat om du tillåter att projektet läses in fullständigt innan du öppnar sidan Prestanda.

* Kolumnen Aktuellt projekt visar resultaten för ditt aktuella projekt och din användarmiljö.
* I kolumnen Riktlinje visas det rekommenderade tröskelvärdet för Adobe för varje faktor.

Dessutom kan du **Hämta som CSV** prestandainnehåll som enkelt kan delas med kundtjänst på Adobe eller interna IT-team.

>[!NOTE]
>
>Informationen på sidan Prestanda varierar varje gång som modalen öppnas, eftersom faktorerna kan ändras. Dessutom kommer Adobe att fortsätta att förfina riktlinjerna i takt med att mer data blir tillgängliga.

![](assets/performance-modal.png)

## Nätverksfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] nätverksfaktorer:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Anslutning till Adobe | Adobe skickar in 10 testanrop när prestandasidan öppnas. Detta motsvarar den procentandel av anropet till Adobe som lyckas. | Problem med lokala nätverk eller Adobe kommer att påverka den här faktorn. | Kontrollera status.adobe.com för att kontrollera om det finns några kända serviceproblem. Validera sedan din lokala nätverksanslutning. |
| Internetbandbredd | Endast för Google Chrome. Webbläsarens uppskattning av bandbredden på din plats. Riktlinjen är 2,0 MB/s. | Din lokala nätverksanslutning kommer att påverka den här faktorn. | Verifiera din lokala nätverksanslutning. |
| Internetfördröjning | Adobe skickar in 10 testanrop när prestandasidan öppnas. Detta anger den tid det i genomsnitt tar för varje begäran att åka till Adobe och returneras. Enklare uttryckt är det ett mått på hur snabbt Internet är mellan er plats och Adobe. Riktlinjen är &lt; 1 sekund. | Problem med lokala nätverk, många öppna webbläsarflikar eller problem med Adobe påverkar detta. | Kontrollera status.adobe.com för att kontrollera om det finns några kända serviceproblem. Validera sedan den lokala nätverksanslutningen och stäng webbläsarflikar som inte används. |

## Webbläsarfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] bland annat följande faktorer:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Beräkningshastighet | Hur snabbt datorn utför ett behandlingstest. Riktlinjen är &lt; 750 ms. | Din maskinvara och samtidiga program kommer att påverka detta. | Öppna Aktivitetshanteraren (PC) eller Aktivitetsövervakaren (Mac) för att avgöra om några program kan stängas. Stäng sedan webbläsarflikarna eller andra program som inte används. <br><br>Om dessa åtgärder inte hjälper dig, diskutera maskinvaruinformation med IT-teamet. |
| Minne som används | Endast för Google Chrome. Alla arbetsyteflikar i en webbläsare i Google Chrome delar totalt 4 GB minne. Detta motsvarar den procentandel av minnestilldelningen som används av det aktuella projektet. Riktlinjen är 3 500 MB, vilket är den punkt där Workspace börjar få minnesfel. | Att arbeta på flera flikar eller hämta 50000 rader data bidrar till ökad minnesanvändning. | Om du får ett minnesfel stänger du andra Workspace-flikar och/eller kör 50000-radens nedladdning en i taget. |
| Lokalt lagringsutrymme används | Data som lagras lokalt på datorn för användning i webbläsaren. Varje ursprung (t.ex. experience.adobe.com) har en tolerans på 10 MB. | Analysis Workspace använder lokal lagring för flera funktioner, bland annat för att lagra automatiskt sparade (befintliga) projekt, användarinställningar och funktionsflaggor. | För att säkerställa att Analysis Workspace funktioner inte störs bör du rensa den lokala lagringen för domänen experience.adobe.com. |
| Återgivningshastighet | FPS står för bildrutor per sekund, vilket är hur många gånger per sekund webbläsaren ritar sidan på skärmen. 24 FPS är det som det mänskliga ögat kan observera. Om antalet bildrutor/s är lägre än så kan du upptäcka återgivningsproblem i arbetsytan. | FPS påverkas av multikörning i många arbetsyteprojekt samtidigt och storleken på det projekt som visas ändras. Andra program som körs på datorn kan ha en effekt, t.ex. direktuppspelning, bakgrundsskannrar m.m. Dessutom påverkar maskinvaran den här faktorn. | Öppna Aktivitetshanteraren (PC) eller Aktivitetsövervakaren (Mac) för att avgöra om några program kan stängas. Stäng sedan webbläsarflikarna eller andra program som inte används. <br><br>Om dessa åtgärder inte hjälper dig, diskutera maskinvaruinformation med IT-teamet. |

## Projektfaktorer

[!UICONTROL Help] > [!UICONTROL Performance] projektfaktorer:

| Faktor | Definition | Optimering |
| --- | --- | --- |
| Antal frågor | Det totala antalet frågor (begäranden) som gjorts till Adobe för att hämta data som visas i projektet. Frågorna innehåller rankade begäranden om tabeller, avvikelseidentifiering, miniatyrbilder, komponenter som visas i den vänstra listen med mera. Exkluderar komprimerade paneler och visualiseringar. Riktlinjen är 100. | Förenkla projektet där det är möjligt genom att dela upp data i flera projekt som har ett specifikt syfte eller en grupp intressenter. Använd taggar för att ordna projekt i teman och använda [direktlänkning](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) skapa en intern innehållsförteckning så att intressenter enklare kan hitta det de behöver. |
| Utökade paneler (av totalt antal paneler) | Antalet expanderade paneler av det totala antalet paneler i projektet. Riktlinjen är 5. | När du har vidtagit åtgärder för att förenkla ditt projekt kan du komprimera paneler i projektet som inte behöver visas vid inläsning. När projektet öppnas bearbetas bara expanderade paneler. Komprimerade paneler bearbetas inte förrän användaren expanderar dem. |
| Utökade visualiseringar (av totalt antal visualiseringar) | Antalet utökade tabeller och visualiseringar av den totala mängden i projektet, inklusive dolda datakällor. Riktlinjen är 15. | När du har vidtagit åtgärder för att förenkla ditt projekt kan du komprimera visualiseringar i ditt projekt som inte behöver visas vid inläsning. Prioritera de bilder som är viktigast för konsumenten av rapporten och dela upp stödet till bilder i en separat, mer detaljerad panel eller projekt vid behov. |
| Antal frihandsceller | Det totala antalet frihandstabellceller i projektet, beräknat med rader * kolumner i alla tabeller. Utesluter dolda datakällor. Riktlinjen är 4000. | Minska antalet kolumner i tabellen till de mest relevanta datapunkterna. Minska antalet rader i tabellen genom att justera antalet rader som visas, använda ett tabellfilter eller använda ett filter. |
| Använda komponenter | Det totala antalet komponenter som används i projektet. Riktlinjen är 100. | Antalet använda komponenter påverkar inte prestandan direkt. Komplexiteten hos dessa komponenter kommer dock att bidra till projektets prestanda. Se optimeringarna i avsnittet&quot;Ytterligare faktorer&quot; nedan. |
| Senaste datumintervall | Den här faktorn visar det längsta datumintervallet som används i projektet. Riktlinjen är ett år. | Dra inte in mer data än du behöver när det är möjligt. Begränsa panelkalendern till relevanta datum för analysen eller använd datumintervallkomponenter (lila komponenter) i frihandstabellerna. Datumintervall som används i en tabell åsidosätter panelens datumintervall. Du kan till exempel lägga till sista månaden, sista veckan och igår i tabellkolumnerna för att begära dessa specifika dataintervall. Mer information om hur du arbetar med datumintervall i Analysis Workspace finns i [den här videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Dessutom bör du minimera antalet jämförelser mellan åren som används i projektet. När en jämförelse mellan år och år beräknas, utförs en genomgång av alla 13 månaders data mellan de givna månaderna. Detta har samma effekt som att ändra panelens datumintervall till de senaste 13 månaderna. |

## Ytterligare faktorer

Ytterligare faktorer som styr övergripande CJA-prestanda finns i [Optimera CJA-prestanda](/help/admin/cja-performance.md).