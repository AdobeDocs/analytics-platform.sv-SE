---
description: Vanliga frågor om Workspace
title: Vanliga frågor och felsökningsarbetsyta
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 42%

---


# Frågor och svar

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

| Fråga | Svar |
|--- |--- |
| Vilka är förutsättningarna för att använda Analysis Workspace? | Analysis Workspace kräver en fungerande Customer Journey Analytics-implementering. Kontrollera att din organisation skickar data till Adobe Experience Platform innan du använder verktyget. |
| Vilka är administrations- och tillträdeskraven för Analysis Workspace? | Se [Administrationskrav](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Kommer användningen av Analysis Workspace att påverka datainsamlingen? | Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till Workspace-projektet för att se vad som är tillgängligt för dig. Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på *[!UICONTROL Project] > [!UICONTROL New]* i den övre vänstra menyn. |
| Hur implementerar man Analysis Workspace? | Ingen särskild implementering krävs. Analysis Workspace är tillgängligt för alla företag i Customer Journey Analytics. Standardbehörigheter för innehåll (t.ex. projektkomponenter) gäller, och för att strukturera och dela projekt. Se Krav för [administration och åtkomst](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Hur kan jag optimera Analysis Workspace prestanda? | Se [Optimera prestanda](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Felsökning

**När jag drar ett mätvärde står det ”Ogiltiga data”.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida.

**När jag drar ett mätvärde ser jag inga data, bara nollor.**

Om du har skapat en rapport för arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.