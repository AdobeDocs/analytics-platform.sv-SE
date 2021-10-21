---
description: 'Läs mer om '
title: Mätvärdestyp och attribuering
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
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

