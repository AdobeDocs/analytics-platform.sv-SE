---
title: Uppgradera genväg Migrera en AppMeasurement- eller Analytics-tilläggsimplementering för att använda Web SDK
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Uppgraderingsgenväg: Migrera en AppMeasurement- eller Analytics-tilläggsimplementering för att använda Web SDK {#shortcut-migrate-websdk}

>[!NOTE]
>
>Den här dokumentationen bör användas som en del av uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrera din Analytics-implementering till att använda Web SDK"
>abstract="I stället för att skicka data via ett XDM-objekt kan du skicka alla variabler i AppMeasurement-format via dataobjektet. Med den här genvägen kan du fortsätta att använda din AppMeasurement-logik för att skicka data till plattformen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migrate_aa_to_websdk"
>title="Migrera din Analytics-implementering till att använda Web SDK"
>abstract="I stället för att skicka data via ett XDM-objekt kan du skicka alla variabler i AppMeasurement-format via dataobjektet. Med den här genvägen kan du fortsätta att använda din AppMeasurement-logik för att skicka data till plattformen."

<!-- markdownlint-enable MD034 -->

När du uppgraderar till Customer Journey Analytics rekommenderar Adobe [en ny implementering av Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation.

Om din Adobe Analytics-implementering är AppMeasurement eller Analytics-tillägget finns det en uppgraderingsgenväg som gör att du kan migrera din Adobe Analytics-implementering till Adobe Experience Platform Web SDK för att börja skicka data till Edge Network och Adobe Analytics innan du skickar den till Customer Journey Analytics.

## Fördelar och fördelar

Tänk på följande fördelar och nackdelar med uppgraderingsgenvägen när du migrerar din AppMeasurement- eller Analytics-implementering till att använda Web SDK:

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>**Tillhandahåller alla fördelar med att lagra data i Experience Edge Network**: <p>Några fördelar:</p><ul><li>Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för [användning av personalisering i realtid](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)</li><li>Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken utan att påverka din befintliga Adobe Analytics-rapportering.</li><li>**Ger flexibilitet att skapa ett XDM-schema för din organisation vid ett senare tillfälle**: Du kan migrera din befintliga Adobe Analytics-implementering till att använda Web SDK och verifiera att allt fungerar i Adobe Analytics, och sedan skapa XDM-schemat. Tack vare den här flexibiliteten kan du uppgradera till Customer Journey Analytics på ett mer metodiskt och genomtänkt sätt.</li></ul> | <ul><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i dataobjektet är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li><li>**Teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov. </li></ul> |

{style="table-layout:auto"}

## Grundläggande steg

Om du bestämmer dig för att migrera din AppMeasurement- eller Analytics-tilläggsimplementering till att använda Web SDK, läggs ett nytt steg till i de dynamiskt genererade stegen för din organisation i [Adobe Analytics till uppgraderingsenkäten för Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

De grundläggande stegen för att migrera en AppMeasurement- eller Analytics-tilläggsimplementering till att använda Web SDK är:

1. Börja skicka data till plattformen.

   Om du redan skickar data till Platform med din Adobe Analytics-implementering är det här steget inte obligatoriskt. Du behöver bara skapa en anslutning mellan plattformsdatauppsättningar och Customer Journey Analytics, vilket beskrivs senare i den här processen.

1. (Valfritt) Skapa ett XDM-schema för din organisation när du har tid.

1. (Villkorligt) Om du skapade ett XDM-schema kan du mappa alla fält i dataobjektet till XDM-schemat med hjälp av datastreamappning.
