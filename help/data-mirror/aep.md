---
title: Konfigurera Experience Platform
description: Förstå hur du konfigurerar scheman och datauppsättningar för Experience Platform Data Mirror för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: 578e19d8a8205bdfa034900c45d7d4a2d8f6a797
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Konfigurera Experience Platform

{{release-limited-testing}}

Experience Platform Data Mirror för Customer Journey Analytics kräver att flera Experience Platform-komponenter är korrekt konfigurerade:

* schema
* datauppsättning
* källkoppling

Här nedan hittar du information som du bör tänka på när du konfigurerar de här komponenterna.

## Schema

Du måste skapa ett [modellbaserat schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based){target="_blank"} som modellerar den interna datalagertabellen som du vill spegla. När du skapar det modellbaserade schemat måste du se till att följande krav uppfylls:

* När du uppmanas att ange typ av modellbaserat schema måste du välja det manuella alternativet.
* Välj lämpligt schema för datatypen. Observera att Experience Platform Data Mirror används mest för tidsseriedata (till exempel händelsedata).

* Definiera fälten i ditt schema och deras attribut
* Konfigurera obligatoriska attribut för fält i ett modellbaserat schema:

   * primärnyckel
   * versionsidentifierare
   * tidsstämpelidentifierare (för tidsseriedata).

## Datauppsättning

Du kan konfigurera en datauppsättning för schemat i förväg eller skapa en datauppsättning när du konfigurerar källkopplingen.
När du skapar en datauppsättning i förväg eller väljer en datauppsättning måste du se till att data använder ett modellbaserat [schema](#schema) som du skapade tidigare.


## Source Connector

Om du vill ställa in källkopplingen till de datalagerlösningar som stöds, använder du arbetsflödet Källor som leder dig igenom konfigurationen. Arbetsflödet består av följande steg:

### Autentisering

Autentisering mot den inbyggda datalagerlösningen som stöds finns i relevant Experience Platform-dokumentation:

* [Azure-databaser](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### Markera data

När du har anslutit till den inbyggda datalagerlösningen väljer du tabellen i den inbyggda datalagerlösningen som du vill använda för dataspegling. När du har valt det här alternativet visas en förhandsvisning av innehållet i data.


### Dataflödesdetaljer

Se till att du aktiverar registrering av ändringsdata. En informationspanel med en beskrivning av kraven för datainhämtning.

Ange en ny eller befintlig datauppsättning som är baserad på det modellbaserade schema som du skapade tidigare. Ange och välj andra alternativ i informationsgränssnittet för dataflöden.


### Mappning

Mappa fälten i tabellen i den inbyggda datalagerlösningen till fälten som du har angett för det modellbaserade schemat.


### Schemaläggning

Definiera ett schema för att spegla data från tabellen i den inbyggda datalagerlösningen till datauppsättningen i Experience Platform.


### Granska

Granska inställningarna för källkopplingen till den inbyggda datalagerlösningen som stöder spegling av data och ändring av datainhämtning.


När du är klar med konfigurationen av källkopplingen skapas ett dataflöde. Från den tidpunkten speglas dataändringar (infogningar, uppdateringar, borttagningar) i den inbyggda datalagerlösningen till den angivna datamängden.


>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda modellbaserade data](model-based.md)
>>[Data Mirror (Experience Platform-dokumentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>>[Modellbaserade scheman (Experience Platform-dokumentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
