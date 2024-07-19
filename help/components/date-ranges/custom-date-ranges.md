---
description: Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.
keywords: Analysis Workspace
title: Skapa anpassade datumintervall
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 47b7747b37f82e4d75d5272ce1d8d37f4e497bb5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 0%

---

# Skapa anpassade datumintervall

Du kan skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.

Mer information om hur du lägger till befintliga datumintervall i ett projekt finns i [Översikt över kalender- och datumintervall](/help/components/date-ranges/calendar.md).

Så här skapar du ett anpassat datumintervall:

1. I Adobe Analytics väljer du **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.

   ![datumintervallsida](assets/date-ranges.png)

1. Välj [!UICONTROL **Skapa nytt datumintervall**].

1. Ange följande information i datumintervallverktyget:

   | Alternativ | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Titel**] | Titeln på datumintervallet som det kommer att visas när användare markerar det i Analysis Workspace. |
   | [!UICONTROL **Beskrivning**] | En beskrivning av datumintervallet. |
   | [!UICONTROL **Taggar**] | Eventuella taggar som du vill använda för datumintervallet. |
   | [!UICONTROL **Datumintervall**] | Välj ett anpassat datumintervall. Som standard är de senaste 30 dagarna markerade. |
   | [!UICONTROL **Förinställning**] | Välj från en lista med förinställda datumintervall, t.ex. [!UICONTROL **I går**], [!UICONTROL **Senaste 7 dagarna**], [!UICONTROL **Senaste 30 dagarna**] o.s.v. |
   | [!UICONTROL **Starttid**] | Den tid på dagen som datumintervallet börjar. |
   | [!UICONTROL **Sluttid**] | Tiden på dagen som datumintervallet slutar. |
   | [!UICONTROL **Använd rullande datum**] | Med rullande datum kan du generera en dynamisk rapport som ser framåt eller bakåt under en angiven tidsperiod baserat på när du körde rapporten. Om du t.ex. vill rapportera alla beställningar som placerats i&quot;Senaste månaden&quot; (baserat på fältet Skapad den) och köra rapporten i december, ser du beställningar som gjorts i november. Om du körde samma rapport i januari skulle du se beställningar i december.<ul><li>**[!UICONTROL Date Preview]**: Anger vilken tidsperiod som den rullande kalendern omfattar.</li><li>**[!UICONTROL Start]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li><li>**[!UICONTROL End]**: Du kan välja mellan aktuell dag, aktuell vecka, aktuell månad, aktuellt kvartal, aktuellt år.</li></ul><br>Markerad som standard. |

1. Välj [!UICONTROL **Spara**].

## Exempel: Datumintervall för&quot;två månader sedan&quot; {#section_C4109C57CB444BB2A79CC8082BD67294}

I följande anpassade datumintervall visas ett datumintervall för&quot;två månader sedan&quot;, med en visualisering av Sammanfattningsändring som visar en riktningsändring.

![](assets/date-range-two-months-ago.png)

Det anpassade datumintervallet visas högst upp på [!UICONTROL Date Range]-komponentpanelen i ditt projekt:

![](assets/date-range-panel-two-months-ago.png)

Du kan dra det här anpassade datumintervallet till en kolumn tillsammans med ett anpassat, månatligt löpande datumintervall med hjälp av förinställningen Senaste månaden för en jämförelse. Lägg till en visualisering av sammanfattningsändring och välj summorna från varje kolumn för att visa riktningsändring:

![](assets/date-range-two-months-table.png)

## Exempel: Använd ett 7-dagars rullande datumintervall {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Du kan skapa ett datumintervall som anger ett 7-dagars rullande fönster som slutar för en vecka sedan:

![](assets/create_date_range.png)

Använd *`rolling daily`*.

* Startinställningarna blir *`current day minus 6 days`*.

* Slutinställningarna blir *`current day minus 7 days`*.

Det här datumintervallet kan vara en komponent som du drar till en frihandstabell.
