---
title: Lär dig hantera målgrupper som skapats i Customer Journey Analytics
description: Lär dig hantera målgrupper i Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: e131fd78ceee67a05a1ea7256e58b4b34ce44ae5
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 1%

---

# Hantera målgrupper

Publiker kan hanteras i Customer Journey Analytics med **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

Genom att hantera tidigare skapade målgrupper kan ni:

* **Schemalägg eller avschemalägg** automatisk uppdatering/uppdatering av målgruppen. Det maximala utgångsdatumet för schemat är 1 år.
* **Förnya ett målgruppsuppdateringsschema** när det snart går ut. Utgångna målgrupper behandlas på samma sätt som schemalagda rapporter som förfaller - administratören får ett e-postmeddelande en månad innan schemat förfaller.
* Visa **uppdateringsintervallet** och **senaste gången en målgrupp uppdaterades**
* Få insikt i hur lång tid det tog att producera en målgrupp **från Customer Journey Analytics.** Det tog att få fram information om hur lång tid det tog att producera en målgrupp. Och hur lång tid det tog att få publiken att visas i kundplattformen i realtid för aktiveringsändamål.
* Se om målgrupperna i Customer Journey Analytics aktivt **används av kundplattformen för realtid**. Eller (helst) alla Experience Platform-program som använder de målgrupper som skapats av Customer Journey Analytics.

Om du har [åtkomst till målgruppsvyn](/help/technotes/access-control.md#user-level-access) kan du visa målgrupper. Om du har [åtkomst för att skapa ](/help/technotes/access-control.md#user-level-access) målgrupper kan du redigera och ta bort målgrupper. I [publiklistan](#audiences-list) visas målgrupperna.

![Målgruppshanteraren](assets/audiences-manager.png)

## Publiklista

I publiklistan ➊ visas kolumner för:

| Kolumn | Beskrivning |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | När en eller flera målgrupper är markerade visas ett blått åtgärdsfält längst ned i publikgränssnittet. Mer information finns i [Åtgärder](#actions). |
| **[!UICONTROL Title & Description]** | Titeln och beskrivningen som du angav när du skapade målgruppen. |
| **[!UICONTROL Data view]** | Datavyn som den här målgruppen skapades i. |
| **[!UICONTROL Audience size]** | Det totala antalet människor i den här publiken. |
| **[!UICONTROL Owner]** | Ägaren till målgruppen - den person som skapade målgruppen. |
| **[!UICONTROL Refresh frequency]** | Uppdateringsintervallet som konfigurerades när målgruppen skapades. |
| **[!UICONTROL Tags]** | Alla taggar som används för den här målgruppen. |
| **[!UICONTROL Publishing status]** | Kan visa ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]** eller ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
| **[!UICONTROL Last refreshed]** | Tidsstämpel när målgruppen senast uppdaterades. |
| **[!UICONTROL Last modified]** | Tidsstämpel när målgruppen senast redigerades eller ändrades. |

Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera vilka kolumner som ska visas. Sök efter en målgrupp med ![Sök](/help/assets/icons/Search.svg).

Så här redigerar du en målgrupp:

1. Välj publikens titel. Använd dialogrutan **[!UICONTROL Edit audience project]** för att uppdatera målgruppen. Mer information finns i [Målgruppsverktyget](publish.md#audience-builder).

1. Välj **[!UICONTROL Republish]** om du vill publicera målgruppen igen.


## Åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt. Du kan välja åtgärder på snabbmenyn:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Etiketter](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Tagga de valda målgrupperna. I dialogrutan **[!UICONTROL Update tags: *målgruppsnamn *]**väljer du taggar i listrutan eller skriver en eller flera nya taggar. Välj **[!UICONTROL Save]**att spara. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda målgrupperna. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på den valda målgruppen. Använd dialogrutan **[!UICONTROL Rename: *målgruppsnamn *]**om du vill byta namn på målgruppen och välja **[!UICONTROL Save]**att spara. |

Följande åtgärder är tillgängliga i det blå åtgärdsfältet när du väljer ett eller flera schemalagda projekt.

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Stäng](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Markera för att avmarkera valda målgrupper. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda målgrupperna. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de valda målgrupperna till en fil med namnet `audiences.csv`. |

## Filter

Du kan filtrera [publiklistan](#audiences-list) med ➋ på filterpanelen. Om du vill visa eller dölja filterpanelen använder du ![Filter](/help/assets/icons/Filter.svg).

Filterpanelen består av följande avsnitt.

### Datavy

| Datavy | Beskrivning |
|---|---|
| ![Ägare](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | I avsnittet **[!UICONTROL Data view]** kan du filtrera på datavyer. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) för att söka efter datavyer som du vill använda för att filtrera.</li><li>Du kan välja mer än en datavy.</li></ul> |

### Ägare

| Ägare | Beskrivning |
|---|---|
| ![Ägare](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | I avsnittet **[!UICONTROL Owner]** kan du filtrera efter ägare. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) för att söka efter ägare som du vill använda för att filtrera.</li><li>Du kan välja mer än en ägare. </li></ul> |

## Uppdateringsfrekvens

| Uppdateringsfrekvens | Beskrivning |
|---|---|
| ![Uppdateringsfrekvens](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | I avsnittet **[!UICONTROL Refresh frequency]** kan du filtrera uppdateringsfrekvensen. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) för att söka efter den uppdateringsfrekvens som du vill använda för att filtrera.</li><li>Endast uppdateringsfrekvenserna som definierats för målgrupperna <br/> i [publiklistan](#audiences-list) visas som tillgängliga alternativ.</li></ul> |


### Taggar

| Taggar | Beskrivning |
|---|---|
| ![Taggar](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | I avsnittet **[!UICONTROL Tags]** kan du filtrera efter taggar. <ul><li>Du använder ![Sök](/help/assets/icons/Search.svg) för att söka efter taggar som du vill använda för att filtrera. |
