---
title: Tratt
description: Identifiera friktionsområden i en serie steg.
source-git-commit: c47c4364cbf027c24a355bb306ee786c3e2446a9
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Tratt

{{release-limited-testing}}

The **Tratt** [Analystyp](overview.md) ger en visuell representation av en användarresa eller konverteringsprocess i produkten. Den vågräta axeln representerar varje händelse som en användare måste peka i ordning. Den lodräta axeln representerar den procentandel användare som berörde varje händelse. Alla kontaktytor måste göras i ordning, men kan inträffa när som helst i rapportfönstret. Användningsexempel för den här analystypen är:

* **Konverteringsanalys**: Med Trnel kan du analysera konverteringar i varje steg i tratten. Genom att spåra antalet användare som går från ett steg till nästa kan ni identifiera flaskhalsar som har ovanliga eller oönskade konverteringsgrader. Denna information är värdefull för att förstå var du kan förbättra produkten och få omedelbara resultat.
* **Optimering av introduktion**: Funnel är till hjälp för att optimera er produkts introduktionsprocess. Genom att undersöka användarbeteenden kring viktiga händelser kan du identifiera vilka steg som användare kämpar med eller misslyckas med.
* **Engagemang och engagemang**: Funnel hjälper dig att förstå hur användare interagerar med specifika funktioner i produkten. Genom att analysera användarnas utveckling genom funktionsrelaterade steg kan du utvärdera hur många funktioner som används och identifiera områden där användarna kan överge eller underanvända vissa funktioner. Du kan sedan använda den här informationen för att fokusera på funktioner eller förbättringar av användargränssnittet för att öka antalet användare.
* **Kampanjutvärdering**: Funnel kan hjälpa till att mäta effektiviteten i marknadsföringskampanjer. Ni kan skapa ett segment som fokuserar på användare som berörde en viss kampanj och jämföra deras konverteringsprocess med andra kampanjer eller inom den övergripande produkten.

[Skärmdump av tratt]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Steg**: De beröringspunkter för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg i en rapport.
* **Folk**: Anger de segment som du vill mäta i rapporten. Varje segment som är markerat här delar upp varje steg i flera fält. Varje färg representerar ett eget segment. Stöd för upp till tre segment.

## Vytyper

Trnel erbjuder följande vytyper. Du kan ändra vytyp med hjälp av listrutan högst upp till vänster i diagrammet.

* **Funktion**: Jämför konverteringsgrader mellan steg.

## Diagraminställningar

Trnel har följande diagraminställningar. Du kan justera diagraminställningarna på menyn mellan vytypen och kalenderväljaren.

* **Mått**: Anger måttet som du vill mäta. Du kan välja sessioner och användare.
* **Diagramtyp**: Anger vilken typ av visualisering du vill använda. Det enda alternativet är Steg.
* **Konvertering från**: Anger procentberäkningen från steg till steg. Alternativen är Första steget och Föregående steg.

## Datumintervall

Start- och slutdatumet för projektet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum. Datumintervall är inte tillgängliga för den här analystypen.
