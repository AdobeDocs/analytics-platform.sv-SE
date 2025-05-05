---
title: Domäner som används av Customer Journey Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Domäner som används av Customer Journey Analytics

Vissa brandväggskonfigurationer blockerar domäner som Customer Journey Analytics använder för sitt produktgränssnitt. Du kan använda den här listan med domäner för att ändra organisationens nätverksinställningar och tillåta produktåtkomst inifrån organisationen. Adobe rekommenderar att du tillåter dessa domäner genom organisationens brandvägg för att få en optimal upplevelse.

| Teknik | Domän |
| --- | --- |
| Customer Journey Analytics domäner | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchMörkt | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud domäner

Förutom ovanstående domäner använder Adobe Experience Cloud flera domäner för datainsamling och export av rapporter. Se [Domäner som används av Adobe Experience Cloud](https://experienceleague.adobe.com/sv/docs/core-services/interface/data-collection/domains) för den här listan över domäner.

>[!MORELIKETHIS]
>
>[IP-adresser som används av Customer Journey Analytics](ip-addresses.md)
>
>[Domäner som används av Adobe Experience Cloud](https://experienceleague.adobe.com/sv/docs/core-services/interface/data-collection/domains)
