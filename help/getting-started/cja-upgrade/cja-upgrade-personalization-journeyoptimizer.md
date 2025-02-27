---
title: Använda personaliseringsobjektet för användning med Adobe Journey Optimizer
description: Lär dig hur du använder personaliseringsobjektet för Adobe Journey Optimizer
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Använda personaliseringsobjektet för användning med Adobe Journey Optimizer {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Använd personaliseringsobjektet för Adobe Journey Optimizer"
>abstract="Använd personaliseringsobjektet i implementeringen för användning i Adobe Journey Optimizer."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Resultatet av personaliseringsobjektet hamnar i en datauppsättning. Resultatet av experimenterande. När en kund har använt AA med Target hamnar det i ett helt annat utrymme än när de migrerar till CJA och kommer att använda CJA med Adobe Target.

Target var det gamla sättet att skapa ett A/B-test eller -experiment. Sedan säkerställde man resultaten av testerna i Target och slutade med AA för rapportering. Om du nu använder Target kan du nu, i stället för att säga att du vill ha data i Target, välja CJA som rapportkälla för en Adobe Target-aktivitet. Så om en kund gör detta i AA och vill gå över till CJA, ...

Om en kund har AJO och använder erbjudanden i AJO kan de lägga upp erbjudanden och det skapar också datauppsättningar i Platform... Men det är inte relevant med uppgradering, exakt.



Frågor vi behöver svara på:

1. Hur fastställer vi personaliseringskriterierna (röd för användare A och blå för användare B)?

1. Vad implementerar vi på webbplatsen för att fastställa det röda/blå objektet?


Två sätt:

Återge innehåll manuellt eller automatiskt.


## Manuell implementering av Web SDK


## Implementering av SDK för mobiler





## Taggar

