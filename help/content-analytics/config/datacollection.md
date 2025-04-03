---
title: Content Analytics datainsamling
description: En översikt över hur data samlas in i Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 795116d41e40bf89ebf31572fb718e2bcb58a6c8
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Content Analytics datainsamling

I den här artikeln förklaras i detalj hur data samlas in med Content Analytics


## Definitioner

Följande definitioner används i den här artikeln:

* **Upplevelse**: En upplevelse definieras som textinnehållet på en hel webbsida. För datainsamling registrerar Content Analytics Experience ID. Content Analytics spelar inte in texten på sidan.
* **Experience ID**: En unik kombination av relevant URL och upplevelseversion.
   * Du anger, som en del av [configuration](configuration.md), vilka parametrar som är relevanta för alla angivna fullständiga URL:er.
   * Du kan definiera den [versionsidentifierare](manual.md#versioning) som används.
* **Resurs**: En bild. Content Analytics sparar resurs-URL:en.
* **Resurs-ID**: Resursens URL.
* **Relevant URL**: Bas-URL:en plus eventuella parametrar som driver innehållet på sidan.


## Funktionalitet

Content Analytics bibliotek samlar in data när:

* Content Analytics ingår i taggbiblioteket som är inläst på sidan.
* Sidans URL har konfigurerats i [Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, som ingår i det inkluderade taggbiblioteket.


## Content Analytics event

Ett Content Analytics-event består av:

* Standardfält
   * Tidsstämpel
   * Identitet
* Upplevelsevyer (om sådana finns, och om de är konfigurerade)
* Upplev klickningar (om sådana finns och har konfigurerats)
* Resursvyer (om sådana finns, och om de är konfigurerade)
* Resursklickningar (om sådana finns, och om de har konfigurerats)


Content Analytics-event samlas in som en sekvens av:

1. [En inspelad vy eller klicka på](#recorded-view-or-click).
1. [En vanlig eller specifik (beteendemässig) händelse](#regular-or-specific-behaviorial-event).

Content Analytics samlar in data på det här sättet för att återspegla den sekvensen, i stället för att samla in en vy eller klicka separat från att samla in händelsen direkt efter den vyn eller klickningen. Detta sätt att samla in innehållsanalysdata minskar också mängden data som samlas in. datainsamling.

### Inspelad vy eller klick

En resursvy registreras när:

* Resursen har inte exkluderats enligt ACA tilläggskonfiguration.
* Tillgången är 75 %.
* Tillgången har inte redan registrerats för den här sidan.

Ett klick på en mediefil registreras när:

* Resursen har visats.
* Resursen har inte exkluderats enligt ACA tilläggskonfiguration.
* Ett klick direkt på resursen, som är en länk, som leder till en annan sida.

En upplevelsevy registreras när:

* Upplevelser aktiveras i Content Analytics-konfigurationen.

En klickning spelas in när:

* Alla klick sker på en länk på sidan där upplevelserna är aktiverade.


### Regelbunden eller specifik (beteendemässig) händelse

Utlösare för att utlösa en vanlig eller specifik (beteendemässig) händelse i Content Analytics-sammanhang är:

* Web SDK eller AppMeasurement skickar en händelse.
* Synligheten ändras till dold, till exempel:
   * Sidan tas bort
   * Fliken Växla
   * Minimera webbläsare
   * Stäng webbläsaren
   * Lås skärm
* URL-adressen ändras, vilket resulterar i en ändrad relevant URL-adress.
* En resursvy överskrider batchgränsen på 32.


## Scheman

Content Analytics data samlas in i datauppsättningar i Experience Platform, baserat på specifika Content Analytics-scheman. Referensscheman är allmänt tillgängliga och används i en standardimplementering av Content Analytics.

* [Digital Asset-schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience-schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Upplev händelsens innehållsschema](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
