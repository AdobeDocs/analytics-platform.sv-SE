---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en plattformsdatauppsättning i kundreseanalysen.
translation-type: tm+mt
source-git-commit: 41029fb428308a247df65072af4e419a90098a15

---


# Skapa en anslutning

Med en anslutning kan ni integrera datauppsättningar från Adobe Experience Platform i Workspace. För att kunna rapportera om plattformsdatauppsättningar måste du först skapa en anslutning mellan datauppsättningar i Platform och Workspace.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) för en videoöversikt.

>[!IMPORTANT] Du kan kombinera flera plattformsdatauppsättningar i en enda anslutning.

1. Gå till [https://analytics.adobe.com](https://analytics.adobe.com).

1. Klicka på **[!UICONTROL Connections]** fliken.

1. Klicka **[!UICONTROL Create new connection]** högst upp till höger.

![Skapa anslutning](assets/create-connection.png)

1. Den vänstra listen visar alla datauppsättningar i Platform som du kan hämta från. Välj en eller flera datauppsättningar som du vill hämta till kundreseanalysen och klicka på **[!UICONTROL Add]**. (Om du har många datauppsättningar att välja bland kan du söka efter de rätta med hjälp av sökfältet ovanför listan med datauppsättningar.)

1. För varje datauppsättning som du har lagt till i den här anslutningen anger kundreseanalysen automatiskt datatypen baserat på de data som kommer in. Det finns tre olika datamängdstyper: Händelsedata, profildata och sökdata.

   | Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
   |---|---|---|---|---|
   | Händelse | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta är typiska klickströmsdata, med ett kund-ID eller ett cookie-ID, och en tidsstämpel. Med händelsedata kan du använda vilket ID du vill. | Anger till Tidsstämpel. | Det plattformsschema som den här datamängdstypen baseras på. | Ej tillämpligt |
   | Sök | Motsvarar en klassificeringsfil. Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. | Ej tillämpligt | Det plattformsschema som den här datamängdstypen baseras på. | Ej tillämpligt |
   | Profil | Motsvarar kundattribut - för attribut som inte ändras eller inte ändras i tid. Data som tillämpas på besökare, användare eller kunder i händelsedata. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Det plattformsschema som den här datamängdstypen baseras på. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i Adobe Experience Platform har en egen uppsättning med ett eller flera definierade person-ID, till exempel cookie-ID, Stitched ID, User ID, Tracking Code, osv.<br>![Person](assets/person-id.png)**IDNote **: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

1. Klicka på **[!UICONTROL Next]**.

1. Ange följande inställningar i dialogrutan Skapa anslutning:

   | Fält | Beskrivning |
   |---|---|
   | Namn | Ge anslutningen ett beskrivande namn. Anslutningen kan inte sparas utan ett namn. |
   | Beskrivning | Lägg till mer information för att skilja den här anslutningen från andra. |
   | Storlek | Den sammanlagda storleken på datauppsättningarna i dataanslutningen. |
   | Datauppsättningar | De datauppsättningar som ingår i den här anslutningen. |
   | Dataströmning | Aktivera dataströmning om du vill börja direktuppspela data för den här anslutningen. När dataströmning är aktiverat för den här anslutningen faktureras ditt konto för den mängd data som anslutningen direktuppspelar. (Observera att du även kan aktivera dataströmning i Anslutningshanteraren.) |

1. Klicka på **[!UICONTROL Save]**. När du sparar den här anslutningen händer två saker:

   * Du hämtar in alla historiska data från Platform för alla datauppsättningar som finns i den här anslutningen.
   * Om du aktiverade direktuppspelning upprättar du en pågående anslutning så att alla nya data som läggs till i datauppsättningarna i den här anslutningen automatiskt flödar till arbetsytan.

Nästa steg i arbetsflödet är att [skapa en datavy](/help/data-views/create-dataview.md).
