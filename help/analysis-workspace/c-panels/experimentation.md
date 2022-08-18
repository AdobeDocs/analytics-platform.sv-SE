---
description: Lär dig mer om hur du kan analysera resultaten av A/B-tester på CJA Experimentation-panelen.
title: Panelen Experimentation
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---


# Panelen Experimentation

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

The **[!UICONTROL Experimentation]** kan ni jämföra olika varianter av användarupplevelser, marknadsföring och meddelanden för att avgöra vilket som är bäst för att uppnå ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst - online, offline, från Adobe-lösningar, Adobe Journey Optimizer och till och med från BYO (ta fram egna) data.

>[!IMPORTANT]
>
>I det här skedet [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) (A4T) data kan inte utvärderas i [!UICONTROL Experimentation] -panelen.

## Åtkomstkontroll

Panelen Experimentation är tillgänglig för alla som använder Customer Journey Analytics (CJA). Inga administratörsrättigheter eller andra behörigheter krävs. Installationen kräver dock etiketter i datavyer som bara administratörer kan tilldela.

## Terminologi

* **Experimentera**: Ett experiment är en uppsättning variationer av en upplevelse som exponerats för slutanvändarna för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera variationer, varav en betraktas som kontrollvariationen.

* **Variation**: En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variation måste väljas som manöverorgan och endast en ändring kan anses vara kontrollvariationen.

* **Kontroll**: En specifik variant som representerar status quo, eller standardläge för en användarupplevelse. Vad alla andra variationer jämförs med.

* **Normaliserar mått**: Grundläggande (sessioner eller personer) som testet ska köras på. Ett test kan till exempel jämföra konverteringsgraden för flera variationer där konverteringsgraden beräknas som konverteringar per session eller konverteringar per person.

* **Konverteringsmått**: Det mått som en användare jämför variationer med. Variationen med det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) förklaras som&quot;vinnaren&quot; av ett experiment.

## Steg 1: Skapa anslutning för att experimentera med datauppsättningar

Efter att dina experimentdata har [inkapslad](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) till Adobe Experience Platform, [skapa en anslutning i CJA](/help/connections/create-connection.md) till en eller flera experimentdatauppsättningar.

## Steg 2: Lägga till kontextetiketter i datavyer

I inställningarna för CJA-datavyer kan administratörer lägga till [kontextetiketter](/help/data-views/component-settings/overview.md) till mått eller mätvärden och CJA-tjänster som [!UICONTROL Experimentation] kan använda dessa etiketter för sina ändamål. Två fördefinierade etiketter används för panelen Experimentation:

* [!UICONTROL Experiment]
* [!UICONTROL Variant]

I datavyn som innehåller experimentella data väljer du två dimensioner, en med experimentella data och en med variantdata. Ge sedan måtten etiketten med **[!UICONTROL Experiment]** och **[!UICONTROL Variant]** etiketter.

![kontextetikett](assets/context-label.png)

Experimentpanelen fungerar inte utan dessa etiketter.

## Steg 3: Konfigurera panelen Experimentera

1. I CJA Workspace drar du panelen Experimentation till ett projekt.

![experimentpanel](assets/experiment.png)




