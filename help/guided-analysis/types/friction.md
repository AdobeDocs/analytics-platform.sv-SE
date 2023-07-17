---
title: Bildvy
description: Jämför konverteringsgrader mellan steg.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: 2b1e0ce53016634e0cb32f9256fa48e02f2a5323
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Bildvy

The **Funktion** ger en visuell representation av en viktig användarresa i din produkt. Den vågräta axeln representerar varje steg som en användare måste gå igenom. Den lodräta axeln representerar procentandelen användare eller sessioner i varje steg. Alla steg måste utföras i den slutliga ordningen, men kan inträffa när som helst i rapportfönstret.

![Funktion](../assets/friction.png)

## Användningsexempel

Exempel:

* **Konverteringsanalys**: Du kan analysera konverteringar i varje steg i tratten. Genom att spåra antalet användare som går från ett steg till nästa kan ni identifiera flaskhalsar som har ovanliga eller oönskade konverteringsgrader. Denna information är värdefull för att förstå var du kan förbättra produkten och få omedelbara resultat.
* **Optimering av introduktion**: Optimera produktens introduktionsprocess genom att undersöka användarbeteenden kring viktiga händelser. Du kan identifiera vilka steg användare kämpar med eller misslyckas med.
* **Engagemang och engagemang**: Förstå hur användarna interagerar med specifika funktioner i produkten. Genom att analysera användarnas utveckling genom funktionsrelaterade steg kan du utvärdera hur många funktioner som används och identifiera områden där användarna kan överge eller underanvända vissa funktioner. Du kan sedan använda den här informationen för att fokusera på funktionsförbättringar för att öka användningen.
* **Kampanjutvärdering**: Mät effektiviteten i marknadsföringskampanjer. Ni kan skapa ett segment som fokuserar på användare som berörde en viss kampanj och jämföra deras konverteringsprocess med andra kampanjer eller inom den övergripande produkten.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Steg**: De kontaktytor för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **Folk**: De segment som du vill jämföra tratten med. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

## Diagraminställningar

I vyn Friktion finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **Mått**: Omfånget som du vill ska tillämpas på tratten. Du kan välja sessioner och användare. Om du väljer sessioner måste alla steg inträffa inom samma session för att räknas. Om du väljer användare måste alla steg inträffa i det rapportfönster som valts för att räknas.
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Steg.
* **Konvertering från**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från det första steget eller föregående steg.

## Använd tidsjämförelse

{{apply-time-comparison}}

![Jämförelse av friktionstid](../assets/friction-compare.png)

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data efter. Den här inställningen påverkar inte vyer som inte är trendade, till exempel Bild.
* **Datum**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
