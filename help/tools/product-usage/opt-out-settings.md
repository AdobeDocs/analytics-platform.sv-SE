---
title: Inställningar för produktanvändningsavanmälan
description: Hantera avanmälningsinställningar för enskilda användare inom organisationen.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Inställningar för produktanvändningsavanmälan {#product-usage-opt-out-settings}

{{release-limited-testing}}

På sidan _Avanvisningsinställningar_ kan du exkludera eller ta med användare i organisationen igen från spårning av produktanvändning. Det är bara synligt för produktadministratörer.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Opt-out settings]**

Följande inställningar är tillgängliga på den här sidan:

* **[!UICONTROL Opt-out user]**: En nedrullningsbar lista som innehåller alla Customer Journey Analytics-användare i din organisation. Välj en användare i den här listrutan och välj **[!UICONTROL Opt-out]** om du vill utesluta användaren från produktanvändningsspårning. Den användaren läggs till i tabellen [!UICONTROL Opt-out user list] nedan.
* **[!UICONTROL Opt-out user list]**: En tabell som visar alla användare som för närvarande är avanmäld från produktanvändningsspårning. Om du vill avanmäla en användare till produktanvändningsspårning markerar du kryssrutan bredvid en viss användare och väljer sedan knappen **[!UICONTROL Opt-in]**.

Adobe använder en kombination av spårning på klientsidan och serversidan för att samla in produktanvändningsdata för din organisation. När en användare avanmäts från början kan användaren fortfarande se data för spårning på klientsidan i felsökaren tills han/hon loggar ut och tillbaka till Customer Journey Analytics. Verifieringen på Adobe-serversidan säkerställer att spårningsdata på klientsidan ignoreras för användare som har valts ut.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Avanmäl användare"
>abstract="Undanta användare från spårning av produktanvändning."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Avanmäl användare"
>abstract="Undanta användare från spårning av produktanvändning."
