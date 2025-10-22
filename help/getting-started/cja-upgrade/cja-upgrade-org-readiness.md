---
title: Uppgradera från Adobe Analytics till Customer Journey Analytics
description: Läs mer om rekommenderad uppgradering från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 0%

---

# Förbered din organisation för uppgradering till Customer Journey Analytics

En del av en lyckad uppgradering (som beskrivs i [Uppgradera från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) är att förbereda organisationen genom att fokusera på vissa operativa överväganden. Vi rekommenderar att du:

* Inköp och anpassning från viktiga intressenter

* Definiera och dokumentera era era mål

* Ange realistiska och genomtänkta tidslinjer

* Definiera tydligt ansvar för medverkande

## Inköp och anpassning av intressenter

De viktigaste aktörerna och beslutsfattarna i organisationen måste anpassa sig efter uppgraderingen till Customer Journey Analytics.

I följande avsnitt beskrivs olika sätt att få kontakt med andra.

### Fokus på värde

Fokusera på det värde Customer Journey Analytics kommer att ge er och på hur ni kommer att nå era affärsmål snabbare.

Tabellen nedan innehåller några viktiga funktioner som du kanske vill markera.

| Funktion | Fördelar | Exempel |
|---------|----------|---------|
| **[Anordnande för alla typer av data](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/home)** | Customer Journey Analytics kombineras med Experience Platform förmåga att lagra alla typer av datarotor och datatyper. | En detaljhandelsorganisation skulle kunna ge hela kundresan synlighet genom att integrera följande typer av data i en enda vy: <ul><li>Webbklickströmstransaktioner</li><li>Mobilappstransaktioner</li><li>Butikstransaktioner</li><li>CRM- och lojalitetsdata</li></ul> |
| **[Flerkanalsanalys](/help/use-cases/cross-channel/cross-channel.md)** | Ger en samlad bild av kundbeteendet i olika kanaler genom att sammanföra data från olika webb-, mobil- och offlineegenskaper. | En detaljhandelsorganisation som samlar in data från flera kanaler kan utföra följande typ av analys:<p>En kund klickar på en betald sökannons, bläddrar bland jeans online, får ett push-meddelande och köper sedan i butiken två dagar senare. Det enhetliga perspektivet möjliggör korrekt flerkanalsattribuering och visar hur digitala kontaktytor bidrar till försäljningen i butiken. Det har också stöd för mer exakt segmentering, till exempel för kunder som surfar online, köpt i butiken med skräddarsydda erbjudanden. Dessutom ger det en tydlig intäktsrapportering i alla kanaler i en enda instrumentpanel, vilket ersätter fragmenterade, isolerade insikter med en helhetsbild av kundbeteendet. |
| **[Rapporttidsbearbetning](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Använd inställningar som är retroaktiva och skapa flera versioner av variabel beständighet utan att behöva ändra hur underliggande data samlas in. | Eftersom Customer Journey Analytics gör det möjligt att skapa och justera mätvärden, dimensioner och attribueringsmodeller direkt utan att inhämta eller bearbeta data, kan en detaljhandelsorganisation se hur en nyligen genomförd social kampanj påverkade både online- och butiksförsäljningen utan att behöva be konstruktionsavdelningen att bygga om datauppsättningar. De kan direkt ändra attribueringsmodellen från sista beröringen till första beröringen eller anpassa regelbaserad attribuering. |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | Hjälper marknadsförarna att förstå hur innehåll påverkar de nyckeltal som ett företag har definierat. Förutom beteendedata samlar Content Analytics in data om hur innehåll konsumeras och hur innehåll påverkar. | Genom att integrera webb-, app-, e-post- och till och med butiksdata kan en detaljhandelsorganisation se exakt hur varje del av det digitala innehåll de skapar bidrar till kundresan och konverteringen. <p>Detaljhandelsorganisationen kan se att en&quot;Sommardenimguide&quot; på en populär plattform för sociala medier skapar ett starkt engagemang bland lojalitetsmedlemmar och att dessa medlemmar är 40 % mer benägna att köpa denim i butik inom en vecka.</p> |

### Utse en chefssponsor

Hitta och utse en chefssponsor inom organisationen. Sponsorn behöver förstå hur Customer Journey Analytics kan nå era affärsmål snabbare.

Den verkställande sponsorn är av avgörande betydelse eftersom de

* Champion Customer Journey Analytics inom organisationen

* Ta bort vägspärrar

* Godkänn resurser

### Säker support från ledande aktörer i hela organisationen

Med hjälp av er chefssponsor kan ni få stöd från andra ledande aktörer i hela organisationen. Det är viktigt att ledarna inom följande områden i er organisation förstår fördelarna med Customer Journey Analytics och att de är villiga att bidra till en framgångsrik implementering:

* Analytics 

* Marknadsföring

* IT

* Juridisk information och efterlevnad

* Enskilda affärsenheter

## Utveckla en uppgraderings- och kommunikationsplan

### Utveckla en uppgraderingsplan och distribuera den till intressenter

En uppgraderingsplan kan innehålla följande information:

* En tydlig beskrivning av varför uppgraderingen sker. Beskriv t.ex. fördelarna för användarna och för organisationen eller företaget som helhet. Mer information om fördelarna finns i [Fokusera på värde](#focus-on-value).

* En allmän tidslinje, t.ex. när uppgraderingen är planerad att påbörjas, en översikt över viktiga milstolpar och en uppskattning av när uppgraderingen är planerad att slutföras.

* En indikation på när användare kan börja ta officiell utbildning för att lära sig hur de använder Customer Journey Analytics. Mer information finns i [Utbilda slutanvändare i hela organisationen](#train-end-users-throughout-your-organization).

* Information om vem som leder uppgraderingen och hur och när man kan få frågor.

### Skapa en kommunikationsplan

En kommunikationsplan kan innehålla följande:

* En definierad gräns för när meddelanden ska skickas till intressenter och användare

* En beskrivning av den typ av information som ska skickas

* En plan för vem som ska skicka kommunikation

* Definierade feedbackslingor som gör det möjligt för intressenter och användare att ställa frågor eller ge feedback

## Utvärdera och granska er implementering av Adobe Analytics

Utför en grundlig utvärdering och granskning av er Adobe Analytics-implementering, med fokus på följande nyckelområden:

* Aktuella användare

* Användaråtkomst

* Projekt

* Affärsprocesser

* Egna komponenter

Läs följande resurser om du vill få hjälp med att samla in den här informationen:

* [Analyslager](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/analytics-inventory)

  Ger information om antalet projekt, segment, beräknade värden, rapportsviter och användare i organisationen.

* [Förbered migrering av komponenter och projekt från Adobe Analytics till Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Innehåller information om hur du kan förbereda för att migrera komponenter, projekt och användare.

## Identifiera förespråkare och användare i förtid

Identifiera Champions i hela er organisation. Dessa kampioner bör vara:

* Adobe Analytics kraftfulla användare

* Kan snabbt skaffa sig kunskaper i Customer Journey Analytics

* Kan hjälpa andra i takt med att Customer Journey Analytics lanseras

## Utbilda slutanvändare i hela organisationen

* Ge praktisk utbildning som fokuserar på skillnaderna i datamodeller, rapportparadigmer och nya funktioner i Customer Journey Analytics.

* Erbjud både live-seminarier (workshops eller kontorstid) och on-demand-resurser (videokurser, dynamiska wiki-sidor och intern dokumentation).

* Direktanvändare till relevant utbildning, självstudiekurser och dokumentation om Experience League.

  Följande resurser kan hjälpa dig att komma igång:

   * [Customer Journey Analytics självstudiekurser](https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Vad är Customer Journey Analytics?](https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Introduktion till Customer Journey Analytics](https://experienceleague.adobe.com/sv/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)

## Följ de rekommenderade uppgraderingsstegen

När du är redo att påbörja uppgraderingen följer du de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de dynamiskt genererade uppgraderingsstegen i Customer Journey Analytics Upgrade Guide. Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.

