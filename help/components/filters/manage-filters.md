---
title: Hantera filter
description: Lär dig hantera filter i Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# Hantera filter

Filterhanteraren erbjuder många sätt att strukturera filter, som att dela, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Filterhanteraren visar alla filter som du äger och som har delats med dig. Administratörsnivåanvändare kan se alla filter i organisationen. I den här översikten visas användargränssnittet och funktionerna i Filterhanteraren.

Öppna Filterhanteraren genom att gå till **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** i den övre navigeringen.

## Användargränssnitt för Filterhanteraren {#ui}

![](assets/filter-manager-ui.png)

| # | Gränssnittsfunktion | Beskrivning |
|---|---|---|
| 1 | Verktygsfältet Filterhantering | När du har markerat ett filter visas det här verktygsfältet. De flesta hanteringsåtgärder kan utföras från det här verktygsfältet. |
| 2 | Kryssrutor | Kontrollera ett filter för att hantera det. |
| 4 | Favoriter | Om du klickar på stjärnan bredvid ett filter ändras stjärnan till gul och filtret markeras som en favorit. |
| 5 | Titel och beskrivning | Finns i Filter Builder. Om du vill redigera titeln och beskrivningen klickar du på titellänken. Då återgår du till Filterverktyget. |
| 7 | Ägare | Anger vem som äger filtret. Om du inte är administratör kan du bara se filter som du äger eller de som delats med dig. |
| 8 | Taggar (inte incheckad i kolumnväljare, därför visas inte kolumnen) | Taggar som har tillämpats på filtret, antingen av dig eller av personer som delat filtret med dig. |
| 9 | Delas med | Visar enskilda personer eller grupper (endast Admin) eller Alla (endast Admin) som du har delat filtret med. |
| 10 | Ändringsdatum | Visar datumet då filtret senast ändrades. |
| 11 | Kolumnväljare | (Överst till höger) Gör att du kan välja vilka kolumner som ska visas i Filterhanteraren. |
| 12 | Ikon för delad | Anger att det här filtret delas av dig eller med dig. |
| 13 | Ikonen Godkänd | Anger att det här filtret har godkänts av en administratör. |
| 14 | Andra filter | Gör att du kan se filter efter taggar, datavyer, ägare och annat (Visa alla, Min, Delas med mig, Godkänd, Favoriter). |

## Planfilter {#plan}

Genom att ägna lite tid åt att planera filter ökar du chansen att de kan vara användbara för din organisation och att deras nummer hålls i schack.

* Tänk på målgruppen: Vem konsumerar den? Med vem ska du dela det? Vilka grupper av människor kommer att använda det här filtret och hur ska jag tagga det därefter? Det innebär också att du får en bra filterbeskrivning. Beskrivningen ska åtminstone svara på följande frågor:

   * Vad är det här filtret användbart för?

   * När ska jag använda det här filtret?

* Bestäm filteromfånget. som [filterbehållare](/help/components/filters/filters-overview.md) bäst representerar omfattningen? Använd den minsta möjliga behållaren.

* Bestäm vilka element som ska inkluderas i filterdefinitionen och vilka värden.

* Tänk på hur ni vill att era godkännandeprocesser ska utvecklas. Kommer en enskild person att granska och godkänna filter eller kommer det att bli ett kommittébeslut?

* Definiera filtren i ett filterbibliotek som ger användarna möjlighet att stapla och återanvända filterdelar eller komponenter på ett modulärt sätt. Vilka moduler behöver du definiera för att göra det här biblioteket till verklighet?

### Taggfilter {#tag}

I Filterhanteraren kan du ordna taggningsfiltren. Alla användare kan skapa taggar för filter och använda en eller flera taggar för ett filter. Men du kan bara se taggar för de filter som du äger eller som har delats med dig.

Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:

* Taggar baserade på teamnamn, som Social Marketing och Mobile Marketing.

* Projekttaggar (analystaggar), t.ex. Sidanalys.

* Kategoritaggar: Män geografi.

* Arbetsflödestaggar: För godkännande. Kuraterad för (en specifik affärsenhet)

Så här taggar du ett filter:

1. Markera kryssrutan bredvid filtret som du vill tagga i Filterhanteraren. Verktygsfältet för filterhantering visas.

1. Klicka **[!UICONTROL Tag]** och antingen

   * välj bland befintliga taggar, eller

   * ange ett nytt taggnamn och tryck på **[!UICONTROL Enter]**.

1. Klicka **[!UICONTROL Tag]** igen för att tagga filtret.

Taggen ska nu visas i kolumnen Taggar. (Klicka på kugghjulsikonen uppe till höger för att hantera kolumnerna.)
Du kan även filtrera på taggar genom att gå till **[!UICONTROL Filters > Tags]**.

### Godkänn filter {#approve}

I Filterhanteraren kan du konfigurera ett arbetsflöde som innefattar godkännande av filter för olika programnivåer, för specifika avdelningar eller grupper, och som är förenligt med rapportobjekten.

Så här flaggar du ett filter som godkänt:

1. Markera kryssrutan till vänster om filtertiteln i Filterhanteraren.

1. Klicka **[!UICONTROL Approve]** i aktivitetsfältet för filterhantering.

1. Överväg att dela de godkända filtren med din organisation.

1. Klicka på **[!UICONTROL OK]**.

   Lägg märke till godkännandeikonen bredvid filtret i listan:

   ![](assets/seg_approved.png)

1. Du kan också avgodkänna ett godkänt filter genom att klicka på **[!UICONTROL Unapprove]**.

### Dela filter {#share}

Beroende på dina behörigheter kan du dela filter med hela organisationen, grupper eller enskilda användare.

| Administratör | Icke-administratör |
|---|---|
| Kan dela filter med Alla, med Grupper och med Användare. Se [Admin Console dokumentation](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) för mer information. | Kan endast dela filter med enskilda användare. |

När bör du dela filter med hela företaget jämfört med bara en grupp användare eller personer? Här är några tips du kan följa:

* Som administratör kan du dela ett filter med Alla om det används av hela företaget och alla känner sig bekväma med att använda det. I det här fallet bör du också överväga att göra det till ett godkänt filter.

* Som administratör kan du dela ett filter med en specifik produktprofil om filtret ger rätt affärsvärde för teamet. Godkänn inte den här typen av filter officiellt.

* Som administratör eller enskild användare kan du dela ett filter med andra för att kontrollera och validera ett filter. Om det inte visar sig användbart kan det kasseras. Godkänn inte den här typen av filter officiellt.

Så här delar du ett filter:

1. Markera kryssrutan bredvid filtret som du vill dela i Filterhanteraren.

1. Klicka på **[!UICONTROL Share]**.

1. Om du är administratör kan du välja Alla eller välja Grupper och Användare i organisationen. Som icke-administratör kan du bara se enskilda användare. Använd sökfältet för att söka efter grupper eller användare. Klicka på **[!UICONTROL Share]**. Ikonen Delad visas bredvid filtret: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

1. Du kan filtrera efter filter som delas med dig genom att gå till Filter > Andra filter > Delade med mig.

### Markera filter som favoriter {#favorites}

Att markera filter som favoriter är ett annat sätt att ordna dem så att de blir lätta att använda.

1. I Filterhanteraren markerar du stjärnan bredvid eventuella filter som du vill markera som favoriter. Stjärnan blir gul när du markerar den.

1. Du kan även filtrera efter favoriter under Filter > Andra filter > Favoriter.
