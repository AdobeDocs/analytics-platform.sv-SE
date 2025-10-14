---
title: Använd sammanfattningsdata i Customer Journey Analytics
description: Använd ett exempel som förklarar hur man överför sammanfattande data till Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 80139806-618a-46ff-b2c4-32d7bb85a526
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '4618'
ht-degree: 7%

---

# Använd sammanfattningsdata

Det här är ett exempel som hjälper dig att förstå hur du använder sammanfattningsdata i din rapportering och analys. I användningsexemplet beskrivs alla steg som krävs för att använda sammanfattningsdata i Customer Journey Analytics:

- [Infoga](#ingest) sammanfattningsdata och andra datakällor i Experience Platform.
- Konfigurera din [anslutning](#connection) för sammanfattningsdata och andra datakällor.
- Konfigurera [datavyn](#data-view) så att datakällorna kombineras.
- Rapportera och analysera i [Workspace](#workspace) på dina kombinerade data.

Användningsexemplet innehåller exempeldata för sammanfattningsdata, händelsedata och sökdata. Alla data innehåller slumpmässiga värden.

## Ingest

Du använder följande exempelsammanfattningsdata för det här användningsfallet och visar sammanfattningsdata för att köra kampanjer på Facebook.

+++Sammanfattningsdata

| _id | campaign_name | kostnad | intrycket | campaign_id | nätverk | ad_group | tidsstämpel |
|---|---|---:|---:|---|---|---|---|
| 1 | 123 Kampanj | 100 | 5000 | abc123 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 2 | 123 Kampanj | 50 | 4000 | def123 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 3 | 123 Kampanj | 125 | 6000 | ghi123 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 4 | 456 Campaign | 25 | 2500 | abc456 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 5 | 456 Campaign | 10 | 1000 | def456 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 6 | 456 Campaign | 115 | 5500 | ghi456 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 7 | 789 Campaign | 200 | 9000 | abc789 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 8 | 789 Campaign | 20 | 2000 | def789 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 9 | 789 Campaign | 225 | 12000 | ghi789 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 10 | 987 Campaign | 125 | 10000 | abc987 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 11 | 987 Campaign | 120 | 15000 | def987 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 12 | 987 Campaign | 315 | 22500 | ghi987 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 13 | 654 Campaign | 325 | 20000 | abc654 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 14 | 654 Campaign | 320 | 25000 | def654 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 15 | 654 Campaign | 315 | 22500 | ghi654 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 16 | 321 Kampanj | 25 | 2000 | abc321 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 17 | 321 Kampanj | 20 | 2500 | def321 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 18 | 321 Kampanj | 15 | 2250 | ghi321 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |

[![DataDownload](/help/assets/icons/DataDownload.svg)](./assets/summary-data.csv)

+++

Om du vill använda sammanfattningsdata i Customer Journey Analytics, i en rapport eller som en del av dataanalysen i Workspace behöver du

- ett sammanfattningsschema i Experience Platform
- en sammanfattning av datauppsättningen i Experience Platform,
- en anslutning i Customer Journey Analytics som är konfigurerad att använda sammanfattningsdatauppsättningen,
- en datavy i Customer Journey Analytics som är korrekt konfigurerad med mått och mått för sammanfattningsdata.

Du använder dessa sammanfattningsdata tillsammans med en datauppsättning för händelsedata och en datauppsättning för sökdata.

+++Händelsedata

Händelsedata är tillgängliga i exempeldatauppsättningen för händelser. Exempeldata ser ut så här:

| tidsstämpel | _id | page_name | person_id | tracking_code | order | intäkt_belopp |
|---|---:|---|---|---|---:|---:|
| 2024-07-18T19:15:39+00:00 | 1 | hemsida | person-1abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 2 | bekräftelsesida | person-1abc123 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 3 | hemsida | person-2def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 4 | hemsida | person-3ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 5 | bekräftelsesida | person-3ghi123 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 6 | hemsida | person-4abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 7 | hemsida | person-5def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 8 | hemsida | person-6ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 9 | bekräftelsesida | person-6ghi456 |  | 1 | 159,25 |
| 2024-07-18T19:15:39+00:00 | 10 | hemsida | person-7abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 11 | hemsida | person-8def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 12 | hemsida | person-9ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 13 | bekräftelsesida | person-9ghi789 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 14 | hemsida | person-10abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 15 | hemsida | person-11def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 16 | hemsida | person-12ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 17 | hemsida | person-13abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 18 | hemsida | person-14def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 19 | hemsida | person-15ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 20 | bekräftelsesida | person-15ghi654 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 21 | hemsida | person-16abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 22 | hemsida | person-17def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 23 | hemsida | person-18ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 24 | hemsida | person-19abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 25 | hemsida | person-20def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 26 | hemsida | person-21ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 27 | bekräftelsesida | person-21ghi123 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 28 | hemsida | person-22abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 29 | hemsida | person-23def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 30 | hemsida | person-24ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 31 | hemsida | person-25abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 32 | bekräftelsesida | person-25abc789 |  | 1 | 139,25 |
| 2024-07-18T19:15:39+00:00 | 33 | hemsida | person-26abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 34 | hemsida | person-27def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 35 | hemsida | person-28ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 36 | hemsida | person-29abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 37 | bekräftelsesida | person-29abc654 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 38 | hemsida | person-30def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 39 | hemsida | person-31ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 40 | hemsida | person-32abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 41 | hemsida | person-33ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 42 | bekräftelsesida | person-33ghi456 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 43 | hemsida | person-34abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 44 | hemsida | person-35def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 45 | hemsida | person-36ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 46 | bekräftelsesida | person-36ghi789 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 47 | hemsida | person-37abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 48 | hemsida | person-38def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 49 | hemsida | person-39ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 50 | hemsida | person-40abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 51 | bekräftelsesida | person-40abc654 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 52 | hemsida | person-41def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 53 | hemsida | person-42ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 54 | hemsida | person-43abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 55 | hemsida | person-44def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 56 | hemsida | person-45ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 57 | hemsida | person-46abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 58 | bekräftelsesida | person-46abc123 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 59 | hemsida | person-47def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 60 | hemsida | person-48ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 61 | hemsida | person-49abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 62 | hemsida | person-50def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 63 | hemsida | person-51ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 64 | hemsida | person-52abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 65 | bekräftelsesida | person-52abc789 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 66 | hemsida | person-53abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 67 | hemsida | person-54def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 68 | hemsida | person-55ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 69 | bekräftelsesida | person-55ghi987 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 70 | hemsida | person-56abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 71 | hemsida | person-57def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 72 | bekräftelsesida | person-57def123 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 73 | hemsida | person-58ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 74 | hemsida | person-59abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 75 | bekräftelsesida | person-59abc456 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 76 | hemsida | person-60def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 77 | hemsida | person-61ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 78 | hemsida | person-62abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 79 | bekräftelsesida | person-62abc789 |  | 1 | 159,25 |
| 2024-07-18T19:15:39+00:00 | 80 | hemsida | person-63def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 81 | hemsida | person-64ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 82 | hemsida | person-65abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 83 | bekräftelsesida | person-65abc987 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 84 | hemsida | person-66def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 85 | hemsida | person-67ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 86 | hemsida | person-68abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 87 | hemsida | person-69def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 88 | hemsida | person-70ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 89 | hemsida | person-71abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 90 | bekräftelsesida | person-71abc321 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 91 | hemsida | person-72def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 92 | hemsida | person-73ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 93 | hemsida | person-74abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 94 | hemsida | person-75def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 95 | hemsida | person-76ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 96 | hemsida | person-77abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 97 | bekräftelsesida | person-77abc456 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 98 | hemsida | person-78def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 99 | hemsida | person-79ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 100 | hemsida | person-80abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 101 | hemsida | person-81abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 102 | bekräftelsesida | person-81abc987 |  | 1 | 139,25 |
| 2024-07-18T19:15:39+00:00 | 103 | hemsida | person-82def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 104 | hemsida | person-83ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 105 | hemsida | person-84abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 106 | hemsida | person-85def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 107 | bekräftelsesida | person-85def654 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 108 | hemsida | person-86ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 109 | hemsida | person-87abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 110 | hemsida | person-88ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 111 | hemsida | person-89abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 112 | bekräftelsesida | person-89abc789 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 113 | hemsida | person-90def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 114 | hemsida | person-91ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 115 | hemsida | person-92abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 116 | bekräftelsesida | person-92abc987 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 117 | hemsida | person-93def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 118 | hemsida | person-94ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 119 | hemsida | person-95abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 120 | hemsida | person-96def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 121 | bekräftelsesida | person-96def654 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 122 | hemsida | person-97ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 123 | hemsida | person-98abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 124 | hemsida | person-99def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 125 | hemsida | person-100ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 126 | hemsida | person-101abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 127 | hemsida | person-102def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 128 | bekräftelsesida | person-102def123 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 129 | hemsida | person-103ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 130 | hemsida | person-104abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 131 | hemsida | person-105def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 132 | hemsida | person-106ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 133 | hemsida | person-107abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 134 | hemsida | person-108abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 135 | bekräftelsesida | person-108abc987 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 136 | hemsida | person-109def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 137 | hemsida | person-110ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 138 | bekräftelsesida | person-110ghi987 |  |  |  |
| 2024-07-18T19:15:39+00:00 | 139 | hemsida | person-111def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 140 | hemsida | person-112def987 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 141 | bekräftelsesida | person-112def987 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 142 | hemsida | person-113ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 143 | hemsida | person-114abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 144 | hemsida | person-115def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 145 | bekräftelsesida | person-115def654 |  | 1 | 159,25 |
| 2024-07-18T19:15:39+00:00 | 146 | hemsida | person-116ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 147 | hemsida | person-117abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 148 | hemsida | person-118def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 149 | bekräftelsesida | person-118def321 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 150 | hemsida | person-119ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 151 | hemsida | person-120abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 152 | hemsida | person-121def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 153 | hemsida | person-122ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 154 | hemsida | person-123abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 155 | hemsida | person-124def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 156 | bekräftelsesida | person-124def456 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 157 | hemsida | person-125ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 158 | hemsida | person-126abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 159 | hemsida | person-127abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 160 | hemsida | person-128def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 161 | hemsida | person-129ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 162 | hemsida | person-130abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 163 | bekräftelsesida | person-130abc654 |  | 1 | 149,25 |
| 2024-07-18T19:15:39+00:00 | 164 | hemsida | person-131def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 165 | hemsida | person-132ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 166 | hemsida | person-133abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 167 | hemsida | person-134ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 168 | bekräftelsesida | person-134ghi456 |  | 1 | 139,25 |
| 2024-07-18T19:15:39+00:00 | 169 | hemsida | person-135abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 170 | hemsida | person-136def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 171 | hemsida | person-137ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 172 | hemsida | person-138abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 173 | bekräftelsesida | person-138abc987 |  | 1 | 124,25 |
| 2024-07-18T19:15:39+00:00 | 174 | hemsida | person-139def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 175 | hemsida | person-140ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 176 | hemsida | person-141abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 177 | hemsida | person-142def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 178 | bekräftelsesida | person-142def654 |  | 1 | 174,25 |
| 2024-07-18T19:15:39+00:00 | 179 | hemsida | person-143ghi654 | ghi654 |  |  |

[![DataDownload](/help/assets/icons/DataDownload.svg)](./assets/event-data.csv)

+++

+++ Sökdata

Uppslagsdata är tillgängliga i datauppsättningen Example Lookup Data. Exempeldata ser ut så här:

| _id | tracking_code | ad_group | campaign_name |
|---|---|---|---|
| 1 | abc123 | abc-adgroup | 123 Kampanj |
| 2 | def123 | def-adgroup | 123 Kampanj |
| 3 | ghi123 | ghi-adgroup | 123 Kampanj |
| 4 | abc456 | abc-adgroup | 456 Campaign |
| 5 | def456 | def-adgroup | 456 Campaign |
| 6 | ghi456 | ghi-adgroup | 456 Campaign |
| 7 | abc789 | abc-adgroup | 789 Campaign |
| 8 | def789 | def-adgroup | 789 Campaign |
| 9 | ghi789 | ghi-adgroup | 789 Campaign |
| 10 | abc987 | abc-adgroup | 987 Campaign |
| 11 | def987 | def-adgroup | 987 Campaign |
| 12 | ghi987 | ghi-adgroup | 987 Campaign |
| 13 | abc654 | abc-adgroup | 654 Campaign |
| 14 | def654 | def-adgroup | 654 Campaign |
| 15 | ghi654 | ghi-adgroup | 654 Campaign |
| 16 | abc321 | abc-adgroup | 321 Kampanj |
| 17 | def321 | def-adgroup | 321 Kampanj |
| 18 | ghi321 | ghi-adgroup | 321 Kampanj |

[![DataDownload](/help/assets/icons/DataDownload.svg) Hämta exempelsökdata](./assets/lookup-data.csv)
+++

>[!INFO]
>
>Mer information om hur du ställer in scheman och datauppsättningar för händelse- och sökdata finns inte. Den här konfigurationen antas vara vanlig kunskap och följer samma steg som för sökdata.
>


### Sammanfattningsschema

Sammanfattningsdata behöver ett sammanfattningsschema i Experience Platform. Ett sammanfattningsschema är ett schema som använder XDM Summary Metrics som basklass.

Så här skapar du ett sammanfattningsschema i Experience Platform:

1. Välj **[!UICONTROL Experience Platform]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Schemas]** i den vänstra listen.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create schema]**.
1. Välj **[!UICONTROL Manual]** i dialogrutan **[!UICONTROL Create a schema]**. Använd sedan **[!UICONTROL Select]** för att fortsätta.
1. I **[!UICONTROL Select a class]**-steget i guiden **[!UICONTROL Schemas]** > **[!UICONTROL Create schema]** väljer du **[!UICONTROL Other]** bland **[!UICONTROL Select a base class for this schema]**-alternativen.
1. I listan väljer du **[!UICONTROL XDM Summary Metrics]** (eller använd fältet ![Sök](/help/assets/icons/Search.svg) för att söka efter) och väljer **[!UICONTROL Next]**.
1. I steget **[!UICONTROL Name and review]** i guiden **[!UICONTROL Schemas]** > **[!UICONTROL Create schema]** anger du en **[!UICONTROL Schema display name]**, till exempel `Example Summary Data Schema`, och en valfri beskrivning. Välj **[!UICONTROL Finish]** för att slutföra det här steget.

Strukturen för ditt grundläggande sammanfattningsschema visas, redo att utökas med fälten för dina sammanfattningsdata. Du lägger till fält i ett schema med fältgrupper.

Så här lägger du till en fältgrupp som innehåller fälten för exempeldata:

1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** i **[!UICONTROL Field groups]**.
1. Välj **[!UICONTROL Create new field group]** i dialogrutan **[!UICONTROL Add field groups]**.
1. Ange **[!UICONTROL Display name]** som fältgrupp, till exempel `Example Summary Data`. Ange en beskrivning om du vill.
1. Välj **[!UICONTROL Add field groups]**.
1. Du är tillbaka i schemastrukturens användargränssnitt. Välj nya **[!UICONTROL Example Summary Data]** i **[!UICONTROL Field groups]**.
1. Markera ![AddCircle](/help/assets/icons/AddCircle.svg) bredvid schemanamnet **[!UICONTROL Example summary Data Schema]**. En **[!UICONTROL Field properties]**-panel öppnas där du kan lägga till information för ett fält.
   1. Ange en **[!UICONTROL Field name]**: `campaign_id`
   1. Ange en **[!UICONTROL Display name]**: `campaign_id`
   1. Välj en **[!UICONTROL Type]** i listrutan **[!UICONTROL Select data type]**: **[!UICONTROL String]**
   1. Kontrollera att **[!UICONTROL Assign to]** **[!UICONTROL Field group]** är markerat och välj **[!UICONTROL Example Summary Data]** i listrutan.
   1. Bläddra nedåt och välj **[!UICONTROL Apply]**.
1. Upprepa föregående steg för de andra fälten i sammanfattningsdata. Se tabellen nedan för rätt värden.

   | Fältnamn | Visningsnamn | Typ | Fältgrupp |
   |---|---|---|---|
   | `ad_group` | `ad_group` | Sträng | Exempel på sammanfattningsdata |
   | `campaign_name` | `campaign_name` | Sträng | Exempel på sammanfattningsdata |
   | `cost` | `cost` | Dubbel | Exempel på sammanfattningsdata |
   | `impression` | `impression` | Heltal | Exempel på sammanfattningsdata |
   | `network` | `network` | Sträng | Exempel på sammanfattningsdata |

1. Om du vill spara fältgruppen **[!UICONTROL Example Summary Data]** som en del av ditt schema väljer du **[!UICONTROL Save]**. En bekräftelse visas när schemat har sparats.

Du har nu definierat ett schema som detaljerar modellen för dina sammanfattningsdata. Liknar den nedan.

![Exempelschema för sammanfattningsdata](../assets/example-summary-schema.png)





### Sammanfattningsdatauppsättning

Om du vill lagra sammanfattningsdata i Experience Platform måste du först skapa en datauppsättning och sedan överföra sammanfattningsdata till datauppsättningen.

Så här skapar du en datauppsättning:

1. Välj **[!UICONTROL Experience Platform]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Datasets]** i den vänstra listen.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create dataset]**.
1. Välj **[!UICONTROL Create dataset from schema]** på skärmen **[!UICONTROL Datasets]** > **[!UICONTROL Create datasets]**.
1. I **[!UICONTROL Select schema]**-steget i guiden **[!UICONTROL Workflows]** > **[!UICONTROL Create dataset from schema]** söker ![&#x200B; efter och väljer &#x200B;](/help/assets/icons/Search.svg).**[!UICONTROL Example Summary Data Schema]**
1. Välj **[!UICONTROL Next]**.
1. I steget **[!UICONTROL Configure dataset]** i guiden **[!UICONTROL Workflows]** > **[!UICONTROL Create dataset from schema]**:
   1. Ange **[!UICONTROL Name]** som datamängd, till exempel: `Example Summary Data Dataset`. Ange en beskrivning om du vill.
   1. Välj **[!UICONTROL Finish]**.

En skärm med information om din nya datauppsättning visas.

Så här överför du exempeldata till den här datauppsättningen:

1. Välj **[!UICONTROL Experience Platform]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Workflows]** i den vänstra listen.
   1. Välj **[!UICONTROL Map CSV to XDM schema]** bland **[!UICONTROL Data ingestion]**-alternativen på skärmen **[!UICONTROL Workflows]**.
   1. Välj **[!UICONTROL Launch]** på panelen **[!UICONTROL Map CSV to XDM schema]**.
1. I steget **[!UICONTROL Dataflow detail]** i guiden **[!UICONTROL Workflows]** > **[!UICONTROL Map CSV to XDM schema]**:
   1. Välj **[!UICONTROL Existing dataset]** för **[!UICONTROL Target dataset]**.
   1. Välj **[!UICONTROL Example Summary Data Dataset]** i listrutan.
   1. Välj **[!UICONTROL Next]**.
1. I steget **[!UICONTROL Select data]** i guiden **[!UICONTROL Workflows]** > **[!UICONTROL Map CSV to XDM schema]**:
   1. Dra och släpp filen med sammanfattningsdata i CSV-format till **[!UICONTROL Drag and drop files]**. Du kan också använda **[!UICONTROL Choose files]** för att välja filen.
   1. Kontrollera att **[!UICONTROL Data format]** och **[!UICONTROL Delimiter]** har rätt värden för dina exempeldata. Till exempel **[!UICONTROL Delimited]** som **[!UICONTROL Data format]** och **[!UICONTROL ,]** som **[!UICONTROL Delimiter]**.
   1. Ett exempel (10 poster) på dina sammanfattningsdata visas i **[!UICONTROL Sample data]**.
   1. Välj **[!UICONTROL Next]**.
1. I steget **[!UICONTROL Mapping]** i guiden **[!UICONTROL Workflows]** > **[!UICONTROL Map CSV to XDM schema]**:
   ![Exempeldatamängdsmappning](../assets/example-dataset-mapping.png)
   1. Kontrollera om alla datafält i **[!UICONTROL Source Data]** är korrekt mappade till motsvarande **[!UICONTROL Target fields]** i ditt schema. För exempeldata rapporteras inga fel eftersom du uttryckligen namngav fälten i ditt schema som liknar fältnamnen i dina exempeldata. I annat fall kan du använda den här skärmen för att korrigera mappningen.
   1. Du kan välja ![Kugghjul](/help/assets/icons/Gear.svg) **[!UICONTROL Validate]** om du vill validera data (en gång till).
   1. Du kan också välja ![Förhandsgranska](/help/assets/icons/Preview.svg) **[!UICONTROL Preview data]** om du vill öppna en dialogruta med en förhandsgranskning av data som har lästs in i datauppsättningen.
   1. Välj **[!UICONTROL Finish]**.

I **[!UICONTROL Sources]** > **[!UICONTROL Dataflow - XX/XX/XXXX, XX:XX XX]** visas status för din överföring. Uppdatera för att se uppdateringar av överföringen. När det är klart läses dina exempeldata in i Experience Platform.




## Anslutning

Om du vill använda exempeldata i Customer Journey Analytics skapar du en anslutning som innehåller datauppsättningen Exempelsammanfattning från Experience Platform.


1. Välj **[!UICONTROL Customer Journey Analytics]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj **[!UICONTROL Create new connection]**.
1. I **[!UICONTROL Connections]** > **[!UICONTROL Untitled connection]**:
   1. Ange en **[!UICONTROL Connection name]**, till exempel `Example Connection Using Summary Data`.
   1. Markera sandlådan som innehåller den datauppsättning som du skapade och de andra datauppsättningar som du vill ta med i listrutan Sandbox.
   1. Välj **[!UICONTROL less than 1 million]** i listrutan **[!UICONTROL Average number of daily events]**.
   1. Välj **[!UICONTROL Add datasets]**.
   1. I steget **[!UICONTROL Select datasets]** i guiden **[!UICONTROL Add datasets]**:
      1. Sök i ![Sök](/help/assets/icons/Search.svg) och välj **[!UICONTROL Example Summary Data Dataset]**, **[!UICONTROL Example Event Data Dataset]** och **[!UICONTROL Example Lookup Data Dataset]**.
      1. Välj **[!UICONTROL Next]**.
   1. I steget **[!UICONTROL Datasets settings]** i guiden **[!UICONTROL Add datasets]**:

      1. För **[!UICONTROL Example Event Data Dataset]**:

         1. Bekräfta att markeringarna för **[!UICONTROL Person ID]** (`person_id`) och **[!UICONTROL Timestamp]** är korrekta.
         1. Välj **[!UICONTROL Web Data]** från **[!UICONTROL Data source type]**.
         1. Aktivera **[!UICONTROL Import all new data]**.
         1. Aktivera **[!UICONTROL Backfill all existing data]**.

      1. För **[!UICONTROL Example Lookup Data Dataset]**:

         1. Välj **[!UICONTROL tracking_code]** som **[!UICONTROL Key]** och **[!UICONTROL tracking_code (Event datasets)]** som **[!UICONTROL Matching]**-nyckel.
         1. Välj **[!UICONTROL Web Data]** från **[!UICONTROL Data source type]**.
         1. Aktivera **[!UICONTROL Import all new data]**.
         1. Aktivera **[!UICONTROL Backfill all existing data]**.

      1. För **[!UICONTROL Example Summary Data Dataset]**:

         1. Bekräfta att markeringarna för **[!UICONTROL Timestamp]** och **[!UICONTROL Timezone]** är korrekta.
         1. Aktivera **[!UICONTROL Import all new data]**.
         1. Aktivera **[!UICONTROL Backfill all existing data]**.

      1. Välj **[!UICONTROL Add datasets]**.

1. Välj **[!UICONTROL Save]** på anslutningsskärmen **[!UICONTROL Connections]** > **[!UICONTROL Example Connection using Summary Data]** för att spara anslutningen.

Data från datauppsättningarna läggs till i Customer Journey Analytics, som kan ta några timmar. Var tålmodig innan du fortsätter.

Efter en stund kontrollerar du att data från datauppsättningarna har lästs in korrekt i Customer Journey Analytics.

1. Välj **[!UICONTROL Customer Journey Analytics]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj din anslutning, till exempel **[!UICONTROL Example Connection Using Summary Data]**.
1. Välj ett lämpligt datumintervall i informationen för **[!UICONTROL Connection]** > **[!UICONTROL Example Connection Using Summary data]**.
   1. Välj ![Kalender](/help/assets/icons/Calendar.svg) och sedan **[!UICONTROL Last 7 days]**.
   1. Välj **[!UICONTROL Apply]**.

I listan med **[!UICONTROL Datasets]** bör värdena i kolumnen **[!UICONTROL Records added]** bekräfta att data från dina datauppsättningar nu är en del av Customer Journey Analytics.

![Exempelanslutning för sammanfattningsdata](../assets/example-connection-summary-data.png)

## Datavy

För att vara säker på att du kan rapportera rätt data i Workspace vill du skapa en datavy med relevanta mått och mått.

1. Välj **[!UICONTROL Customer Journey Analytics]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Data views]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj **[!UICONTROL Create new data view]**.
1. Gå igenom guideskärmarna i **[!UICONTROL Data views]** för att konfigurera datavyn.
   1. I **[!UICONTROL Configure]**-steget i **[!UICONTROL Data views]**:
      1. Välj din anslutning från **[!UICONTROL Settings]** | **[!UICONTROL Connection]**. Exempel: **[!UICONTROL Example Connection Using Summary Data]**.
      1. Ange **[!UICONTROL Name]** som datavy, till exempel `Example Data View Using Summary Data`.
      1. Lämna alla andra inställningar.
      1. Välj **[!UICONTROL Save and continue]**.
   1. I **[!UICONTROL Components]**-steget av **[!UICONTROL Data views]** > **[!UICONTROL Example Data View Using Summary Data]**:
      1. Lägg till följande komponenter i Dimensions- och Metrics-listan. Observera att komponentnamnen av tydlighetsskäl ändras från standardnamnet, med **[!UICONTROL Component name]** i **[!UICONTROL Component settings]** på komponentpanelen (till höger).

         **Mätvärden**

         | Komponentnamn | Datauppsättning | Datatypen Schema | Schemasökväg |
         |---|---|---|---|
         | Kostnad | Exempeldatamängd för sammanfattningsdata | Dubbel | *_tenant*.cost |
         | Impressions | Exempeldatamängd för sammanfattningsdata | Heltal | *_tenant*.intryckt |
         | Beställningar | Exempel på händelsedatamängd | Heltal | *_tenant*.orders |
         | Intäkter | Exempel på händelsedatamängd | Dubbel | *_tenant*.intäkt_belopp |

         **Dimensioner**

         | Komponentnamn | Datauppsättning | Datatypen Schema | Schemasökväg |
         |---|---|---|---|
         | Annonsgrupp (sökning) | Exempel på datauppsättning för sökning | Sträng | *_tenant*.ad_group |
         | Annonsgrupp (sammanfattning) | Exempeldatamängd för sammanfattningsdata | Sträng | *_tenant*.ad_group |
         | Kampanj-ID | Exempeldatamängd för sammanfattningsdata | Sträng | *_tenant*.campaign_id |
         | Kampanjnamn (sökning) | Exempel på datauppsättning för sökning | Sträng | *_tenant*.campaign_name |
         | Kampanjnamn (sammanfattning) | Exempeldatamängd för sammanfattningsdata | Sträng | *_tenant*.campaign_name |
         | Nätverk | Exempeldatamängd för sammanfattningsdata | Sträng | *_tenant*.network |
         | Sidnamn | Exempel på händelsedatamängd | Sträng | *_tenant*.page_name |
         | Person-ID | Exempel på händelsedatamängd | Sträng | *_tenant*.person_id |
         | Spårningskod (händelse) | Exempel på händelsedatamängd | Sträng | *_tenant*.tracking_code |
         | Spårningskod (sökning) | Exempel på datauppsättning för sökning | Sträng | *_tenant*.tracking_code |

      1. Välj dimensionen **[!UICONTROL Tracking Code (Event)]** i listan **[!UICONTROL Dimensions]**. I komponentpanelen:

         ![Kodsammanfattningsdata för spårning](../assets/tracking-code-summary-data.png)
         1. Gräv upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary Data Group]**.
         1. Aktivera **[!UICONTROL Create grouping]**.
         1. Välj **[!UICONTROL Campaign Id]** i listrutan **[!UICONTROL Dimension]**. Detta steg säkerställer att händelsedata och sammanfattningsdata kombineras korrekt för rapportering.
         1. Du kan även aktivera **[!UICONTROL Hide in reporting]**. [!UICONTROL Hide in reporting] säkerställer att den valda dimensionen ([!UICONTROL Campaign Id]) döljs i Analysis Workspace och andra rapportverktyg från Customer Journey Analytics. Om du har aktiverat det här alternativet kan du verifiera alternativet:
            1. Välj dimensionen **[!UICONTROL Campaign Id]** i listan **[!UICONTROL Dimensions]**.
            1. Du ser att **[!UICONTROL Hide component in reporting]** i **[!UICONTROL Component settings]** nu är automatiskt aktiverat.

      1. Skapa ett nytt härlett fält, till exempel `Campaign Name (Lookup Derived Field)`, för att säkerställa att du kan rapportera i Workspace med hjälp av dimensionen Campaign Name (Lookup) i datauppsättningen Example Lookup.

         ![Härlett fält för kampanjnamn](../aa-data/../assets/summary-derived-field.png)

         1. Välj **[!UICONTROL campaign_id]** för **[!UICONTROL Value]**.
         1. Välj **[!UICONTROL Example Lookup Data Dataset]** i listrutan **[!UICONTROL Lookup dataset]**.
         1. Välj **[!UICONTROL tracking_code]** i listrutan **[!UICONTROL Matching Key]**.
         1. Välj **[!UICONTROL campaign_name]** i listrutan **[!UICONTROL Values to return]**.
         1. Välj **[!UICONTROL Save]**.

      1. Lägg till det nyskapade härledda fältet, **[!UICONTROL Campaign Name (Lookup Derived Field)]**, i komponentlistan för **[!UICONTROL Dimensions]**.

      1. Välj dimensionen **[!UICONTROL Campaign Name (Lookup)]** i listan **[!UICONTROL Dimensions]**. I komponentpanelen:

         ![Datagrupp för härledd fältsammanfattning](../assets/derived-field-summary-data-group.png)

         1. Gräv upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary Data Group]**.
         1. Aktivera **[!UICONTROL Create grouping]**.
         1. Välj **[!UICONTROL Campaign Name (Lookup Derived Field)]** i listrutan **[!UICONTROL Dimension]**. Detta steg säkerställer att kampanjnamnet (Sök efter) från datauppsättningen Example Lookup kan användas på ett säkert sätt vid rapportering (se [Workspace](#workspace)).

      1. Välj måttet **[!UICONTROL Revenue]** i listan **[!UICONTROL Metrics]**. I komponentpanelen:

         ![Sammanfattningsdata för intäkter](../assets/revenue-summary-data.png)
         1. Gräv upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Attribution]**.
            1. Välj ![AttributeLastTouch](/help/assets/icons/AttributeLastTouch.svg) **[!UICONTROL Last Touch]** i listrutan **[!UICONTROL Attribution Model]**.
            1. Välj **[!UICONTROL 30 Day]** i listrutan **[!UICONTROL Lookback window]**.
         1. Bygg upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **Format**.
            1. Välj **[!UICONTROL Currency]** i listrutan **[!UICONTROL Format]**.
            1. Välj **[!UICONTROL 2]** i listrutan **[!UICONTROL Decimal places]**.

      1. Välj måttet **[!UICONTROL Orders]** i listan **[!UICONTROL Metrics]**. I komponentpanelen:

         ![Sammanfattningsdata för beställningar](../assets/orders-summary-data.png)
         1. Gräv upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Attribution]**.
            1. Välj ![AttributeLastTouch](/help/assets/icons/AttributeLastTouch.svg) **[!UICONTROL Last Touch]** i listrutan **[!UICONTROL Attribution Model]**.
            1. Välj **[!UICONTROL 30 Day]** i listrutan **[!UICONTROL Lookback window]**.
         1. Gräv upp ![SparronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Format]**.
            1. Välj **[!UICONTROL Decimal]** i listrutan **[!UICONTROL Format]**.
            1. Välj **[!UICONTROL ▲ Good (green)]** i listrutan **[!UICONTROL Show upward trend as]**.

      1. Välj **[!UICONTROL Save and continue]**.

   1. I **[!UICONTROL Settings]**-steget i **[!UICONTROL Data views]**:
      1. Lämna alla inställningar som de är.
      1. Välj **[!UICONTROL Save and finish.]**

Du har nu konfigurerat datavyn för korrekt rapportering av sammanfattningsdata.


## Workspace

Skapa ett nytt projekt i Analysis Workspace om du vill rapportera sammanfattningsdata.

1. Välj **[!UICONTROL Customer Journey Analytics]** på menyn   ![&#x200B; App &#x200B;](/help/assets/icons/Apps.svg)   appväxlare.
1. Välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj **[!UICONTROL Create project]**.
1. Välj **[!UICONTROL Blank Workspace project]** i dialogrutan med alternativ för att skapa ett tomt Workspace-projekt.
1. Välj **[!UICONTROL Create]**.

Du ser en tom arbetsyta med en [!UICONTROL Freeform]-panel, som består av en tom [!UICONTROL Freeform table].

1. Se till att datavyn som valts för panelen refererar till datavyn som innehåller konfigurationen för sammanfattningsdata. Exempel: **[!UICONTROL Example Data View Using Summary Data.]**
1. Kontrollera att datumintervallet är giltigt för de data som du vill rapportera om. Till exempel: **[!UICONTROL Last 2 full months]**.
1. Dra **[!UICONTROL Tracking Code (Event)]** från **[!UICONTROL Dimensions]** och släpp dimensionen i den tomma friformstabellen.
1. Dra **[!UICONTROL Orders]** från **[!UICONTROL Metrics]** och släpp måttet i kolumnen **[!UICONTROL Events]** för att ersätta den kolumnen i friformstabellen.
1. Dra **[!UICONTROL Revenue]** från **[!UICONTROL Metrics]** och släpp måttet för att lägga till det som en extra kolumn i friformstabellen.
1. Dra **[!UICONTROL Impressions (Summary)]** från **[!UICONTROL Metrics]** och släpp måttet för att lägga till det som en extra kolumn i friformstabellen.
1. Dra **[!UICONTROL Cost (Summary)]** från **[!UICONTROL Metrics]** och släpp måttet för att lägga till det som en extra kolumn i friformstabellen.
1. Om du vill spara projektet väljer du **[!UICONTROL Project]** > **[!UICONTROL Save]** och anger ett namn för projektet. Exempel: `Example Project Using Summary Data`.

Du vill använda kraften i att rapportera sammanfattningsdata och rapportera om kostnad per intryck och avkastning på annonskostnaderna. Om du vill rapportera dessa mått måste du skapa två beräknade värden.

1. Välj **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** om du vill lägga till ett nytt beräknat mått.
   1. Ange `Cost per Impression` för **[!UICONTROL Name]**.
   1. Välj **[!UICONTROL Currency]** för **[!UICONTROL Format]**.
   1. Ange `4` för **[!UICONTROL Decimal places]**.
   1. Använd ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Cost (Summary)]** **[!UICONTROL ÷]** **[!UICONTROL Impressions (Summary)]** som **[!UICONTROL Definition]**.
   1. Välj **[!UICONTROL Save]**.
1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** om du vill lägga till ett nytt beräknat mått.
   1. Ange `Return on Ad Spend` för **[!UICONTROL Name]**.
   1. Välj **[!UICONTROL Currency]** för **[!UICONTROL Format]**.
   1. Välj `2` för **[!UICONTROL Decimal places]**.
   1. Använd ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Revenue (Last Touch | 30 Days)]** **[!UICONTROL −]** ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Cost (Summary)]** som **[!UICONTROL Definition]**.
   1. Välj **[!UICONTROL Save]**.

Lägg till dina beräknade värden i rapporten.

1. Dra **[!UICONTROL Cost per Impression]** ![Beräkna](/help/assets/icons/Calculator.svg) från **[!UICONTROL Metrics]** och släpp måttet för att lägga till det som en extra kolumn i friformstabellen.
   1. Välj ![Ange &#x200B;](/help/assets/icons/Setting.svg) kolumninställningar.
      1. Inaktivera **[!UICONTROL Percent]**.
1. Dra **[!UICONTROL Return on Ad Spend]** ![Beräkna](/help/assets/icons/Calculator.svg) från **[!UICONTROL Metrics]** och släpp måttet för att lägga till det som en extra kolumn i friformstabellen.
   1. Välj ![Ange &#x200B;](/help/assets/icons/Setting.svg) kolumninställningar.
      1. Inaktivera **[!UICONTROL Percent]**.
      1. Aktivera **[!UICONTROL Conditional formatting]**.
         1. Välj **[!UICONTROL Auto-generated]**.
         1. Välj önskad **[!UICONTROL Conditional formatting palette]**.
   1. Välj **[!UICONTROL Save]** om du vill spara projektet.

Om du vill rapportera kampanjnamn i stället för spårningskod (Event) gör du så här:

1. Duplicera visualiseringen av friformstabellen **[!UICONTROL Summary Data Report]**.
1. Byt namn på den duplicerade visualiseringen till `Summary Data Report (using Campaign Name)`.
1. Ersätt ![Växla](/help/assets/icons/Switch.svg) dimensionen **[!UICONTROL Tracking Code (Event)]** med dimensionen **[!UICONTROL Campaign Name (Lookup)]**.

Du kan rapportera korrekt om kampanjnamn (sökning) på grund av det härledda fältet som du skapade och den sammanfattande datakomponentkonfigurationen för kampanjnamn (sökning). Se [Datavy](#data-view).

Det färdiga projektet ska se ut som det som visas nedan.

![Exempelprojekt med sammanfattningsdata, med sammanfattningsdatapanelen och sammanfattningsdatarapport](../assets/summary-workspace.png)


>[!MORELIKETHIS]
>
>[Sammanfattningsdata](/help/data-views/summary-data.md)
>[Komponentinställningar för sammanfattningsdatagrupp &#x200B;](/help/data-views/component-settings/summary-data-group.md)
