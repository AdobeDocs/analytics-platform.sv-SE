---
title: Skapa ett datumintervall
description: Skapa ett datumintervall för rapportering.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---


# Skapa ett datumintervall

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan skapa ett anpassat datumintervall på något av följande två sätt:

* Direkt i ett arbetsyteprojekt genom att klicka på`+`&quot;knapp bredvid listan med datumintervallkomponenter till vänster
* Inom datumintervallhanteraren

Så här skapar du ett datumintervall i hanteraren för datumintervall:

1. Logga in på [analys.adobe.com](https://analytics.adobe.com) använda dina AdobeID-autentiseringsuppgifter.
1. Navigera till [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Klicka på [!UICONTROL Add] för att öppna det modala fönstret som skapar ett datumintervall.

## Skapa ett modalt fönster för datumintervall

Det modala fönstret har fyra fält som du kan redigera:

* **Datumintervall**: Datumintervallet som du vill använda för den här komponenten.
* **Rubrik**: Namnet som du vill ha för den här komponenten. Rubriken används i arbetsyteprojekt.
* **Beskrivning**: Beskrivningen som du vill ha för den här komponenten. Beskrivningen visas när du klickar på ![i](../assets/i.png) ikon.
* **Taggar**: Använd taggar för att ordna datumintervallen. Ett datumintervall kan tillhöra flera taggar.

## Välja ett datumintervall

När du klickar på datumintervallet i det modala fönstret finns det flera alternativ:

* **Kalender**: Välj start- och slutdatum.
* **Använd rullande datum**: Markera den här rutan om datumintervallet ska ändras allt eftersom tiden går. Markera inte den här rutan om datumintervallet ska förbli statiskt.
* **Välj förinställning**: Använd den här listrutan om du vill ha ett anpassat datumintervall baserat på ett intervall som Adobe erbjuder som standard. När du väljer en förinställning kan du anpassa datumintervallet ytterligare efter dina behov. Det påverkar inte den förinställning som Adobe erbjuder.

## Rullningsdatumintervall

Om du vill ha ett rullande datumintervall kan du anpassa när det rullas. Du kan styra när start- och slutdatumen rullas oberoende av varandra.

* **När datumet börjar**: Välj om datumet börjar i början av en tidsperiod, i slutet av en tidsperiod eller om du vill använda en fast dag.
* **Tidsperioden som ska användas**: Välj hur ofta datumintervallet ska rullas. Du kan låta den rullas varje dag, varje vecka, varje månad, varje kvartal eller varje år.
* **Förskjutning**: Välj förskjutningen för datumintervallet. Du kan lägga till eller ta bort dagar, veckor, månader, kvartal eller år.

## Exempel på rullande datum

Vissa datumintervall kan vara användbara i vissa rapporter.

Senast år:

```text
Start: Start of current year
End: End of current day
```

I torsdags till torsdag:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Räkenskapsår (t.ex. om ett räkenskapsår börjar i december)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
