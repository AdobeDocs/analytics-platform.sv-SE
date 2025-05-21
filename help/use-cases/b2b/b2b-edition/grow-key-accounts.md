---
title: Utöka nyckelkonton
description: Läs om hur du kan utöka nyckelkonton med Customer Journey Analytics B2B edition.
solution: Customer Journey Analytics
feature: Use Cases
role: User
hide: true
hidefromtoc: true
source-git-commit: d0268ce9ba22228c5c42d600c173f39cd1001638
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Utöka nyckelkonton

Att utöka och behålla nyckelkonton är en hög prioritet för B2B-företag. En förutsättning för att se till att avtalsutvecklingen går framåt är att kommunicera med viktiga intressenter i målkontona vid rätt tidpunkt.

När du funderar på hur nyckelkonton ska växa genom nya kundvärvnings-, lojalitets- eller merförsäljningsrörelser hjälper Customer Journey Analytics B2B edition dig (säljteamet och affärsanalytikerna) med djupare insikter i säljfasens utveckling och samarbete mellan olika team. I följande avsnitt finns exempel.

## Förlopp för försäljningsfas

Du vill generera och distribuera rapporter om ad hoc-lead-konvertering och förstå hur kontona utvecklas genom säljprocessen.

Med visualiseringen [Utfall](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) kan du visualisera konverterings- och avlämningsfrekvenser mellan fördefinierade steg under en sekventiell resa.

### Exempel

Du vill se utfallet för den översta säljtratten (från lead till tillfälle) för konton.

1. [Skapa och konfigurera en utfallsvisualisering](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md).
1. Välj ![Inställning](/help/assets/icons/Setting.svg) för att välja **[!UICONTROL Account]** som **[!UICONTROL Fallout container]**.
1. Den första kontaktytan ska vara **[!UICONTROL All Accounts]**.
1. Lägg till en ny kontaktyta: **[!UICONTROL Lead Form: Complete exists]**.
1. Lägg till en ny kontaktyta: **[!UICONTROL Lead Generated exists]**.
1. Lägg till en ny kontaktyta: **[!UICONTROL MQL Qualified exists]**.

   ![B2B - utöka nyckelkonton - status för försäljningsfas - utfall](assets/b2b-uc-grow-key-accounts-fallout.png)


## Collaboration

Ni vill förbättra kommunikationen mellan sälj-, marknadsförings- och produktgruppen. Tillgängliga alternativ för att säkerställa att alla intressenter har en enhetlig databerättelse är varningar, anteckningar, kommentering i projekt samt delning av rapporter och visualiseringar.

Du kan använda följande funktioner i Customer Journey Analytics B2B edition:

![Användningsexempel B2B - utöka nyckelkonton - samarbete - dela](assets/b2b-uc-grow-key-accounts-share.png)

1. [Anteckningar](/help/components/annotations/overview.md)
1. [Intelligenta aviseringar](/help/components/c-intelligent-alerts/intelligent-alerts.md)
1. [Dela med användare av arbetsytan eller med vem som helst](/help/analysis-workspace/curate-share/share-projects.md)
1. [Kommentarer](/help/analysis-workspace/build-workspace-project/comment-projects.md)

