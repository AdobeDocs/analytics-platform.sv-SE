---
description: Läs mer om vanliga frågor om Workspace och felsökningstips.
title: Frågor och svar
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
role: User
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 41%

---

# Frågor och svar

| Fråga | Svar |
|--- |--- |
| **Vilka är förutsättningarna för att använda Analysis Workspace?** | Analysis Workspace i Customer Journey Analytics kräver en fungerande implementering av Customer Journey Analytics. Kontrollera att din organisation skickar data till Adobe Experience Platform innan du använder verktyget. |
| **Vilka är administrations- och åtkomstkraven för Analysis Workspace?** | Se [Administrationskrav](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Kommer Analysis Workspace att påverka datainsamlingen?** | Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig. Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på *[!UICONTROL Project] > [!UICONTROL New]* i den övre vänstra menyn. |
| **Hur implementerar jag Analysis Workspace?** | Ingen särskild implementering krävs. Analysis Workspace är tillgängligt för alla företag i Customer Journey Analytics. Standardbehörigheter för innehåll (t.ex. projektkomponenter) gäller, och för att strukturera och dela projekt. Se [Krav för administration och åtkomst](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Hur kan jag optimera prestanda för Analysis Workspace?** | Se [Optimera prestanda](/help/technotes/optimizing-performance.md). |

## Felsökning

**När jag drar ett mätvärde står det ”Ogiltiga data”.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida.

**När jag drar ett mätvärde ser jag inga data, bara nollor.**

Om du har skapat en rapport om arbetsytan men det inte finns några data kan du kontrollera några saker:

* Om du tillämpade ett filter i rapporten kanske filtervillkoren inte matchar några data. Försök att ta bort filtret eller justera filterdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd [Felsökning](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) för att verifiera att data samlas in.
