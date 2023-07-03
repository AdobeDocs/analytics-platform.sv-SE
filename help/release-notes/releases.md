---
description: Beskriver den kontinuerliga funktionsreleasestrategin för Customer Journey Analytics
title: Funktionsreleaser för Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 1%

---

# Funktionsreleaser för Customer Journey Analytics

Customer Journey Analytics-releaser fungerar enligt en kontinuerlig leveransmodell som möjliggör en skalbar, stegvis driftsättning av funktioner.

## Frisläppningsstrategi

[!UICONTROL Analysis Workspace] använder funktionsflaggor (kallas även&quot;växlar&quot;) för att styra synligheten för nya funktioner, vilket möjliggör kontrollerad skaltestning före den fullständiga versionen. Den här versionsstrategin innehåller följande faser:

* **Begränsad testning**: En stegvis release börjar med testning av användare i Adobe. Den görs sedan tillgänglig för en liten grupp kundkonton för att säkerställa att funktionen uppfyller kundernas behov och förväntningar.

* **Början av utrullning**: Utrullning av en fasversion börjar med den begränsade testfasen. Versionen skalas sedan från 0 % till 100 % för kunder under ett par månader. Utfasad utrullning sker på organisationsnivå, så att alla berättigade användare i en organisation får samma upplevelse.

* **Allmän tillgänglighet (GA)**: Funktionen är tillgänglig för 100 % av berättigade Experience Cloud-organisationer och har släppts fullständigt.

För varje funktionsversion kan tidslinjen från RTP till GA variera. Målet är att hålla releaserna korta, så att en funktion blir GA inom två månader från lanseringsstarten (RTP).

## Funktionsflaggor

Funktionsflaggor används för att styra synligheten för nya funktioner under lanseringen. Adobe rekommenderar att du lägger till `app.launchdarkly.com` till er brandvägg [tillåtelselista](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html) för en optimal upplevelse under lanseringen. Kort efter att GA har nåtts tas flaggan bort.

Du kan när som helst visa flaggor för den aktiva funktionen under **Hjälp > Om arbetsyta > Aktiva funktionsflaggor**.

## Fördelar

Med fasade versioner kan Adobe bättre anpassa driftsättningsprocessen och se till att funktionerna blir bättre före den allmänna tillgängligheten. Funktioner kan också släppas så snart de är tillgängliga, i stället för att följa ett fast månadsfönster.

## Vanliga frågor

| Fråga | Svar |
| --- | --- |
| Kan jag begära tidig åtkomst till en funktion? | Nej. Tidig tillgång kommer inte att beviljas.<br>Om du vill testa tidiga Analytics-koncept rekommenderar vi att du försöker [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html) för att ge feedback på våra branschledande innovationer. |
| Påverkar den här versionsstrategin min tillgång till funktioner? | Nej. När en funktion har nått GA får du tillgång till funktionen om den ingår i Analytics-paketet. |
