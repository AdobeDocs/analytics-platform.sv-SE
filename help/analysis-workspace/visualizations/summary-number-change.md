---
description: Använd visualiseringar av sammanfattningsnummer och sammanfattningsändringar för att visa viktiga datapunkter i ett projekt.
title: Sammanfattningsnummer och sammanfattning
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 639c3d3c349615078c76f8806bcd5bb458b0f6f2
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Sammanfattningsnummer och ändring

>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras visualiseringar av sammanfattningsnummer och sammanfattningsändringar i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Se [Sammanfattningsnummer och Sammanfattningsändring](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualisering av sammanfattningsnummer och sammanfattningsändring](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

## Sammanfattningsnummer {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Sammanfattningsnummer"
>abstract="Skapa en visualisering som visar summor och delsummor."

<!-- markdownlint-enable MD034 -->

Använd visualiseringen ![Sammanfattning](/help/assets/icons/123.svg) **[!UICONTROL Summary number]** för att markera ett stort antal som är viktiga i ett projekt. Den här visualiseringen fungerar på följande sätt med den associerade datakällan:

* Markerar kolumnsumman om ingen cell är markerad.
* Om en enskild cell är markerad visas sammanfattningen för den cellen.
* Om flera celler är markerade visas den första cellen som är markerad.
* Om kolumnen är markerad väljs det första cellvärdet i kolumnen.

![Visualisering av sammanfattningsnummer](asses/../assets/summary-number.png)

Som en del av visualiseringsinställningarna finns det specifika alternativ för Sammanfattningsnummer.

| Alternativ | Definition |
|--- |--- |
| **[!UICONTROL Abbreviate value]** | Välj **[!UICONTROL Abbreviate value]** om du vill förkorta talvärdet på ett intelligent sätt. När du har markerat det här alternativet anger du ett tal för att definiera förkortningen. Till exempel:<br/><table><tr><td>**Ursprungligt värde**</td><td>**Förkortningsvärde**</td><td>**Resultat**</td></tr><tr><td>12 011 141,25 USD</td><td>Inte markerad</td><td  align="right">12 011 141,25 USD</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `0`</td><td align="right">12 miljoner dollar</td></tr><tr><td>12 011 141,25 USD</td><td> Markerad, inställd på `1`</td><td  align="right">$12.0M</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `2`</td><td align="right">$12.01M</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `3`</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL Summarize value by]** | Välj om du vill visa max, min, medelvärde, median eller summan för ett dataurval. |

## Sammanfattningsändring {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Sammanfattningsändring"
>abstract="Skapa en visualisering som visar delta (ändring) mellan två tal"

<!-- markdownlint-enable MD034 -->


Använd visualiseringen ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Summary Change]** för att visa delta (ändring) mellan två tal. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

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


Som en del av visualiseringsinställningarna är specifika **[!UICONTROL Summary change options]** tillgängliga.

| Alternativ | Definition |
|--- |--- |
| **[!UICONTROL Show percent change]** | Visa procentuell ändring mellan de två talen. |
| **[!UICONTROL Show raw difference]** | Visa den obearbetade skillnaden mellan de två talen. Med det här alternativet kan du även förkorta värden och visa upp till tre decimaler. |
| **[!UICONTROL Abbreviate value]** | Välj **[!UICONTROL Abbreviate value]** om du vill förkorta det ändrade värdet på ett intelligent sätt. När du har markerat det här alternativet anger du ett tal för att definiera förkortningen. Till exempel:<br/><table><tr><td>**Ursprungligt värde**</td><td>**Förkortningsvärde**</td><td>**Resultat**</td></tr><tr><td>12 011 141,25 USD</td><td>Inte markerad</td><td  align="right">12 011 141,25 USD</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `0`</td><td align="right">12 miljoner dollar</td></tr><tr><td>12 011 141,25 USD</td><td> Markerad, inställd på `1`</td><td  align="right">$12.0M</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `2`</td><td align="right">$12.01M</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på `3`</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Visualiseringsinställningar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Snabbmenyn Visualisering ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
