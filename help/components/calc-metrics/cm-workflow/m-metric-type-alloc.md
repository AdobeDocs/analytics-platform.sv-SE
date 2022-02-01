---
description: Läs mer om
title: Mätvärdestyp och attribuering
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 5%

---

# Mätvärdestyp och attribuering

Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.

## Mätningstyp

![](assets/cm_type_alloc.png)

| Mätningstyp | Definition |
|---|---|
| Standard | Dessa mått är samma som de som används i standard [!DNL Analytics] rapportering. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel: [Beställningar] / [Besök] tar emot order för den specifika radartikeln och dividerar den med antalet besök för den specifika radartikeln. |
| Totalt | Använd summan för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalt mätvärde visas samma totala antal på varje radartikel. Totala värden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Till exempel: [Beställningar] / [Totalt antal besök] visar hur stor andel av beställningarna som gäller för ALLA besök på er webbplats, inte bara besöken till den specifika radobjektet. |

## Attribuering

>[!IMPORTANT]
>En fullständig lista över icke-standardattribueringsmodeller och uppslagsfönster som stöds finns i [Attributmodeller och uppslagsfönster](/help/analysis-workspace/attribution/models.md).
