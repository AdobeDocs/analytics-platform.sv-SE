---
title: Konfigurera målgruppsanalys
description: Lär dig konfigurera målgruppsanalys
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3f4b9e5929f1fe5bf0524236ab956487469c1778
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 0%

---

# Konfigurera målgruppsanalys {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Kopplingsprincip"
>abstract="Sammanslagningsprinciper kombinerar profildata från flera datauppsättningar till enhetliga kundprofiler som används för att skapa målgrupper. Välj &#39;Standardtidsbaserad&#39; om du ser flera sammanfogningsprinciper och du är osäker på vilka du ska välja. Eller fråga ditt datateam om vilka målgrupper som är kopplade till varje kopplingsregel."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Markera den sandlåda som innehåller rätt profildatauppsättningar för Experience Platform. Dessa datauppsättningar måste innehålla de målgruppsdata som du vill rapportera om i Analysis Workspace. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="Person-ID"
>abstract="Välj ett fält i schemat som representerar person-ID:t. Markeringen är begränsad till listan med fält i schemat som är markerade som Identitet och har ett identitetsnamnutrymme."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Använd namnutrymme för primär identitet"
>abstract="Aktivera det här alternativet om du vill att Customer Journey Analytics ska hitta identiteten i identitetskartan som är markerad med ett primär=true-attribut och använda den identiteten som ID för den raden. Den här identiteten är den primärnyckel som används i Experience Platform för partitionering. <br/>Om du låter det här alternativet vara inaktiverat väljer du ett namnutrymme i fältet Identity namespace nedan. Customer Journey Analytics söker efter den här namnområdesnyckeln i varje rads identitetskarta och använder identiteten under namnutrymmet som ID för den raden."

<!-- markdownlint-enable MD034 -->

Med hjälp av målgruppsanalys kan ni importera målgruppsmedlemskapsdata från Experience Platform-profildatauppsättningar till en Customer Journey Analytics-anslutning. Publiken blir tillgänglig som nya dimensioner för användning i Analysis Workspace. Mer detaljerad översiktsinformation om målgruppsanalys finns i [Översikt över målgruppsanalys](/help/connections/audience-analysis/audience-analysis-overview.md).

När du skapar en konfiguration för målgruppsanalys väljer du sandlådan och sammanfogningsprincipen som är kopplad till de Experience Platform-målgrupper som du vill analysera. Customer Journey Analytics skapar en ny uppslagsdatauppsättning och lägger sedan automatiskt till uppslagsdatauppsättningen och profildatauppsättningen till den anslutning du väljer.

Så här skapar du en konfiguration för målgruppsanalys:

1. I Customer Journey Analytics väljer du **[!UICONTROL Data Management]** > **[!UICONTROL Audience analysis configuration]**.

   ![Huvudsida för målgruppsanalys](assets/audience-analysis-empty.png)

1. Välj **[!UICONTROL Create configuration]**.

   ![Skapa konfiguration för målgruppsanalys](assets/audience-analysis-create.png)

1. Ange följande information i avsnittet **[!UICONTROL Details]**:

   | Fält | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Name]** | Ange ett namn för konfigurationen. |
   | **[!UICONTROL Sandbox]** | Markera den sandlåda som innehåller den profildatauppsättning som du vill lägga till i anslutningen. <p>Adobe Experience Platform tillhandahåller [sandlådor](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) som partitionerar en enda plattformsinstans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Du kan tänka dig sandlådor som&quot;dataisoleringar&quot; som innehåller datauppsättningar. Sandlådor används för att styra åtkomst till datauppsättningar.</p> |

1. Ange följande information i avsnittet **[!UICONTROL Profile dataset]**:

   | Fält | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Merge policy]** | Välj den sammanfogningsprincip som motsvarar den profildatauppsättning som du vill använda för målgruppsanalys. <p>Sammanslagningsprinciper avgör hur Adobe Experience Platform kombinerar profildata från flera datauppsättningar till enhetliga kundprofiler som används för att skapa målgrupper. Den sammanfogningsprincip du väljer påverkar vilka profilattribut som ingår i dina målgrupper. Varje dag genereras en ögonblicksbild av dessa data i Experience Platform. Den här ögonblicksbilden ger en statisk vy av data vid en viss tidpunkt och innehåller inga händelsedata.</p><p>Välj sammanfogningsprincipen **[!UICONTROL Default Timebased]** om du ser flera sammanfogningsprinciper och du är osäker på vilken du ska välja. Du kan också rådfråga ditt datateam för att få en bättre förståelse för vilka målgrupper som är kopplade till varje kopplingsregel.</p> |
   | **[!UICONTROL Profile dataset]** | Profildatauppsättningen som är associerad med den sammanfogningsprincip som du har valt. Profildatauppsättningen innehåller de målgruppsdata från Experience Platform som du vill analysera. Den här profildatauppsättningen läggs till i anslutningen som du väljer.<p>När du har valt en sammanfogningsprincip visas export av ögonblicksbilder av profiler. Till exempel: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>Mer information finns i [Datauppsättningar för profilattribut](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) i Experience Platform Dashboards Guide.</p> |

1. Klicka på **[!UICONTROL Connection]** i avsnittet **[!UICONTROL Select a connection]**.

1. I dialogrutan Anslutningar markerar du kryssrutan bredvid anslutningen där du vill lägga till profildatauppsättningen och väljer sedan **[!UICONTROL Use connection]**.

1. Ange följande information för att konfigurera anslutningen:

   | Fält | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Person ID]** | Välj ett fält i schemat som representerar person-ID:t. Markeringen är begränsad till listan med fält i schemat som är markerade som Identitet och som har ett identitetsnamnutrymme.<p>Om det inte finns några person-ID:n att välja från betyder det att ett eller flera person-ID:n inte har definierats i schemat. Mer information finns i [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity).</p> |
   | **[!UICONTROL Use primary identity namespace]** | Det här alternativet visar om du väljer **[!UICONTROL Identity Map]** som person-ID.<p>Aktivera det här alternativet om du vill att Customer Journey Analytics ska hitta identiteten i identitetskartan som är markerad med ett primär=true-attribut och använda den identiteten som ID för den raden. Den här identiteten är den primärnyckel som används i Experience Platform för partitionering. Och den här identiteten är också den primära kandidaten för användning som Customer Journey Analytics person-ID (beroende på hur datauppsättningen konfigureras i en Customer Journey Analytics-anslutning).</p> |
   | **[!UICONTROL Identity namespace]** | Det här alternativet visar om du väljer **[!UICONTROL Identity Map]** som person-ID. Det här alternativet är inaktiverat om du använder namnutrymmet för primärt ID. <p>Identitetsnamnutrymmen är en komponent i [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces). Namnutrymmen fungerar som indikatorer för det sammanhang som en identitet relateras till. Om du anger ett namnutrymme söker Customer Journey Analytics igenom varje rads identitetskarta efter namnutrymmesnyckeln och använder identiteten under namnutrymmet som ID för den raden. Eftersom Customer Journey Analytics inte kan göra en fullständig datauppsättningssökning av alla rader för att avgöra vilka namnutrymmen som finns, visas alla möjliga namnutrymmen i listrutan. Ha koll på vilka namnutrymmen som anges i data. Dessa namnutrymmen identifieras inte automatiskt.</p> |

1. Klicka på **[!UICONTROL Data views]** i avsnittet **[!UICONTROL Select data views]**.

1. I dialogrutan Datavyer markerar du kryssrutan bredvid en eller flera datavyer som du vill använda när du analyserar Experience Platform målgruppsdata inom Analysis Workspace. Dessa datavyer konfigureras automatiskt med Experience Platform målgruppsdata för rapportering.

1. Välj **[!UICONTROL Use data views]**.

1. Välj **[!UICONTROL Create]** för att skapa konfigurationen.

   Eftersom profildatauppsättningen uppdateras en gång per dag är målgrupperna tillgängliga i Customer Journey Analytics datavyer dagen efter att du har skapat konfigurationen för målgruppsanalys.


