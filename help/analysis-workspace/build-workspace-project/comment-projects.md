---
description: Lär dig kommentera ett projekt i Analysis Workspace
title: Lägga till och visa kommentarer i projekt
feature: Workspace Basics
role: User
exl-id: 05f69a1c-31c2-40d8-ae8b-a084169897b1
source-git-commit: 91ac84764a186d81f3270bb3ec9673d93b11bd38
workflow-type: tm+mt
source-wordcount: '1820'
ht-degree: 0%

---

# Lägga till och hantera kommentarer i projekt {#comment-on-projects}

{{release-limited-testing}}

Med kommentarerna i Analysis Workspace kan du dela insikter och ställa frågor i samband med ett Analysis Workspace-projekt. Detta kan effektivisera diskussioner om data och hålla konversationer inom ramen för de data som ska diskuteras.

>[!NOTE]
>
>Möjligheten att lägga till och hantera kommentarer i ett projekt kan inaktiveras antingen på projektnivå eller på organisationsnivå. Om du inte kan lägga till och hantera kommentarer enligt beskrivningen i det här avsnittet har Customer Journey Analytics-administratören eller projektägaren inaktiverat den här funktionen.
>
>* **Projekt:** Projektägaren kan inaktivera den här funktionen för projektet, enligt beskrivningen i [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md).
>* **Organisation:** Customer Journey Analytics-administratören kan inaktivera den här funktionaliteten för organisationen enligt beskrivningen i [Inställningar](/help/analysis-workspace/user-preferences.md).

## Visa kommentarer

Du kan visa kommentarer från kommentarområdet i den högra listen eller från kommentarmärket om det finns några.

>[!NOTE]
>
>Ett projekt måste sparas innan kommentarsområdet visas i den högra listen. Om projektet inte har sparats tidigare måste du [spara projektet](/help/analysis-workspace/build-workspace-project/save-projects.md) innan du lägger till kommentarer.


![Visa kommentarer i Analysis Workspace](assets/workspace-comments-view.png)

### Visa kommentarer i kommentarsområdet

Alla kommentarer som görs i ett Analysis Workspace-projekt visas i kommentarsområdet i den högra listen. Det totala antalet kommentarer visas på kommentarsikonen.

1. Som standard utökas kommentarsområdet för varje projekt i Analysis Workspace första gången du öppnar ett projekt.

   Välj ikonen för kommentarområdet till höger om ett projekt för att öppna eller stänga kommentarsområdet.

   ![Kommentarsområdet stängt](assets/comments-area-closed.png)

   Varje kommentar visar en tidsstämpel för dagen som kommentaren publicerades. Om kommentaren bokfördes den aktuella dagen visas tidpunkten på dagen. För musen över dag eller tid för att visa hela datumet och tiden som kommentaren bokfördes.

1. (Valfritt) Om du vill söka i kommentarområdet väljer du sökikonen ![sökikonen](assets/comments-search-icon.png) och skriver sedan ett ord eller en fras. Kommentarsområdet filtreras så att det bara innehåller kommentarer som innehåller det ordet eller den frasen.

### Visa kommentarsemblem i ett projekt

Kommentarer som görs [ i ett visst område i projektet ](#comment-on-a-specific-area-of-the-project) har ett **kommentarsemblem** ![som visas över det område i projektet som kommentaren hör till.](assets/comment-indicator.svg) Välj ett märke för att visa kommentaren. När du har valt märket kan du markera själva kommentaren för att markera kommentaren i kommentarområdet till höger.

Nummer visas på varje emblem i ett projekt och ordnas i den ordning som de skapades. Om flera kommentarer placeras i samma område i ett projekt, visar märket 3 punkter ![kommentarsemblem flera](assets/comment-indicator-multiple.svg). Markera 3-punktssymbolen om du vill visa alla kommentarer i det området.

<!-- Insert screeshot-->

Så här döljer du alla kommentarmärken från ett projekt:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Aktivera alternativet **[!UICONTROL Hide placed badges]** längst ned i kommentarsområdet.

## Lägg till kommentarer

Du kan lägga till en kommentar som refererar till ett visst område i projektet eller lägga till en allmän kommentar.

### Kommentera ett visst område i projektet

Så här kommenterar du ett visst område i projektet (till exempel ett måttvärde i en frihandstabell):

1. Med projektet öppet i Analysis Workspace högerklickar du på det område i projektet där du vill infoga kommentaren.

   Alla visualiseringar har stöd för kommentarmärken i visualiseringshuvudet, men endast följande visualiseringar har stöd för kommentarmärken på specifika datapunkter i visualiseringen:

   * Frihandsregister
   * Kohortabell
   * Linje

   <!--add screenshot-->

1. Välj **[!UICONTROL Add comment]**.

1. Ange din kommentar i fältet **[!UICONTROL New comment]**.

   Kommentarer kan innehålla upp till 15 000 tecken och kan innehålla grundläggande markeringar, hyperlänkar, punktlistor, numrerade listor och känslolägesikoner.

1. (Valfritt) Meddela en annan person om din kommentar genom att skriva @-symbolen följt av namnet på personen. Mer information om hur du använder @-symbolen för att meddela andra finns i [Inkludera andra i en kommentar](#include-others-in-a-comment).

1. Välj **[!UICONTROL Submit]**.

   Ett **kommentarsemblem** ![kommentarsemblem](assets/comment-indicator.png) placeras i det område i Workspace-projektet där du lade till kommentaren, vilket beskrivs i [Visa kommentarsemblem i ett projekt](#view-comment-badges-in-a-project). Kommentaren visas också längst upp i kommentarsområdet i den högra listen.

### Lägg till en allmän kommentar om projektet

Så här lägger du till kommentarer i ett projekt i Analysis Workspace:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace. <!-- add screen shot -->

1. Ange din kommentar i fältet **[!UICONTROL New comment]**.

   Kommentarer kan innehålla upp till 15 000 tecken och kan innehålla grundläggande markeringar, hyperlänkar, punktlistor, numrerade listor och känslolägesikoner.

1. (Valfritt) Meddela en annan person om din kommentar genom att skriva @-symbolen följt av namnet på personen. Mer information om hur du använder @-symbolen för att meddela andra finns i [Inkludera andra i en kommentar](#include-others-in-a-comment).

1. Välj **[!UICONTROL Submit]**.

   Kommentaren visas högst upp i kommentarsområdet, vilket beskrivs i [Visa kommentarer i kommentarsområdet](#view-comments-in-the-comments-area).

## Inkludera andra i en kommentar

Kommentarsfunktionen i Analysis Workspace gör det enklare att samarbeta med andra.

Tänk på följande när du använder symbolen @ för att inkludera personer i en kommentar:

* Personer som du inkluderar får meddelanden baserade på deras meddelandeinställningar för Adobe Experience Cloud.

  Mer information finns i [Få meddelanden om kommentarer](#receive-notifications-about-comments).

* Du kan inkludera vem som helst i en kommentar som finns i din organisation och har tillgång till Customer Journey Analytics, men om du gör det får de inte automatiskt åtkomst att redigera projektet.

Så här tar du med en annan person i kommentaren:

1. Skriv in @-symbolen och börja sedan skriva förnamnet, efternamnet eller e-postadressen för den person som du vill ta med.

   ![tagga användare](assets/comments-tag-user.png)

1. Markera personens namn när det visas i listrutan.

## Svara på en kommentar

1. Öppna det projekt i Analysis Workspace där du vill lägga till en kommentar.

1. Markera ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) i den högra listen i Analysis Workspace och välj sedan **[!UICONTROL Reply]** bredvid kommentaren som du vill svara på.

   Om du vill ta med texten i kommentaren som du svarar på, med den ursprungliga texten omsluten av en citattagg, markerar du 3-punktsikonen bredvid den specifika kommentaren eller det svar som du vill svara på och väljer sedan **[!UICONTROL Quote reply]**. Ett svar på en offert är ett bra sätt att ange vilken kommentar eller vilket svar din kommentar hänvisar till.

   eller

   Markera kommentarsikonen på panelen eller visualiseringen där kommentaren gjordes och välj sedan **[!UICONTROL Reply]**.

1. Ange din kommentar i fältet **[!UICONTROL New comment]**.

   Kommentarer kan innehålla upp till 15 000 tecken och kan innehålla grundläggande markeringar, hyperlänkar, punktlistor, numrerade listor och känslolägesikoner.

1. (Valfritt) Meddela en annan person om din kommentar genom att skriva @-symbolen följt av namnet på personen. Mer information om hur du använder @-symbolen för att meddela andra finns i [Inkludera andra i en kommentar](#include-others-in-a-comment).

1. Välj **[!UICONTROL Submit]**.

## Få meddelanden om kommentarer

Projektägare och [specifika personer som du anger](#include-others-in-a-comment) får meddelanden baserat på deras Adobe Experience Cloud-meddelandeinställningar. Som standard får de ett meddelande i appen som visas från [Experience Cloud-ikonen ](https://experienceleague.adobe.com/sv/docs/core-services/interface/features/account-preferences#view-notifications) ![Experience Cloud-meddelandeikonen](assets/experience-cloud-notification.svg) i Customer Journey Analytics.

Dessutom kan användare konfigurera sina inställningar för Experience Cloud-meddelanden så att de får e-postmeddelanden och Slack-meddelanden genom att [prenumerera på e-postmeddelanden](https://experienceleague.adobe.com/sv/docs/core-services/interface/features/account-preferences#subscribe-to-in-app-and-email-notifications) och [prenumerera på Slack-meddelanden](https://experienceleague.adobe.com/sv/docs/core-services/interface/features/account-preferences#slack).

## Placera ett emblem för en befintlig kommentar

Om det finns en kommentar i kommentarsområdet på den högra listen men den inte har något emblem i projektet ännu, kan du lägga till märket.

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Välj ikonen ![Mer ](/help/assets/icons/MoreSmallList.svg) bredvid kommentaren som du vill placera ett märke för och välj sedan **[!UICONTROL Place badge]**.

1. Markera det område i projektet där du vill placera emblemet för den befintliga kommentaren.

   Ett **kommentarsemblem** ![kommentarsemblem](assets/comment-indicator.png) placeras i det område i Workspace-projektet som du har valt. Kommentaren visas också längst upp i kommentarsområdet i den högra listen.

   Mer information finns i [Visa kommentarsemblem i ett projekt](#view-comment-badges-in-a-project).

Så här tar du bort ett märke:

1. Markera den bricka som du vill ta bort och välj sedan **[!UICONTROL Remove badge]**.

   Märket tas bort, men kommentaren är fortfarande tillgänglig i kommentarsområdet till höger.

## Flytta ett emblem för en befintlig kommentar

Du kan flytta ett kommentarsmärke som redan finns för en befintlig kommentar.

1. Med projektet öppet i Analysis Workspace letar du reda på märket för kommentaren som du vill flytta.

1. Högerklicka på märket och välj sedan **[!UICONTROL Move placement]**.

1. Markera det område i projektet där du vill placera emblemet.

<!-- add section about adding images to comments. will be available at GA. Include that "you can have a maximum of 5 images per comment, and each image can be up to 2 MB." -->

## Kopiera länken till en kommentar

Du kan kopiera länken till en kommentar och dela länken med andra. Det är bara personer som redan har åtkomst till projektet som har åtkomst till det via länken.

Så här kopierar du länken till en kommentar:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Markera ikonen ![Mer ](/help/assets/icons/MoreSmallList.svg) bredvid kommentaren vars länk du vill kopiera och välj sedan **[!UICONTROL Copy link]**.

   Länken kopieras till systemets Urklipp. Du kan klistra in länken i ett e-postmeddelande eller i annan typ av meddelande.

## Kopiera texten i en kommentar

Du kan kopiera brödtexten i en kommentar och dela den med andra.

Så här kopierar du brödtexten i en kommentar:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Markera ikonen ![Mer ](/help/assets/icons/MoreSmallList.svg) bredvid kommentaren som innehåller texten som du vill kopiera och välj sedan **[!UICONTROL Copy body text]**.

   Kommentarens brödtext kopieras till systemets Urklipp.

## Gilla en kommentar

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Välj **[!UICONTROL Like]** under kommentaren som du vill godkänna.

## Ta bort en kommentar

När du tar bort en kommentar tas även den ursprungliga kommentaren och eventuella svar eller bilagor bort.

Borttagna kommentarer kan inte återställas.

Så här tar du bort en kommentar:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Markera ikonen ![Mer ](/help/assets/icons/MoreSmallList.svg) bredvid kommentaren som du vill ta bort och välj sedan **[!UICONTROL Delete]**.

1. Välj **[!UICONTROL Delete]** igen för att bekräfta borttagningen.

## Lösa en kommentar

När du löser en kommentar markeras kommentaren som löst och dold i kommentarområdet. Om kommentaren har ett kopplat märke tas märket bort från projektet.

Så här löser du en kommentar:

1. Med projektet öppet i Analysis Workspace väljer du ikonen för kommentarområdet ![Ikonen för kommentarområdet](/help/assets/icons/Comment.svg) till höger i Analysis Workspace.

1. Välj ikonen ![Mer ](/help/assets/icons/MoreSmallList.svg) bredvid kommentaren som du vill lösa och välj sedan **[!UICONTROL Resolve]**.

1. Bekräfta genom att välja **[!UICONTROL Resolve]** igen.

Som standard är lösta kommentarer dolda i kommentarområdet. Så här visar du lösta kommentarer:

1. Markera filterikonen i kommentarsområdet och avmarkera sedan alternativet **[!UICONTROL Hide resolved comments]**.
