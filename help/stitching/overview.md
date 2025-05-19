---
title: Översikt över titlar
description: Översikt över häftning
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 1a697ce0372d1cb544940778850714a198a000ec
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---

# Översikt över titlar

>[!NOTE]
>
>Du måste ha paketet **Select** eller senare (för [fältbaserad sammanfogning](fbs.md)) eller paketet **Prime** eller senare (för [diagrambaserad sammanfogning](gbs.md)) för att kunna använda de funktioner som beskrivs i det här avsnittet. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

Identitetssammanfogning (eller helt enkelt sammanfogning) är en kraftfull funktion som ökar en händelsedatamängds lämplighet för flerkanalsanalys. Flerkanalsanalys är ett vanligt användningsfall som Customer Journey Analytics kan hantera och som gör det möjligt att kombinera och köra rapporter sömlöst på flera datauppsättningar från olika kanaler, baserat på en gemensam identifierare (person-ID).

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren stöter på ett problem med sin beställning och ger sedan kundtjänstteamet ett samtal för att hjälpa till att lösa det. Med flerkanalsanalys kan ni attribuera callcenter-händelser till den annons som de ursprungligen klickade på.

Tyvärr är inte alla händelsebaserade datauppsättningar som är en del av din anslutning i Customer Journey Analytics tillräckligt kompletta med data för att stödja denna attribuering. I synnerhet har webbaserade eller mobilbaserade upplevelsedatamängder ofta ingen faktisk person-ID-information tillgänglig för alla händelser.

Med hjälp av häftning kan du skriva in identiteter på nytt i en datamängds rader, så att person-ID (sammanfogat ID) är tillgängligt för varje händelse. Stitching tittar på användardata från både autentiserade och oautentiserade sessioner för att avgöra det gemensamma tillfälliga ID-värdet (person-ID) som kan användas som sammanfogat ID. Denna inmatning gör det möjligt att lösa olika poster till ett enda sammanfogat ID för analys på personnivå, i stället för på enhets- eller cookienivå.

Customer Journey Analytics stöder två typer av sammanfogning: [fältbaserad sammanfogning](fbs.md) och [diagrambaserad sammanfogning](gbs.md).

## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att utföra flerkanalsanalys korrekt.

Innan du använder stygn bör du kontrollera att din organisation har förberetts med följande:

- Stitching inkluderar sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du aktiverar sammanfogning av en händelsedatamängd. Mer information finns i [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity).

- Importera önskade data till Adobe Experience Platform:

   - Information om Adobe Analytics finns i [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Andra typer av data finns i [Skapa ett schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) och [Infoga data](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) i Adobe Experience Platform-dokumentationen.

Du kan dra nytta av flerkanalsanalys om du kombinerar en eller flera av dina sammanfogade datauppsättningar med andra datauppsättningar, till exempel callcenter-data, som en del av arbetet med att definiera din Customer Journey Analytics-anslutning. Den här anslutningskonfigurationen förutsätter att dessa andra datauppsättningar redan innehåller ett person-ID på varje rad, som liknar det sammanfogade ID:t.


## Begränsningar

>[!IMPORTANT]
>
>
>- Använd alla ändringar du gör i källhändelsens dataschema även i det nya sammanfogade dataschemat, annars bryts den sammanfogade datauppsättningen.
>
>- Om du tar bort källdatauppsättningen avbryts bearbetningen av den sammanfogade datauppsättningen och tas bort av systemet.
>
>- Dataanvändningsetiketter sprids inte automatiskt till det sammanslagna dataset-schemat. Om du har använt dataanvändningsetiketter på källdataschemat måste du använda dessa dataanvändningsetiketter manuellt på det sammanslagna dataset-schemat. Mer information finns i [Hantera dataanvändningsetiketter i Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview).

Stitching är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

- Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
- Med hjälp av fästfunktionen omvandlas inte det fält som används för sammanfogning på något sätt. Vid Stitching används värdet i det angivna fältet som det finns i den osydda datauppsättningen inom datarinden.
- Smältningsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i fältet, och ibland ordet &#39;BOB&#39; visas, behandlas dessa id:n som två separata personer.

Försäkra dig om att du inte förväxlar stygn med:

- Sammanfogningen av två eller flera datauppsättningar. Gäller endast en datauppsättning. Sammanfogning av datauppsättningar sker som ett resultat av att en Customer Journey Analytics-anslutning skapas och att samma person-ID väljs för de markerade datauppsättningarna i anslutningen.

- Sammanfogning av två datauppsättningar. I Customer Journey Analytics används ofta en join för uppslag eller klassificeringar i Analysis Workspace. Även om sammanfogning använder sammanfogningsfunktioner innebär själva processen mer än sammanfogningar.

>[!MORELIKETHIS]
>
>[Fältbaserad häftning](fbs.md)
>[Diagrambaserad sammanfogning ](gbs.md)
>[Använd sammanfogning](use-stitching.md)
>[Validera sammanfogning ](validate.md)
>[Vanliga frågor om stygn](faq.md)

