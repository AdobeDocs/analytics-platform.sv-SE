---
title: Skapa en datavy
description: Beskriver hur du skapar en datavy till en plattformsdatamängd i Customer Journey Analytics (CJA).
translation-type: tm+mt
source-git-commit: de265170126c1a9fc1f66364a79a74ff487d0b71
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# Skapa en datavy

En datavyn liknar en virtuell rapportsvit i Analytics, eftersom den på sätt och vis är en &quot;filtrerad&quot; vy av data. Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns, attribut osv. för besök. Du kan skapa flera datavyer för en enskild datamängd. Du kan t.ex. ha en datavy där alla dimensioner är inställda på &quot;Last Touch&quot; och samtidigt en annan datavy (baserad på samma datamängd) med alla dimensioner inställda på &quot;First Touch&quot;.

Arbetsyteprojekt i Customer Journey Analytics baseras på datavyer.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) för en videoöversikt.

## Nödvändig

Innan du kan skapa datavyer måste du [konfigurera en eller flera anslutningar till Experience Platform-datauppsättningar](/help/connections/create-connection.md).

## Konfigurera inställningar

1. Gå till Customer Journey Analytics **[!UICONTROL Data Views]** flik.

1. Klicka **[!UICONTROL Add]** för att lägga till en datavy och konfigurera dess inställningar.

   | Sessionsinställning | Definition |
   |---|---|
   | Anslutning | Det här fältet länkar datavyn till den anslutning som du tidigare upprättade och som innehåller [!UICONTROL Experience Platform] datamängd/datamängder. |
   | Namn | Det är obligatoriskt att ge datavyn ett namn. |
   | Beskrivning | En detaljerad beskrivning är inte obligatorisk, men rekommenderas. |
   | Lägg till taggar | Med taggar kan du ordna datavyer i kategorier. |
   | Tidszon | Välj tidszon för datavyn. |
   | Tidsgräns för session | Välj vad du vill definiera som &quot;session&quot;. Tidsgränsen för sessionen anger hur mycket inaktivitet en unik besökare måste ha innan en ny session startas automatiskt. Standardvärdet är 30 minuter. Om du t.ex. anger sessionens timeout till 45 minuter skapas en ny sessionsgruppering för varje sekvens av träffar som samlas in, åtskild med 45 minuters inaktivitet. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Starta ny session med händelse | En ny session startar när en händelse utlöses, oavsett om tidsgränsen för en session har uppnåtts. Den nyligen skapade sessionen innehåller händelsen som startade den. Dessutom kan du använda flera händelser för att starta en session och ett nytt sessionsbränder om någon av dessa händelser observeras i data. Den här inställningen påverkar ditt besöksantal, segmentbehållaren för session (tidigare besök) och besökets förfallologik för dimensioner. |
   | Lägg till filter | &quot;Filter&quot; är termen för &quot;segment&quot; i Customer Journey Analytics. Om du vill filtrera data drar du det aktuella filtret här från vänster räl. Om du inte väljer ett filter innehåller datavyn alla data. |

1. Klicka på **[!UICONTROL Continue]**.

## Lägg till komponenter

1. Nu är det dags att lägga till komponenter (dimensioner, mått) i datavyn (liknande kursionsupplevelsen i virtuella rapportuppsättningar). Observera att alla fält i datauppsättningarna nu översätts till dimensioner eller mått. Dra mått och mått till panelen eller **[!UICONTROL Select All]** om du vill lägga till alla komponenter.

   ![](assets/add-all-components.png)

1. Klicka på **[!UICONTROL Add Components]** Fliken om du vill lägga till dimensioner och mått i datavyn.

   ![](assets/add-all-components2.png)

1. (Valfritt) Du kan byta namn på en komponent till ett eget namn eller ändra dess attributinställningar genom att markera den och redigera dess inställning. Observera att det underliggande namnet bevaras. Mer information finns i [Konfigurera datavyer och attribut](/help/data-views/configure-dataviews.md).

1. Nästa steg är att [ange inställningar för komponenter och attribut](/help/data-views/configure-dataviews.md).