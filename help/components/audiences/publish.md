---
title: Skapa och publicera målgrupper i kundprofilen i realtid
description: Lär dig hur du publicerar målgrupper från Customer Journey Analytics
source-git-commit: fbe6f346d35d5f80fcbc9ed69b3ab4730c0715d6
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---


# Skapa och publicera målgrupper

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

I det här avsnittet beskrivs hur du publicerar målgrupper som identifierats i Customer Journey Analytics (CJA) till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) i Adobe Experience Platform för kundanpassning och personalisering.

Läs det här [översikt](/help/components/audiences/audiences-overview.md) för att bekanta dig med konceptet CJA-målgrupper.

## Skapa målgrupper

1. Du kan skapa målgrupper på tre sätt:

   | Skapandemetod | Detaljer |
   | --- | --- |
   | Från huvudsidan **[!UICONTROL Components]>[!UICONTROL Audiences]** meny | Sidan Audiences Manager öppnas. Klicka **[!UICONTROL Create audience]** och [!UICONTROL Audience builder] öppnas. |
   | Från en friformstabell | Högerklicka på ett objekt i en frihandstabell och välj **[!UICONTROL Create an audience from selection]**. Om du använder den här metoden fylls filtret i automatiskt med den dimension eller dimensionspost som du valde i tabellen. |
   | Från gränssnittet för att skapa/redigera filter | Markera rutan som innehåller **[!UICONTROL Create an audience from this filter]**. Om du använder den här metoden fylls filtret i automatiskt. |

   {style=&quot;table-layout:auto&quot;}

1. Bygg publiken.

   Konfigurera de här inställningarna innan du kan publicera målgruppen.

   ![](assets/create-audience.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | [!UICONTROL Name] | Publiken. |
   | [!UICONTROL Tags] | Alla taggar som du vill ska tilldelas till målgruppen för organisatoriska ändamål. Du kan använda en befintlig tagg eller ange en ny. |
   | [!UICONTROL Description] | Lägg till en bra beskrivning av målgruppen för att skilja den från andra. |
   | [!UICONTROL Refresh frequency] | Hur ofta du vill uppdatera publiken.<ul><li>Du kan välja att skapa en engångskarp målgrupp (standard) som inte behöver uppdateras, vilket kan vara praktiskt för specifika engångskampanjer.</li><li>Du kan välja andra uppdateringsintervall. För 4-timmarsfrekvensen finns det en gräns på 150 målgrupper, eftersom den här uppdateringsfrekvensen är mycket bearbetningsintensiv. För andra intervall finns det inget högsta antal målgrupper.</li></ul> |
   | Utgångsdatum | När publiken slutar uppdatera. Standardvärdet är 1 år från skapandedatumet. Utgångna målgrupper behandlas på samma sätt som schemalagda rapporter som förfaller - administratören får ett e-postmeddelande en månad innan målgruppen förfaller. |
   | Uppdatera uppslagsfönstret | Anger hur långt tillbaka i datafönstret du vill gå när du skapar den här målgruppen. Max. är 90 dagar. |
   | [!UICONTROL One-time date range] | Datumintervall när du vill att en engångspublik ska publiceras. |
   | [!UICONTROL Filter] | Filter är huvudindata för publiken. Du kan lägga till upp till 20 filter. Dessa filter kan kombineras med `And` eller `Or` operatorer. |
   | [!UICONTROL View sample IDs] | Ett exempel på ID:n i den här målgruppen. Använd sökfältet för att söka efter exempel-ID:n.<p>!![](assets/sample-ids.png |

   {style=&quot;table-layout:auto&quot;}

1. Tolka förhandsgranskningen av data.

   Publiken förhandsvisas i den högra listen. Det möjliggör avancerad analys av den målgrupp ni har skapat.

   ![](assets/data-preview.png)

   | Förhandsvisningsinställning | Beskrivning |
   | --- | --- |
   | [!UICONTROL Data preview] window | Datumintervallet för målgruppen. |
   | [!UICONTROL Total people] | Ett summerat antal personer i den här publiken. Den kan gå upp till 100 miljoner människor. Om er målgrupp överstiger 100 miljoner människor måste ni minska målgruppens storlek innan ni kan publicera den. |
   | [!UICONTROL Audience size limit] | Visar hur långt från gränsen på 100 miljoner som den här målgruppen är. |
   | [!UICONTROL Estimated audience return] | Den här inställningen är användbar för återmarknadsföring av kunder i den här målgruppen som kommer tillbaka till er webbplats. (Med andra ord, som visas i den här datauppsättningen igen.) <p>Här kan du välja tidsram (nästa 7 dag, nästa 2 veckor, nästa månad) för det uppskattade antalet kunder som kan komma att returnera. |
   | [!UICONTROL Estimated to return] | Numret ger ett uppskattat antal återkommande kunder under den tidsperiod som du valde i listrutan. Vi tittar på den historiska bortfallsfrekvensen för den här publiken för att förutse detta antal. |
   | [!UICONTROL Preview metrics] | Med den här inställningen kan du titta på specifika mätvärden för att se om den här målgruppen bidrar med ett oproportionerligt belopp till det här mätvärdet, till exempel &#39;[!UICONTROL Revenue]&#39; eller &#39;[!UICONTROL Average time on site]&#39;. Det ger dig det sammanlagda antalet mätvärden, liksom procentandelen av det totala antalet. Du kan välja alla mätvärden som är tillgängliga i datavyn. |
   | Namnutrymmen ingår | De specifika namnutrymmen som är associerade med personerna i din publik. Exempel är ECID, CRM-ID, e-postadresser osv. |
   | Sandbox | Sandlådan Experience Platform som den här publiken bor i. När du publicerar den här målgruppen på Platform kan du bara arbeta med den inom gränserna för den här sandlådan. |

   {style=&quot;table-layout:auto&quot;}

1. Om allt ser bra ut klickar du **[!UICONTROL Publish]**.

## Nästa steg

* Om du vill hantera den här målgruppen går du till [Hanteringsgränssnitt](/help/components/audiences/manage.md).
* Om du vill arbeta med den här målgruppen i Adobe Experience Platform går du hit.
