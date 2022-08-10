---
title: Skapa och publicera målgrupper i kundprofilen i realtid
description: Lär dig hur du publicerar målgrupper från Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 235f08b275fd2f5706024823005e732b61af1c07
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 0%

---

# Skapa och publicera målgrupper

I det här avsnittet beskrivs hur du skapar och publicerar målgrupper som identifieras i Customer Journey Analytics (CJA) till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) i Adobe Experience Platform för kundanpassning och personalisering.

Läs det här [översikt](/help/components/audiences/audiences-overview.md) för att bekanta dig med konceptet CJA-målgrupper.

## Skapa målgrupper {#create}

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
   | [!UICONTROL Refresh frequency] | Hur ofta du vill uppdatera publiken.<ul><li>Du kan välja att skapa en enda målgrupp (standard) som inte behöver uppdateras. Detta kan till exempel vara användbart för specifika engångskampanjer.</li><li>Du kan välja andra uppdateringsintervall. För 4-timmarsfrekvensen finns det en gräns på 75 eller 150 målgrupper, beroende på ditt CJA-berättigande. För andra intervall finns det inget högsta antal målgrupper.</li></ul> |
   | Utgångsdatum | När publiken slutar uppdatera. Standardvärdet är 1 år från skapandedatumet. Utgångna målgrupper behandlas på samma sätt som schemalagda rapporter som förfaller - administratören får ett e-postmeddelande en månad innan målgruppen förfaller. |
   | Uppdatera uppslagsfönstret | Anger hur långt tillbaka i datafönstret du vill gå när du skapar den här målgruppen. Max 90 dagar. |
   | [!UICONTROL One-time date range] | Datumintervall när du vill att en engångspublik ska publiceras. |
   | [!UICONTROL Filter] | Filter är huvudindata för publiken. Du kan lägga till upp till 20 filter. Dessa filter kan kombineras med `And` eller `Or` operatorer. |
   | [!UICONTROL View sample IDs] | Ett exempel på ID:n i den här målgruppen. Använd sökfältet för att söka efter exempel-ID:n. |

   {style=&quot;table-layout:auto&quot;}

1. Tolka förhandsgranskningen av data.

   Publiken förhandsvisas i den högra listen. Här kan ni göra en sammanfattande analys av den målgrupp ni har skapat.

   ![](assets/data-preview.png)

   | Förhandsvisningsinställning | Beskrivning |
   | --- | --- |
   | [!UICONTROL Data preview] window | Datumintervallet för målgruppen. |
   | [!UICONTROL Total people] | Ett summerat antal personer i den här publiken. Den kan gå upp till 20 miljoner människor. Om er målgrupp överstiger 20 miljoner människor måste ni minska målgruppens storlek innan ni kan publicera den. |
   | [!UICONTROL Audience size limit] | Visar hur långt från gränsen på 20 miljoner som den här målgruppen är. |
   | [!UICONTROL Estimated audience return] | Den här inställningen är användbar för återmarknadsföring av kunder i den här målgruppen som kommer tillbaka till er webbplats. (Med andra ord, som visas i den här datauppsättningen igen.) <p>Här kan du välja tidsram (nästa 7 dag, nästa 2 veckor, nästa månad) för det uppskattade antalet kunder som kan komma att returnera. |
   | [!UICONTROL Estimated to return] | Numret ger ett uppskattat antal återkommande kunder under den tidsperiod som du valde i listrutan. Vi tittar på den historiska bortfallsfrekvensen för den här publiken för att förutse detta antal. |
   | [!UICONTROL Preview metrics] | Med den här inställningen kan du titta på specifika mätvärden för att se om den här målgruppen bidrar med ett oproportionerligt belopp till det här mätvärdet, till exempel &#39;[!UICONTROL Revenue]&#39; eller &#39;[!UICONTROL Average time on site]&#39;. Det ger dig det sammanlagda antalet mätvärden, liksom procentandelen av det totala antalet. Du kan välja alla mätvärden som är tillgängliga i datavyn. |
   | [!UICONTROL Namespaces included] | De specifika namnutrymmen som är associerade med personerna i din publik. Exempel är ECID, CRM-ID, e-postadresser osv. |
   | [!UICONTROL Sandbox] | The [Experience Platform sandlåda](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) där den här publiken bor. När du publicerar den här målgruppen på Platform kan du bara arbeta med den inom gränserna för den här sandlådan. |

   {style=&quot;table-layout:auto&quot;}

1. Kontrollera målgruppskonfigurationen och klicka **[!UICONTROL Publish]**.

   Om allt gick bra får du ett bekräftelsemeddelande om att publiken publicerades. Det tar bara några minuter för publiken att dyka upp i Experience Platform. (Även för målgrupper med miljontals medlemmar bör det ta mindre än fem minuter.)

1. Klicka **[!UICONTROL View audience in AEP]** inom samma meddelande kommer du till [Segmentgränssnitt](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=en) i Adobe Experience Platform. Mer information finns nedan.

## Använda CJA-målgrupper i Experience Platform {#audiences-aep}

CJA tar nu alla namnområdes- och ID-kombinationer från den publicerade målgruppen och strömmar dem till kundprofilen i realtid (RTCP). CJA skickar målgruppen vidare till Experience Platform med den primära identiteten inställd på det som valdes som person-ID när anslutningen konfigurerades.

RTCP undersöker sedan varje namnutrymmes-/ID-kombination och söker efter en profil som det kan vara en del av. En profil är i princip ett kluster med länkade namnutrymmen, ID:n och enheter. Om en profil hittas läggs namnutrymmet och ID:t till i de andra ID:n i den här profilen som ett segmentmedlemsattribut. Nu kan till exempel&quot;user@adobe.com&quot; användas på alla enheter och kanaler. Om ingen profil hittas skapas en ny.

Du kan visa CJA-målgrupper i Platform genom att gå till **[!UICONTROL Segments]** > **[!UICONTROL Create segments]** > **[!UICONTROL Audiences]** tab > **[!UICONTROL CJA Audiences]**.

Du kan dra CJA-målgrupper till segmentdefinitionen för AEP-segment.

![](assets/audiences-aep.png)

## Vad händer om en användare inte längre är medlem i en publik i CJA? {#no-member}

I det här fallet skickas en exit-händelse till Experience Platform från CJA.

## Vad händer om du tar bort en publik i CJA? {#delete}

När en CJA-publik tas bort visas den inte längre i användargränssnittet för Experience Platform. Inga profiler som är kopplade till den målgruppen tas emellertid bort i Platform.

## Nästa steg

* Om du vill hantera den här målgruppen går du till [Hanteringsgränssnitt](/help/components/audiences/manage.md).
