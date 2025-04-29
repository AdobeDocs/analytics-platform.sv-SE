---
title: Överför resurser
description: Lär dig överföra komponenter från en användare till en annan
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# Överför resurser

Med verktyget Resursöverföring kan du överföra ägarskap av resurser till andra användare. Assets kan innehålla komponenter som projekt, segment, datumintervall, beräknade värden, anteckningar, aviseringar och schemalagda projekt.

Assets är ofta knutet till en enskild ägare och kan i vissa fall, t.ex. segment och beräknade värden, inte redigeras eller delas ens av administratörer. När användare lämnar organisationen eller ändrar sin roll kan det bli nödvändigt att överföra ägarskapet av dessa resurser till andra användare för att säkerställa kontinuitet och lämplig åtkomst.

## Behörigheter

Resursöverföring kräver produktadministratörsbehörighet för Customer Journey Analytics.

## Överför resurser

1. I CJA går du till **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]**.

   ![Menyobjekt för resursöverföring](/help/tools/asset-transfer/assets/asset-transfer.png)

1. I dialogrutan **[!UICONTROL Users]** söker du efter och väljer den användare som du vill överföra resurser från.

   >[!IMPORTANT]
   >
   >Du kan bara göra en 1:1-överföring från en användare till en annan användare. 1:N- eller många-till-1-överföringar stöds inte.


1. När du har valt en användare visas alternativet Överför resurser längst ned på skärmen.

   ![Menyalternativet Överför resurser](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicka på **[!UICONTROL Transfer assets]**.

1. På skärmen **[!UICONTROL Transfer assets]** väljer du först mottagaren som du vill överföra resurser till.

1. Gå igenom varje komponentmapp i den vänstra navigeringen för att välja enskilda komponenter eller alla resurser i en mapp som ska överföras.

   >[!NOTE]
   >
   >Att överföra resurser från en administratör till en annan person uppgraderar inte mottagaren till en administratör.


   >[!NOTE]
   >
   >    När du överför resurser som refererar till andra komponenter (till exempel projekt som refererar till andra segment och beräknade värden), delas komponenter som inte ägs av den aktuella ägaren av projektet endast med mottagaren. Ägarskapet för alla andra komponenter överförs till mottagaren.

1. Om du vill markera _alla_ resurser i en mapp markerar du kryssrutan bredvid **[!UICONTROL Name]** högst upp i tabellen.

   ![välj resurser att överföra](/help/tools/asset-transfer/assets/select-assets.png)

1. Klicka på **[!UICONTROL Transfer]** överst till höger när du har gjort alla dina val.

1. Klicka på **[!UICONTROL Confirm]** när bekräftelsemeddelandet visas.

   >[!IMPORTANT]
   >
   >Stäng inte skärmen under överföringen för att undvika att processen avbryts. Detta ger en smidig överföringsupplevelse.

## Överföringsresultat

Det finns tre möjliga konsekvenser för en överföring:

- **Överföringen lyckades**: &quot;Assets har överförts.&quot;

- **Delvis slutförd**: &quot;Vissa resurser har överförts.&quot;

- **Överföringsfel**: &quot;Det gick inte att överföra resurser. Försök igen.&quot;

### Potentiella orsaker till misslyckad överföring av tillgångar

- Beroende tjänster som orsakar fel: Resursöverföringen interagerar med olika tjänster för varje komponenttyp (t.ex. nätverksproblem, problem med underordnade tjänster), vilket kan orsaka ett partiellt eller fullständigt fel eller återkommande fel.

- Komponent saknas eller har överförts av en annan administratör: En komponent togs bort av en annan användare, eller överfördes av en annan administratör till någon annan, medan ett överföringsjobb fortfarande pågår.

- API POST-brödtexten fylls inte i korrekt: en komponent kan inte skickas i API POST-brödtexten när flera komponenttyper är markerade.

- Användaren finns inte: Användaren togs bort från mellanöverföringen eller är ogiltig av en annan anledning. Om användaren är ogiltig innan överföringen startar kommer verktyget att fånga upp detta och kommer inte att bearbeta jobbet. Om användaren togs bort från mitten av överföringen kan detta orsaka partiella fel.

- Anslutnings-/nätverksfel: anslutningen avbryts vid mellanöverföring. Eventuella batchar av överföringsjobb som redan har skickats till backend-servern fortsätter att slutföras, men användaren kommer inte att se överföringsresultatmeddelandet med en sammanfattning av vad som lyckades och vad som misslyckades.

- Fliken Webbläsare stängd mitt i överföringen: För mycket stora överföringar, om webbläsarfliken är stängd eller sidan navigeras bort från mittöverföringen, kommer bara nätverksbegäranden som gjorts innan flikstängning/sidnavigering sker att överföra resurser korrekt. Om användaren går tillbaka till sidan får han/hon inte något svarsstatusmeddelande som anger vilka resurser som överfördes och vilka som inte gjorde det.

## Överför resurser under uppgradering från Adobe Analytics till Customer Journey Analytics

Ett av de största användningsområdena för överföring av mediefiler är vid uppgradering från Adobe Analytics till Customer Journey Analytics.

Med funktionen [Komponentmigrering](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) i Adobe Analytics kan du migrera administratörsägda projekt till andra administratörer. Alla komponenter som ingår i dessa projekt återskapas sedan i Customer Journey Analytics och mottagaradministratören äger alla dessa komponenter, oavsett vem som skapade dem.

Med det här verktyget kan administratörer sedan omtilldela komponenter till sina rättsinnehavare, oavsett om de är administratörer eller inte.

>[!IMPORTANT]
>
>Även om du kan överföra komponenter med det här verktyget måste du som administratör fortfarande se till att mottagaren har tillgång till de datavyer som krävs för att visa/använda dessa komponenter. Du kan visa och tilldela behörigheter i [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html).

## Exportera till CSV

Med alternativet **[!UICONTROL Export to CSV]** kan administratörer bara hämta en lista över användare som visas i en CSV-fil. De kan inte exportera en lista med överförda resurser till en CSV-fil.

## Inaktiva användare

Alla tidigare borttagna användare visas under en Inaktiva användare-post tillsammans med alla deras överordnade komponenter. Dessa komponenter kan överföras till en ny mottagare. Den här funktionen blir tillgänglig i januari.

![Inaktiva användare visas i gränssnittet för överföring av resurser](assets/inactive-users.png)

