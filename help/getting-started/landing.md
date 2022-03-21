---
description: Beskriver den nya landningssidans funktioner.
title: Customer Journey Analytics landningssida
role: User, Admin
feature: CJA Basics
source-git-commit: 2aafa1b1181377ff80b12dbaecd9634e53f1a08c
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---

# Customer Journey Analytics landningssida

På landningssidan för Customer Journey Analytics finns en startsida för projektledaren och ett utbildningsavsnitt som hjälper dig att komma igång effektivare.

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

## Åtkomst till landningssidan {#access-landing}

När du har loggat in på Adobe Experience Cloud och Customer Journey Analytics aktiverar du [!UICONTROL New landing page - Beta] växlingsknappen i det nedre vänstra hörnet. Åtkomsten till växlingsknappen är användarspecifik per organisation, inte företagsspecifik.

![Landning](assets/landing.png)

Ni kan

* Expandera [!UICONTROL Projects] tabell till helskärm. Om du vill expandera tabellen klickar du bara på menyikonen för hamburgaren. Den här åtgärden komprimerar flikarna till vänster.
* Anpassa kolumnbredden genom att dra kolumnavgränsaren.
* Ändra ordning på fästa objekt. Om du vill flytta fasta objekt uppåt och nedåt klickar du på ellipsen bredvid det fästa objektet och väljer **[!UICONTROL Move up]** eller **[!UICONTROL Move down]**.

## Navigera i [!UICONTROL Projects] tab {#navigate-projects}

[!UICONTROL Projects] fungerar som [!UICONTROL Workspace] hemsida. Alla arbetsyteprojekt visas här, inklusive Mobile Scorecards. **[!UICONTROL Projects]** är saker som du har skapat eller som någon annan har byggt och delat med dig. [!UICONTROL Projects] hänvisar också till tomma projekt och tomma mobilstyrkort.

>[!NOTE]
>
>Flera av följande inställningar finns kvar (sparas) både under sessionen och mellan sessionerna. Exempel: Vilken flik du är på, vilka filter som har markerats, vilka kolumner som har markerats och kolumnsorteringsriktningen. Sökresultaten sparas dock inte.

| UI-element | Definition |
| --- | --- |
| ... Mer | Gör att du kan [!UICONTROL View Tutorials]och [Redigera användarinställningar](/help/analysis-workspace/user-preferences.md). |
| **[!UICONTROL Create new]** modal är tillbaka | När du klickar **[!UICONTROL Create new]** i arbetsytan får du ännu en gång möjlighet att välja mellan [!UICONTROL Blank project] och [!UICONTROL Blank mobile scorecard]. Du kan också välja bland de mallar som företaget har skapat. |
| [!UICONTROL Show less/more] | Växlar mellan att inte visa och visa banderollen: ![Övre banderoll](assets/top-banner.png) |
| [!UICONTROL Blank project] | Skapar en tom [Arbetsyteprojekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=en) för att fylla i. |
| [!UICONTROL Blank mobile scorecard] | Skapar en tom [mobilstyrkort](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=en) för att fylla i. |
| [!UICONTROL Open Training Tutorial] | Öppnar självstudiekursen om arbetsytan där du kan vägleda nya användare genom att bygga ett projekt steg för steg. |
| [!UICONTROL Open release notes] | Öppnar den senaste versionsinformationen för Adobe Experience Cloud. |
| Filterikon | Du kan filtrera på taggar, rapportsviter, ägare, typer och andra filter (Min, Delad med mig, Favoriter och Godkänd) |
| Sökfältet | Sökningen innehåller nu alla kolumner i tabellen. |
| Markeringsruta | Om du klickar i den här rutan bredvid ett eller flera projekt visas de projekthanteringsåtgärder du kan utföra: Ta bort, tagga, fästa, godkänn, dela, byta namn, kopiera och exportera till CSV. Du kanske inte har behörighet att utföra alla dessa åtgärder. |
| [!UICONTROL Favorites] | Om du väljer att Favoritera ett projekt placeras en stjärna bredvid sig och taggas som en favorit som du kan filtrera på. |
| [!UICONTROL Name] | Projektets namn. |
| Info (i), ikon | Om du klickar på informationsikonen visas följande information om det här projektet: Typ, Projektroll, Ägare, Beskrivning och vem det delas med. Det anger också vem som kan [redigera eller duplicera](/help/analysis-workspace/curate-share/share-projects.md) det här projektet. |
| Ellips (..) | När du klickar på ellipsen bredvid ett projekt visas de projekthanteringsåtgärder du kan utföra: Ta bort, tagga, fästa, godkänn, dela, byta namn, kopiera och exportera till CSV. Observera att du kanske inte har behörighet att utföra alla dessa åtgärder. |
| [!UICONTROL Type] | Anger om den här typen är ett Workspace-projekt eller ett Mobile-styrkort. |
| [!UICONTROL Tags] | Du kan tagga rapporter för att ordna dem i grupper. |
| [!UICONTROL Project Role] | Projektroller avser om du är projektägare och om du har behörighet att redigera eller duplicera projektet. |
| [!UICONTROL Data View] | Tabeller och visualiseringar i en panel hämtar data från den datavy som är vald i panelens övre högra hörn. Datavyn avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda en eller flera datavyer, beroende på dina analysexempel. Listan med datavyer sorteras efter relevans. Adobe definierar relevansen baserat på hur nyligen och ofta datavyn har använts av den aktuella användaren och hur ofta datavyn används i organisationen. |
| [!UICONTROL Owner] | Personen som skapade projektet. |
| [!UICONTROL Shared with] | Vem projektet delades med. |
| [!UICONTROL Last Modified] | När det här projektet senast ändrades. |
| [!UICONTROL Last opened] | När det här projektet senast öppnades av dig. |
| [!UICONTROL Scheduled] | Ange till [!UICONTROL On] när ett projekt är schemalagt eller **[!UICONTROL Off]** när det inte är det. Klicka på **[!UICONTROL On]** -länken kan du visa information om det schemalagda projektet. Du kan också [redigera projektschemat](/help/analysis-workspace/curate-share/t-schedule-report.md) om du är projektägare. |
| [!UICONTROL Project ID] | Projekt-ID kan användas för felsökningsprojekt. |
| [!UICONTROL Longest Date Range] | Längre datumintervall ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiderna. |
| [!UICONTROL Number of Queries] | Ett högre antal projektfrågor ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiden. |
| Anpassa tabellikon | (Överst till höger) Om du vill lägga till eller ta bort kolumner från listan med projekt kan du göra det genom att markera eller avmarkera dem. |
| &lt; (Bakåt-knappen) | Den här knappen i ett Workspace-projekt tar dig tillbaka till den senaste konfigurationen för landningssidan. Vilken sidkonfiguration du än hade när du lämnade landningssidan kommer att finnas kvar när du kommer tillbaka. |

## Navigera på fliken Utbildning {#navigate-learning}

Utbildningssidan innehåller praktiska videoutgångar och självstudiekurser samt länkar till dokumentation.

* The [!UICONTROL Workspace Fundamentals] Demo tar dig direkt till arbetsytan och leder dig igenom arbetsytelayouten och var du kan hitta/utföra de vanligaste åtgärderna. Du kan när som helst starta om den här demon direkt i Workspace via verktygstipset i panelhuvudet.
* När du klickar på en video/demo läggs en **[!UICONTROL Viewed]** -tagg. Den här taggen hjälper dig att spåra dina framsteg med utbildningsinnehållet. Du kan klicka på taggen så försvinner den om du inte har slutfört innehållet än.
* The **[!UICONTROL Learn more]** på den spärrade videon tar dig till en Adobe Experience League-dokumentationssida med mer hjälpinnehåll om den video du just tittade på.  **[!UICONTROL View more videos]** tar dig till hela spelningslistan för Analysis Workspace YouTube.

## Vanliga frågor om landningssidan {#landing-faq}

| Fråga | Svar |
| --- | --- |
| Finns det ett maximalt antal projekt jag kan fästa? | Nej, det finns ingen gräns för hur många projekt du kan fästa. |
| Kan administratörer ange den här landningssidan för sina användare? | Nej, administratörer kan inte ange landningssidan för användarnas räkning. Enskilda användare måste aktivera växeln själva. |