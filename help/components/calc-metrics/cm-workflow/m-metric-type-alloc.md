---
description: Läs mer om
title: Mätvärdestyp och attribuering
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 7f3412dc852ccae1ad5e122c200da5567ba89e87
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---

# Mätvärdestyp och attribuering

Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.

## Mätningstyp

Så här anger du måtttypen när du skapar ett beräknat mått:

1. Markera kugghjulsikonen bredvid mätvärdet vars typ du vill markera.

   ![](assets/cm_type_alloc.png)

1. Välj bland följande alternativ:

   | Mätningstyp | Definition |
   |---|---|
   | Standard | Dessa mått är samma som de som används i standard [!DNL Analytics] rapportering. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel: [Beställningar] / [Sessioner] tar emot order för den specifika radartikeln och dividerar den med antalet sessioner för den specifika radartikeln. |
   | Summa | Använd totalsumman för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalmått visas samma totaltal för varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Till exempel: [Beställningar] / [Totalt antal sessioner] visar andelen order mot ALLA sessioner på din webbplats, inte bara sessionerna med den specifika radobjektet. |

## Attribuering

Mer information om attribuering i Customer Journey Analytics finns i [Inställningar för attribueringskomponent](/help/data-views/component-settings/attribution.md).
