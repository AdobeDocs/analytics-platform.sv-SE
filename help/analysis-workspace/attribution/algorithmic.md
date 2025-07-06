---
title: Algoritmisk attribuering
description: Förstå detaljerna om den algoritmiska attribueringsmodellen.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Algoritmisk attribuering

Den algoritmiska [attribueringsmodellen](models.md) i Analysis Workspace skiljer sig från andra modeller på så sätt att den använder statistiska tekniker för att allokera kredit över dimensionsobjekten i din rapport eller frihandstabell. Precis som alla andra attribueringsmodeller i Analysis Workspace kan algoritmisk attribuering användas på alla dimensioner och mätvärden. Algoritmisk attribuering stöder obegränsad segmentering och uppdelning och distribuerar 100 % av konverteringarna till en eller flera dimensioner i tabellen (kallas även&quot;fraktionell&quot; attribuering).


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algoritmisk attribuering](https://video.tv.adobe.com/v/36205?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (uppkallad efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.

På en hög nivå ser attribueringsberäkningen av konverteringskrediten för varje kontaktyta varje kontaktyta inom marknadsföringen som en koalition av aktörer. För denna koalition av aktörer måste ett överskott fördelas jämnt. Varje koalitions överskottsfördelning bestäms av det överskott som varje tidigare delkoalition rekursivt har skapat.

Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:

* Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelets teori, 2(28)*, 307-317.
* Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *Internationell ekonomisk granskning 4(2)*, 194-220.

>[!NOTE]
>
>Resultatet av algoritmisk attribuering skiljer sig bara från andra modeller när det finns flera kontaktytor i det angivna uppslagsfönstret. Konverteringar med en enda kontaktyta får 100 % rabatt oavsett attribueringsmodell.
