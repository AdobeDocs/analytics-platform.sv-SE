---
title: Skapa en datavy
description: Beskriver hur du skapar en datavy för en plattformsdatauppsättning i kundreseanalys (CJA).
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Skapa en datavy

En datavy liknar en virtuell rapportserie i Analytics eftersom den i själva verket är en&quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan skapa flera datavyer för en enskild datauppsättning. Du kan till exempel ha en datavy där alla dimensioner är inställda på&quot;Sista beröringen&quot; och samtidigt en annan datavy (baserad på samma datauppsättning) med alla dimensioner inställda på&quot;Första beröringen&quot;.

Arbetsyteprojekt i kundreseanalys baseras på datavyer.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) för en videoöversikt.

## Förutsättning

Innan du kan skapa datavyer måste du [konfigurera en eller flera anslutningar till Experience Platform] -datauppsättningar](/help/connections/create-connection.md).

## Konfigurera inställningar

1. Gå till **[!UICONTROL Data Views]** fliken Customer Journey Analytics.

1. Klicka för **[!UICONTROL Add]** att lägga till en datavy och konfigurera dess inställningar.

   | Sessionsinställning | Definition |
   |---|---|
   | Anslutning | Det här fältet länkar datavyn till anslutningen som du upprättade tidigare, som innehåller [!UICONTROL Experience Platform] datauppsättningen/datauppsättningarna. |
   | Namn | Det är obligatoriskt att ge datavyn ett namn. |
   | Beskrivning | En detaljerad beskrivning är inte obligatorisk, men rekommenderas. |
   | Lägg till taggar | Med taggar kan du ordna datavyer i kategorier. |
   | Tidszon | Välj tidszon för datavyn. |
   | Tidsgräns för session | Välj vad din definition av en &quot;session&quot; är. Sessionens timeout-inställning definierar hur mycket inaktivitet en unik besökare måste ha innan en ny session startas automatiskt. Standardvärdet är 30 minuter. Om du till exempel anger timeout för sessionen till 45 minuter skapas en ny sessionsgruppering för varje sekvens av träffar som samlats in, åtskilda med 45 minuters inaktivitet. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Starta ny session med händelse | En ny session startar när en händelse utlöses, oavsett om en session har uppnått tidsgränsen eller inte. Den nyligen skapade sessionen innehåller händelsen som startade den. Dessutom kan du använda flera händelser för att starta en session och en ny session utlöses om någon av dessa händelser observeras i data. Den här inställningen påverkar antalet besök, segmentbehållaren för session (tidigare besök) och besökets förfallologik för dimensioner. |
   | Lägg till filter | &quot;Filter&quot; är termen för&quot;segment&quot; i kundreseanalys. Om du vill filtrera dina data drar du lämpligt filter hit från den vänstra listen. Om du inte väljer ett filter kommer datavyn att innehålla alla dina data. |

1. Klicka på **[!UICONTROL Continue]**.

## Lägg till komponenter

1. Nu är det dags att lägga till komponenter (mått, mätvärden) i datavyn (liknande kureringsupplevelsen i virtuella rapportsviter). Observera att vart och ett av fälten i datauppsättningarna nu översätts till mått eller mätvärden. Dra mått och mätvärden till panelen eller **[!UICONTROL Markera alla** om du vill lägga till alla komponenter.

   ![](assets/add-all-components.png)

1. Klicka på **[!UICONTROL Add Components]** fliken för att lägga till mått och mått i datavyn.

   ![](assets/add-all-components2.png)

1. (Valfritt) Du kan byta namn på en komponent till ett eget namn eller ändra dess attribueringsinställningar genom att markera den och redigera dess inställning. Observera att det underliggande namnet bevaras. Mer information finns i [Konfigurera datavyer och attribuering](/help/data-views/configure-dataviews.md).

1. Nästa steg är att [ange komponent- och attribueringsinställningar](/help/data-views/configure-dataviews.md).