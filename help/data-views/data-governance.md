---
title: CJA-stöd för Adobe Experience Platform Data Governance
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# CJA-stöd för Adobe Experience Platform Data Governance

Integrationen mellan CJA och [Adobe Experience Platform datastyrning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) möjliggör märkning av känsliga CJA-data och tillämpning av sekretesspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för CJA-datavyer. Dessa etiketter stoppar eller varnar användare som skapar mätvärden och/eller dimensioner från känsliga fält.

När data exporteras från CJA (via rapportering, export, API osv.) läggs dessutom varningar eller etiketter till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett visst sätt.

Tack vare den här integreringen kan ni hantera regelefterlevnaden enklare. Datahanteringen i organisationen kan ange regler som begränsar användningen. Detta innebär att era CJA-användare kan använda data med större tillförsikt, i vetskap om att de följer policyer som definieras av dataförvaltare.

## Etiketter och regler i Adobe Experience Platform

När du skapar en datauppsättning i Experience Platform kan du skapa [etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) för vissa eller alla element i datauppsättningen. Hittills har dessa etiketter inte exponerats i CJA. I den här versionen kan du visa dessa etiketter i CJA. CJA är av särskilt intresse för C8-etiketten, som säger&quot;Data kan inte användas för att mäta organisationens webbplatser eller appar&quot;.

Etikettering i sig innebär inte att dessa dataanvändningsetiketter används. Det är det policyer används för. Du skapar dina profiler via [API för principtjänst](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) i Experience Platform.

Principer har två komponenter: Dataetiketten och en marknadsföringsåtgärd som datakonsumentkan vidta inom ramen för begränsade dataanvändningspolicyer. Inom ramen för CJA har två Adobe definierats [marknadsföringsaktiviteter](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) är viktiga:

* Analys - använda data för analyssyften, som att mäta, analysera och rapportera om konsumentanvändningen av organisationens webbplatser eller appar.

* Exportera dessa data från Adobe-miljön, t.ex. exportera data till en tredje part.

Ni knyter etiketter och marknadsföringsåtgärder till en policy och aktiverar sedan policyn. Policyn tar etiketten och marknadsföringsåtgärderna och säger: tillämpa denna begränsning. Två Adobe-definierade politiska strategier presenteras i CJA:

* Analyspolicy
* Hämtningspolicy

## Visa dataetiketter i CJA-datavyer

Dataetiketter som har skapats i Experience Platform visas på tre platser i användargränssnittet för datavyer:

| Plats | Beskrivning |
| --- | --- |
| Informationsknappen i ett schemafält | Om du klickar på den här knappen visas vilka dataanvändningsetiketter som gäller för ett fält:<p>![](assets/data-label-left.png) |
| Höger räl under [Komponentinställningar](/help/data-views/component-settings/overview.md) | Etiketter för dataanvändning visas här:<p>![](assets/data-label-right.png) |
| Lägg till dataetiketter som en kolumn | Du kan lägga till dataetiketter som en kolumn i kolumnerna Inkluderade komponenter i datavyer. Klicka bara på ikonen för kolumnväljaren och välj Etiketter för dataanvändning:<p>![](assets/data-label-column.png) |

### Filtrera på datastyrningsetiketter i CJA

I redigeraren för datavyer klickar du på filterikonen i det vänstra spåret och filtrerar datavykomponenter efter datastyrningsetiketter:

![](assets/filter-labels.png)

### Filter på datastyrningsprinciper i CJA

Du kan kontrollera om en profil är aktiverad som blockerar användningen av vissa CJA-datavytelement för analys eller export.

Klicka på ikonen Filter igen i den vänstra listen och klicka på Profiler under Datastyrning:

![](assets/filter-policies.png)

Om principen är aktiverad kan de schemafält som har vissa dataetiketter (till exempel C8) kopplade till dem inte användas för analys eller nedladdning (till exempel för att skicka eller dela PDF-filer) i CJA-arbetsytan.

Observera att

* Du får inte lägga till dem i datavyer. De här fälten är nedtonade i den vänstra listan över schemafält.
* Du kan inte spara en datavy som innehåller blockerade fält.


