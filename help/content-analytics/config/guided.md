---
title: Guidad konfiguration för innehållsanalys
description: Konfigurera Content Analytics med en introduktionsguidad konfiguration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: c63fa8f776fcf3390d312fb44ae6c422e7fa7222
workflow-type: tm+mt
source-wordcount: '1599'
ht-degree: 0%

---

# Guidad konfiguration för innehållsanalys

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{#release-limited-testing}

Med den guidade konfigurationen kan du konfigurera innehållsanalyser snabbt och enkelt. I den guidade konfigurationen används en guide för att konfigurera kraven för att konfigurera Content Analytics automatiskt för din organisation. På skärmen **[!UICONTROL Configuration]** kan du antingen skapa en ny konfiguration eller redigera en befintlig konfiguration.

Få åtkomst till konfigurationen för innehållsanalys

* Välj **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** på huvudmenyn i Customer Journey Analytics.

På skärmen Konfiguration av innehållsanalys visas en tabell med befintliga konfigurationer för innehållsanalys.

![Konfigurationer för innehållsanalys](../assets/aca-configuration-table.png)
För varje konfiguration finns följande information:

| Kolumn | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Namnet på konfigurationen. |
| **[!UICONTROL Created by]** | Det tekniska konto som skapade konfigurationen. |
| **[!UICONTROL Created on]** | Tidsstämpeln när konfigurationen skapades. |
| **[!UICONTROL Modified on]** | Tidsstämpeln när konfigurationen senast ändrades. |
| **[!UICONTROL Sandbox]** | Sandlådan inom organisationen där innehållsanalys har konfigurerats och implementerats (planeras att konfigureras). |
| **[!UICONTROL Status]** | Konfigurationens status. Statusen kan vara:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**: Konfigurationen sparas för senare och distribueras inte.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**: Konfigurationen misslyckades. Du måste redigera konfigurationen och göra nödvändiga ändringar.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: Konfigurationen har slutförts och implementerats. |

Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att anpassa tabellen. Välj vilka kolumner som ska visas i dialogrutan **[!UICONTROL Customize table]** och välj **[!UICONTROL Apply]** för att tillämpa ändringarna.

På skärmen Innehållsanalys **[!UICONTROL Configuration]** kan du skapa en ny konfiguration eller redigera en befintlig konfiguration.

Så här skapar du en ny konfiguration:

* Välj **[!UICONTROL Create configuration]**. Den här åtgärden öppnar guiden för guidad konfiguration.

Redigera en befintlig konfiguration:

* Välj ![Mer](/help/assets/icons/More.svg) och sedan ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** för en befintlig konfiguration för innehållsanalys. Den här åtgärden öppnar guiden för guidad konfiguration.

## Guiden Guidad konfiguration

Guiden för guidad konfiguration består av fyra avsnitt ([Detaljer](#details), [Datavy](#data-view), [Experience capture &amp; definition](#experience-capture-and-definition) och [Data collection](#data-collection)), där du uppmanas ange information som krävs för att konfigurera och konfigurera Content Analytics. Slutför varje avsnitt innan du går till nästa avsnitt, eftersom vissa inställningar i ett avsnitt kan bero på konfigurationsvärden i tidigare avsnitt.

### Information {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Information"
>abstract="Ange ett namn för anslutningen. I avsnitten **[!UICONTROL Data view]**, **[!UICONTROL Experience capture and definition]** och **[!UICONTROL Data collection]** anger du mer information för att säkerställa att innehållsanalysen kan konfigureras korrekt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Information"
>abstract="Den här guiden ställer in de krav som krävs för att konfigurera Content Analytics. Ange ett namn för konfigurationen"

<!-- markdownlint-enable MD034 -->

Varje konfiguration kräver ett unikt namn. Exempel: `Example Content Analytics configuration`.

![Konfigurationsinformation för innehållsanalys](../assets/aca-configuration-details.png)


### Datavy {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Datavy"
>abstract="För konfigurationen av innehållsanalysen måste du välja en befintlig datavy. Så att ni kan sammanfoga era innehållsanalysdata med andra data."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Datavy"
>abstract="Välj en befintlig datavy från Customer Journey Analytics som du vill sammanfoga innehållsanalysdata med.<br/>[Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target=\"_blank\"}"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Datavy"
>abstract="Välj en befintlig datavy från Customer Journey Analytics som du vill sammanfoga dina innehållsanalysdata med.<br/>"

<!-- markdownlint-enable MD034 -->

Din konfiguration kräver att du väljer en [datavy](/help/data-views/data-views.md).

![Konfiguration av innehållsanalys för en datavy](../assets/aca-configuration-dataview.png)

Så här väljer du en datavy:

1. Använd ![Data](/help/assets/icons/Data.svg) **[!UICONTROL Select Data view]**. Du ser en **[!UICONTROL Data view]**-dialogruta där du kan välja en datavy för din konfiguration.

   Om du skapar en ny konfiguration visar listan endast datavyer som är kopplade till sandlådor som inte har någon aktiv konfiguration.
Om du redigerar en befintlig konfiguration visas endast datavyer som är tillgängliga i sandlådan som redan är kopplad till den befintliga konfigurationen.

   * Om du vill filtrera listan med tillgängliga datavyer väljer du ![Visa filter](/help/assets/icons/Filter.svg). Du kan filtrera listan på Connection, Owner och Sandbox.<br/>Använd ![Dölj](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** för att dölja filterrutan.
   * Om du vill definiera vilka kolumner som ska visas i tabellen väljer du ![Kolumninställningar](/help/assets/icons/ColumnSetting.svg). Välj vilka kolumner som ska visas i dialogrutan **[!UICONTROL Customize table]** och välj **[!UICONTROL Apply]** för att tillämpa ändringarna.
1. Välj **[!UICONTROL Save]** för att bekräfta den valda datavyn. Välj **[!UICONTROL Cancel]** om du vill avbryta.

En datavy är kopplad till en [anslutning](/help/connections/overview.md) i Customer Journey Analytics. Och en Connection är baserad på en sandlåda i organisationen. När du har sparat konfigurationen fylls **[!UICONTROL Sandbox]** automatiskt i med rätt namn på sandlådan, baserat på den valda datavyn.


### Upplevelsehantering och -definition

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Upplevelsehantering och -definition"
>abstract="Du kan välja att inkludera upplevelser i de data du samlar in med Content Analytics. När du väljer det här alternativet måste du definiera en eller flera kombinationer av en regex- och frågeparametrar för att definiera för vilka URL:er du vill inkludera upplevelser."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Upplevelsehantering och -definition"
>abstract="Samla upplevelser i innehållsanalys"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_url_header"
>title="Upplevelsehantering och -definition"
>abstract="Ange URL-adresser som parametrarna nedan gäller för"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="Upplevelsehantering och -definition"
>abstract="Du kan redigera inställningarna i tillägget Adobe Content Analytics i taggegenskapen som är kopplad till den markerade konfigurationen."



<!-- markdownlint-enable MD034 -->

I det här avsnittet kan du välja att inkludera upplevelser i de data som du samlar in med Content Analytics. En upplevelse är all text på en webbsida som är reproducerbar med den URL som den första användaren använder när han/hon besöker den webbsidan. När du väljer det här alternativet måste du definiera för vilka URL-adresser som du vill inkludera upplevelser.

Så här inkluderar du upplevelser i en ny eller ej implementerad konfiguration:

![Konfiguration av innehållsanalys - Hämta och definiera ](../assets/aca-configuration-experience.png)

1. Aktivera **[!UICONTROL Include experiences]**.
1. Ange parametrarna som bestämmer hur innehåll återges på webbplatsen. Parametrarna är noll eller flera kombinationer av **[!UICONTROL Domain regular expression]** och **[!UICONTROL Query parameters]**.
   1. Ange en **[!UICONTROL Domain regular expression]**, till exempel `(?!.*\b(store|help|admin)\b)`.
   1. Ange en kommaavgränsad lista med **[!UICONTROL Query parameters,]**, till exempel `outdoors, patio, kitchen`.
   1. Välj **[!UICONTROL Remove]** om du vill ta bort en kombination.
   1. Välj **[!UICONTROL Add another]** om du vill lägga till en annan kombination.

Så här redigerar du befintliga eller inkluderar nya upplevelser i en implementerad konfiguration:

![Konfiguration av innehållsanalys - Hämta och definiera ](../assets/aca-configuration-experience-edit.png)

* Välj ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera parametrarna i tillägget Adobe Content Analytics i taggegenskapen, som är associerad med den markerade konfigurationen.


### Datainsamling {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Datainsamling"
>abstract="Definiera vilken taggegenskap du vill använda eller skapa en ny. Och definiera de sidor och resurser som du vill inkludera eller exkludera med hjälp av reguljära uttryck."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Datainsamling"
>abstract="Ange en taggegenskap"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Datainsamling"
>abstract="**Sidor som ska inkluderas/exkluderas**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Datainsamling"
>abstract="Ange vilka sidor som ska **inkluderas** eller **exkluderas** vid insamling av data för innehållsanalys"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Datainsamling"
>abstract="**Assets att inkludera/exkludera**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Datainsamling"
>abstract="Ange vilka resurser som ska **inkluderas** eller **exkluderas** vid insamling av data för innehållsanalys"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Datainsamling"
>abstract="Du kan redigera inställningarna för sidor i tillägget Adobe Content Analytics i taggegenskapen som är kopplad till den markerade konfigurationen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Datainsamling"
>abstract="Du kan redigera inställningarna för resurser i Adobe Content Analytics-tillägget i taggegenskapen som är kopplad till den markerade konfigurationen."

<!-- markdownlint-enable MD034 -->

#### Ny konfiguration

I en ny konfiguration måste du definiera vilken taggegenskap du vill använda eller skapa en ny taggegenskap. Och du måste definiera sidorna och resurserna som du vill inkludera eller exkludera med hjälp av reguljära uttryck.

* Så här använder du en befintlig taggegenskap:

  ![Tagg för befintlig datainsamling för innehållsanalys](../assets/aca-configuration-datacollection-existingtag.png)

   * Välj **[!UICONTROL Existing]**.
   * Välj en befintlig egenskap i listrutan **[!UICONTROL Tag property]**.

* Så här skapar du en ny taggegenskap:

  ![Datainsamling för innehållsanalys - ny tagg](../assets/aca-configuration-datacollection-newtag.png)

   1. Välj **[!UICONTROL Create new]**.
   2. Ange en **[!UICONTROL Tag name]**, till exempel `ACA Test`.
   3. Ange en eller flera **[!UICONTROL Domains]**, till exempel `example.com`.

   * Om du vill lägga till fler domäner väljer du **[!UICONTROL Add another]**.
   * Om du vill ta bort en domän väljer du ![CrossSize75](/help/assets/icons/CrossSize75.svg).

* Om du har valt att inkludera upplevelser, ange vilka sidor som ska inkluderas eller exkluderas när du samlar in data för Content Analytics.

   * Ange ett vanligt uttryck för **[!UICONTROL Experience]**. Till exempel: `(?!.*\b(store|help|admin)\b)`.

* Ange vilka resurser som ska inkluderas eller exkluderas när du samlar in data för Content Analytics.

   * Ange ett vanligt uttryck för **[!UICONTROL Asset]**. Till exempel: `(?!.*\b(store|help|admin)\b)`.


#### Befintlig konfiguration

För en befintlig konfiguration kan du inte redigera taggegenskapen. Du kan dock redigera sidor och resurser som ska inkluderas eller exkluderas.

* Om du vill redigera vilka sidor som ska inkluderas eller exkluderas när du samlar in data för innehållsanalys väljer du ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** under **[!UICONTROL Experience]**.

* Om du vill redigera vilka resurser som ska inkluderas eller exkluderas när du samlar in data för innehållsanalys väljer du ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** under **[!UICONTROL Asset]**.

### Sammanfattning

När du har angett all nödvändig information visas ett **[!UICONTROL You're almost ready to implement _konfigurationsnamn _för innehållsanalyssammanfattningen]**.

För befintliga implementerade konfigurationer visas ett **[!UICONTROL You have implemented _konfigurationsnamn _för en sammanfattning av innehållsanalys]**.

![Konfigurationssammanfattning för innehållsanalys](../assets/aca-configuration-summary.png)

### Åtgärder

När du har skapat eller redigerat en konfiguration är följande åtgärder tillgängliga.

* **[!UICONTROL Discard]**: Alla ändringar som gjorts som en del av skapandet av en ny konfiguration eller redigeringen av en befintlig konfiguration tas bort.
* **[!UICONTROL Save for later]**: Ändringar som görs i en ny konfiguration eller en befintlig konfiguration som ännu inte implementerats sparas. Du kan gå igenom konfigurationen igen senare om du vill göra ytterligare ändringar eller implementera konfigurationen.
* **[!UICONTROL Implement]**: Ändringar som görs i en ny konfiguration eller befintlig, ännu inte implementerad konfiguration sparas och implementeras. Implementeringen består av följande:
   * **[!UICONTROL Adobe Experience Platform]**-konfiguration:
      1. Skapa scheman för att modellera Content Analytics-händelser, resursattribut och (om de är konfigurerade) upplevelseattribut.
      1. Skapa datauppsättningar för att samla in Content Analytics-händelser, resursattribut och (om de är konfigurerade) upplevelseattribut.
   * **[!UICONTROL Content Analytics]**-konfiguration:
      * Inställning av en funktionsmonteringsprocess baserad på konfigurationen.
   * **[!UICONTROL Customer Journey Analytics]**-konfiguration:
      1. Den valda datavyn uppdateras med mått och mått för innehållsanalys.
      1. Anslutningen som är kopplad till den valda datavyn har ändrats så att den inkluderar händelser- och attributdatamängder för Content Analytics.
      1. Rapporteringsmallar för innehållsanalyser läggs till i Workspace.
   * **[!UICONTROL Data collection]**-konfiguration:
      1. Den nya eller befintliga taggegenskapen är konfigurerad för att stödja insamling av innehållsanalysdata. Den här konfigurationen innebär att tillägget Adobe Content Analytics för taggar ingår.
      1. En datastream skapas för Content Analytics-händelser.
      1. Tillägget Adobe Content Analytics är konfigurerat för att säkerställa att Content Analytics-händelser skickas till datastream för Content Analytics.
      1. Om Web SDK inte är konfigurerat för taggegenskapen skapas en ny Web SDK-konfiguration som endast skickar Content Analytics-händelser.
      1. Om Web SDK är konfigurerat för den här taggegenskapen görs inga ändringar i den befintliga Web SDK-konfigurationen.
* **[!UICONTROL Save]**: Ändringar som görs i en implementerad konfiguration sparas och implementeringen uppdateras.
