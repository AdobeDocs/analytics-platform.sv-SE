---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en plattformsdatauppsättning i kundreseanalysen.
translation-type: tm+mt
source-git-commit: fa7898d73756c33a0bae22c8758bc9f0a649626a

---


# Skapa en anslutning

Med en anslutning kan du integrera datauppsättningar från [!DNL Adobe Experience Platform] till [!UICONTROL Workspace]. För att kunna rapportera om plattformsdatauppsättningar måste du först skapa en anslutning mellan datauppsättningar i Platform och Workspace.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) för en videoöversikt.

>[!IMPORTANT] Du kan kombinera flera plattformsdatauppsättningar i en enda anslutning.

1. Gå till [https://analytics.adobe.com](https://analytics.adobe.com).

1. Klicka på **[!UICONTROL Connections]** fliken.

1. Klicka **[!UICONTROL Create new connection]** högst upp till höger.

![Skapa anslutning](assets/create-connection.png)

1. Den vänstra listen visar alla datauppsättningar i Platform som du kan hämta från. Markera en eller flera datauppsättningar som du vill hämta till [!UICONTROL Customer Journey Analytics] och klicka på **[!UICONTROL Add]**. (Om du har många datauppsättningar att välja bland kan du söka efter de rätta med hjälp av sökfältet ovanför listan med datauppsättningar.)

1. För varje datauppsättning som du har lagt till i den här anslutningen anges datauppsättningstypen automatiskt baserat på de data som kommer in. [!UICONTROL Customer Journey Analytics] Det finns tre olika datamängdstyper: Händelsedata, profildata och sökdata.

   | Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta är typiska klickströmsdata, med ett kund-ID eller ett cookie-ID, och en tidsstämpel. Med händelsedata kan du använda vilket ID du vill. | Anger till Tidsstämpel. | Det plattformsschema som den här datamängdstypen baseras på. | Ej tillämpligt |
   | [!UICONTROL Lookup] | Motsvarar en klassificeringsfil. Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. | Ej tillämpligt | Det plattformsschema som den här datamängdstypen baseras på. | Ej tillämpligt |
   | [!UICONTROL Profile] | Motsvarar [!UICONTROL Customer Attributes] - för attribut som inte ändras eller som inte är temporala. Data som tillämpas på era besökare, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Det schema som den här datamängdstypen [!UICONTROL Platform] baseras på. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i Adobe Experience Platform har en egen uppsättning med ett eller flera definierade person-ID, till exempel cookie-ID, Stitched ID, User ID, Tracking Code, osv.<br>![Person](assets/person-id.png)**IDNote **: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

1. När du klickar **[!UICONTROL Next]** öppnas [!UICONTROL Create Connection] dialogrutan.

   ![Skapa anslutning](assets/create-connection2.png)

1. Ange följande inställningar i [!UICONTROL Create Connection] dialogrutan:

   | Fält | Beskrivning |
   |---|---|
   | [!UICONTROL Name Connection] | Ge anslutningen ett beskrivande namn. Anslutningen kan inte sparas utan ett namn. |
   | [!UICONTROL Description] | Lägg till mer information för att skilja den här anslutningen från andra. |
   | [!UICONTROL Datasets] | De datauppsättningar som ingår i den här anslutningen. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Välj det här alternativet om du vill upprätta en pågående anslutning så att alla nya databatchar som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar in i [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | När du väljer det här alternativet och sparar anslutningen importeras alla befintliga (historiska) data från plattformen för alla datauppsättningar som finns i den här anslutningen. I framtiden kommer även alla befintliga historiska data för nya datauppsättningar som läggs till i den här sparade anslutningen att importeras automatiskt. <br>**Observera att den här inställningen inte kan ändras när anslutningen har sparats.** |

   **Kom ihåg att:**

   * Om den kumulativa storleken på historiska data för alla datauppsättningar i anslutningen överstiger 1,5 miljarder rader visas ett felmeddelande om att du inte kan importera den här mängden historiska data. Men om du lägger till en datauppsättning med 1 miljard rader med historiska data och importerar dessa data, och en vecka senare, lägger till ytterligare en datauppsättning med samma storlek och importerar dess historiska data, skulle det fungera.
   * Vi prioriterar nya data som läggs till i en datauppsättning i anslutningen, så att dessa data har den lägsta latensen.
   * Eventuella bakåtfyllnadsdata (historiska) importeras i en långsammare takt.

1. Klicka på **[!UICONTROL Save]**.

Nästa steg i arbetsflödet är att [skapa en datavy](/help/data-views/create-dataview.md).
