---
title: Skapa och publicera målgrupper i kundprofilen i realtid
description: Lär dig hur du publicerar målgrupper från Customer Journey Analytics
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Skapa och publicera målgrupper

I det här avsnittet beskrivs hur du publicerar målgrupper som identifierats i Customer Journey Analytics (CJA) till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) i Adobe Experience Platform för kundanpassning och personalisering.

## Skapa målgrupper

1. Du kan skapa målgrupper på tre sätt:

   | Skapandemetod | Detaljer |
   | --- | --- |
   | Från **[!UICONTROL Components]>[!UICONTROL Audiences]** | Sidan Audiences Manager öppnas. Klicka **[!UICONTROL Create audience]** och [!UICONTROL Audience builder] öppnas. |
   | Från en friformstabell | Högerklicka på ett objekt i en frihandstabell och välj **[!UICONTROL Create an audience from selection]**. Om du använder den här metoden fylls filtret i automatiskt med den dimension eller dimensionspost som du valde i tabellen. |
   | Från filterredigeringsgränssnittet | Markera rutan som innehåller **[!UICONTROL Create an audience from this filter]**. Om du använder den här metoden fylls filtret i automatiskt. |

   {style=&quot;table-layout:auto&quot;}

1. Konfigurera målgruppen.

   | Inställning | Beskrivning |
   | --- | --- |
   | [!UICONTROL Name] | Publiken. |
   | [!UICONTROL Tags] | Alla taggar som du vill ska tilldelas till målgruppen för organisatoriska ändamål. Du kan använda en befintlig tagg eller ange en ny. |
   | [!UICONTROL Description] | Lägg till en bra beskrivning av målgruppen för att skilja den från andra. |
   | [!UICONTROL Refresh frequency] | Hur ofta du vill uppdatera publiken.<ul><li>Du kan välja att skapa en engångskarp målgrupp (standard) som inte behöver uppdateras, vilket kan vara praktiskt för specifika engångskampanjer.</li><li>Du kan välja andra uppdateringsintervall. För 4-timmarsfrekvensen finns det en gräns på 150 målgrupper, eftersom den här uppdateringsfrekvensen är mycket bearbetningsintensiv. För andra intervaller finns det inget maximalt antal målgrupper.</li></ul> |
   | Utgångsdatum | När publiken slutar uppdatera. Standardvärdet är 1 år från skapandedatumet. |
   | Uppdatera uppslagsfönstret | Anger hur långt tillbaka i datafönstret du vill gå när du skapar den här målgruppen. Max. är 90 dagar. Utgångna målgrupper behandlas på samma sätt som schemalagda rapporter som förfaller - administratören får ett e-postmeddelande en månad innan schemat förfaller. |
   | [!UICONTROL One-time date range] | Datumintervall när du vill att en engångspublik ska publiceras. |
   | [!UICONTROL Filter] | Filter är huvudindata för publiken. Du kan lägga till upp till 20 filter. Dessa filter kan kombineras med `And` eller `Or` operatorer. |

   {style=&quot;table-layout:auto&quot;}

1. Tolka förhandsgranskningen av data.

   Publiken förhandsvisas i den högra listen.

   | Förhandsvisningsinställning | Beskrivning |
   | --- | --- |
   | Fönstret Förhandsgranska data | Datumintervallet för målgruppen. |
   | Totalt antal personer i publiken | Ett summeringsnummer som kan uppgå till 100 miljoner. |
   | Storleksgräns för målgrupp | Visar hur långt från gränsen på 100 miljoner som den här målgruppen är. |
   | Uppskattad målgruppsavkastning |  |
   | Beräknad att returnera | Ett sammanfattningsnummer.. |
   | Förhandsvisa mått |  |

   {style=&quot;table-layout:auto&quot;}


