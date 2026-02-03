---
title: Stitching Overview
description: Lär dig mer om begrepp, fördelar, förutsättningar och begränsningar för identitetssammanfogning.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9bebfaf7e10762bc7382d8b0d55148ee23698dd9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 0%

---

# Översikt över titlar

>[!NOTE]
>
>Du måste ha Customer Journey Analytics **Select**-paketet eller senare (för [fältbaserad sammanfogning](fbs.md)) eller Customer Journey Analytics **Prime**-paketet eller senare (för [diagrambaserad sammanfogning](gbs.md)) för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

Identitetssammanfogning (eller helt enkelt sammanfogning) är en kraftfull funktion som ökar en händelsedatamängds lämplighet för flerkanalsanalys. Flerkanalsanalys är det viktigaste användningsområdet för Customer Journey Analytics. Med den här funktionen kan du kombinera och köra rapporter sömlöst på flera datauppsättningar från olika kanaler utifrån en gemensam identifierare (person-ID).

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel din webbplats via en annons på sin dator. Användaren köper en produkt, men sedan upptäcker användaren ett problem med ordern. Användaren ringer sedan kundtjänstteamet för att få hjälp med att lösa problemet. Med flerkanalsanalys kan du attribuera callcenter-händelser till annonsen som användaren ursprungligen klickade på.

Tyvärr är inte alla händelsebaserade datauppsättningar som är en del av din anslutning i Customer Journey Analytics tillräckligt kompletta med data för att stödja denna attribuering. I synnerhet har webbaserade eller mobilbaserade upplevelsedatamängder ofta ingen faktisk person-ID-information tillgänglig för alla händelser.

Stitching nycklar om identiteter inom en datauppsättnings rader för att säkerställa att person-ID (sammanfogat ID) är tillgängligt för varje händelse. Stitching undersöker användardata från både autentiserade och oautentiserade sessioner för att avgöra vilket ID-värde som kan användas som sammanfogat ID. Denna inmatning löser olika poster till ett sammanfogat ID för analys på personnivå, i stället för på enhets- eller cookienivå.

Customer Journey Analytics stöder två typer av sammanfogning: [fältbaserad sammanfogning](fbs.md) och [diagrambaserad sammanfogning](gbs.md).

## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att utföra flerkanalsanalys korrekt.

Innan du använder stygn bör du kontrollera att din organisation har förberetts med följande:

- Stitching inkluderar sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du aktiverar sammanfogning av en händelsedatamängd.

- Importera önskade data till Adobe Experience Platform:

   - Information om Adobe Analytics finns i [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Andra typer av data finns i [Skapa ett schema](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/tutorials/create-schema-ui) och [Infoga data](https://experienceleague.adobe.com/sv/docs/experience-platform/ingestion/home) i Adobe Experience Platform-dokumentationen.

Du kan dra nytta av flerkanalsanalys om du kombinerar en eller flera av dina sammanfogade datauppsättningar med andra datauppsättningar, till exempel callcenter-data, som en del av arbetet med att definiera din Customer Journey Analytics-anslutning. Den här anslutningskonfigurationen förutsätter att dessa andra datauppsättningar redan innehåller ett person-ID på varje rad, som liknar det sammanfogade ID:t.

När din organisation uppfyller allmänna [krav](overview.md#prerequisites), förstår vanliga [begränsningar](overview.md#limitations) och också sammanfogar metodspecifika ([fältbaserade](fbs.md) och [diagrambaserade](gbs.md)) krav och begränsningar, kan du följa de här stegen för att begära och börja använda sammanfogning i Customer Journey Analytics.


## Begränsningar

Stitching är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

- Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
- Med hjälp av fästfunktionen omvandlas inte det fält som används för sammanfogning på något sätt. Vid Stitching används värdet i det angivna fältet som det finns i den osydda datauppsättningen inom datarinden.
- Smältningsprocessen är skiftlägeskänslig. Identitetsvärdena `Bob` och `BOB` behandlas som två separata personer.

Försäkra dig om att du inte förväxlar stygn med:

- Sammanfogningen av två eller flera datauppsättningar. Gäller endast en datauppsättning. Sammanfogning av datauppsättningar sker som ett resultat av att en Customer Journey Analytics-anslutning skapas och att samma person-ID väljs för de markerade datauppsättningarna i anslutningen.

- Sammanfogning av två datauppsättningar. I Customer Journey Analytics används ofta en join för uppslag eller klassificeringar i Analysis Workspace. Även om sammanfogning använder sammanfogningsfunktioner innebär själva processen mer än sammanfogningar.


## Alternativ

Det Customer Journey Analytics-paket som du är berättigad till avgör vilka sammanfogningsmetoder som är tillgängliga, alternativ för inledande varaktighet för bakåtfyllning, fönster för uppspelningsfrekvens och maximalt antal datauppsättningar som tillåts för sammanfogning. Mer information finns i [Customer Journey Analytics produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/customer-journey-analytics.html). Bestäm vilka alternativ som är tillgängliga innan du aktiverar sammanfogning.

| | Customer Journey Analytics<br/>Välj | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Tillgängliga sammanfogningsmetoder | Fältbaserad stygn | Fältbaserad häftning<br/>Diagrambaserad häftning | Fältbaserad häftning<br>Diagrambaserad häftning</li> |
| Varaktighet för engångssammanfogning av bakfyllning | 13 månader | 13 månader | 25 månader |
| Fönster för uppspelning och uppspelningsfrekvens | 1 dag, varje dag<br/>upp till 7 dagar, varje vecka | 1 dag, varje dag<br/>upp till 14 dagar, varje vecka | 1 dag, varje dag<br/>upp till 30 dagar, varje vecka |
| Högsta antal datauppsättningar som tillåts för sammanfogning | 5 | 15 | 50 |

## Aktivera sammanfogning

Du kan aktivera sammanfogning på två sätt:

- [Begäran om att aktivera sammanfogning](/help/stitching/use-stitching.md) (borttagen). När den har godkänts skapas en duplicerad datauppsättning för den datauppsättning som du har begärt sammanfogning för. Den här duplicerade datauppsättningen innehåller en extra kolumn med den sammanslagna identifieraren. Du måste skapa en ny eller redigera en befintlig anslutning som innehåller den sammanslagna datauppsättningen för att kunna använda sammanfogade data i Customer Journey Analytics.
- [Aktivera sammanfogning i anslutningsgränssnittet](/help/stitching/use-stitching-ui.md). När du konfigurerar sammanfogning för en datauppsättning i anslutningsgränssnittet sker sammanfogningen direkt när data från den datauppsättningen i Customer Journey Analytics hämtas.


## Journey Optimizer dataset

Stitching stöder följande automatiskt genererade Journey Optimizer-datauppsättningar:

- AJO Journey Step Events
- Inkommande aktivitetshändelsedatauppsättning för AJO
- AJO Surfaces Dataset
- AJO händelsedatauppsättning för meddelandefeedback* AJO Push Tracking Experience Event datauppsättning
- AJO Experience Event-datauppsättning för e-postspårning
- AJO BCC Feedback Event Dataset
- AJO Live Activity Feedback Event - datauppsättning
- AJO ExD Decision Event Dataset

>[!MORELIKETHIS]
>
>[Fältbaserad häftning](fbs.md)
>[Diagrambaserad häftning &#x200B;](gbs.md)
>[Använd sammanfogning](use-stitching.md)
>[Validera sammanfogning &#x200B;](validate.md)
>[Vanliga frågor om stygn](faq.md)

