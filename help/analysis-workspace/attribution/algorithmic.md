---
title: Algoritmisk attribuering
description: Information om algoritmisk attribueringsmodell.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 4%

---


# Algoritmisk attribuering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL Algorithmic attribution]** har för närvarande begränsad testning. Mer information finns i [Adobe Analytics-funktionsreleaser](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html).

Algoritmisk [attribueringsmodell](models.md) i Analysis Workspace skiljer sig från andra modeller på så sätt att den använder statistiska tekniker för att allokera kredit över dimensionsobjekten i din rapport eller frihandstabell. Precis som alla andra attribueringsmodeller i Analysis Workspace kan den användas på alla dimensioner eller mätvärden och har stöd för obegränsad segmentering och uppdelningar och distribuerar 100 % av konverteringarna till de dimensioner som anges i tabellen (kallas även&quot;fraktionerad&quot; attribuering).

Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.

På en hög nivå ser attribueringsberäkningen av konverteringskrediten för varje kontaktyta varje kontaktyta inom marknadsföringen som en koalition av aktörer till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapats genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:

* Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelteori, 2(28)*, 307-317.
* Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Resultatet av algoritmisk attribuering skiljer sig bara från andra modeller när det finns flera kontaktytor i det angivna uppslagsfönstret. Konverteringar med en enda kontaktyta får 100 % rabatt oavsett attribueringsmodell.
