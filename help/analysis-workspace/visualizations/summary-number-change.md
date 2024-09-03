---
description: Använd visualiseringarna Sammanfattningsnummer och Ändra för att visa viktiga datapunkter i ett projekt.
title: Sammanfattningsnummer och sammanfattning
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 61c1fe48ebe8ebff5b7104cebae1ce7b62289b7d
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---

# Sammanfattningsnummer och sammanfattning

## Visualisering av sammanfattningsnummer {#summary-number}

Använd visualisering av sammanfattningsnummer för att markera ett stort tal som är viktigt i ett projekt. Den här visualiseringen fungerar på följande sätt:

* Markerar kolumnsumman om ingen cell är markerad.
* Om en enskild cell är markerad visas sammanfattningen för den cellen.
* Om flera celler är markerade visas den första cellen som är markerad.
* Om kolumnen är markerad väljs det första cellvärdet i kolumnen.

Klicka på **Visualiseringsinställningarna** i det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsnummer:

| Inställning | Definition |
|--- |--- |
| Procenttal | Visa procenttal i stället för råa tal. |
| Förklaring synlig | Visa information om måttet som visas. |
| Förkortningsvärde | Välj om du vill förkorta värden och visa upp till tre decimaler. |
| Summera värdet efter | Välj om du vill visa max, min, medelvärde, median eller summan för ett dataurval. |

{style="table-layout:auto"}

## Visualisering av sammanfattningsändring {#summary-change}

Använd visualisering av sammanfattningsändring för att visa delta (ändring) mellan två tal.

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Den här visualiseringen fungerar på följande sätt:

* Om ingen cell är markerad jämförs de två första cellvärdena i kolumnen.
* Om en cell är markerad visas 0, eftersom cellvärdet jämförs med sig själv.
* Om två celler är markerade tas den första markerade cellen som täljare och den andra som nämnare.
* Om fler än två celler är markerade kommer endast de första två att användas för jämförelse.
* Om ett cellintervall är markerat jämförs den första med den sista cellen i intervallet.
* Om kolumnen är markerad jämförs det första värdet med sig självt, vilket innebär en ändring på 0.


![Visualisering av sammanfattningsändring som visar delta mellan två tal.s](assets/summary-change.png)


Klicka på **Visualiseringsinställningarna** i det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsändring:

| Inställning | Definition |
|--- |--- |
| Procenttal | Visa procenttal i stället för råa tal. |
| Förklaring synlig | Visa information om måttet som visas. |
| Visa procentuell ändring | Visar procentuell ändring mellan de två talen. |
| Visa råskillnad | Visar den obearbetade skillnaden mellan de två talen. Med det här alternativet kan du även förkorta värden och visa upp till tre decimaler. |
