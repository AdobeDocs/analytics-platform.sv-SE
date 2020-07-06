---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en Platform-datauppsättning i Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 1%

---


# Skapa en anslutning

Med en anslutning kan du integrera datauppsättningar från [!DNL Adobe Experience Platform] till [!UICONTROL Workspace]. För att kunna rapportera om [!DNL Experience Platform] datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i [!DNL Experience Platform] och [!UICONTROL Workspace].

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) för en videoöversikt.

>[!IMPORTANT]
>
>Du kan kombinera flera [!DNL Experience Platform] datauppsättningar till en enda anslutning.

1. Gå till [https://analytics.adobe.com](https://analytics.adobe.com).

1. Klicka på **[!UICONTROL Connections]** fliken.

1. Klicka **[!UICONTROL Create new connection]** högst upp till höger.

   ![Skapa anslutning](assets/create-connection.png)

1. Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.

   Adobe Experience Platform tillhandahåller [sandlådor](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) som partitionerar en enda Platform-instans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar. Du kan inte komma åt data över sandlådor. När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen.

1. Markera en eller flera datauppsättningar som du vill hämta till [!UICONTROL Customer Journey Analytics] och klicka på **[!UICONTROL Add]**.

   (Om du har många datauppsättningar att välja bland kan du söka efter de rätta med hjälp av sökfältet ovanför listan med datauppsättningar.)

1. För varje datauppsättning som du har lagt till i den här anslutningen anges datauppsättningstypen automatiskt baserat på de data som kommer in. [!UICONTROL Customer Journey Analytics]

   Det finns tre olika datamängdstyper: [!UICONTROL Event] data, [!UICONTROL Profile] data och [!UICONTROL Lookup] data.

   | Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta kan till exempel vara typiska klickströmsdata, med ett kund-ID eller ett cookie-ID och en tidsstämpel. Med händelsedata får du flexibilitet vad gäller vilket ID som används som person-ID. | Är automatiskt inställt på standardtidsstämpelfältet från händelsebaserade scheman i [UICONTROL Experience Platform]. | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet&quot;Time Series&quot;. Exempel är &quot;XDM Experience Event&quot; eller &quot;XDM Decision Event&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code osv. |
   | [!UICONTROL Lookup] | Motsvarar en klassificeringsfil. Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet &quot;Record&quot;, förutom klassen &quot;XDM Individual Profile&quot;. | Ej tillämpligt |
   | [!UICONTROL Profile] | Motsvarar [!UICONTROL Customer Attributes] - för attribut som inte ändras eller som inte är temporala. Data som tillämpas på era besökare, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på klassen &quot;XDM Individual Profile&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning med ett eller flera definierade person-ID, t.ex. cookie-ID, Stitched ID, User ID, Tracking Code, osv.<br>![Person](assets/person-id.png)**IDNote **: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

1. Klicka **[!UICONTROL Next]** för att gå till [!UICONTROL Create Connection] dialogrutan.

   ![Skapa anslutning](assets/create-connection2.png)

1. Ange följande inställningar i [!UICONTROL Create Connection] dialogrutan:

   | Fält | Beskrivning |
   |---|---|
   | [!UICONTROL Name Connection] | Ge anslutningen ett beskrivande namn. Anslutningen kan inte sparas utan ett namn. |
   | [!UICONTROL Description] | Lägg till mer information för att skilja den här anslutningen från andra. |
   | [!UICONTROL Datasets] | De datauppsättningar som ingår i den här anslutningen. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Välj det här alternativet om du vill upprätta en pågående anslutning så att alla nya databatchar som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar in i [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | När du väljer det här alternativet och sparar anslutningen importeras alla befintliga (historiska) data från [!DNL Experience Platform] alla datauppsättningar som finns i den här anslutningen. I framtiden kommer även alla befintliga historiska data för nya datauppsättningar som läggs till i den här sparade anslutningen att importeras automatiskt. <br>**Observera att den här inställningen inte kan ändras när anslutningen har sparats.** |

   **Kom ihåg:**

   * Om den kumulativa storleken på historiska data för alla datauppsättningar i anslutningen överstiger 1,5 miljarder rader visas ett felmeddelande om att du inte kan importera den här mängden historiska data. Men om du lägger till en datauppsättning med 1 miljard rader med historiska data och importerar dessa data, och en vecka senare, lägger till ytterligare en datauppsättning med samma storlek och importerar dess historiska data, skulle det fungera.
   * Vi prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa data har den lägsta latensen.
   * Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt.

1. Klicka på **[!UICONTROL Save]**.

Nästa steg i arbetsflödet är att [skapa en datavy](/help/data-views/create-dataview.md).
