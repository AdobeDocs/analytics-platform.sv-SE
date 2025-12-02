---
title: Lär dig hantera målgrupper som skapats i Customer Journey Analytics
description: Lär dig hantera målgrupper i Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 1%

---

# Hantera publicerade målgrupper

Publiker kan hanteras i Customer Journey Analytics med **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

## Förstå målgruppshantering

Genom att hantera tidigare skapade målgrupper kan ni:

* **Schemalägg eller avschemalägg** automatisk uppdatering/uppdatering av målgruppen. Det maximala utgångsdatumet för schemat är 1 år.
* **Förnya ett målgruppsuppdateringsschema** när det snart går ut. Utgångna målgrupper behandlas på samma sätt som schemalagda rapporter som förfaller - administratören får ett e-postmeddelande en månad innan schemat förfaller.
* Visa **uppdateringsintervallet** och **senaste gången en målgrupp uppdaterades**
* Få insikt i hur lång tid det tog att producera en målgrupp **från Customer Journey Analytics.** Det tog att få insikt i hur lång tid det tog att producera en målgrupp. Och hur lång tid det tog att få publiken att visas i kundplattformen i realtid för aktiveringsändamål.
* Se om målgrupperna i Customer Journey Analytics **används aktivt av kundplattformen i realtid**. Eller (helst) alla Experience Platform-program som använder de målgrupper som skapats av Customer Journey Analytics.

Om du har [åtkomst till målgruppsvyn](/help/technotes/access-control.md#user-level-access) kan du visa målgrupper. Om du har [åtkomst för att skapa &#x200B;](/help/technotes/access-control.md#user-level-access) målgrupper kan du redigera och ta bort målgrupper.

## Visa målgrupper i publiklistan

Publiklistan ➊ visar de befintliga målgrupperna.

![Målgruppshanteraren](assets/audiences-manager.png)

Så här visar du målgruppslistan:

1. I Customer Journey Analytics väljer du **[!UICONTROL Components]** > **[!UICONTROL Published audiences]**.

1. (Valfritt) Använd ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att konfigurera vilka kolumner som ska visas.

1. (Valfritt) Sök efter en målgrupp med ![Sök](/help/assets/icons/Search.svg).

   Följande kolumner är tillgängliga med information om varje målgrupp:

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

## Redigera målgrupper

Du kan redigera inställningarna för en viss målgrupp när som helst. När du redigerar en målgrupp (antingen en engångspublik eller en återkommande målgrupp) krävs en publicering på nytt.

Så här redigerar du en målgrupp:

1. I Customer Journey Analytics väljer du **[!UICONTROL Components]** > **[!UICONTROL Published audiences]**.

   Sidan Publiker visas.

1. Markera titeln på den målgrupp som du vill redigera.

   Dialogrutan **[!UICONTROL Edit audience]** visas.

1. Du kan uppdatera alla tillgängliga fält för målgruppen. Mer information om fälten som du kan uppdatera finns i [Målgruppsverktyget](/help/components/audiences/publish.md#audience-builder) i artikeln [Skapa och publicera målgrupper](/help/components/audiences/publish.md).

1. Välj **[!UICONTROL Republish]**.

## Åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt. Du kan välja åtgärder på snabbmenyn:

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Etiketter](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Tagga de valda målgrupperna. I dialogrutan **[!UICONTROL Update tags: *målgruppsnamn *]**&#x200B;väljer du taggar i listrutan eller skriver en eller flera nya taggar. Välj **[!UICONTROL Save]**&#x200B;att spara. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda målgrupperna. |
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Byt namn på den valda målgruppen. Använd dialogrutan **[!UICONTROL Rename: *målgruppsnamn *]**&#x200B;om du vill byta namn på målgruppen och välja **[!UICONTROL Save]**&#x200B;att spara. |

Följande åtgärder är tillgängliga i det blå åtgärdsfältet när du väljer ett eller flera schemalagda projekt.

| Ikon | Åtgärd | Beskrivning |
|:---:|---|---|
| ![Stäng](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Markera för att avmarkera valda målgrupper. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort de valda målgrupperna. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Exportera de valda målgrupperna till en fil med namnet `audiences.csv`. |

## Filtrera målgruppslistan

Du kan filtrera [publiklistan](#audiences-list) med filterpanelen ➋. Om du vill visa eller dölja filterpanelen använder du ![Filter](/help/assets/icons/Filter.svg).

![Målgruppshanteraren](assets/audiences-manager.png)

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
