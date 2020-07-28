---
title: Skapa en anslutning
description: Beskriver hur du skapar en anslutning till en Platform-datauppsättning i Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 756c6e7c187b76636cf96d18c949908a97db51ed
workflow-type: tm+mt
source-wordcount: '1565'
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

   ![Skapa anslutning](assets/create-connection0.png)

1. Välj en sandlåda i Experience Platform som innehåller den eller de datauppsättningar som du vill skapa en anslutning till.

   Adobe Experience Platform tillhandahåller [sandlådor](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) som partitionerar en enda Platform-instans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar. Du kan inte komma åt data över sandlådor. När du har valt sandlådan visas alla datauppsättningar i den sandlådan som du kan hämta från den vänstra listen.

1. Markera en eller flera datauppsättningar som du vill hämta till [!UICONTROL Customer Journey Analytics] och klicka på **[!UICONTROL Add]**.

   (Om du har många datauppsättningar att välja bland kan du söka efter de rätta med hjälp av sökfältet **[!UICONTROL Search datasets]** ovanför listan med datauppsättningar.)

## Konfigurera datauppsättning

Till höger kan du nu konfigurera den datauppsättning som du har lagt till.

![Konfigurera datauppsättning](assets/create-connection.png)

1. **[!UICONTROL Dataset type]**: För varje datauppsättning som du har lagt till i den här anslutningen anges datauppsättningstypen automatiskt baserat på de data som kommer in. [!UICONTROL Customer Journey Analytics]

   Det finns tre olika datamängdstyper: [!UICONTROL Event] data, [!UICONTROL Profile] data och [!UICONTROL Lookup] data.

   | Typ av datauppsättning | Beskrivning | Tidsstämpel | Schema | Person-ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta kan till exempel vara typiska klickströmsdata, med ett kund-ID eller ett cookie-ID och en tidsstämpel. Med händelsedata får du flexibilitet vad gäller vilket ID som används som person-ID. | Är automatiskt inställt på standardtidsstämpelfältet från händelsebaserade scheman i [UICONTROL Experience Platform]. | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet&quot;Time Series&quot;. Exempel är &quot;XDM Experience Event&quot; eller &quot;XDM Decision Event&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datamängdsschema som definieras i Experience Platform kan ha en egen uppsättning av en eller flera identiteter som är definierade och associerade med ett identitetsnamnutrymme. Alla dessa kan användas som person-ID. Exempel är cookie-ID, Stitched ID, User ID, Tracking Code osv. |
   | [!UICONTROL Lookup] | Motsvarar en klassificeringsfil. Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på en XDM-klass med beteendet &quot;Record&quot;, förutom klassen &quot;XDM Individual Profile&quot;. | Ej tillämpligt |
   | [!UICONTROL Profile] | Motsvarar [!UICONTROL Customer Attributes] - för attribut som inte ändras eller som inte är temporala. Data som tillämpas på era besökare, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. | Ej tillämpligt | Alla inbyggda eller anpassade scheman som baseras på klassen &quot;XDM Individual Profile&quot;. | Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning med ett eller flera definierade person-ID, t.ex. cookie-ID, Stitched ID, User ID, Tracking Code, osv.<br>![Person](assets/person-id.png)**IDNote **: Om du skapar en anslutning som innehåller datauppsättningar med olika ID:n, återspeglas detta i rapporten. Om du verkligen vill sammanfoga datauppsättningar måste du använda samma person-ID. |

1. **[!UICONTROL Dataset ID]**: Detta ID genereras automatiskt.

1. **[!UICONTROL Time stamp]**: lägg till innehåll här

1. **[!UICONTROL Schema]**: Detta är det [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) som baserar sig på vilket datauppsättningen skapades i Adobe Experience Platform.

1. **[!UICONTROL Person ID]**: Välj ett person-ID i listrutan med tillgängliga identiteter. Dessa identiteter definierades i datauppsättningsschemat i Experience Platform. Nedan finns information om hur du använder identitetskartan som ett person-ID.

   >[!IMPORTANT]
   >
   >Om det inte finns några person-ID:n att välja mellan, innebär det att ett eller flera person-ID:n inte har definierats i schemat. Se [den här videon](https://youtu.be/G_ttmGl_LRU) om hur du definierar en identitet i Experience Platform.

1. Klicka **[!UICONTROL Next]** för att gå till [!UICONTROL Enable Connection] dialogrutan.

### Använd identitetskarta som person-ID

Customer Journey Analytics har nu stöd för möjligheten att använda identitetskartan för sitt person-ID. Identitetskarta är en kartdatastruktur som gör att någon kan överföra nyckel -> värdepar. Nycklarna är identitetsnamnutrymmen och värdet är en struktur som innehåller identitetsvärdet. Identitetskartan finns för varje överförd rad/händelse och fylls i för varje rad i enlighet med detta.

Identitetskartan är tillgänglig för alla datauppsättningar som använder ett schema baserat på [ExperienceEvent-klassen XDM](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) . När du väljer en sådan datauppsättning som ska inkluderas i en CJA-anslutning kan du välja att antingen välja ett fält som primärt ID eller identitetskartan:

![](assets/idmap1.png)

Om du väljer Identitetskarta får du ytterligare två konfigurationsalternativ:

| Alternativ | Beskrivning |
|---|---|
| [!UICONTROL Use Primary ID Namespace] | Detta instruerar CJA, per rad, att hitta identiteten i identitetskartan som är markerad med ett primär=true-attribut och använda det som ID för den raden. Detta innebär att det här är den primärnyckel som ska användas i Experience Platform för partitionering. Det är också den primära kandidaten för CJA:s besökar-ID (beroende på hur datauppsättningen konfigureras i en CJA-anslutning). |
| [!UICONTROL Namespace] | (Det här alternativet är bara tillgängligt om du inte använder namnutrymmet för primärt ID.) Identitetsnamnutrymmen är en komponent i [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) som fungerar som indikatorer för det sammanhang som en identitet relateras till. Om du anger ett namnutrymme söker CJA efter den här namnutrymmesnyckeln i varje rads identitetskarta och använder identiteten under namnutrymmet som ID för den raden. Observera att eftersom CJA inte kan göra en fullständig datauppsättningssökning av alla rader för att avgöra vilka namnutrymmen som faktiskt finns, visas alla möjliga namnutrymmen i listrutan. Du måste veta vilka namnutrymmen som anges i data; detta kan inte identifieras automatiskt. |

### Kantärenden för identitetskarta

I den här tabellen visas de två konfigurationsalternativen när det finns kantfall och hur de hanteras:

| Alternativ | Det finns inga ID:n i identitetskartan | Inga ID har markerats som primära | Flera ID:n är markerade som primära | Ett ID är markerat som primärt | Ogiltigt namnutrymme med ett ID markerat som primärt |
|---|---|---|---|---|---|
| **Använd namnutrymme för primärt ID markerat** | Raden tas bort av CJA. | Raden tas bort av CJA eftersom inget primärt ID har angetts. | Alla ID:n som markerats som primära, under alla namnutrymmen, extraheras till en lista. De sorteras sedan alfabetiskt, med den här nya sorteringen används det första namnutrymmet med dess första ID som person-ID. | Det enda ID som är markerat som primärt används som person-ID. | Även om namnutrymmet kan vara ogiltigt (inte finns i AEP) kommer CJA att använda det primära ID:t under namnutrymmet som Person-ID. |
| **Namnområdet Specifik identitetskarta har valts** | Raden tas bort av CJA. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. | Alla ID:n under det markerade namnutrymmet extraheras till en lista och det första används som person-ID. (Endast ett giltigt namnutrymme kan väljas när anslutningen skapas, så det är inte möjligt att använda ett ogiltigt namnutrymme/ID som person-ID) |

## Aktivera anslutning

![Aktivera anslutning](assets/create-connection2.png)

1. Om du vill aktivera en anslutning definierar du följande inställningar:

   | Alternativ | Beskrivning |
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
