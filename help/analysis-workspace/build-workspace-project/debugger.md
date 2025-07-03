---
description: Lär dig hur du använder felsökningsfunktionen för att felsöka problem med ditt projekt i Analysis Workspace.
keywords: Analysis Workspace
feature: Workspace Basics
title: Felsökning av projekt
role: User
source-git-commit: ae8c1fb127accae53ab9363a8cceedd5221a245b
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Felsökning av projekt

Med felsökningsfunktionen för projekt kan du och Adobe Support felsöka problem med dina projekt i Analysis Workspace. Adobe Support kan begära att du aktiverar felsökningsfunktionen för att felsöka biljetter som du har tagit upp hos Adobe Support. Exempel på problem är inläsningstid för visualiseringar eller brutna komponenter i dina visualiseringar.

>[!NOTE]
>
>Om du vill använda felsökaren måste du ha **Redigera** eller **Kopiera** [åtkomst till projektet](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-25744).
>


## Aktivera felsökning

>[!IMPORTANT]
>
>Spara projektet innan du aktiverar felsökaren.
>

Så här aktiverar du felsökaren:

1. Välj **[!UICONTROL Help]** > **[!UICONTROL Enable debugger]** på Analysis Workspace projektmeny.
1. Välj **[!UICONTROL OK]** i dialogrutan **[!UICONTROL Enable Debugger]**.
1. Bekräfta när webbläsaren uppmanar dig att läsa in sidan eller webbplatsen igen.


## Använd felsökning

När du har aktiverat felsökaren har alla visualiseringar i ditt projekt en extra ![felikon](/help/assets/icons/Bug.svg) .

Så här använder du felsökaren för en viss visualisering:

1. Välj ![Fel](/help/assets/icons/Bug.svg) högst upp i visualiseringen.

   ![Snabbmenyn Felsökning](assets/debugger-context-menu.png)

1. Välj lämplig åtgärd på snabbmenyn. Vilka åtgärder som är tillgängliga beror på visualiseringen och anger vilken typ av felsökning du vill utföra. Om du till exempel väljer **[!UICONTROL Anomalies]** vill du felsöka avvikelsefunktionerna i visualiseringen.
1. Välj en tidsstämpel på undermenyn.
1. Ett **[!UICONTROL Oberon XML]**-felsökningsfönster öppnas med information om de specifika funktioner som visualiseringen har utfört. Nedan finns ett exempel på resultatet av en avvikelsebegäran.

   ![Begäran om felsökning av utdata](assets/debugger-oberon.png)

   Mer information:

   * **[!UICONTROL Request timestamp]**
   * **[!UICONTROL Response timestamp]**
   * **[!UICONTROL Request time]**
   * **[!UICONTROL Queue time]**
   * **[!UICONTROL Server processing time]**
   * **[!UICONTROL Lookup time]**
   * **[!UICONTROL Complexity]**
   * **[!UICONTROL Month boundaries]**
   * **[!UICONTROL Columns]**
   * **[!UICONTROL Segments]**
   * **[!UICONTROL XML]** **[!UICONTROL Request]** och **[!UICONTROL Response]**
   * **[!UICONTROL cURL Request]**
   * **[!UICONTROL JSON]** **[!UICONTROL Request]** och **[!UICONTROL Response]**

1. Använd ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy all field to clipboard]** om du vill kopiera all felsökningsinformation till Urklipp. Klistra in informationen i den redigerare eller det verktyg du föredrar. Informationen består av

   * XML (begäran)
   * XML (svar)
   * JSON (begäran)
   * JSON (svar)
   * Lätt begäran

1. Använd ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy to clipboard]** under **[!UICONTROL cURL Request]** för att kopiera begäran till Urklipp.
1. Håll markören över något av textområdena **[!UICONTROL Request]** eller **[!UICONTROL Response]** som ska visas och välj ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy to clipboard]** för att kopiera innehållet i textområdet (XML eller JSON) till Urklipp.

1. Utbyt den information du har kopierat och vilken Adobe Support har begärt för att felsöka visualiseringarna i ditt Analysis Workspace-projekt.

1. Välj **[!UICONTROL Cancel]** om du vill stänga felsökningsfönstret i **[!UICONTROL Oberon XML]** och återgå till projektet.

Upprepa stegen ovan för all annan visualisering som du vill felsöka.

## Inaktivera felsökning

>[!IMPORTANT]
>
>Innan du inaktiverar felsökaren bör du spara ändringar som du har gjort i projektet och vill behålla som en del av felsökningen.
>

Så här inaktiverar du felsökaren:

1. Välj **[!UICONTROL Help]** > **[!UICONTROL Disable debugger]** på Analysis Workspace projektmeny.
1. Välj **[!UICONTROL OK]** i dialogrutan **[!UICONTROL Disable debugger]**.
1. Bekräfta när webbläsaren uppmanar dig att läsa in sidan eller webbplatsen igen.



