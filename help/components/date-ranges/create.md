---
title: Skapa ett datumintervall
description: Skapa ett datumintervall för rapportering.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Skapa ett datumintervall

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Funktionsuppsättningen skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan skapa ett anpassat datumintervall på något av följande två sätt:

* Direkt i ett arbetsyteprojekt genom att klicka på`+`&#39; vid listan med datumintervallkomponenter till vänster
* Inom datumintervallhanteraren

Så här skapar du ett datumintervall i datumintervallhanteraren:

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Navigera till [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Klicka på [!UICONTROL Add] för att öppna det modala fönstret som skapar ett datumintervall.

## Skapa ett modalt datumintervallfönster

Det modala fönstret har fyra fält som du kan redigera:

* **Datumintervall**: Datumintervallet som du vill använda för den här komponenten.
* **Titel**: Namnet som du vill använda för den här komponenten. Titeln används i arbetsyteprojekt.
* **Beskrivning**: Den beskrivning som du vill använda för den här komponenten. Beskrivningen visas när du klickar på ![i](../assets/i.png) ikon.
* **Taggar**: Använd taggar för att ordna datumintervallen. Ett datumintervall kan tillhöra flera taggar.

## Markera ett datumintervall

När du klickar på datumintervallet i det modala fönstret har du flera alternativ:

* **Kalender**: Välj start- och slutdatum.
* **Använd rullande datum**: Markera den här rutan om du vill att datumintervallet ska ändras allt eftersom tiden går. Markera inte den här rutan om du vill att datumintervallet ska förbli statiskt.
* **Välj förinställning**: Använd den här listrutan om du vill ha ett anpassat datumintervall baserat på ett intervall som Adobe erbjuder som standard. När du väljer en förinställning kan du anpassa datumintervallet ytterligare efter dina behov. Den påverkar inte förinställningen som Adobe erbjuder.

## Datumintervall för rullande text

Om du vill ha ett rullande datumintervall kan du anpassa när det rullas. Du kan styra när start- och slutdatum rullar oberoende av varandra.

* **När datumet börjar**: Välj om datumet börjar i början av en tidsperiod, i slutet av en tidsperiod eller om du vill använda en fast dag.
* **Den tidsperiod som ska användas**: Välj hur ofta datumintervallet ska rullas. Du kan få den att rulla varje dag, varje vecka, varje månad, varje kvartal eller varje år.
* **Förskjutning**: Välj förskjutning för datumintervallet. Du kan lägga till eller ta bort dagar, veckor, månader, kvartal eller år.

## Exempel på rullande datum

Vissa datumintervall kan vara användbara i vissa rapporter.

Hittills i år:

```text
Start: Start of current year
End: End of current day
```

Torsdag till torsdag:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Räkenskapsår (t.ex. om ett räkenskapsår börjar i december)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
