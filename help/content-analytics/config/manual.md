---
title: Manuell konfiguration för innehållsanalys
description: Konfigurera Content Analytics manuellt
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
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

Så här aktiverar du en ny konfiguration eller ändringar som du har gjort i en befintlig konfiguration:

1. Du måste följa [publiceringsflödet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Endast om du har publicerat biblioteket för taggegenskapen som innehåller din konfiguration för innehållsanalys samlas data för innehållsanalysen in för de domäner, upplevelser och resurser som du har konfigurerat.

1. Du måste [installera](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) inbäddningskoden i `<head>`-elementet för sidorna i din utvecklings-, staging- eller publiceringsmiljö, enligt Content Analytics.


## Inaktivera

Så här inaktiverar du insamling av innehållsanalysdata:

1. Ta bort [inbäddningskoden](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) i `<head>`-elementet för sidorna i din utvecklings-, staging- eller produktionsmiljö, som omfattas av Content Analytics.
1. [Ta bort](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) den associerade taggegenskapen för din konfiguration för innehållsanalys.



## Ändra

I allmänhet bör du använda den [guidade konfigurationsguiden](guided.md) för att göra ändringar i implementeringen.

Du kan också använda [Adobe Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) i taggegenskapen som är kopplad till din Content Analytics-konfiguration för att göra ändringar i följande artefakter:

* [Sandbox och datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Du måste verifiera att den sandlåda och datastam som du konfigurerar i Adobe Content Analytics-tillägget redan har konfigurerats för Content Analytics med den [guidade konfigurationen](guided.md) i ett tidigare skede. Den här konfigurationen ser till att alla nödvändiga artefakter är tillgängliga.<br/><br/>Du måste också verifiera att uppdateringar för sandbox eller datastreams inte stör en annan Content Analytics-konfiguration som är konfigurerad att använda samma sandlåda eller datastreams.
  >

* [Händelsefiltrering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Du kan redigera reguljära uttryck för att ändra hur du filtrerar sidor och resurser.


När du har gjort ändringar i Adobe Content Analytics-tillägget kontrollerar du att du använder [publiceringsflödet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} för att aktivera ändringarna.



>[!MORELIKETHIS]
>
>[Guidad konfiguration](guided.md)
>[Översikt över publicering av datainsamlingstaggar ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versioner

Om du behöver versionshantering av dina Content Analytics-upplevelser måste du lägga till en global `adobe.getContentExperienceVersion`-funktion på de sidor som du betraktar som upplevelser som du vill analysera.

Funktionen `adobe.getContentExperienceVersion` ska returnera en sträng som värde, vilket kan vara vad du än väljer för att identifiera versionen. Versionen läggs till i Experience ID-URL:en.

Om funktionen inte finns eller om inget värde returneras från funktionen används värdet `NoVersion` som standard.

### Exempel

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
