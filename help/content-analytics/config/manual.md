---
title: Manuell konfiguration av Content Analytics
description: Konfigurera Content Analytics manuellt
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# Manuell konfiguration av Content Analytics

I den här artikeln beskrivs de manuella åtgärder som krävs för att starta eller stoppa datainsamlingen i en Content Analytics-konfiguration eller för att redigera din Content Analytics-implementering.

Följande manuella konfigurationsåtgärder är tillgängliga:

## Starta datainsamling

Så här startar du datainsamlingen för en implementerad Content Analytics-konfiguration:

1. Följ [publiceringsflödet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Biblioteket för taggegenskapen som innehåller din Content Analytics-konfiguration har publicerats.

1. [Installera](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) den inbäddade koden i elementet `<head>` på sidorna i din utvecklings-, staging- eller publiceringsmiljö, enligt Content Analytics.


## Stoppa datainsamling

Så här stoppar du datainsamlingen för en implementerad Content Analytics-konfiguration:

1. Ta bort den [inbäddade koden](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) i `<head>`-elementet för sidorna i din utvecklings-, staging- eller produktionsmiljö, som omfattas av Content Analytics.
1. [Ta bort](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) den associerade taggegenskapen för din Content Analytics-konfiguration.



## Ändra datainsamling

Du kan göra några mindre ändringar i en implementerad konfiguration med hjälp av [guiden för guidad konfiguration](guided.md). Du kan till exempel ändra datavyn eller aktivera eller inaktivera upplevelser.

Du använder [Adobe Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) i taggegenskapen som är kopplad till din Content Analytics-konfiguration för att göra ändringar i följande artefakter:

* [Sandbox och datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Kontrollera att den sandlåda och datastam som du konfigurerar i Adobe Content Analytics-tillägget redan har konfigurerats för Content Analytics med den [guidade konfigurationen](guided.md) i ett tidigare skede. Den här konfigurationen ser till att alla nödvändiga artefakter är tillgängliga.<br/><br/>Verifiera också att uppdateringar för sandbox eller datastreams inte stör en annan Content Analytics-konfiguration som är konfigurerad att använda samma sandlåda eller datastreams.
  >

* [Upplevelsehämtning och definition](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Du kan aktivera eller inaktivera upplevelser och redigera kombinationer av reguljära uttryck och frågeparametrar för att avgöra hur innehåll återges på webbplatsen.

* [Händelsesegmentering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Du kan redigera reguljära uttryck för att ändra hur du segmenterar sidor och resurser.


När du har gjort ändringar i Adobe Content Analytics-tillägget kontrollerar du att du använder [publiceringsflödet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} för att starta datainsamlingen baserat på de ändringar du har gjort.



>[!MORELIKETHIS]
>
>[Guidad konfiguration](guided.md)
>>[Översikt över publicering av datainsamlingstaggar ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versioner

Om du vill samla in Content Analytics-upplevelser bör du överväga att implementera versionshantering för att säkerställa att nya upplevelser (ändringar på din webbsida) samlas in på rätt sätt.

Om du vill implementera versionshantering lägger du till en global `adobe.getContentExperienceVersion`-funktion på sidorna som du anser att upplevelser som du vill analysera ska analyseras.

Funktionen `adobe.getContentExperienceVersion` ska returnera en sträng som värde, vilket kan vara vad du vill för att identifiera versionen. Versionen har lagts till i URL:en för [upplevelse-ID](/help/content-analytics/report/components.md#experience-metadata).

Om funktionen inte finns eller om inget värde returneras från funktionen används värdet `NoVersion` som standard.

### Exempel

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

## Identiteter

Content Analytics hanterar identiteter på följande sätt:

* ECID fylls i automatiskt i `identityMap`-delen av Content Analytics-schemat.
* Om du behöver andra identitetsvärden i `identityMap` måste du ange dessa värden i `onBeforeEventSend`-återanropet i Web SDK-tillägget.
* Fältbaserad sammanfogning stöds inte eftersom schemat ägs av systemet. Du kan alltså inte lägga till ett annat fält i schemat som stöd för fältbaserad sammanslagning


För att Content Analytics identitetsdata och Adobe Experience Platform Web SDK-datatidentitetsdata ska sammanfogas korrekt på fältnivå måste du göra ändringar i Web SDK [on innan ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"}-återanrop skickas.

1. Navigera till egenskapen **[!UICONTROL Tags]** som innehåller Adobe Experience Platform Web SDK-tillägget och Adobe Content Analytics-tillägget.
1. Välj ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]**.
1. Välj tillägget **[!UICONTROL Adobe Experience Platform Web SDK]**.
1. Välj **[!UICONTROL Configure]**.
1. I avsnittet **[!UICONTROL SDK instances]** rullar du nedåt till **[!UICONTROL Data collection]** - **[!UICONTROL On before event send callback]**.

   ![På före händelsens skicka återanrop](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Välj **[!UICONTROL </> Provide on before event send callback code]**.
1. Lägg till följande kod:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![På före händelsens skicka återanrop](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Välj **[!UICONTROL Save]** om du vill spara koden.
1. Välj **[!UICONTROL Save]** om du vill spara tillägget.
1. [Publicera](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) uppdateringarna för taggegenskapen.





