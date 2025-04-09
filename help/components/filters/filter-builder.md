---
description: I filterverktyget finns en arbetsyta där du kan dra och släppa mått, filter och händelser för att filtrera personer baserat på behållarhierarkiens logik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar personattribut och åtgärder för besök och händelser.
title: Skapa filter
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 0%

---

# Skapa filter {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Skapa publik"
>abstract="Målgrupper kan skapas från ett filter och delas med Adobe Experience Platform för aktivering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Förhandsgranska data"
>abstract="Jämför data i det här filtret med data i datavyn. Procentandelen för förhandsgranskning baseras på det totala antalet i datavyn från de **senaste 90 dagarna**.<br><br/>Om förhandsgranskningen inte läses in kan anslutningen fortfarande återfyllas."

<!-- markdownlint-enable MD034 -->



Dialogrutan **[!UICONTROL Filter builder]** används för att skapa nya eller redigera befintliga filter. Dialogrutan heter **[!UICONTROL New filter]** eller **[!UICONTROL Edit filter]** för filter som du skapar eller hanterar från hanteraren [[!UICONTROL Filters] ](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Filterverktyget]

![Fönstret Filterinformation visar fält och alternativ som beskrivs i nästa avsnitt.](assets/filter-builder.png)

>[!TAB Skapa eller redigera filter]

![Fönstret Filterinformation visar fält och alternativ som beskrivs i nästa avsnitt.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Ange följande information (![Obligatorisk](/help/assets/icons/Required.svg) krävs):

   | Element | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Data view]** | Du kan välja datavyn för filtret.  Filtret som du definierar är tillgängligt som ett filter på fliken [Inställningar](/help/data-views/create-dataview.md#settings-filters) i en datavy. |
   | **[!UICONTROL Project-only filter]** | En informationsruta som förklarar att filtret bara visas i det projekt där det skapades och att filtret inte läggs till i komponentlistan. Aktivera **[!UICONTROL Make this filter available to all your projects and add it to your component list]** om du vill ändra den inställningen. Den här informationsrutan visas bara när du skapar ett [snabbfilter](quick-filters.md) och aktiverar snabbfilterinformationen som ett vanligt filter med **[!UICONTROL Open builder]** från [!UICONTROL Quick filter]-gränssnittet. |
   | **[!UICONTROL Title]** ![Krävs](/help/assets/icons/Required.svg) | Ge filtret ett namn, till exempel `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Ange en beskrivning för filtret, till exempel `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Ordna filtret genom att skapa eller använda en eller flera taggar. Börja skriva för att hitta befintliga taggar som du kan markera. Eller tryck på **[!UICONTROL ENTER]** för att lägga till en ny tagg. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort en tagg. |
   | **[!UICONTROL Definition]** ![Krävs](/help/assets/icons/Required.svg) | Definiera filtret med [Definitionsverktyget](#definition-builder). |

   {style="table-layout:auto"}

1. Om du vill kontrollera om filterdefinitionen är korrekt använder du den ständigt uppdaterade förhandsgranskningen av filterresultatet högst upp till höger.
1. Om du vill skapa en målgrupp från filtret och dela målgruppen med Experience Platform väljer du **[!UICONTROL Create audience from filter]**. Mer information finns i [Skapa och publicera målgrupper](/help/components/audiences/publish.md).
1. Välj:
   * **[!UICONTROL Save]** om du vill spara filtret.
   * **[!UICONTROL Save As]** om du vill spara en kopia av filtret.
   * **[!UICONTROL Delete]** för att ta bort filtret.
   * **[!UICONTROL Cancel]** om du vill avbryta alla ändringar du har gjort i filtret eller avbryta skapandet av ett nytt filter.


## Definition builder

Du använder Definitionsverktyget för att skapa filterdefinitionen. I den konstruktionen använder du komponenter, behållare, operatorer och logik.

Du kan konfigurera typen och omfattningen av din definition:

1. Om du vill ange typen av definition anger du om du vill att definitionen ska vara inkluderad eller exkluderad. Välj ![Inställning](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** och i listrutan **[!UICONTROL Include]** eller **[!UICONTROL Exclude]**.
1. Om du vill ange definitionens omfattning väljer du i listrutan **[!UICONTROL Include]** eller **[!UICONTROL Exclude]** om du vill att definitionens omfattning ska vara **[!UICONTROL Event]**, **[!UICONTROL Session]**, **[!UICONTROL Person]**, **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} eller **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}}

Du kan alltid ändra de här inställningarna senare.

### Komponenter

En viktig del av arbetet med att skapa filterdefinitioner är att använda mått, mätvärden, befintliga filter och datumintervall. Alla dessa komponenter är tillgängliga från komponentpanelen i filterverktyget.

![Börja bygga en definition](assets/start-building-filter.gif){width=100%}

Så här lägger du till en komponent:

1. Dra och släpp en komponent från komponentpanelen till **[!UICONTROL Drag and drop Metric(s), Filter(s), and/or Dimensions here]**. Du kan använda ![sökfunktionen](/help/assets/icons/Search.svg) i komponentfältet för att söka efter specifika komponenter.
1. Ange information för komponenten. Välj till exempel ett värde från **[!UICONTROL Select value]**. Eller ange ett värde. Vad och hur du kan ange ett eller flera värden beror på komponenten och operatorn.
1. Om du vill kan du ändra standardoperatorn. Exempel: från **[!UICONTROL equals]** till **[!UICONTROL equals any of]**. Se [Operatorer](operators.md) för en detaljerad översikt över tillgängliga operatorer.

Så här redigerar du en komponent:

* Välj en ny operator för komponenten i listrutan operator.
* Välj eller ange ett annat värde för operatorn om det är lämpligt.
* Om komponenttypen är en dimension kan du definiera attribueringsmodellen. Mer information finns i [Attributmodell](#attribution-models).

Så här tar du bort en komponent:

* Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) i en komponent.

### Behållare

Du kan gruppera flera komponenter i en eller flera behållare och definiera logik i och mellan behållare. Med behållare kan du skapa komplexa definitioner för filtret.

![Lägg till en behållare](assets/add-container.gif){Width=100%}

* Om du vill lägga till en behållare väljer du **[!UICONTROL Add container]** från ![Inställningar](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* Om du vill lägga till en befintlig komponent i behållaren drar och släpper du komponenten i behållaren.
* Om du vill lägga till en annan komponent i behållaren drar och släpper du en komponent från komponentpanelen i behållaren. Använd den blå infogningslinjen som stödlinje.
* Om du vill lägga till en annan komponent utanför behållaren drar och släpper du en komponent från komponentpanelen utanför behållaren, men inuti huvuddefinitionsbehållaren. Använd den blå infogningslinjen som stödlinje.
* Om du vill ändra logiken mellan komponenterna i en behållare, mellan behållare eller mellan en behållare och en komponent, väljer du lämplig **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]**. När du väljer Sedan kan du göra om filtret till ett sekventiellt filter. Mer information finns i [Skapa sekventiellt filter](seg-sequential-build.md).
* Om du vill ändra behållarnivån väljer du ![Global](/help/assets/icons/Globe.svg) **[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Konto](/help/assets/icons/Account.svg) **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Möjlighet](/help/assets/icons/Opportunity.svg) **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![BuyingGroup](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Buying Group]** [!BADGE B2B edition **[!UICONTROL Event]** 19}, ![WebPage]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} ](/help/assets/icons/WebPage.svg), ![Besök](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** eller ![Användare](/help/assets/icons/User.svg) **[!UICONTROL Person]**.

Du kan använda ![Setting](/help/assets/icons/Setting.svg) i en behållare för följande åtgärder:

| Behållaråtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Add container]** | Lägg till en kapslad behållare i behållaren. |
| **[!UICONTROL Exclude]** | Uteslut resultatet från behållaren i filterdefinitionen. Ett tunt rött fält till vänster identifierar en exkluderingsbehållare. |
| **[!UICONTROL Include]** | Inkludera resultatet från behållaren i filterdefinitionen. Inkludera är standard. Ett tunt grått fält till vänster identifierar en inkluderingsbehållare. |
| **[!UICONTROL Name container]** | Byt namn på behållaren från standardbeskrivningen. Skriv ett namn i textfältet. Om du inte anger några indata används standardbeskrivningen. |
| **[!UICONTROL Delete container]** | Ta bort behållaren från definitionen. |


## Datumintervall

Du kan skapa filter som innehåller rullande datumintervall. Ni kan alltså besvara frågor om pågående kampanjer eller evenemang. Du kan t.ex. skapa ett filter som innehåller *alla som har gjort ett onlineköp de senaste 60 dagarna*.

![Filtrera med rullande datumintervall](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rullande datumintervall i segment](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Staplingsfilter {#stack}

Du kan skapa ett filter med hjälp av filter. När du använder filter i ett filter kan du optimera filtret och minska komplexiteten.

Tänk dig att du vill filtrera efter kombinationen av enhetstyp (2) och USA (50). Du kan antingen skapa 100 filter, var och en för den unika kombinationen av enhetstyp (mobiltelefon eller surfplatta) och USA-läge. Om du vill få tillgång till den kaliforniska surfplattan använder du något av de 100 filtren:

![Enkelt filter för CA och surfplatta](assets/filter-ca-tablet-single.png)

Eller så kan du definiera 52 filter: 50 filter för USA, ett för mobiltelefonen och ett för surfplattan. Sedan staplar du filtren för att få samma resultat. För att få tillgång till den kaliforniska surfplattan behöver du två filter:

![Staplat filter för CA och surfplatta](assets/filter-ca-tablet-stacked.png)


## Tillskrivning {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Upprepande"
>abstract="Inkluderar instanser och beständiga värden för dimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instance"
>abstract="Inkluderar instanser och beständiga värden för dimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Icke upprepande instans"
>abstract="Inkluderar unika (icke upprepande) instanser för dimensionen."

<!-- markdownlint-enable MD034 -->



När du använder en dimension i filterverktyget har du möjlighet att ange attribueringsmodellen för den dimensionen. Den attribueringsmodell du väljer avgör om data uppfyller villkoren som du har angett för dimensionskomponenten.

Välj ![Inställning](/help/assets/icons/Setting.svg) i dimensionskomponenten och välj en av attributmodellerna i popup-fönstret:

| Models | Beskrivning |
|---|---|
| **[!UICONTROL Repeating model (default)]** | Inkludera instans- och beständiga värden för dimensionen för att avgöra kvalificeringen. |
| **[!UICONTROL Instance]** | Inkludera endast instansvärden för dimensionen för att bestämma kvalificeringen. |
| **[!UICONTROL Non-repeating instance]** | Inkludera unika instansvärden (ej upprepade) för dimensionen för att fastställa kvalificeringen. |


![Attributmodell i dimension när ett filter skapas](assets/filter-dimension-attribution.png)

### Exempel

Som en del av en filterdefinition har du angett följande villkor: Sidnamn är lika med Kvinnor. Liknar exemplet ovan. Du upprepar den här filterdefinitionen med två andra attribueringsmodeller. Du har alltså tre filter var och en med en egen attribueringsmodell:

* Kvinnors sida - Attribution - Upprepande (standard)
* Kvinnlig sida - Attribution - Instans
* Women Page - Attribution - Non-repeating instance


Tabellen nedan förklarar, för varje attribueringsmodell, vilka inkommande händelser som är kvalificerade ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) för det villkoret.


| Kvinnssida - Attribution - <br/>*attribueringsmodell* | Händelse 1:<br/>Sidnamnet är lika med<br/>Kvinnor | Händelse 2:<br/>Sidnamnet är lika med<br/>Män | Händelse 3:<br/>Sidnamnet är lika med<br/>Kvinnor | Händelse 4:<br/>Sidnamnet är lika med<br/>Kvinnor<br/>(beständigt) | Händelse 5:<br/>Sidnamnet är lika med<br/>Utcheckning | Händelse 6:<br/>Sidnamnet är lika med<br/>Kvinnor | Händelse 7:<br/>Sidnamnet är lika med<br/>Hem |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Upprepande (standard) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) |
| Instance | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) |
| Icke upprepande instans | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![Ta bort](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Ta bort](/help/assets/icons/Remove.svg) |

En exempelrapport om händelser som använder de tre filtren ser ut så här:

![Resultat av filterattribueringsmodell](assets/filter-dimension-attribution-results.png)
