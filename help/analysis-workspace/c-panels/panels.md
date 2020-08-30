---
description: 'null'
title: Översikt över paneler
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 2%

---


# Översikt över paneler

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

En panel är en samling tabeller och visualiseringar. Du kan öppna paneler från den övre vänstra ikonen på arbetsytan. Paneler är användbara när du vill organisera dina projekt enligt tidsperioder, affärsenheter, geografi osv. Dessa fyra typer av paneler finns i Analysis Workspace for Customer Journey Analytics:

* [Tom panel](blank-panel.md)
* [Snabbinsikter, panel](quickinsight.md)
* [Panelen Attribution](attribution.md)
* [Frihandspanel](freeform-panel.md)

Snabbinsikter, Blanka- och frihandspaneler är utmärkta platser att starta analysen på, medan attributets IQ-panel ger sig själv till mer avancerade analyser. A `"+"` knappen är tillgänglig i projekt så att du när som helst kan lägga till tomma paneler.

Standardstartpanelen är frihandspanelen, men du kan göra [tom panel](/help/analysis-workspace/c-panels/blank-panel.md) även din standard.

## Listruta-filter på paneler

Listringsfunktionerna för panelens släppzon finns i listrutan. Med dessa filter kan du interagera med projektdata på ett kontrollerat sätt så att du kan göra djupgående analyser, förenkla dina projekt och/eller dela med dig av insikter till andra.

Här följer ett exempel på ett förenklat projekt: Anta att du har flera versioner av ett projekt/en panel för att tillhandahålla landsspecifik rapportering. Du kan nu komprimera dessa projekt/paneler till en enda panel och lägga till i en landlistruta i stället för att filtrera mellan olika datauppsättningar.

![](assets/dropdowns.png)

Kom ihåg detta:

* Du kan släppa i flera komponenter (eller dimensionsobjekt) och sedan växla mellan dem i en listruta för att filtrera panelinnehållet.
* Du kan också skapa flera listrutor på samma panel.
* Du kan anpassa titeln på den nedrullningsbara listan genom att klicka på titeln och ändra den, eller ta bort titeln helt genom att klicka på x bredvid den.
* Du kan skapa nedrullningsbara filter med valfri komponenttyp: dimensioner, datumintervall, segment och mått. Observera att datumintervallen i listrutan alltid åsidosätter paneldatumintervallen.
* Vi behåller komponentfärgerna från vänster räl: gult för dimensionsartikelnedrullning, grönt för mått, blått för segment och lila för datumintervall.
* Idroppzonen skapar fortfarande segment på träffnivå för objekt som dras in som segment. Du kan ändra dem som vanligt genom att klicka på informationsikonen (i) bredvid segmentet, sedan på den pennformade redigeringsikonen och redigera den i Segment Builder.

**Så här skapar och använder du nedrullningsbara filter:**

1. Välj objekt från vänster räl och **samtidigt som du håller ner tangenten**, släppa dem i panelens släppzon.

   ![](assets/create_dropdown.png)

   Då omvandlas komponenterna till en listruta i stället för till ett segment. (Du kan även lägga till segment genom att inte hålla ned tangenten.)

   ![](assets/dropdown.png)

1. Välj ett av alternativen i listrutan om du vill ändra data på panelen nedan. (Du kan också välja att inte filtrera några paneldata genom att markera **[!UICONTROL No filter]**.
1. Om du t.ex. också vill segmentera data efter marknadsföringskanal kan du lägga till ytterligare en listruta som heter &quot;Marknadsföringskanal&quot;:

   ![](assets/mc_dropdown.png)

