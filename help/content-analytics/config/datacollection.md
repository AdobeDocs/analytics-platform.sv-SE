---
title: Content Analytics datainsamling
description: En översikt över hur data samlas in i Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 7909388273af4c19d2dfda671c2af8eac470fff9
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---

# Content Analytics datainsamling

I den här artikeln beskrivs i detalj hur Content Analytics samlar in data

## Definitioner

Följande definitioner används i den här artikeln:

* **Upplevelse**: En upplevelse definieras som textinnehållet på en hel webbsida. För datainsamling registrerar Content Analytics det Experience ID som baseras på sidans URL. Senare hämtas texten på sidan via hämtningstjänsten.
* **Experience ID**: En unik kombination av relevant URL (bas-URL plus eventuella parametrar som driver innehåll på sidan) och [upplevelseversion](manual.md#versioning).
   * Du anger, som en del av [configuration](configuration.md), vilka parametrar som är relevanta för alla angivna fullständiga URL:er.
   * Du definierar en [versionsidentifierare](manual.md#versioning) som ska användas, så att du samlar in ändringar i dina upplevelser på rätt sätt.
* **Resurs**: En bild. Content Analytics sparar resurs-URL:en.
* **Resurs-ID**: Resursens URL.
* **Relevant URL**: Bas-URL:en plus eventuella parametrar som driver innehållet på sidan.


## Funktionalitet

Content Analytics kräver att Experience Platform Edge Network Web SDK samlar in data om innehållshändelser. Händelsedatainsamlingen kombineras med (befintlig) datainsamling av beteendehändelsedata via funktioner som Experience Platform Edge Network (Web SDK, Server API) eller Analytics-källkopplingen (till exempel med AppMeasurement).

Content Analytics bibliotek samlar in data när:

* Content Analytics ingår i taggbiblioteket som är inläst på sidan.
* Sidans URL har konfigurerats i [Content Analytics-tillägget](https://experienceleague.adobe.com/sv/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, som ingår i det inkluderade taggbiblioteket.


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
1. [En utlösare för att skicka en Content Analytics-händelse](#trigger-to-send-a-content-analytics-event).

Content Analytics samlar in data på det här sättet för att återspegla den sekvensen, i stället för att samla in en vy eller klicka separat från att samla in händelsen direkt efter den vyn eller klickningen. Detta sätt att samla in innehållsanalysdata minskar också mängden data som samlas in.

### Inspelad vy eller klick

En resursvy registreras när:

* Resursen har inte exkluderats enligt Content Analytics tilläggskonfiguration.
* Tillgången är 75 %.
* Tillgången har inte redan registrerats för den här sidan.

Ett klick på en mediefil registreras när:

* Resursen har visats.
* Resursen har inte exkluderats enligt Content Analytics tilläggskonfiguration.
* Ett klick direkt på resursen, som är en länk, som leder till en annan sida.

En upplevelsevy registreras när:

* Upplevelser aktiveras i Content Analytics-konfigurationen.

En klickning spelas in när:

* Alla klick sker på en länk på sidan där upplevelserna är aktiverade.


### Utlösare för att skicka en Content Analytics-händelse

För att minska antalet samtal som lämnar sidan samlar Content Analytics in information men skickar inte informationen direkt. Information om innehållsinteraktion samlas in och en händelse som innehåller den informationen skickas endast när någon av följande utlösare inträffar:

* Web SDK eller AppMeasurement skickar en händelse.
* Synligheten ändras till dold, till exempel:
   * Sidan tas bort
   * Fliken Växla
   * Minimera webbläsare
   * Stäng webbläsaren
   * Lås skärm
* URL-adressen ändras, vilket resulterar i en ändrad relevant URL-adress.
* Inspelade resursvyer som är klara att skickas överskrider antalet 32.

>[!NOTE]
>
>De ytterligare Content Analytics-händelserna påverkar troligen alla definitioner av studsfrekvens som baseras på antalet händelser i en session eller på en sida.
>


## Scheman

Content Analytics data samlas in i datauppsättningar i Experience Platform, baserat på specifika Content Analytics-scheman. Referensscheman är allmänt tillgängliga:

* [Digital Asset-schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience-schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Upplev händelsens innehållsschema](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
