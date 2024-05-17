---
description: ställa frågor om Customer Journey Analytics dokumentation
title: AI Assistant för Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 49f2c393bbd0bff28dd8bc166b3c60bc49d4df37
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# AI Assistant för Adobe Customer Journey Analytics

>[!NOTE]
>
>AI Assistant för Customer Journey Analytics är för närvarande i Beta. Funktionen och dess dokumentation kan komma att ändras.

AI Assistant är en gränssnittsfunktion som du kan använda för att navigera bland och förstå Adobe Customer Journey Analytics koncept och terminologi. AI Assistant i Customer Journey Analytics är utbildad i sin Adobe Experience League-dokumentation. När AI Assistant tillfrågas om det finns ett användbart svar som gör att du snabbt kan lära dig mer.

Som nybörjare kan du använda AI Assistant för att lära dig Customer Journey Analytics koncept och själv ta till vara produkter och funktioner som du inte är bekant med. Som erfaren användare kan du använda AI Assistant för att visa mer avancerade användningsexempel eller tips och tricks.

Några exempel på konceptfrågor är:

* Vad är skillnaden mellan batchinmatning och direktuppspelning?
* Vad är Customer Journey Analytics bäst för?
* Hur konfigurerar jag en datavy?

Modellen för dokumentationsåterhämtning har utbildats på Customer Journey Analytics. Frågor utanför Customer Journey Analytics, t.ex. frågor om andra Adobe-produkter som Adobe Target och Adobe Creative Cloud Suite, kan inte besvaras.

AI Assistant för Customer Journey Analytics är tillgängligt på alla produktnivåer.

>[!IMPORTANT]
>
>I nuläget besvarar inte AI Assistant för Customer Journey Analytics användningsfrågor om dataobjekt i organisationen.

## Funktionsåtkomst

I den här första versionen styrs åtkomsten till AI-assistentfunktionen av följande parametrar:

* **Åtkomst till lösningar**: AI-assistenten finns i Customer Journey Analytics, men inte i Adobe Analytics. Det finns också i Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP och andra appar för Experience Platform.

* **Kontraktsåtkomst**: Ditt säljkontrakt för Adobe måste innehålla en klausul som gör att Adobe kan använda dina data i AI/ML-modellutveckling (klausul 6.2).

* **Behörigheter**: [!UICONTROL Adobe Admin Console] [!UICONTROL Reporting Tools] Behörigheten&quot;AI Assistant Documentation&quot; bestämmer åtkomsten till det här verktyget. Detta tillstånd läggs till i avsnittet Rapporteringsverktyg i mitten av maj. Du måste se till att du skapar en [produktprofil](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) i Admin Console med detta tillstånd och lägg till användare manuellt i profilen.

## Åtkomst till AI-assistenten i användargränssnittet i Customer Journey Analytics

1. Om du vill starta AI Assistant väljer du AI Assistant-ikonen i det övre sidhuvudet på en Customer Journey Analytics-sida.

   ![AI Assistant, ikon](assets/ai-asst1.png)

   När du använder AI Assistant för första gången visas en ansvarsfriskrivning med villkor för användning av assistenten.

1. I rutan ställer du en specifik fråga på naturspråket i AI-assistenten.

   ![Frågeruta](assets/ai-asst2.png)

1. (Valfritt) Om du vill visa källor klickar du på **[!UICONTROL Show Sources]** och dokumentationskällan/dokumentationskällorna som informerade svaret visas.

1. (Valfritt) Du kan även ge en röstning med upp- eller nedstaplar om hur användbart ett visst svar är.
