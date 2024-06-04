---
description: ställa frågor om Customer Journey Analytics dokumentation
title: AI Assistant för Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: 7e2a372d6e1fcbcfc26a63ddc804a592d6ee1725
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---


# AI Assistant för Adobe Customer Journey Analytics

>[!NOTE]
>
>AI Assistant för Customer Journey Analytics är för närvarande i Beta. Funktionen och dess dokumentation kan komma att ändras.

AI Assistant är en konversationsupplevelse som gör det möjligt för yrkesverksamma att utföra uppgifter snabbt - oavsett om de förstår koncept, felsöker problem eller söker igenom information. Det gör det även möjligt för icke-experter att utföra expertuppgifter och ökar den övergripande kvaliteten på arbetet.

AI Assistant i Customer Journey Analytics är utbildad i sin Adobe Experience League-dokumentation. När AI Assistant tillfrågas om det finns ett användbart svar som gör att du snabbt kan lära dig mer.

Som nybörjare kan du använda AI Assistant för att lära dig Customer Journey Analytics koncept och själv ta till vara produkter och funktioner som du inte är bekant med. Som erfaren användare kan du använda AI Assistant för att visa mer avancerade användningsexempel eller tips och tricks.

Några exempel på konceptfrågor är:

* Vad är skillnaden mellan batchinmatning och direktuppspelning?
* Vad är Customer Journey Analytics bäst för?
* Hur konfigurerar jag en datavy?

## Produktkunskap {#knowledge}

Modellen för hämtning av produktkunskap är utbildad i Customer Journey Analytics. Andra funktioner, som dataanalys, kommer att introduceras vid en senare tidpunkt.

| Produktkunskap | Exempel |
| --- | --- |
| Undervisning | <ul><li>Vad är skillnaden mellan Adobe Analytics och Customer Journey Analytics?</li><li>Hur bygger jag upp ett beräknat mätvärde?</li></ul> |
| Öppna identifiering | <ul><li>Hur exporterar jag ett Workspace-projekt?</li><li>Hur hittar jag duplicerade arbetsytekomponenter?</li></ul> |
| Felsökning | <ul><li>Hur lång tid tar det innan data kommer in i CJA?</li><li>Hur många härledda fält kan jag ha i en Customer Journey Analytics-anslutning?</li></ul> |

Frågor utanför Customer Journey Analytics, t.ex. frågor om andra Adobe-produkter som Adobe Target och Adobe Creative Cloud Suite, kan inte besvaras.

AI Assistant för Customer Journey Analytics är tillgängligt på alla produktnivåer.

## Funktionsåtkomst

I den här första versionen styrs åtkomsten till AI-assistentfunktionen av följande parametrar:

* **Åtkomst till lösningar**: AI-assistenten finns i Customer Journey Analytics, men inte i Adobe Analytics. Det finns också i Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP och andra appar för Experience Platform.

* **Kontraktsåtkomst**: Om du inte kan använda AI Assistant kontaktar du organisationens administratör eller Adobe Account Representant. Innan AI Assistant kan användas av din organisation måste ditt företag godkänna vissa GenAI-relaterade juridiska villkor.

* **Behörigheter**: I [!UICONTROL Adobe Admin Console], [!UICONTROL Reporting Tools] &quot;AI Assistant: Product Knowledge&quot; avgör åtkomsten till det här verktyget.
A [produktprofiladministratör](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) måste följa dessa steg i Admin Console:
   1. Navigera till [!UICONTROL Admin Console] > [!UICONTROL Products and services] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] > [!UICONTROL Edit Reporting Tools].
   1. Lägg till&quot;AI Assistant: Product Knowledge&quot;.

## Åtkomst till AI-assistenten i användargränssnittet i Customer Journey Analytics

1. Om du vill starta AI Assistant väljer du AI Assistant-ikonen i det övre sidhuvudet på en Customer Journey Analytics-sida.

   ![AI Assistant, ikon](assets/ai-asst1.png)

   När du använder AI Assistant för första gången visas en ansvarsfriskrivning med villkor för användning av assistenten.

1. I rutan ställer du en specifik fråga på naturspråket i AI-assistenten.

   ![Frågeruta](assets/ai-asst2.png)

1. (Valfritt) Om du vill visa källor klickar du på **[!UICONTROL Show Sources]** och dokumentationskällan eller -källorna som informerade svaret visas.

1. (Valfritt) Du kan även ge en röstning med upp- eller nedstaplar om hur användbart ett visst svar är.
