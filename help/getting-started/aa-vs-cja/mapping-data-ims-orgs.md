---
title: Mappa analysdata från flera IMS-organisationer
description: Lär dig hur du kan begära att mappa data från rapportsviter från flera IMS-organisationer för att rapportera programsviter och slutligen datauppsättningar i en IMS-målorganisation.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 888420e8cd11cd447fec99257b213669edd345c1
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 0%

---

# Datamappning mellan IMS

I den här artikeln beskrivs hur du mappar data från rapportsviter i flera IMS-organisationer till rapportsviter, och i slutänden datauppsättningar, i en IMS-organisation.

Källkopplingen för Analytics importerar data från Adobe Analytics rapportsviter inom en enda organisation som standard. *Cross-IMS-datamappning* är en funktion för att mappa Analytics-data från flera IMS-organisationer och erbjuder en lösning för den här begränsningen. Hur du aktiverar den här funktionen beskrivs i den här artikeln.


## Scenario

Ni har tillgång till flera IMS-organisationer och har Analytics-data i flera rapportsviter i dessa IMS-organisationer. Detta kan bero på följande:

* förvärv eller samgåenden
* organisatoriska strukturkrav
* begränsningar för regional distribution

Körklar kan du inte rapportera om kombinationen av data från flera rapportsviter i flera IMS-organisationer i Customer Journey Analytics. Anledningen till denna begränsning är att datainmatning från Adobe Analytics till Experience Platform via källkopplingen för analys endast stöder inmatning av data som ägs av en enda IMS-organisation. Den IMS-organisation som du är etablerad för och som du använder för att logga in på Adobe Analytics, Experience Platform och Customer Journey Analytics.

Med *Cross-IMS-datamappning* kan du begära att Adobe mappar data. Funktionen använder Analytics-källkopplingen för att mappa data från rapportsviter som finns i flera IMS-organisationer för *källa* för att rapportera programsviter (och i slutändan datauppsättningar) som ingår i en IMS-organisation för *mål*. Exempel:

| Illustration | Förklaring |
|---|---|
| ![Mappa data över flera IMS-organisationer](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Med den här mappningen kan du rapportera om rapportsviter som finns i IMS-organisation 1, IMS-organisation 2 och IMS-organisation 3 från en anslutning i Customer Journey Analytics som har etablerats i IMS-organisation 3. |

{style="table-layout:fixed"}

## Så här använder du

Om du vill konfigurera och aktivera datamappningen *Cross-IMS* måste du begära mappningen via din kontohanterare för Adobe. Så här gör du:

1. Som administratör för IMS-målorganisation begär du e-postmeddelanden om godkännande från alla IMS-källorganisationens administratörer som du vill mappa rapportsviter för. Du kan använda följande text som mall för e-postmeddelandet för att begära godkännande från IMS-organisationens källadministratörer.

   | Exempelmall för e-post |
   | --- |
   | *Företagsnamnrepresentant*, om du vill ge den valda målorganisationen åtkomst till följande IMS-organ (lista över IMS-källorgan) måste du se till att en administratör för varje IMS-organisation skickar sitt godkännande för att ge åtkomst till deras data. Detta bidrar till att säkerställa att vi har respekterat dataåtkomstbehörigheterna från alla IMS-organisationer som påverkas. Se till att vi har fått rätt godkännande genom att ha en registrerad Adobe-administratör för varje administratör eller ett svar på det här e-postmeddelandet med namn och IMS-organisation som de representerar och som anger att de godkänner att IMS-organisationens data ska visas i målorganisationen [list destination IMS org]. Observera att den här administratören måste vara en administratör som är registrerad i Adobe-systemet som administratör för den IMS-organisationen. |

1. Skicka ett e-postmeddelande till kontohanteraren för Adobe för IMS-organisationens måladministratör som begär mappning från rapportsviter inom flera IMS-målorganisationer till IMS-målorganisationen. Bifoga e-postmeddelanden om godkännande som du har fått från IMS-administratörerna för källorganisationen.

När Adobe Account Manager har fått e-postmeddelandet med en begäran om att mappa analysdata från flera organ, granskas begäran inom Adobe. Adobe Account Manager kontaktar dig om du har frågor, utbildning eller annan information.

När mappningen har godkänts skapas den och du meddelas. Namnet på IMS-källorganisationen läggs till efter namnet på rapportsviten i listan [i Analytics-rapportsviterna](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) i Experience Platform.


## Begränsningar

Följande begränsningar gäller för datamappningsfunktionen *Cross-IMS*:

* Du kan bara ansluta en rapportsserie en gång till olika organisationer.
* Du måste ta bort alla anslutningar för en IMS-organisation som är definierad som mål-IMS-organisation i en mappning innan du kan begära att mappningen ska tas bort.
* ECID:n är inte kompatibla mellan mappade IMS-källorganisationer och inte kompatibla med IMS-målorganisationen.


## Överväganden

Du kanske vill ta hänsyn till följande ämnen innan du begär datamappningen *Cross-IMS*:

### Profiler

När funktionen *Cross-IMS-datamappning* har godkänts kan du lägga till data i Experience Platform för en eller flera av rapportsviterna i mål-IMS-organisationen. Det gör du genom att konfigurera [Analytics-källkopplingen](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Måldatauppsättningar skapas sedan i Experience Platform. Som en del av den här konfigurationen och processen kan du välja att skicka profildata från en eller flera rapportsviter till profiltjänsten.

Uppskatta det totala antalet profiler som är resultatet av konfigurationen och processen enligt ovan. Se till att det totala antalet ligger inom det antal profiler som du enligt avtal har rätt till för målorganisationen. Använd [filtreringsregler och villkor](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} om du vill inkludera eller exkludera data selektivt från konsumtion till profiltjänsten. Eller inaktivera alternativet att skicka profildata till profiltjänsten för relevanta rapportsviter.


#### Stitlar

Du kan använda både [fältbaserad](/help/stitching/fbs.md) och [diagrambaserad](/help/stitching/gbs.md) sammanfogning på måldatamängderna. När du använder diagrambaserad sammanfogning på en eller flera av dessa måldatamängder måste du se till att du håller dig inom dina avtalsenliga berättiganden för antalet profiler enligt beskrivningen i avsnittet [Profiler](#profiles).

Om du inte är licensierad för kundprofil i realtid, men ändå vill använda diagrambaserad sammanfogning på en eller flera måldatauppsättningar, kontrollerar du att du bara aktiverar [identitetstjänsten](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) för dessa måldatauppsättningar.


### Behörigheter

En användare med tillräcklig behörighet för att konfigurera Analytics-källkopplingen i mål-IMS-organisationen kan importera Analytics-data från alla mappade IMS-källorganisationer. Inga behörigheter kontrolleras för den användaren för någon IMS-källorganisation.

### Rapport om data

Funktionen *Cross-IMS-datamappning* är bara ett första steg som säkerställer att du kan använda data som en del av en Customer Journey Analytics [anslutning](/help/connections/overview.md), en eller flera [datavyer](/help/data-views/data-views.md) och [arbetsyteprojekt](/help/analysis-workspace/home.md). Du måste noggrant kontrollera de data som du nu har tillgängliga i en IMS-organisation. Ta hänsyn till funktioner som datapresentation, härledda fält, extra uppslagstabeller med mera innan du kan rapportera dessa data på rätt sätt.
