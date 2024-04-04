---
description: Använd intelligenta bildtexter för att generera insikter på naturliga språk för att snabbt identifiera trender inom visualiseringar.
title: Intelligenta bildtexter
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c5f4ddd2f0a2840e7c0d456475f95d891863666e
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 1%

---

# Intelligenta bildtexter

Intelligenta bildtexter använder avancerad maskininlärning och generativ AI för att ge värdefulla insikter på naturspråket för arbetsytevisualiseringar. Den första versionen innehåller automatiskt genererade insikter om [Linje](line.md) visualisering. (Övriga visualiseringar följer.)

Intelligenta bildtexter inriktas på följande:

* Analytiker som behöver berättelser att dela med andra användare. Analytikerna behöver dessa insikter för att kunna ge sina användare kontext.
* Affärsanvändare som snabbt vill upptäcka högnivåaktiviteter.

Bildtexter är tillgängliga för alla Customer Journey Analytics-användare och kräver ingen särskild behörighet.

## Starta intelligenta bildtexter {#launch}

Om du vill starta automatiskt genererade bildtexter för en radvisualisering klickar du på **[!UICONTROL Intelligent captions]** ikonen längst upp till höger i visualiseringen.

![Öppna analysfönstret som visar trenden för intelligenta bildtexter för produktvyer. ](assets/intell-caps-1.png)

Naturliga språkkunskaper genereras nu.

Kom ihåg

* Du behöver minst 3 datapunkter för att bildtexterna ska kunna genereras. Annars kan du få ett felmeddelande som läser &quot;Inte tillräckligt med data för att analysera&quot;.

* Bildtexter genereras varje gång de underliggande markerade data ändras i tabellen som styr visualiseringen.

* Om det finns flera mätvärden i tabellen, genereras bildtexter endast för det första mätvärdet eller det mätvärde som användaren har valt.

* Om du sparar projektet nu och läser in det igen senare, uppdateras bildtexterna automatiskt med nya data. Detsamma gäller för schemalagda projekt och PDF-filer som exporteras från det här projektet.

## Visa och tolka bildtexter {#view}

Här följer ett exempel på hur bildtexterna kan se ut:

![Intelligenta bildtexter för linjevisualisering inklusive Seasonality, Min, Max, Spike och Decline.](assets/captions.png)

## Kopiera till Urklipp {#copy}

Du kan kopiera bildtexterna till ett urklipp och klistra in dem i en PowerPoint eller något annat verktyg. Hitta **[!UICONTROL Copy captions to clipboard]** ikonen längst upp till höger i dialogrutan med bildtexter.

## Redigera bildtexter {#edit}

Du kan redigera beskrivningarna, till exempel dölja eller visa en viss kategori med insikter. Om du t.ex. inte vill ha insikten om minimibeställningen kan du bara dölja den och klicka på Använd. Då visas den inte igen.

1. Klicka **[!UICONTROL Edit intelligent captions display]** -ikonen bredvid urklippsikonen.

1. I redigeringsdialogrutan klickar du på ögonikonen bredvid den insikt du vill dölja.

1. Klicka på **[!UICONTROL Apply]**.

Använd samma process för att visa bildtexter.

## Exportera bildtexter {#export}

Du kan **exportera bildtexter via PDF**, så länge projektet sparas med de bildtexter som skapas.

## Växla av bildtexter {#toggle}

Om du inte vill att intelligenta bildtexter ska genereras kan du inaktivera den här funktionen genom att gå till Visualiseringsinställningarna och avmarkera kryssrutan **[!UICONTROL Show intelligent captions]**.

![Alternativ för linjevisualisering som visar alternativet att avmarkera Visa intelligenta bildtexter.](assets/toggle-captions.png)

## Intelligenta bildtexter i Mobile Scorecards

Mer information finns i [Hantera styrkort](/help/mobile-app/manage-scorecard.md)