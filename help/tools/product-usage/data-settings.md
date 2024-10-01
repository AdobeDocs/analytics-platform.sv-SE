---
title: Inställningar för produktanvändningsdata
description: Aktivera, inaktivera eller konfigurera inställningar för produktanvändning.
hide: true
hidefromtoc: true
source-git-commit: 5c18fd78a71ddffef62dc3ac69f1abc3b42bddda
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# Inställningar för produktanvändningsdata {#product-usage-data-settings}

Sidan _Datainställningar_ hanterar din produktanvändningskonfiguration. Du kan använda den här sidan för att aktivera eller inaktivera produktanvändning för din organisation. Du kan också konfigurera vilken Adobe Experience Platform-sandlåda som datauppsättningen skapas under och åsidosätta datalagringsfönstret om du vill. Det är bara synligt för produktadministratörer.

**Customer Journey Analytics** > **Verktyg** > **Produktanvändning** > **Datainställningar**

>[!IMPORTANT]
>
>När du aktiverar den här funktionen måste du godkänna villkoren innan du använder den. När du godkänner dessa villkor gör du det för hela din organisations räkning.

Följande inställningar är tillgängliga på den här sidan:

* **Aktivera produktanvändning**: Växlar tillgänglighet för insamling av produktanvändningsdata. Om du aktiverar produktanvändning och sedan inaktiverar den i framtiden tas inte datauppsättningen, anslutningen och datavyn bort. Spärra/knip är inaktiverat globalt för din organisation när den är avstängd.
* **Sandbox**: Anger den Adobe Experience Platform-sandlåda som schemat och datauppsättningen skapas under. Sandlådan som du väljer påverkar inte insamling av produktanvändningsdata. Om du ändrar den här sandlådeinställningen skapas en separat datamängd, anslutning och datavy. Historiska data finns kvar i föregående sandlåda.
* **Åsidosätt datalagringsfönstret**: Alla datauppsättningar har ett standardfönster för datalagring. Om den här inställningen är inaktiverad följer produktanvändningen den standardtidsperioden. Du kan aktivera den här inställningen om du vill korta ned den tid som data sparas. Du kan inte utöka datalagringen utanför datauppsättningens standardfönster för datalagring.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform sandlåda"
>abstract="Anger den Adobe Experience Platform-sandlåda som schemat och datauppsättningen skapas under."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Åsidosätt fönstret för datalagring"
>abstract="Minska tillgängligheten av produktanvändningsdata för att minska kostnaderna."
