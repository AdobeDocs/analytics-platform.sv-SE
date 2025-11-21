---
title: Analysera Experience Platform-målgrupper i Customer Journey Analytics
description: Lär dig hur du analyserar Experience Platform målgrupper i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Analysera Experience Platform-målgrupper i Customer Journey Analytics {#analyze-audiences-RTCDP}

Du kan börja analysera Experience Platform-målgrupper i Customer Journey Analytics när du har [skapat en konfiguration för målgruppsanalys](/help/connections/audience-analysis/audience-analysis-configure.md), när målgruppsdata är tillgängliga som nya dimensioner i Analysis Workspace.

En mall för en publiköversikt finns i Customer Journey Analytics.

Mer information om hur du får åtkomst till mallen för målgruppsöversikt finns i [Åtkomst till och kör en mall](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) i [Använd mallar](/help/analysis-workspace/templates/use-templates.md).

Mallen Målgruppsöversikt innehåller följande paneler:

## Panelen Användningsöversikt

Visar data för alla målgrupper med användningshändelser som är associerade med den valda datavyn. Information om målgruppsmedlemskap uppdateras dagligen från Experience Platform. Data visas alltid i går, så om du ändrar panelens datumintervall blir data felaktiga.

Använd tabellen i den här panelen för att bättre förstå målgruppernas beteende. Dra dimensionen Målgruppsbeskrivning från den markerade datavyn och lägg till den som en uppdelning. Eller använd någon annan interaktionsdimension (som Sida, Åtgärd o.s.v.) som uppdelning.

## Panelen De bästa målgrupperna

Visar var målgruppen skapades, oavsett om det är i RTCDP, Customer Journey Analytics o.s.v.

Använd tabellen i den här panelen för att bättre förstå hur målgruppens ursprung kan påverka andra faktorer. Dra dimensionen Målgruppsnamn från den markerade datavyn och lägg till den som en uppdelning. Eller använd någon annan interaktionsdimension (som Sida, Åtgärd o.s.v.) som uppdelning.

## Panelen Målgruppsöverlappning

Visar data för alla målgrupper med användningshändelser som är associerade med den valda datavyn. Data visas alltid i går, så om du ändrar panelens datumintervall blir data felaktiga.

Välj upp till tre målgrupper i tabellen på den här panelen för att se hur de överlappar varandra i motsvarande Venndiagram.

## Avslutade målgruppsanvändning

Visar data för alla befintliga målgrupper med användningshändelser som är associerade med den valda datavyn. Data visas alltid i går, så om du ändrar panelens datumintervall blir data felaktiga. &quot;Utdragna målgrupper&quot; är målgrupper där personer med användningshändelser lämnade eller slutade igår.

Använd tabellen i den här panelen för att bättre förstå målgruppernas beteende. Dra dimensionen Befintlig målgruppsbeskrivning från den markerade datavyn och lägg till den som en uppdelning. Eller använd någon annan interaktionsdimension eller mätmetod (som Sida, Åtgärd o.s.v.) som uppdelning.

## Avancerad målgruppspanel

Visar var varje målgrupp som slutade ursprungligen skapades, oavsett om det var i RTCDP, Customer Journey Analytics och så vidare.

Använd tabellen i den här panelen för att bättre förstå hur målgruppens ursprung kan påverka andra faktorer. Dra dimensionen Avslutade målgruppsnamn från den markerade datavyn och lägg till den som en uppdelning. Eller använd någon annan interaktionsdimension eller mätmetod (som Sida, Åtgärd o.s.v.) som uppdelning.








