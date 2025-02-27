---
title: Skapa ett anpassat schema för Customer Journey Analytics
description: Lär dig skapa ett anpassat schema för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 0%

---

# Skapa ett anpassat schema som kan användas med Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Skapa önskat anpassat schema i Adobe Experience Platform"
>abstract="Använd användargränssnittet i Adobe Experience Platform för att skapa ett schema så att Adobe vet vilket format som ska användas för att lagra data.<br><br>I det här steget ska du skapa det schema som din organisation har godkänt. Den beräknade tiden för att skapa schemat i Adobe Experience Platform-gränssnittet är ungefär en vecka, beroende på hur många dimensioner och mått som behöver skapas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Skapa ett schema med fältgruppen Adobe Analytics ExperienceEvent"
>abstract="Använd fältgruppen Adobe Analytics ExperienceEvent för att skapa ett schema i Adobe Experience Platform som innehåller alla fält som används av Adobe Analytics.<br><br>Det är enkelt att skapa ett schema baserat på fältgruppen Adobe Analytics ExperienceEvent, vilket tar bara några minuter att slutföra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Aktivera ditt schema för profil"
>abstract="Aktivera en profil i ditt schema för användning i Adobe CDP i realtid. Det här steget visas eftersom du valde att integrera med Adobe CDP i realtid.<br><br>Eftersom det här steget innebär att du klickar i en enskild ruta tar det här steget bara några minuter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>Innan du börjar skapa ett anpassat schema bör du samarbeta med ditt datateam och andra intressenter i hela organisationen för att identifiera din organisations idealiska schemadesign för Customer Journey Analytics och de andra Adobe Experience Platform-program du använder. Mer information finns i [Skapa ditt schema för användning med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

I följande avsnitt beskrivs hur du skapar ett schema som kan användas med Customer Journey Analytics. Följande schemaalternativ är tillgängliga:

* **Anpassat XDM-schema:** (rekommenderas) Tillåter ett anpassat schema som passar organisationens behov och de plattformsspecifika program som du använder. Eventuella framtida ändringar är okomplicerade.

* **Adobe Analytics-schema som använder fältgruppen Adobe Analytics ExperienceEvent:** Kräver tillägg av tusentals fält som inte behövs. Eventuella nödvändiga framtida ändringar är svårare.

Mer information om de här schemaalternativen finns i [Välja schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Skapa schemat

Det anpassade schema som du definierar för din Web SDK-implementering representerar modellen för de data som du samlar in i Adobe Experience Platform.

Så här skapar du ett anpassat schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. I Adobe Experience Platform väljer du **[!UICONTROL Schemas]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create schema]**.

1. I steget **[!UICONTROL Select a class]** i guiden Skapa schema:

   1. Välj **[!UICONTROL Experience Event]**.

      ![Skapa en schemamarkering för Experience Event](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ett Experience Event-schema används för att modellera _beteendet_ för en profil (som scennamn, push-knapp som läggs till i kundvagnen). Ett enskilt profilschema används för att modellera profilen _attribut_ (som namn, e-post, kön).

   1. Välj **[!UICONTROL Next]**.


1. I [!UICONTROL Name and review step] i guiden [!UICONTROL Create schema]:

   1. Ange en **[!UICONTROL Schema display name]** för ditt schema och (valfritt) en **[!UICONTROL Description]**.

      ![Skapa schemafönster med namnet på schemafälten](assets/create-ee-schema-wizard-step-2.png)

   1. Välj **[!UICONTROL Finish]**.

1. Lägg till alla fältgrupper som innehåller fält som du vill inkludera i schemat.

   Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka ditt schema.

   1. Välj **[!UICONTROL + Add]** i avsnittet **[!UICONTROL Field groups]**.

      ![Lägg till fältgrupp](assets/add-field-group-button.png)

   1. I dialogrutan [!UICONTROL Add fields groups] väljer du fältgruppen **[!UICONTROL AEP Web SDK ExperienceEvent]** i listan.

      ![AEP Web SDK ExperienceEvent, fältgrupp](assets/select-aepwebsdk-experienceevent.png)

      Du kan välja knappen för förhandsgranskning om du vill se en förhandsgranskning av fälten som ingår i den här fältgruppen, till exempel `web > webPageDetails > name`.

      ![AEP Web SDK ExperienceEvent, förhandsgranskning av fältgrupp](assets/aepwebsdk-experiencevent-preview.png)

      Välj **[!UICONTROL Back]** om du vill stänga förhandsgranskningen.

   1. (Valfritt) Markera eventuella ytterligare fältgrupper som du vill ta med.

      Om du väljer att använda Adobe Analytics standardschema i stället för att skapa ett anpassat XDM-schema, kan du lägga till fältgruppen Adobe Analytics ExperienceEvent nu. Adobe rekommenderar dock att du skapar ett anpassat XDM-schema i stället för att lägga till den här fältgruppen.

      Mer information om de här schemaalternativen finns i [Välja schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Välj **[!UICONTROL Add field groups]**.

1. (Valfritt) Om du har anpassade fält som du vill inkludera i ditt schema skapar du en anpassad fältgrupp och lägger till anpassade fält i fältgruppen.

   1. Välj **[!UICONTROL + Add]** i avsnittet **[!UICONTROL Field groups]**.

      ![Lägg till fältgrupp](assets/add-field-group-button.png)

   1. Välj **[!UICONTROL Create new field group]** i dialogrutan [!UICONTROL Add fields groups].

   1. Ange ett visningsnamn och en valfri beskrivning och välj sedan **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet på panelen [!UICONTROL Structure].

   ![Knappen Lägg till fält i exempelschema](assets/example-schema-plus.png)

1. På panelen [!UICONTROL Field Properties] anger du `Identification` som namn, **[!UICONTROL Identification]** som [!UICONTROL Display name], väljer **[!UICONTROL Object]** som [!UICONTROL Type] och väljer **[!UICONTROL ExperienceEvent Core v2.1]** som [!UICONTROL Field Group].

   >[!NOTE]
   >
   >Om fältgruppen inte är tillgänglig söker du efter en annan fältgrupp som innehåller identitetsfält. Eller [skapa en ny fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) och [lägg till nya identitetsfält](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (som `ecid`, `crmId` och andra som du behöver) i fältgruppen och markera den nya fältgruppen.

   ![Identifieringsobjekt](assets/identification-field.png)

   Identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I så fall vill du identifiera profiler som besöker din webbplats med hjälp av Experience Cloud ID och e-postadress. Det finns många andra attribut som du kan använda för att spåra din persons ID (till exempel kundens ID, lojalitets-ID).

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Markera fältet **[!UICONTROL ecid]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** och **[!UICONTROL ECID]** i listan [!UICONTROL Identity namespace] i den högra panelen.

   ![Ange ECID som identitet](./assets/specify-identity.png)

   Du anger Experience Cloud Identity som den primära identitet som Adobe Experience Platform Identity-tjänsten kan använda för att kombinera (sammanfoga) beteendet hos profiler med samma ECID.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i attributet ecid.

1. Markera fältet **[!UICONTROL email]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]** och **[!UICONTROL Email]** i listan [!UICONTROL Identity namespace] på panelen [!UICONTROL Field Properties].

   ![Ange e-postadress som identitet](./assets/specify-email-identity.png)

   Du anger e-postadressen som en annan identitet som kan användas av tjänsten Adobe Experience Platform Identity för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

   Välj **[!UICONTROL Save]**.

1. (Valfritt) Om du vill integrera Customer Journey Analytics med RTCDP markerar du rotelementet i schemat med schemats namn och väljer sedan växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Mer information finns i [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >När du har aktiverat ett schema för profilen kan det inte inaktiveras för profilen.

   ![Aktivera schema för profilen](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

   Du har skapat ett minimalt schema som modellerar de data som du kan hämta från webbplatsen. Schemat gör det möjligt att identifiera profiler med hjälp av Experience Cloud Identity och e-postadress. Genom att aktivera schemat för profil ser du till att data som hämtas från din webbplats läggs till i kundprofilen i realtid.

   Bredvid beteendedata kan du även hämta profilattributdata från din webbplats (till exempel information om profiler som prenumererar på ett nyhetsbrev).

   Så här hämtar du profildata:

   * Skapa ett schema baserat på klassen XDM Individual Profile.

   * Lägg till fältgruppen Profilkärna v2 i schemat.

   * Lägg till ett identifieringsobjekt baserat på fältgruppen Profile Core v2.

   * Definiera Experience Cloud ID som primär identifierare och e-postadress som identifierare.

   * Aktivera schemat för profilen

   Mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema finns i [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html).

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
