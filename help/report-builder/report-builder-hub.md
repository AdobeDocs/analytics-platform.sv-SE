---
title: Vad är Report Builder navet i Customer Journey Analytics?
description: Beskriver komponenterna för Report Builder Hub
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 0%

---

# Report Builder Hub

Använd Report Builder nav för att skapa, uppdatera eller ta bort datablock.

Navet Report Builder innehåller panelerna KOMMANDON och QUICK EDIT.

![](./assets/image13.png)

## KOMMANDON

Använd KOMMANDON-panelen för att komma åt kommandon som är kompatibla med de markerade cellerna eller en tidigare åtgärd.

![](./assets/hub1.png)

### Kommandon

| Visade kommandon | Tillgängligt när.. | Syfte |
|------|------------------|--------|
| Skapa datablock | En eller flera celler markeras i arbetsboken. | Används för att skapa ett datablock |
| Redigera datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att redigera ett datablock |
| Uppdatera datablock | Markeringen innehåller minst ett datablock. Kommandot uppdaterar bara de markerade datablocken. | Används för att uppdatera ett eller flera datablock |
| Uppdatera alla datablock | Arbetsboken innehåller ett eller flera datablock. | Används för att uppdatera ALLA datablock i arbetsboken |
| Kopiera datablock | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | Används för att kopiera ett datablock |
| Ta bort datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att ta bort ett datablock |

## SNABBREDIGERING, panel

När du markerar ett eller flera datablock i ett kalkylblad visas panelen QUICK EDIT i Report Builder. Du kan använda panelen QUICK EDIT för att ändra parametrar i ett enda datablock eller för att ändra parametrar i flera datablock samtidigt.

![](./assets/hub2.png)

De ändringar du gör i snabbredigeringsavsnitten gäller för alla markerade datablock.

### Datavyer

Datablocken hämtar data från en markerad datavy. Om flera datablock är markerade i ett kalkylblad och de inte hämtar data från samma datavy, kan du **Datavyer** länk *Flera*.

När du ändrar datavyn används den nya datavyn för alla datablock i markeringen. Komponenterna i datablocket matchas mot den nya datavyn baserat på ID, till exempel matchning ```evars```). Om en komponent inte hittas i ett datablock visas ett varningsmeddelande och komponenten tas bort från datablocket.

Om du vill ändra datavyn väljer du en ny datavy i listrutan.

![](./assets/image16.png)

### Datumintervall

**Datumintervall** visar datumintervallet för de markerade datablocken. Om flera datablock har markerats med flera datumintervall **Datumintervall** länk *Flera*.

### Filter

The **Filter** I visas en lista med de filter som används av de markerade datablocken. Om flera datablock är markerade med flera filter **Filter** länk *Flera*.
