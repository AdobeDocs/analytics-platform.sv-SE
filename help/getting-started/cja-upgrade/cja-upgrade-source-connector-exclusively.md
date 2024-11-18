---
title: Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics
description: Lär dig hur du skapar Analytics-källkopplingen och kartfälten
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i checklistan för uppgradering av [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Även om det inte rekommenderas kan du använda Analytics-källkopplingen som enda implementeringsväg för Customer Journey Analytics. På grund av de inneboende nackdelarna med den här typen av uppgradering rekommenderar Adobe att du använder Analytics-källkopplingen i kombination med en ny implementering av Experience Platform Web SDK. Mer information om den här rekommenderade uppgraderingssökvägen finns i [Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Använd följande information för att förstå fördelarna och nackdelarna med att endast använda källkopplingen:

| Fördelar | Nackdelar |
|----------|---------|
| <ul><li>Minst tidskrävande och krävande uppgraderingsalternativ. <p>Data migreras snabbt och enkelt till Customer Journey Analytics.</p></li></ul> | <ul><li>**Data skickas inte till Edge Network**: <p>Detta medför följande nackdelar:</p><ul><li>Den högsta nivån av [latens](/help/technotes/guardrails.md#latencies) i rapportering för alla uppgraderingssökvägar, inte optimerad för användning av personalisering i realtid.</li><li>Data kan inte delas med andra Adobe Experience Platform-program, utan begränsas till endast Customer Journey Analytics</li><li>Använder Adobe Analytics nomenklatur (prop, eVar, event osv.)</li></ul><li>**Svårighet att gå över till Web SDK i framtiden**: Till slut vill du förmodligen ha tillgång till de fördelar som Experience Platform Web SDK ger. För att kunna börja använda Experience Platform Web SDK måste du göra en ny implementering.</li><li>**Använder fältgruppen Analytics Experience Event i ditt schema**: Den här fältgruppen lägger till många Adobe Analytics-händelser som inte behövs i ditt Customer Journey Analytics-schema.  Detta kan leda till ett mer rörigt, komplext schema än vad som annars behövs för Customer Journey Analytics.</li><li>**Kräver licenser för både Adobe Analytics och Customer Journey Analytics**: Om du använder Analytics-källkopplingen måste du betala för både Adobe Analytics och Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

