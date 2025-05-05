---
title: IP-adresser som används av Customer Journey Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe använder du den här listan för att uppdatera brandväggsinställningarna.
solution: Customer Journey Analytics
feature: Basics
exl-id: 5c52986c-7ff3-45b5-9039-2bfb6529238c
role: Admin
source-git-commit: 0e4ea634a604a65484a57f5af8021badb86a865a
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# IP-adresser som används av Customer Journey Analytics

Vissa brandväggskonfigurationer blockerar IP-adresser som kommer från Adobe datainsamlingsservrar eller servrar som är ansvariga för dataåtkomst. Du kan använda den här listan med intervall för att ändra organisationens brandväggsinställningar så att åtkomst tillåts och data skickas inifrån organisationen.

Den här sidan innehåller IP-adresser som du måste lägga till i tillåtelselista för att utgående system ska fungera, till exempel [exportera data till en molnleverantör](/help/analysis-workspace/export/export-cloud.md).

>[!IMPORTANT]
>
>Även om Adobe gör sitt bästa för att hålla det här dokumentet aktuellt kan det inte garantera att listan med IP-intervall är densamma. Möjliga förändringar är bland annat tillväxt och expansion av verksamheten, ett Internetregister kräver ändringar av Adobe IP-adressutrymme eller att en Internetleverantör slutar fungera.

## Kunder i USA och Amerika

| IP-block (CIDR-notation) |
| --- |
| `52.254.106.192/28` |
| `52.254.107.80/28` |
| `52.254.106.240/28` |
| `52.254.107.32/28` |
| `52.254.106.176/28` |
| `52.254.106.144/28` |
| `52.254.107.64/28` |
| `20.186.185.181` |
| `20.186.185.239` |
| `52.254.106.160/28` |
| `40.70.154.136/29` |
| `20.22.83.112` |
| `52.254.107.16/28` |
| `52.254.105.192/28` |
| `52.254.107.144/28` |
| `52.254.106.0/28` |
| `52.254.106.224/28` |
| `52.254.107.128/28` |
| `52.254.106.208/28` |
| `20.186.185.227` |
| `52.254.107.0/28` |
| `66.117.18.0/24` |

## Europa

| IP-block (CIDR-notation) |
| --- |
| `40.74.6.128/28` |
| `51.144.184.248/29` |
| `40.74.7.192/28` |
| `40.74.7.128/28` |
| `40.74.7.176/28` |
| `20.50.23.153` |
| `40.74.6.80/28` |
| `40.74.6.144/28` |
| `40.74.5.128/28` |
| `51.105.144.1` |
| `51.105.144.81` |
| `40.74.4.176/28` |
| `52.142.236.87` |
| `40.74.4.144/28` |
| `20.101.246.9` |
| `40.74.4.160/28` |
| `40.74.7.160/28` |
| `40.74.7.144/28` |
| `40.74.3.176/28` |
| `51.124.70.4` |
| `40.74.6.96/28` |
| `40.74.7.208/28` |
| `40.74.6.112/28` |

## Australien

| IP-block (CIDR-notation) |
| --- |
| `20.43.110.192/28` |
| `20.40.185.111` |
| `20.43.97.95` |
| `20.43.111.16/28` |
| `20.193.38.208/28` |
| `20.43.110.64/28` |
| `20.40.185.225` |
| `20.43.110.112/28` |
| `20.43.110.224/28` |
| `20.193.36.37` |
| `20.43.110.240/28` |
| `20.43.111.32/28` |
| `20.40.185.185` |
| `20.43.111.0/28` |
| `20.43.110.208/28` |
| `20.43.110.96/28` |
| `20.43.110.48/28` |
| `20.43.110.128/28` |
| `20.43.110.160/28` |
| `20.43.110.80/28` |
| `20.193.56.144/28` |
| `20.193.56.160/28` |
| `20.43.110.176/28` |
| `20.43.110.144/28` |
| `20.53.111.113` |
| `20.193.56.128/28` |
| `20.227.32.175` |

## Kanada

| IP-block (CIDR-notation) |
| --- |
| `20.116.159.80/28` |
| `20.116.159.224/28` |
| `20.116.159.192/28` |
| `20.116.159.64/28` |
| `20.151.241.173` |
| `20.116.159.128/28` |
| `20.116.159.208/28` |
| `20.116.159.48/28` |
| `20.151.240.247` |
| `20.116.159.0/28` |
| `20.220.243.238` |
| `20.116.175.240/28` |
| `20.116.155.128/28` |
| `20.116.248.0/28` |
| `20.151.241.138` |
| `20.116.159.144/28` |
| `20.116.175.224/28` |
| `20.116.248.16/28` |
| `20.151.241.124` |
| `20.116.159.160/28` |
| `20.116.159.96/28` |
| `20.104.5.248` |
| `20.116.159.112/28` |
| `20.116.159.176/28` |
| `20.116.159.32/28` |
| `20.116.158.240/28` |

>[!MORELIKETHIS]
>
>[Domäner som används av Customer Journey Analytics](domains.md)
>
>[IP-adresser som används av Adobe Experience Cloud](https://experienceleague.adobe.com/sv/docs/core-services/interface/data-collection/ip-addresses)