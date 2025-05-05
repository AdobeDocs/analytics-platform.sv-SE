---
description: ställa frågor om Customer Journey Analytics dokumentation
title: AI Assistant för Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---


# AI Assistant för Adobe Customer Journey Analytics

AI Assistant är en konversationsupplevelse som gör det möjligt för yrkesverksamma att utföra uppgifter i snabb takt. Om uppgiften är att förstå begrepp, felsöka problem eller söka igenom information. Med AI Assistant kan även icke-experter utföra expertuppgifter och öka den övergripande kvaliteten på arbetet.

AI Assistant i Customer Journey Analytics är utbildad i sin Adobe Experience League-dokumentation. När AI Assistant tillfrågas om det finns ett användbart svar som gör att du snabbt kan lära dig mer.

Som nybörjare kan du använda AI Assistant för att lära dig Customer Journey Analytics koncept och själv ta till vara produkter och funktioner som du inte är bekant med. Som erfaren användare kan du använda AI Assistant för att visa mer avancerade användningsexempel eller tips och tricks.

Några exempel på konceptfrågor är:

* Vad är skillnaden mellan batchinmatning och direktuppspelning?
* Vad är Customer Journey Analytics bäst för?
* Hur konfigurerar jag en datavy?

Frågor utanför Customer Journey Analytics, t.ex. frågor om andra Adobe-produkter som Adobe Target och Adobe Creative Cloud Suite, kan inte besvaras.

AI Assistant för Customer Journey Analytics är tillgängligt på alla produktnivåer.

## Produktkunskap {#knowledge}

Modellen för hämtning av produktkunskap är utbildad i Customer Journey Analytics. Andra funktioner, som dataanalys, kommer att lanseras senare.

| Produktkunskap | Exempel |
| --- | --- |
| Undervisning | <ul><li>Vad är skillnaden mellan Adobe Analytics och Customer Journey Analytics?</li><li>Hur bygger jag upp ett beräknat mätvärde?</li></ul> |
| Öppna identifiering | <ul><li>Hur exporterar jag ett Workspace-projekt?</li><li>Hur hittar jag duplicerade Workspace-komponenter?</li></ul> |
| Felsökning | <ul><li>Hur lång tid tar det innan data kommer in i CJA?</li><li>Hur många härledda fält kan jag ha i en Customer Journey Analytics-anslutning?</li></ul> |

## Funktionsåtkomst

Följande parametrar styr åtkomsten till AI-assistentfunktionen:

* **Åtkomst till lösning**: AI-assistenten är tillgänglig i Customer Journey Analytics, men inte i Adobe Analytics. Det finns också i Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP och andra appar för Experience Platform.

* **Kontraktsåtkomst**: Om du inte kan använda AI Assistant kontaktar du organisationens administratör eller Adobe-kontorepresentant. Innan din organisation kan använda AI Assistant måste du godkänna vissa GenAI-relaterade juridiska villkor.

* **Behörigheter**: I [!UICONTROL Adobe Admin Console] avgör behörigheten [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Product Knowledge]** åtkomsten till det här verktyget. En [produktprofiladministratör](https://helpx.adobe.com/se/enterprise/using/manage-product-profiles.html) måste följa de här stegen i [!UICONTROL Admin Console]:
   1. Navigera till **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Välj titeln för den produktprofil som du vill ge åtkomst till [!UICONTROL AI Assistant: Product Knowledge].
   1. Välj **[!UICONTROL Permissions]** i den specifika produktprofilen.
   1. Välj ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera **[!UICONTROL Reporting Tools]**.
   1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) om du vill lägga till **AI-assistenten: Produktkunskap** i **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](assets/ai-assistant-permissions.png).

   1. Välj **[!UICONTROL Save]** om du vill spara behörigheterna.

Mer information finns i [Åtkomstkontroll](/help/technotes/access-control.md#access-control).

## Åtkomst till AI-assistenten i användargränssnittet i Customer Journey Analytics

1. Om du vill starta AI Assistant väljer du AI Assistant-ikonen i det övre sidhuvudet på en Customer Journey Analytics-sida.

   ![AI Assistant-ikon](assets/ai-asst1.png)

   När du använder AI Assistant för första gången visas en ansvarsfriskrivning med villkor för användning av assistenten.

1. I rutan ställer du en specifik fråga på naturspråket i AI-assistenten.

   ![Frågeruta](assets/ai-asst2.png)

1. (Valfritt) Om du vill visa källor klickar du på **[!UICONTROL Show Sources]** och dokumentationskällan eller -källorna som informerade svaret visas.

1. (Valfritt) Du kan även ge en röstning med upp- eller nedstaplar om hur användbart ett visst svar är.

1. (Valfritt) Du kan flagga svaret för olämpligt eller skadligt innehåll.
