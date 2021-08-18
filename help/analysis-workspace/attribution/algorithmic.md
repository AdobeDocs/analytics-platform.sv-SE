---
title: Algoritmisk attribuering
description: Information om algoritmisk attribueringsmodell.
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: 3f893e5430eb4591939226e694f70064a90c7adb
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 2%

---

# Algoritmisk attribuering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Här är en videoöversikt av algoritmisk attribuering:

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Algoritmisk [attribueringsmodell](models.md) i Analysis Workspace skiljer sig från andra modeller på så sätt att den använder statistiska tekniker för att allokera kredit över dimensionsobjekten i din rapport eller frihandstabell. Precis som alla andra attribueringsmodeller i Analysis Workspace kan den användas på alla mått och mätvärden och har stöd för obegränsade filter och uppdelningar och distribuerar 100 % av konverteringarna till de mått som anges i tabellen (kallas även&quot;bråkdelsattribuering&quot;).

Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.

På en hög nivå ser attribueringsberäkningen av konverteringskrediten för varje kontaktyta varje kontaktyta inom marknadsföringen som en koalition av aktörer till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapats genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:

* Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelteori, 2(28)*, 307-317.
* Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>Resultatet av algoritmisk attribuering skiljer sig bara från andra modeller när det finns flera kontaktytor i det angivna uppslagsfönstret. Konverteringar med en enda kontaktyta får 100 % rabatt oavsett attribueringsmodell.
