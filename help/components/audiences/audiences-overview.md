---
title: CJA Auditions publishing overview
description: Läs mer om begreppet målgruppspublicering i Customer Journey Analytics
source-git-commit: ba98ee1372c4ce396af3f41aeb98bc42ee6d02ce
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 1%

---


# CJA Audience publishing - översikt

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

Nu kan du skapa och publicera målgrupper som identifierats i Customer Journey Analytics (CJA) till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) i Adobe Experience Platform för kundanpassning och personalisering. Med kundprofilen i realtid kan ni se en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online, offline, CRM och tredje part. Med hjälp av profilen kan ni sammanställa kunddata i en enhetlig vy som ger ett användbart, tidsstämplat konto för varje kundinteraktion.

Att publicera målgrupper är ett tydligt sätt att vidta åtgärder för insikter som hittas i CJA. Dessa åtgärder kan omfatta:

* Skicka e-post till den här målgruppen.
* Skicka push-meddelanden till den här målgruppen.
* Använda publiken för en resa i Adobe Journey Optimizer.
* Exportera målgruppen till en tredje part via ett Experience Platform-mål.

## Viktiga termer

**Målgrupp**: En uppsättning eller en lista med identiteter som har både ett namnutrymme och ett specifikt ID relaterat till det namnutrymmet. Publiken kan flyttas från Adobe Experience Platform och program som finns ovanpå det (t.ex. CJA). Publiker kan innehålla blandade namnutrymmen.

**Filter**: En uppsättning regler som, när de utvärderas över en datauppsättning under en tidsperiod, skapar en delmängd av data. Ett filter kan användas för att skapa en målgrupp i kombination med andra stödtjänster. Filter definieras och bevaras i CJA.

**Filter** kontra **Segment**: CJA använder inte begreppet&quot;segment&quot;, utan i stället&quot;filter&quot;. Båda är en uppsättning regler som kan innehålla liknande logik, men de ger olika utdata. Ett filter används för att begränsa en datauppsättning för analysändamål. Ett segment används för att skapa en lista med identiteter som kan användas för aktivering. Segment producerar målgrupper i kundprofilen i realtid, men inte filter (enbart). CJA Audience Publishing är den process genom vilken vi använder ett CJA-filter för att skapa en målgrupp som kan konsumeras av kundprofilen i realtid.

## Behörigheter

Administratörer får automatiskt [!UICONTROL Audience Publishing] behörighet i Adobe Admin Console. De kan ge behörighet till enskilda användare.

## Nästa steg

* [Skapa och publicera målgrupper](/help/components/audiences/publish.md)
* [Hantera målgrupper](/help/components/audiences/manage.md)


