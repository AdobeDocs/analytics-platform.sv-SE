---
description: Tidsåtgången tar tidsstämpeln för insamlade träffar och gör att den blir mer meningsfull, t.ex. "Dagens timme" eller "Veckodag".
title: Tidsdelning av dimensioner
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 3%

---


# Tidsdelning av dimensioner

Tidsåtgången tar tidsstämpeln för insamlade träffar och gör att den blir mer meningsfull, t.ex. &quot;Dagens timme&quot; eller &quot;Veckodag&quot;.

Tidsdelningsdimensionerna baseras på tidszonen för rapportsviten eller den virtuella rapportsviten. De här dimensionerna finns på Analysis Workspace och kan hjälpa dig att besvara följande frågor:

* Vilken är den populäraste tiden på dagen för besökare att komma åt min webbplats eller app över ett stort datumintervall?
* Finns det dagar i veckan, eller timmar på dagen, där konverteringen är högre på min webbplats eller app?
* Hur kan min försäljning under helgen jämföras med min försäljning under veckodagen?
* Genererar en viss marknadsföringskampanj högre omställningar på morgonen eller på eftermiddagen?

>[!NOTE]
>
>Tidsdelningsdimensioner är bara tillgängliga på Analysis Workspace. Om du vill använda tidsdelningsdimensioner i andra analyslösningar kan du implementera [getTimeParting-plugin-program](https://docs.adobe.com/content/help/en/analytics/implementation/vars/plugins/gettimeparting.html).

Tidsdelningsdimensioner i analysarbetsytan omfattar:

| Dimension | Exempelvärden |
|--- |--- |
| Dagens timme | 0-23 |
| AM/EM | AM, EM |
| Veckodag | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| Vecka/Veckodag | Vecka, Veckodag |
| Dag i månad | 1-31 |
| Årets månad | Januari-december |
| Dag på året | 1-366 |
| Kvartal | Q1, Q2, Q3, Q4 |
