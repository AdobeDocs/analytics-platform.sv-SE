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
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

En panel är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i arbetsytan. Paneler är användbara när du vill ordna dina projekt efter tidsperioder, affärsenheter, geografi, osv. Följande fyra typer av paneler finns i Analysis Workspace för Customer Journey Analytics:

* [Tom panel](blank-panel.md)
* [Panelen Snabbinsikter](quickinsight.md)
* [Panelen Attribution](attribution.md)
* [Frihandspanel](freeform-panel.md)

Snabba insikter, tomma paneler och frihandspaneler är bra platser att börja analysera på, medan Attribution IQ ger sig själv till mer avancerade analyser. En `"+"`-knapp är tillgänglig i projekt, så du kan när som helst lägga till tomma paneler.

Standardstartpanelen är friformspanelen, men du kan göra den tomma panelen[till din standardpanel](/help/analysis-workspace/c-panels/blank-panel.md).

## Nedrullningsbara filter i paneler

Panelens listzon har funktioner för nedrullningsbar filtrering. Med dessa filter kan du interagera med projektdata på ett kontrollerat sätt så att du kan göra djupgående analyser, förenkla projekt och/eller dela insikter med andra.

Här är ett exempel på ett förenklat projekt: Anta att du har flera versioner av ett projekt/en panel för landsspecifik rapportering. Du kan nu komprimera dessa projekt/paneler till en enda panel och lägga till i en nedrullningsbar listruta i stället för att filtrera mellan olika datauppsättningar.

![](assets/dropdowns.png)

Tänk på detta:

* Du kan släppa flera komponenter (eller dimensionsobjekt) och sedan växla mellan dem i en listruta för att filtrera panelinnehållet.
* Du kan också skapa flera nedrullningsbara listor på samma panel.
* Du kan anpassa titeln på den nedrullningsbara listan genom att klicka på titeln och ändra den, eller ta bort titeln helt genom att klicka på x:et bredvid den.
* Du kan skapa nedrullningsbara filter med valfri komponenttyp: dimensioner, datumintervall, segment och mätvärden. Observera att datumintervall i listrutan alltid åsidosätter panelens datumintervall.
* Komponentfärgerna bevaras från den vänstra listen: gult för dimensionsobjektlistrutor, grönt för mätvärden, blått för segment och lila för datumintervall.
* Dropzone kommer fortfarande att skapa träffnivåsegment för objekt som dras som segment. Du kan ändra dessa som vanligt genom att klicka på informationsikonen (i) bredvid segmentet, sedan den pennformade redigeringsikonen och redigera den i segmentbyggaren.

**Så här skapar och använder du nedrullningsbara filter:**

1. Markera ett objekt från den vänstra listen och **håll ned** och släpp dem i panelens släppzon.

   ![](assets/create_dropdown.png)

   Detta gör att komponenterna förvandlas till en nedrullningsbar lista i stället för till ett segment. (Du kan även lägga till segment genom att inte hålla ned tangenten.)

   ![](assets/dropdown.png)

1. Välj ett av alternativen i listrutan om du vill ändra data i panelen nedan. (Du kan också välja att inte filtrera paneldata genom att välja **[!UICONTROL No filter]**.)
1. Om du till exempel även vill segmentera data efter marknadsföringskanal kan du lägga till en annan listruta som kallas&quot;marknadsföringskanal&quot;:

   ![](assets/mc_dropdown.png)

