---
title: Manuell konfiguration för innehållsanalys
description: Konfigurera Content Analytics manuellt
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Manuell konfiguration för innehållsanalys

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{{release-limited-testing}}

I den här artikeln beskrivs de manuella åtgärder som krävs för att aktivera eller inaktivera en konfiguration för innehållsanalys eller för att redigera implementeringen av din Content Analytics.

Följande manuella konfigurationsåtgärder är tillgängliga:

## Aktivera

Om du vill aktivera en ny konfiguration eller ändringar som du har gjort i en befintlig konfiguration måste du [publicera](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} den associerade taggegenskapen. Det är bara när du publicerar taggegenskapen för innehållsanalys som du samlar in data för de domäner, upplevelser och resurser som du har konfigurerat.


## Inaktivera

Om du vill inaktivera insamling av innehållsanalysdata [avpublicerar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} den associerade taggegenskapen för din konfiguration för innehållsanalys.



## Ändra

I allmänhet bör du använda den [guidade konfigurationsguiden](guided.md) för att göra ändringar i implementeringen.

Du kan också använda tillägget Adobe Content Analytics i taggegenskapen som är kopplad till din Content Analytics-konfiguration för att göra ändringar i följande artefakter:

* [Sandbox och datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Du måste verifiera att den sandlåda och datastam som du konfigurerar i Adobe Content Analytics-tillägget redan har konfigurerats för Content Analytics med den [guidade konfigurationen](guided.md) i ett tidigare skede. Den här konfigurationen ser till att alla nödvändiga artefakter är tillgängliga.<br/><br/>Du måste också verifiera att uppdateringar för sandbox eller datastreams inte stör en annan Content Analytics-konfiguration som är konfigurerad att använda samma sandlåda eller datastreams.
  >

* [Händelsefiltrering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  Du kan redigera reguljära uttryck för att ändra hur du filtrerar sidor och resurser.


När du har gjort ändringar i Adobe Content Analytics-tillägget kontrollerar du att dina ändringar är [aktiverade](#activate).



>[!MORELIKETHIS]
>
>[Guidad konfiguration](guided.md)
>[Översikt över publicering av datainsamlingstaggar ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>