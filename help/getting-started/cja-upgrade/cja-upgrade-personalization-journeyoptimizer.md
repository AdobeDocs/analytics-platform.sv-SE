---
title: Använda personaliseringsobjektet för användning med Adobe Journey Optimizer
description: Lär dig hur du använder personaliseringsobjektet för Adobe Journey Optimizer
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---

# Använda personaliseringsobjektet för användning med Adobe Journey Optimizer {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Använd personaliseringsobjektet för Adobe Journey Optimizer"
>abstract="Genom att utnyttja den senaste tekniken inom maskininlärning och djupinlärning under övervakning kan en företagsanvändare (marknadsförare) med personaliserad optimering definiera affärsmål och använda sina kunddata för att utbilda affärsorienterade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Genom att utnyttja den senaste tekniken inom maskininlärning och djupinlärning under övervakning kan en företagsanvändare (marknadsförare) med personaliserad optimering definiera affärsmål och använda sina kunddata för att utbilda affärsorienterade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal.

1. Följ informationen i [Personlig optimeringsmodell](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model) i Journey Optimizer Guide.

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->

