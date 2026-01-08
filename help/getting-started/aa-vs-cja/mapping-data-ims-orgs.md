---
title: Mappa analysdata från flera IMS-organisationer
description: Lär dig hur du kan begära att mappa data från rapportsviter från flera IMS-organisationer med olika källor till en IMS-målorganisation.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Mappa analysdata från flera IMS-organisationer

Analysens källanslutning kan bara importera data från Adobe Analytics rapportsviter som tillhör samma organisation som du har rätt att använda Customer Journey Analytics för. Funktionen för att mappa analysdata från flera IMS-organisationer ger en lösning på den här begränsningen. Hur du aktiverar den här funktionen beskrivs i den här artikeln.


## Scenario

Ni har tillgång till flera IMS-organisationer och har Analytics-data i flera rapportsviter i dessa IMS-organisationer. Detta kan bero på följande:

* förvärv eller samgåenden
* organisatoriska strukturkrav
* begränsningar för regional distribution

Körklar kan du inte rapportera om kombinationen av data från flera rapportsviter i flera IMS-organisationer i Customer Journey Analytics. Anledningen till denna begränsning är att datainmatning från Adobe Analytics till Experience Platform via källkopplingen för analys endast stöder inmatning av data som ägs av en enda IMS-organisation. Den IMS-organisation som du är etablerad för och som du använder för att logga in på Adobe Analytics, Experience Platform och Customer Journey Analytics.

Med funktionen *mappa analysdata från flera IMS-organisationer* kan du begära att Adobe mappar data. Funktionen använder Analytics-källkopplingen för att mappa data från rapportsviter som finns i flera IMS-organisationer för *källa* till datauppsättningar som ingår i en IMS-organisation för *mål*. Exempel:

| Illustration | Förklaring |
|---|---|
| ![Mappa data över flera IMS-organisationer](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Med den här mappningen kan du rapportera om rapportsviter som finns i IMS-organisation 1, IMS-organisation 2 och IMS-organisation 3 från en anslutning i Customer Journey Analytics som har etablerats i IMS-organisation 3. |

{style="table-layout:fixed"}

## Så här använder du

Om du vill konfigurera och aktivera funktionen *mappa analysdata från flera IMS-organisationer* måste du begära mappningen via din kontohanterare för Adobe. Så här gör du:

1. Som administratör för IMS-målorganisation begär du e-postmeddelanden om godkännande från alla IMS-källorganisationens administratörer som du vill mappa rapportsviter för. Du kan använda följande text som mall för e-postmeddelandet för att begära godkännande från IMS-organisationens källadministratörer.

   | Exempelmall för e-post |
   | --- |
   | *Företagsnamnrepresentant*, om du vill ge den valda målorganisationen åtkomst till följande IMS-organ (lista över IMS-källorgan) måste du se till att en administratör för varje IMS-organisation skickar sitt godkännande för att ge åtkomst till deras data. Detta bidrar till att säkerställa att vi har respekterat dataåtkomstbehörigheterna från alla IMS-organisationer som påverkas. Se till att vi har fått rätt godkännande genom att ha en registrerad Adobe-administratör för varje administratör eller ett svar på det här e-postmeddelandet med namn och IMS-organisation som de representerar och som anger att de godkänner att IMS-organisationens data ska visas i målorganisationen [list destination IMS org]. Observera att den här administratören måste vara en administratör som är registrerad i Adobe-systemet som administratör för den IMS-organisationen. |

1. Skicka ett e-postmeddelande som mål-IMS-organisationsadministratör till den kontohanterare i Adobe som begär mappning från rapportsviter inom flera IMS-målorganisationer till mål-IMS-organisationen. Bifoga e-postmeddelanden om godkännande som du har fått från IMS-administratörerna för källorganisationen.

När kontohanteraren har fått e-postmeddelandet med en begäran om att mappa analysdata från flera organ, granskas begäran inom Adobe. Kontohanteraren kontaktar dig om du har frågor, utbildning eller annan information.

När mappningen har godkänts skapas den och du meddelas. Namnet på IMS-källorganisationen läggs till efter namnet på rapportsviten i listan [i Analytics-rapportsviterna](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) i Experience Platform.

## Begränsningar och risker

Följande begränsningar gäller för funktionen *map Analytics data från flera IMS-organisationer*:

* Du kan bara ansluta en rapportsserie en gång till olika organisationer.
* Du måste ta bort alla anslutningar för en IMS-organisation som är definierad som mål-IMS-organisation i en mappning innan du kan begära att mappningen ska tas bort.
* ECID:n är inte kompatibla mellan mappade IMS-källorganisationer och inte kompatibla med IMS-målorganisationen.
* En användare med tillräcklig behörighet för att konfigurera Analytics-källkopplingen i mål-IMS-organisationen kan importera Analytics-data från alla mappade IMS-källorganisationer. Inga behörigheter kontrolleras för den användaren för någon IMS-källorganisation.
