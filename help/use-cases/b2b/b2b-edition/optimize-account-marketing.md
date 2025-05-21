---
title: Optimera kontomarknadsföring
description: Läs om hur ni optimerar kontomarknadsföring med Customer Journey Analytics B2B edition.
solution: Customer Journey Analytics
feature: Use Cases
role: User
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: d5e44546-ea82-42eb-98df-19d51c71e9be
source-git-commit: f66df039c56fc1df3fb0e102745f500a3782d26d
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# Optimera kontomarknadsföring

{{draft-b2b}}

Effektiv kontobaserad marknadsföring kräver en djupgående förståelse för köpresan på kontonivå. Så att ni kan avgöra vilka marknadsföringsaktiviteter som är mest effektiva för att skapa ett nära avtal.

För att få en förståelse vill du analysera och utforska:

* Marknadsföringseffekter:

   * Över flera kampanjer, kanaler och innehåll.
   * Om inköpsgrupper inom konton

* Försäljningsförloppet.
* Merförsäljning och korsförsäljning.
* Kundkontohälsa.


Customer Journey Analytics B2B edition kan hjälpa er att optimera kontomarknadsföringen. I följande avsnitt finns exempel.


## Kontobaserad marknadsföring

Ni vill identifiera vilka upplevelser, både online och offline, som är mest effektiva för att skapa slutna möjligheter.

Använd visualiseringen [Resursyta](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) för att mappa varje interaktion mellan konton, affärsmöjligheter, inköpsgrupper, kampanjer och kanaler för att få insikter om vad som fungerar i er kontomarknadsföring och var ni kan förbättra den.

Med en visualisering av arbetsytan kan du göra följande:

* Se hela artikeln. Du kan till exempel visa en detaljerad sökväg till ett *specifikt*-konto med högt värde eller en inköpsgrupp som innehåller alla kända interaktioner online och offline.
* Sammanställ viktiga stunder som leder till eller följer viktiga milstolpar (till exempel en marknadsföringskvalificerad lead-utlösare eller skapande av affärsmöjligheter).
* Stöder säljarna genom visualiseringens interaktionshistorik för specifika konton. En sådan visualisering möjliggör relevanta samtal.

### Exempel

Du vill visualisera resan från ett leadformulär till en stängd seger.

1. [Skapa och konfigurera en visualisering av en arbetsyta för resan](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
1. Konfigurera **[!UICONTROL Account]** som **[!UICONTROL Primary metric]**.
1. Se till att du väljer **[!UICONTROL Account]** som **[!UICONTROL Journey canvas container]**.

   ![Användningsexempel B2B - optimera kontomarknadsföring - arbetsyta för resan - config](assets/b2b-uc-optimize-marketing-journey-canvas-config.png)

1. Välj **[!UICONTROL Build]**.
1. Dra och släpp noder på arbetsytan och anslut noderna för att illustrera kontoresan. Till exempel: från **[!UICONTROL Lead Form: Step 1]**-formulär till **[!UICONTROL Opp. Created]**.

   ![Användningsexempel B2B - optimera kontomarknadsföring - arbetsyta för resan](assets/b2b-uc-optimize-marketing-journey-canvas.png)


## Kohortsegmentering

Du vill identifiera nyckelgruppen med köpare så att du kan aktivera de här köpargrupperna för andra kanaler, som betalda medier, e-post och sociala medier.

Använd [Kohorttabellvisualisering](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) för att gruppera B2B-enheter (konton, affärsmöjligheter, inköpsgrupper) baserat på en delad startpunkt (som ett lead-datum för en marknadskvalifikation (MQL)). Och spåra varje enhets förlopp över tiden i efterföljande faser eller milstolpar.

Med en kohorttabellvisualisering kan du:

* Analysera hur snabbt kohorter av konton eller affärsmöjligheter når viktiga milstolpar (t.ex. från en marknadsföringsberättigad lead till en säljkvalificerad lead) under veckor eller månader.
* Identifiera om vissa kohorter (per segment, kampanjkälla, köpgruppstyp) rör sig snabbare genom säljcykeln än andra kohorter.
* Utvärdera om strategiska initiativ (till exempel marknadsföringskampanjer) korrelerar med kortare utvecklingstider för efterföljande kohorter.

### Exempel

Du vill se månatliga kohorter av stängda möjligheter.

1. [Skapa och konfigurera en kohorttabellvisualisering](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
1. Använd **[!UICONTROL Opportunity Created]** som **[!UICONTROL Inclusion criteria]**-mått. Välj **[!UICONTROL >=]** som operator och ange värdet `1`.
1. Använd **[!UICONTROL Closed-Won]** som **[!UICONTROL Return criteria]**-mått. Välj **[!UICONTROL >=]** som operator och ange värdet `1`.
1. Välj **[!UICONTROL Opportunity]** som behållare.

   ![Användningsexempel B2B - kohortsegmentering - kohorttabell - config](assets/b2b-uc-optimize-marketing-cohort-table-config.png)

1. Välj **[!UICONTROL Build]**. Nedan finns ett exempel på en kohorttabell.

   ![Användningsexempel B2B - kohortsegmentering - kohorttabell](assets/b2b-uc-optimize-marketing-cohort-table.png)


## Personliga händelser

Du vill rapportera om engagerad konto- och visningsaktivitet för flera personliga händelser. Så att ni kan analysera och optimera effekten av personlig närvaro.

Med en [flödesvisualisering](/help/analysis-workspace/visualizations/c-flow/flow.md) kan du visualisera sökvägar för användare, men nu även konton eller köpgrupper, ta mellan interaktioner eller faser över tid.

Med en flödesvisualisering kan ni:

* Identifiera de vanligaste sekvenserna av kontaktytor som genomkorsas av B2B-enheter (t.ex. från *webbplatsbesök* till *Informationsnedladdning* till *demonstrationsbegäran*).
* Visualisera hur konton eller inköpsgrupper navigerar icke-linjärt (till exempel: hoppa bakåt, hoppa över steg eller ta oväntade vägar).
* Fokusera på flödet före eller efter en kritisk interaktion (till exempel en demonstrationsbegäran) för att förstå vilka faktorer som bidrar till eller vilka åtgärder som följer efter interaktionen.

### Exempel

Ni vill visualisera effekten på genereringen av MQL (marknadsföringskvalificerade leads).

1. [Skapa och konfigurera visualisering av flöde](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
1. Välj **[!UICONTROL MQL Qualified]** för **[!UICONTROL End with]**.
1. Välj **[!UICONTROL Content Type]** för **[!UICONTROL Pathing dimension]**.
1. Välj **[!UICONTROL Show advanced settings]**.
1. Ange `5` som **[!UICONTROL Number of columns]**.
1. Välj **[!UICONTROL Account]** för **[!UICONTROL Flow container]**.

   ![Användningsexempel för B2B - personliga händelser - flödeskonfiguration](assets/b2b-uc-optimize-marketing-flow-config.png)

1. Välj **[!UICONTROL Build]**.

   ![Användningsexempel för B2B - personliga händelser - flödeskonfiguration](assets/b2b-uc-optimize-marketing-flow.png)
