---
description: Beskriver den nya landningssidans funktioner.
title: Customer Journey Analytics landningssida
role: User, Admin
feature: Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
source-git-commit: c3d97fe2353011f4747d0c1742e49189cc91b85c
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 0%

---

# Customer Journey Analytics landningssida

Landningssidan för Customer Journey Analytics visar [!DNL Analysis Workspace] och innehåller en startsida för projektledaren samt en utbildningssektion som hjälper dig att hantera kundresedata mer effektivt.

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

Landningssidan för Customer Journey Analytics består av följande underflikar: Projekt och utbildningsmaterial.

**[!UICONTROL Projects]** är anpassade designer som kombinerar datakomponenter, tabeller och visualiseringar som du har skapat eller som någon annan har skapat och delat med dig. [!UICONTROL Projects] refererar också till tomma projekt och tomma mobilstyrkort.

Fliken **[!UICONTROL Learning]** innehåller praktiska videoutgångar, självstudiekurser och länkar till dokumentation.

## Navigera på fliken [!UICONTROL Projects] {#navigate-projects}

[!UICONTROL Projects] fungerar som startsida för [!UICONTROL Workspace]. Fliken Projekt visar företagsmappen, eventuella personliga mappar som du har skapat, dina projekt och Mobile Scorecards. Använd den här sidan om du vill visa, skapa och ändra mappar, projekt och mobila styrkort. Mer information finns i [Om mappar i Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Landing all](assets/landing-all2.png)

**[!UICONTROL Projects]** är anpassade designer som kombinerar datakomponenter, tabeller och visualiseringar som du har skapat eller som någon annan har skapat och delat med dig. [!UICONTROL Projects] refererar också till tomma projekt och tomma mobilstyrkort.

>[!NOTE]
>
>Flera av följande inställningar finns kvar under sessionen och mellan sessionerna. Till exempel den flik du har markerat, de markerade filtren, de markerade kolumnerna och kolumnsorteringsriktningen. Sökresultaten är inte beständiga.

### Anpassa tabellkolumner

Om du vill anpassa kolumnbredder drar du det lodräta strecket som skiljer varje kolumn åt.

Om du vill lägga till eller ta bort kolumner från listan med projekt klickar du på kolumnikonen (![Landing all](assets/select-column.png) ) i det övre högra hörnet och markerar eller avmarkerar sedan kolumnrubriker.

De tillgängliga kolumnerna är:

| Kolumnnamn | Beskrivning |
|---------|----------|
| [!UICONTROL **Namn**] | Identifierar namnet på projektet. |
| [!UICONTROL **Typ**] | Anger om den här typen är ett Workspace-projekt, ett Mobile-styrkort eller en mapp. |
| [!UICONTROL **Taggar**] | Taggar projekt för att ordna dem i grupper. |
| [!UICONTROL **Schemalagd**] | Ange [!UICONTROL On] när ett projekt är schemalagt eller [!UICONTROL Off] när det inte är det. Om du klickar på länken [!UICONTROL On] kan du visa information om det schemalagda projektet. Du kan också [redigera projektschemat](/help/analysis-workspace/export/t-schedule-report.md) om du är projektägare. |
| [!UICONTROL **Projektroll**] | Identifierar projektrollerna: om du är projektägare och om du har behörighet att redigera eller duplicera projektet. |
| [!UICONTROL **Rapportsviten**] | Identifierar de rapportsviter som är kopplade till projektet.<br>Tabeller och visualiseringar i en panel hämtar data från rapportsviten som har valts i panelens övre högra hörn. Rapportsviten avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda en eller flera rapportsviter beroende på dina analysexempel. Listan med rapportsviter sorteras efter relevans. Adobe definierar relevansen baserat på hur nyligen och ofta sviten har använts av den aktuella användaren och hur ofta sviten används i organisationen. |
| [!UICONTROL **Ägare**] | Identifierar den person som skapade projektet. |
| [!UICONTROL **Delas med**] | Visar vem projektet delas med. |
| [!UICONTROL **Senast ändrad**] | Datum och tid då projektet senast ändrades. |
| [!UICONTROL **Senast öppnad**] | Identifierar det datum då ett projekt senast öppnades av den användare som för närvarande visar projektsidan. |
| [!UICONTROL **Senast använd**] | Hjälper till att avgöra om ett projekt är värdefullt för användare i organisationen genom att visa datum och tid när projektet senast öppnades av någon användare i organisationen.<p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Användningsinformation finns tillgänglig från och med september 2023.</li><li>Den här kolumnen är bara tillgänglig för systemadministratörer.</li></ul> |
| [!UICONTROL **Projekt-ID**] | Kan användas för felsökning. |
| [!UICONTROL **Högsta datumintervall**] | Längre datumintervall ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiderna. |
| [!UICONTROL **Antal frågor**] | Det totala antalet begäranden som gjorts till Analytics när projektet läses in. Ett högre antal projektfrågor ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiden. Dessa data är bara tillgängliga när ett projekt har lästs in eller när ett schemalagt projekt har skickats. |
| [!UICONTROL **Plats**] | Visar mappen där projektet finns. |

### Andra gränssnittselement på sidan Projekt

| UI-element | Definition |
| --- | --- |
| Redigera inställningar | Gör att du kan [!UICONTROL View Tutorials] och [redigera användarinställningar](/help/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Öppnar det modala projektet där du kan skapa ett Workspace-projekt eller ett Mobile-styrkort eller öppna en företagsmall. |
| [!UICONTROL Show less<br> Visa mer] | Växlar mellan att inte visa och visa banderollen: ![Övre banderoll](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Skapar ett tomt [Workspace-projekt](/help/analysis-workspace/home.md) som du kan utforma och skapa. |
| [!UICONTROL Mobile scorecard] | Skapar ett tomt [mobilstyrkort](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) som du kan utforma och skapa. |
| [!UICONTROL Open Training Tutorial] | Öppnar Workspace självstudiekurs som vägleder dig genom processen att skapa ett nytt startprojekt i en stegvis självstudiekurs. |
| [!UICONTROL Open release notes] | Öppnar Adobe Analytics-delen av den senaste versionsinformationen för Adobe Experience Cloud. |
| Filterikon | Filter efter taggar, rapportsviter, ägare, typer och andra filter (Min, Delad med mig, Favoriter och Godkänd) |
| Sökfältet | Söker igenom alla kolumner i tabellen. |
| Markeringsruta | Väljer ett eller flera projekt för att visa de projekthanteringsåtgärder som du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta uppåt**, **Flytta nedåt**, **Tagg** 6}Godkänn **,** Exportera CSV **och** Flytta till **.** Du kanske inte har behörighet att utföra alla listade åtgärder. |
| [!UICONTROL Favorites] | Lägger till en stjärna bredvid ett favoritprojekt eller en mapp som kan användas som filter. |
| [!UICONTROL Name] | Identifierar namnet på projektet. |
| Fäst ikon | Fäster objekt så att de alltid visas högst upp i listan, men du kan ändra ordningen genom att flytta dem uppåt eller nedåt i den ordning som de visas. Använd ellipsalternativmenyn och välj **Flytta upp** eller **Flytta ned** i listan. |
| Info (i), ikon | Visar följande information om ett projekt: Typ, Projektroll, Ägare, Beskrivning och vem det delas med. Det anger också vem som kan [redigera eller duplicera](/help/analysis-workspace/curate-share/share-projects.md) det här projektet. |
| Ellips (...) | Visar de projekthanteringsåtgärder du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta upp**, **Flytta ned**, **Tagg**, **Godkänn**, **Exportera CSV** och **Flytta till**. Du kanske inte har behörighet att utföra alla listade åtgärder. |
| VISA: Mappar och projekt eller alla projekt | Ändrar visningsinställningen för tabellen så att mappar och projekt visas enligt mapporganisationen **eller**, vilket visar alla dina projekt i en oordnad lista. |
| &lt; (Bakåt-knappen) | Returnerar dig till den senaste konfigurationen av landningssidan i ett Workspace-projekt eller en rapport. Sidkonfigurationen som du hade när du lämnade landningssidan kommer att finnas kvar när du kommer tillbaka. |

## Använda fliken Utbildning {#navigate-learning}

Utbildningssidan innehåller praktiska videoutgångar, självstudiekurser och länkar till dokumentation.

Lär dig mer med utbildningssidan i Customer Journey Analytics:

* Nybörjare, mellanliggande eller avancerade funktioner och användningsområden i CJA
* Gå smidigare från Adobe Analytics till CJA

### Gå till sidan Utbildning

1. I Customer Journey Analytics väljer du [!UICONTROL **Workspace**] > [!UICONTROL **Learning**].

### Funktioner för utbildningssidor

* **Filtrera innehåll:** Med Filterikonen i den vänstra listen kan du filtrera utbildningsinnehåll efter erfarenhetsnivå (Nybörjare, Mellan eller Avancerat) och efter innehållstyp (dokument, video eller Tours och självstudiekurser).
* **Spåra förlopp:** När du har markerat en del av innehållet visas en **[!UICONTROL Viewed]** -tagg. Den här taggen hjälper dig att spåra dina framsteg med utbildningsinnehållet. Du kan markera taggen **[!UICONTROL Viewed]** om du vill ta bort den från innehållet.
* **Visa ytterligare innehåll:** När du visar en videofilm kan du visa relaterat dokumentationsinnehåll på Experience League genom att klicka på knappen **[!UICONTROL Learn more]** . Du kan också välja något av följande alternativ på sidan Lär dig mer om du vill visa ytterligare innehåll:
   * **[!UICONTROL Visit YouTube]:** Visa hela spelningslistan för Analysis Workspace YouTube.
   * [!UICONTROL **Gå till Experience League**]: Se hela uppsättningen CJA-dokumentation på Experience League.
* **Grundläggande om nya användare:** Demonstrationen [!UICONTROL Workspace Fundamentals] rekommenderas för nya användare. Demonstrationen tar dig direkt till Workspace och leder dig igenom de vanligaste åtgärderna. Demonstrationen kan också öppnas igen när som helst i Workspace via verktygstipset i panelhuvudet.

## Ange landningssida {#set-landing}

Användare kan ange sin favoritlandningssida.

1. Gå till Analytics > [!UICONTROL Components] > [!UICONTROL Preferences] > [!UICONTROL General].
1. Kontrollera vilken landningssida du vill använda:

   ![Ange landningssida](assets/landing-pref.png)

## Vanliga frågor om landningssidan {#landing-faq}

| Fråga | Svar |
| --- | --- |
| Överför mitt arbete i betaprogrammets användargränssnitt till produktionen [!UICONTROL Workspace]? | Ja, allt arbete som görs i betaversionen överförs till den gamla/aktuella [!UICONTROL Workspace]-upplevelsen. |
| Finns det ett maximalt antal projekt jag kan fästa? | Nej, det finns ingen gräns för hur många projekt du kan fästa. |
| Kan administratörer ange den här landningssidan för sina användare? | Nej, administratörer kan inte ange landningssidan för användarnas räkning. Enskilda användare måste aktivera växeln själva. |

<!-- | Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> | 
-->
