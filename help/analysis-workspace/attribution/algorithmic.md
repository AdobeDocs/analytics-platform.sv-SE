---
title: Algoritmisk attribuering
description: Information om algoritmisk attribueringsmodell.
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# Algoritmisk attribuering

Här är en videoöversikt av algoritmisk attribuering:

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

The Algorithmic [attribueringsmodell](models.md) i Analysis Workspace skiljer sig från andra modeller genom att använda statistiska tekniker för att fördela krediter mellan dimensionsobjekten i din rapport eller frihandstabell. Precis som alla andra attribueringsmodeller i Analysis Workspace kan den användas på alla mått och mätvärden och har stöd för obegränsade filter och uppdelningar och distribuerar 100 % av konverteringarna till de mått som anges i tabellen (kallas även&quot;bråkdelsattribuering&quot;).

Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.

På en hög nivå ser attribueringsberäkningen av konverteringskrediten för varje kontaktyta varje kontaktyta inom marknadsföringen som en koalition av aktörer till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapats genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:

* Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelteori, 2(28)*, 307-317.
* Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *Internationell ekonomisk granskning 4.2*, 194-220.

>[!IMPORTANT]
>
>Resultatet av algoritmisk attribuering skiljer sig bara från andra modeller när det finns flera kontaktytor i det angivna uppslagsfönstret. Konverteringar med en enda kontaktyta får 100 % rabatt oavsett attribueringsmodell.
