---
title: Inställningar för produktanvändningsdata
description: Aktivera, inaktivera eller konfigurera inställningar för produktanvändning.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Inställningar för produktanvändningsdata {#product-usage-data-settings}

Sidan _Datainställningar_ hanterar din produktanvändningskonfiguration. Du kan använda den här sidan för att aktivera eller inaktivera produktanvändning för din organisation. Du kan också konfigurera vilken Adobe Experience Platform-sandlåda som datauppsättningen skapas under och åsidosätta datalagringsfönstret om du vill. Det är bara synligt för produktadministratörer.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Data settings]**

>[!IMPORTANT]
>När du aktiverar den här funktionen måste du godkänna villkoren innan du använder den. När du godkänner dessa villkor gör du det för hela din organisations räkning.

Följande inställningar är tillgängliga på den här sidan:

* **[!UICONTROL Enable product usage]**: Växlar tillgänglighet för datainsamling om produktanvändning. Om du aktiverar produktanvändning och sedan inaktiverar den i framtiden tas inte datauppsättningen, anslutningen och datavyn bort. Spärra/knip är inaktiverat globalt för din organisation när den är avstängd.
* **[!UICONTROL Sandbox]**: Anger den Adobe Experience Platform-sandlåda som schemat och datauppsättningen skapas under. Sandlådan som du väljer påverkar inte insamling av produktanvändningsdata. Om du ändrar den här sandlådeinställningen tas alla befintliga data bort. En ny datauppsättning, anslutning och datavy skapas i den valda sandlådan.
* **[!UICONTROL Override data retention window]**: Alla datauppsättningar har ett standardfönster för datalagring. Om den här inställningen är inaktiverad följer produktanvändningen den standardtidsperioden. Du kan aktivera den här inställningen om du vill korta ned den tid som data sparas. Förkorta tidsfönstret för datalagring och minska kostnaderna och gör det möjligt att följa eventuella personalspecifika riktlinjer för sekretess. Du kan inte utöka datalagringen utanför datauppsättningens standardfönster för datalagring.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform sandlåda"
>abstract="Anger den Adobe Experience Platform-sandlåda som schemat och datauppsättningen skapas under."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Åsidosätt fönstret för datalagring"
>abstract="Korta tillgängligheten för produktanvändningsdata för att minska kostnaderna eller följa riktlinjerna för integritet."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Adobe Experience Platform sandlåda"
>abstract="Anger den Adobe Experience Platform-sandlåda som schemat och datauppsättningen skapas under."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Åsidosätt fönstret för datalagring"
>abstract="Korta tillgängligheten för produktanvändningsdata för att minska kostnaderna eller följa riktlinjerna för integritet."
