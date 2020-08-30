---
title: Algoritmisk attribuering
description: Information om algoritmisk tilldelningsmodell.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 4%

---


# Algoritmisk attribuering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL Algorithmic attribution]** testas för närvarande i begränsad omfattning. Se [Utsläpp av Adobe Analytics-funktioner](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html) för mer information.

Algorithmic [tilldelningsmodell](models.md) i Analysis Workspace skiljer sig från andra modeller genom att statistiska tekniker används för att allokera kredit mellan dimensionsobjekten i rapporten eller friformstabellen. I likhet med alla andra attributmodeller i Analysis Workspace kan den användas på alla dimensioner eller mått och stöder obegränsad segmentering och uppdelning och distribuerar 100 % av konverteringarna till dimensionen/dimensionerna i tabellen (kallas även &quot;fraktionerad&quot; tilldelning).

Den algoritm som används för tilldelning baseras på Harsanyi-utdelningen från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (uppkallad efter nobelpriskonomisten Lloyd Shapley) för att fördela kredit mellan aktörer i ett spel med ojämlika bidrag till resultatet.

Vid beräkningen av tilldelningen av konverteringskrediten för varje beröringspunkt betraktas var och en av försäljningsställena inom ett retroaktivt fönster som en koalition av spelare till vilken ett överskott måste fördelas rättvist. Varje koalitions överskottsfördelning bestäms på grundval av det överskott som tidigare skapades genom varje subkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapleys originaldokument:

* Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till Gamelteori, 2(28)*, 307-317.
* Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det ideella kooperativa spelet. *Internationell ekonomisk översyn 4.2*, 194-220.

>[!NOTE]
>
>Utfallet av Algorithmic-attribut skiljer sig bara från andra modeller när det finns flera beröringspunkter inom det angivna synbakfönstret. Konverteringar med en enda kontaktpunkt får 100 % kredit oavsett attributmodell.
