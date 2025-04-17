---
description: Administratörer ansvarar för att övervaka hälsotillståndet för datamordlistor. Detta inkluderar huruvida komponenter samlar in data, är godkända, innehåller beskrivningar och är fria från dubbletter.
title: Övervaka dataordlistans hälsa
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---

# Övervaka dataordlistans hälsa

Customer Journey Analytics-administratörer ansvarar för att upprätthålla en felfri datamordlista.

## Egenskaper för en frisk datamordlista

En felfri datamordlista är en ordlista där alla komponenter:

* Används och samlar in data

* Innehåller användbara beskrivningar så att användarna vet hur de bäst använder dem

* Är fria från onödiga dubbletter

* Godkänns av administratören

## Kontrollera hälsotillståndet för din datamordlista

Så här identifierar du hälsoproblem i din Data Dictionary:

1. Öppna ett Analysis Workspace-projekt.

1. Välj ikonen Datamordlista till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i Åtkomst till dataordlistan i [Översikt över dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Vyn som administratör för dataordlista visar ordlistehälsa](assets/data-dictionary-admin.png)

1. Kontrollera att rätt datavy är markerad i listrutan.

1. På fliken [!UICONTROL **Lexikon**] väljer du [!UICONTROL **Visa**] bredvid något av följande alternativ:

   * [!UICONTROL **komponenter saknar beskrivningar**]

   * [!UICONTROL **komponenter har dubbletter**]

   * [!UICONTROL **komponenter har inga data anslutna**]

   Beroende på vad du väljer används rätt segment i datamallen, och endast de relevanta komponenterna visas.

1. Redigera någon av komponenterna för att förbättra hälsan i datamallen. Mer information om hur du redigerar en komponent i Data Dictionary finns i [Redigera komponentposter i Data Dictionary](/help/components/data-dictionary/edit-entries-data-dictionary.md).
