---
description: Läs mer om
title: Mättyp och attribut
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---

# Mättyp och attribut

Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.

## Mätningstyp

Så här anger du måtttypen när du skapar ett beräknat mått:

1. Markera kugghjulsikonen bredvid mätvärdet vars typ du vill markera.

   ![Kugghjulsikon med popup-fönster som visar en metrisk typ som är lika med Standard.](assets/cm_type_alloc.png)

1. Välj bland följande alternativ:

   | Mätningstyp | Definition |
   |---|---|
   | Standard | Dessa mått är samma mått som används i [!DNL Analytics]-standardrapporter. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel tar [Beställningar] / [Sessioner] order för det specifika radobjektet och dividerar det med antalet sessioner för det specifika radobjektet. |
   | Summa | Använd totalsumman för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalmått visas samma totaltal för varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med totaldata. Till exempel visar [Beställningar] / [Totalt antal sessioner] andelen order mot ALLA sessioner i en kanal, inte bara sessionerna med det specifika radobjektet. |

## Tillskrivning

Mer information om attribuering i Customer Journey Analytics finns i [Inställningar för attribueringskomponent](/help/data-views/component-settings/attribution.md).
