---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 0%

---

# Skapa ett XDM-schema som ska användas med Customer Journey Analytics

>[!NOTE]
>
>Den här dokumentationen bör användas när uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) har slutförts.
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare steg som har genererats dynamiskt för din organisation.
>
>När du är klar med stegen på den här sidan fortsätter du med uppgraderingsstegen som har skapats dynamiskt för din organisation från uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

>[!IMPORTANT]
>
>Innan du börjar skapa ditt XDM-schema bör du samarbeta med datagruppen och andra intressenter i hela organisationen för att identifiera din organisations idealiska schemadesign för Customer Journey Analytics och andra Adobe Experience Platform-program som du använder. Mer information finns i [Skapa ditt schema för användning med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Adobe rekommenderar att du skapar ett XDM-schema (Experience Data Model) när du uppgraderar till Customer Journey Analytics. Ett XDM-schema möjliggör ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder. När du behöver ändra schemat behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras.

## Skapa schemat

Det XDM-schema som du definierar representerar modellen för de data som du samlar in i Adobe Experience Platform.

Så här skapar du ett schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. I Adobe Experience Platform väljer du **[!UICONTROL Schemas]** i [!UICONTROL DATA MANAGEMENT] till vänster.

1. Välj **[!UICONTROL Create schema]**.

1. I steget Välj en klass i guiden Skapa schema:

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

1. På fliken Struktur i exempelschemat:

   1. Välj **[!UICONTROL + Add]** i [!UICONTROL Field groups].

      ![Lägg till fältgrupp](assets/add-field-group-button.png)

      Fältgrupper är återanvändbara samlingar av objekt och attribut som gör att du enkelt kan utöka ditt schema.

   1. I dialogrutan [!UICONTROL Add fields groups] väljer du fältgruppen **[!UICONTROL AEP Web SDK ExperienceEvent]** i listan.

      ![AEP Web SDK ExperienceEvent, fältgrupp](assets/select-aepwebsdk-experienceevent.png)

      Du kan välja knappen för förhandsgranskning om du vill se en förhandsgranskning av fälten som ingår i den här fältgruppen, till exempel `web > webPageDetails > name`.

      ![Förhandsgranskning av AEP Web SDK ExperienceEvent-fältgrupp](assets/aepwebsdk-experiencevent-preview.png)

      Välj **[!UICONTROL Back]** om du vill stänga förhandsgranskningen.

   1. Välj **[!UICONTROL Add field groups]**.

1. Välj **[!UICONTROL +]** bredvid schemanamnet på panelen [!UICONTROL Structure].

   ![Knappen Lägg till fält i exempelschema](assets/example-schema-plus.png)

1. På panelen [!UICONTROL Field Properties] anger du `Identification` som namn, **[!UICONTROL Identification]** som [!UICONTROL Display name], väljer **[!UICONTROL Object]** som [!UICONTROL Type] och väljer **[!UICONTROL ExperienceEvent Core v2.1]** som [!UICONTROL Field Group].

   >[!NOTE]
   >
   >Om fältgruppen inte är tillgänglig söker du efter en annan fältgrupp som innehåller identitetsfält. Eller [skapa en ny fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) och [lägg till nya identitetsfält](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (som `ecid`, `crmId` och andra som du behöver) i fältgruppen och markera den nya fältgruppen.

   ![Identifieringsobjekt](assets/identification-field.png)

   Identifieringsobjektet lägger till identifieringsfunktioner i ditt schema. I ditt fall vill du identifiera profiler som besöker din webbplats med hjälp av Experience Cloud-ID och e-postadress. Det finns många andra attribut som du kan använda för att spåra din persons ID (till exempel kundens ID, lojalitets-ID).

   Välj **[!UICONTROL Apply]** om du vill lägga till det här objektet i ditt schema.

1. Markera fältet **[!UICONTROL ecid]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]**, **[!UICONTROL Primary Identity]** och **[!UICONTROL ECID]** i listan [!UICONTROL Identity namespace] i den högra panelen.

   ![Ange ECID som identitet](./assets/specify-identity.png)

   Du anger Experience Cloud Identity som den primära identitet som Adobe Experience Platform Identity-tjänsten kan använda för att kombinera (sy ihop) beteendet hos profiler med samma ECID.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i attributet ecid.

1. Markera fältet **[!UICONTROL email]** i det identifieringsobjekt som du nyss lade till och välj **[!UICONTROL Identity]** och **[!UICONTROL Email]** i listan [!UICONTROL Identity namespace] på panelen [!UICONTROL Field Properties].

   ![Ange e-postadress som identitet](./assets/specify-email-identity.png)

   Du anger e-postadressen som en annan identitet som kan användas av tjänsten Adobe Experience Platform Identity för att kombinera (sammanfoga) beteendet för profiler.

   Välj **[!UICONTROL Apply]**. En fingeravtrycksikon visas i e-postattributet.

   Välj **[!UICONTROL Save]**.

1. Markera rotelementet i schemat som visar schemats namn och välj sedan växeln **[!UICONTROL Profile]**.

   Du uppmanas att aktivera schemat för profilen. När data har aktiverats, när data har importerats till datauppsättningar som baseras på detta schema, sammanfogas dessa data i kundprofilen i realtid.

   Mer information finns i [Aktivera schemat för användning i kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    När du har sparat ett schema som är aktiverat för profilen kan det inte längre inaktiveras för profilen.

   ![Aktivera schema för profilen](./assets/enable-for-profile.png)

1. Välj **[!UICONTROL Save]** om du vill spara ditt schema.

   Du har skapat ett minimalt schema som modellerar de data som du kan hämta från webbplatsen. Schemat gör det möjligt att identifiera profiler med hjälp av Experience Cloud-identitet och e-postadress. Genom att aktivera schemat för profil ser du till att data som hämtas från din webbplats läggs till i kundprofilen i realtid.

   Bredvid beteendedata kan du även hämta profilattributdata från din webbplats (till exempel information om profiler som prenumererar på ett nyhetsbrev).

   Så här hämtar du profildata:

   * Skapa ett schema baserat på klassen XDM Individual Profile.

   * Lägg till fältgruppen Profilkärna v2 i schemat.

   * Lägg till ett identifieringsobjekt baserat på fältgruppen Profile Core v2.

   * Definiera Experience Cloud-ID som primär identifierare och e-post som identifierare.

   * Aktivera schemat för profilen

   Mer information om hur du lägger till och tar bort fältgrupper och enskilda fält i ett schema finns i [Skapa och redigera scheman i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html).

1. Följ uppgraderingsstegen som har skapats dynamiskt för din organisation från uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
