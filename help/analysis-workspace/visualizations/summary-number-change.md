---
description: Använd visualiseringarna Sammanfattningsnummer och Ändra för att visa viktiga datapunkter i ett projekt.
title: Sammanfattning av antal och förändring
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 158c9da54f7d5dcdd0cca6223b5d4833df53abb7
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 6%

---


# Sammanfattning av antal och förändring

## Visualisering av sammanfattningsnummer {#summary-number}

Använd visualisering av sammanfattningsnummer för att markera ett stort antal som är viktigt i ett projekt. Denna visualisering fungerar på följande sätt:

* Markerar kolumnsumman om ingen cell är markerad.
* Om du har markerat en enda cell visas sammanfattningen för den cellen.
* Om mer än en cell är markerad visas den första markerade cellen.
* Om kolumnen är markerad, väljs det första cellvärdet i kolumnen.

Klicka på **Visualiseringsinställningar** Växla till höger överst för att konfigurera inställningarna för sammanfattningsnummer:

| Inställning | Definition |
|--- |--- |
| Procentsatser | Visa procentvärden i stället för rånummer. |
| Förklaring synlig | Visa information om det mått som visas. |
| Förkortat värde | Välj att förkorta värdena och visa upp till 3 decimaler. |
| Summera värde efter | Välj att visa max, min, medel, median eller summa för ett urval av data. |

## Översikt över ändring av visualisering {#summary-change}

Använd visualiseringen för Sammanfattningsändring för att visa delta (ändring) mellan två tal. Den gröna och röda färgen för den sammanfattande ändringen kan styras genom [anpassad händelsepolaritet](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) eller ett beräknat mått [Visa uppåttrender som](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) alternativ.

Denna visualisering fungerar på följande sätt:

* Om ingen cell är markerad jämförs de två första cellvärdena i kolumnen.
* Om en cell är markerad visas 0, eftersom cellvärdet jämförs med sig självt.
* Om två celler är markerade används den första markerade cellen som täljare och den andra som nämnare.
* Om fler än två celler är markerade, beaktas bara de två första för jämförelse.
* Om ett cellområde är markerat jämförs det första med det sista cellområdet.
* Om kolumnen är markerad jämförs det första värdet med det egna, vilket visar en ändring med 0.

Klicka på **Visualiseringsinställningar** Växla till höger överst för att konfigurera inställningarna för Sammanfattningsändring:

| Inställning | Definition |
|--- |--- |
| Procentsatser | Visa procentvärden i stället för rånummer. |
| Förklaring synlig | Visa information om det mått som visas. |
| Visa procentuell ändring | Visar procentändringen mellan de 2 talen. |
| Visa rådifferens | Visar den råa skillnaden mellan de 2 talen. Med det här alternativet kan du också förkorta värdena och visa upp till 3 decimaler. |
