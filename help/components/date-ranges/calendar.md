---
description: Ange datum och datumintervall eller välj en förinställning.
title: Översikt över kalender- och datumintervall
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
role: User
source-git-commit: 47b7747b37f82e4d75d5272ce1d8d37f4e497bb5
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 0%

---

# Översikt över kalender- och datumintervall

Med kalendern kan du ange datum och datumintervall eller välja en förinställning. Datumintervall är en typ av komponent som du kan använda i Workspace-projekt. De gör att du kan se data som trendas över tid eller se när händelser inträffar som mest. Datumintervall färgkodas i lila. Med anpassade datumintervall kan du anpassa de datum som visas i arbetsyteprojekt.

Kalenderval gäller på panelnivå, men du kan välja att använda dem på alla paneler. När du klickar på ett datumintervall i Arbetsyta visas den aktuella kalendermånaden och den föregående kalendermånaden i gränssnittet. Du kan justera dessa två kalendrar genom att klicka på höger- och vänsterpilarna i respektive övre hörn.

![Kalender som visar oktober 2022 och november 2022 med 1 till 30 november vald.](assets/aw_calendar2.png){width="60%"}

Första klicket i en kalender startar ett datumintervallval. Den andra klickningen slutför ett datumintervallval som markeras. Om `Shift` om du håller ned tangenten (eller högerklickar om används) läggs den till i det markerade området.

Du kan också dra datum (och tidsdimensioner) till ett Workspace-projekt. Du kan välja specifika dagar, veckor, månader, år eller rullande datum.

[Använda datumintervall och kalender i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html) (4:07)

| Inställning | Beskrivning |
| --- | --- |
| Valda dagar | Utvalda dagar/veckor/månader/år |
| Använd rullande datum | Med rullande datum kan du generera en dynamisk rapport som ser framåt eller bakåt under en angiven tidsperiod baserat på när du körde rapporten. Om du t.ex. vill rapportera alla beställningar som placerats i&quot;Senaste månaden&quot; (baserat på fältet Skapad den) och köra rapporten i december, ser du beställningar som gjorts i november. Om du körde samma rapport i januari skulle du se beställningar i december.<ul><li>**[!UICONTROL Date Preview]**: Anger vilken tidsperiod som den rullande kalendern omfattar.</li><li>**[!UICONTROL Start]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li><li>**[!UICONTROL End]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li></ul>Till exempel, gå [här](/help/components/date-ranges/custom-date-ranges.md). |
| Datumintervall | Välj ett förinställt datumintervall. De senaste 30 dagarna är standard. **[!UICONTROL This week/month/quarter/year (excluding today)]** Med kan du välja från datumintervall som inte innehåller data för delar av dagen från och med idag. |
| Använd på alla paneler | Här kan du inte bara ändra det markerade datumintervallet för den aktuella panelen, utan även för alla andra paneler i projektet. |
| Använd | Använder endast datumintervallet på den här panelen. |

## Om relativa paneldatumintervall {#relative-panel-dates}

Om du arbetar i Workspace kan du göra datumintervallets komponenter relativa till panelkalendern. Tre vanliga användningsområden där du ser relativa paneldatum som börjar gälla är Combo-diagram, Sammanfattning av nyckelmått och datumintervall i frihandstabellen.

Använda relativa paneldatumintervall

1. Välj **Arbetsyta** -fliken.
1. Välj **Tomt projekt**.
1. Lägg till mått, mätvärden och filter från den vänstra listen.
1. Klicka på panelens datumintervallfält för att växla den relativa panelens datumintervallinställning.
1. Välj **Gör datumintervallskomponenter relativa till panelkalendern**.
   * Välj alternativet om du vill att datumintervallets komponenter ska vara relativa till panelkalendern.
Om du väljer relativa datum baseras rullande datum på startdatumet för panelkalendern och inte på dagens datum.
   * Om det här alternativet inte är markerat baseras rullande datum på dagens datum.

   ![Kalender med Gör datumintervallkomponenter relativa till den valda panelkalendern](assets/relative-date-selected.png){width="60%"}

1. Klicka **Använd**.
De relativa datumen visas i det övre högra hörnet.

   ![Frihandstabell med relativa datum markerade och senaste månaden markerade. ](assets/relative-date-range1.png)

## Riktlinjer för relativa paneldatumintervall {#guidelines}

Tänk på följande när du använder relativa paneldatumintervall.

### Formler och relativa datumintervall {#formula-relative-dates}

Om du har markerat relativa datum används panelens startdatum som startpunkt i alla datumformler.

### Anpassade kalendrar och relativa datumintervall {#custom-calendar-formulas}

När du använder en veckobaserad anpassad kalender och lägger till månader eller år, beräknas förskjutningen för dagen i den angivna perioden enligt formeln. Det faktiska datumet kan vara ett annat på grund av förskjutningen. Formeln väljer landningsdagen på samma plats i den anpassade kalendern. Den tredje fredagen i den tredje veckan i en anpassad kalender.

### Om filter som använder rullande datum och relativa paneldatumintervall {#segments-relative-dates}

Om du skapar ett filter eller använder ett filter med ett rullande datum, till exempel de senaste 7 dagarna eller de senaste 2 veckorna, och du klickar på filterförhandsvisningen, startar det rullande datumet från *Idag* i stället för panelens startdatum. Det innebär att förhandsvisningen av filtret inte matchar när du faktiskt använder filtret i tabellen. Förhandsgranskningen påverkas, inte själva filtret.

## Riktlinjer för paneldatumintervall och förhandsvisningar {#guidelines-panel-dates}

* Från och med februari-versionen baseras förhandsgranskningarna av komponenter och data på panelens datumintervall och inte på de senaste 90 dagarna.
* Alla komponenter i den vänstra listen är tillgängliga baserat på panelens datumintervall.
* Alla förhandsvisningar av datum i filtret och beräknade mätvärden baseras på panelens datumintervall (såvida de inte öppnas från komponenthanterarna, som inte har någon associerad panel, kommer de fortfarande att baseras på de senaste 90 dagarna).
* Förhandsgranskningar av data visar data eller komponenter baserat på panelens datumintervall.