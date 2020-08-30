---
title: Hantera filter
description: Lär dig hur du hanterar filter i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 1%

---


# Hantera filter

Filterhanteraren erbjuder många olika sätt att bota segment, t.ex. delning, tagg, godkännande, kopiering, borttagning och markering som favoriter.

Filterhanteraren visar alla filter som du äger och som har delats med dig. Administratörsnivåanvändare kan se alla filter i organisationen. I den här översikten visas användargränssnittet och funktionerna i filterhanteraren.

Öppna filterhanteraren genom att gå till **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** i den översta navigeringen.

## Filter Manager-gränssnitt

![](assets/filter-manager-ui.png)

| # | UI-funktion | Beskrivning |
|---|---|---|
| 1 | Verktygsfältet Filterhantering | När du har markerat ett filter visas verktygsfältet. De flesta hanteringsuppgifter kan slutföras från det här verktygsfältet. |
| 2 | Kryssrutor | Kontrollera ett filter för att hantera det. |
| 4 | Favoriter | Om du klickar på stjärnan bredvid ett filter blir stjärnan gul och filtret markeras som en favorit. |
| 5 | Rubrik och beskrivning | Tillhandahålls i Filter Builder. Om du vill redigera rubrik och beskrivning klickar du på titellänken - det här tar dig tillbaka till Filter Builder. |
| 6 | Rapportsviter | I den här kolumnen anges i vilken rapportsvit filtret senast sparades. |
| 7 | Ägare | Anger vem som äger filtret. Som icke-administratör kan du endast se filter som du äger eller som delats med dig. |
| 8 | Taggar (inte incheckad i kolumnväljare, därför visas inte kolumnen) | Taggar som tillämpades på filtret, antingen av dig eller av personer som delade filtret med dig. |
| 9 | Delad med | Listar individer eller grupper (endast Admin) eller Alla (endast Admin) som du har delat filtret med. |
| 10 | Ändrat datum | Visar det datum då filtret senast ändrades. |
| 11 | Kolumnväljare | (Överst till höger) Gör att du kan välja vilka kolumner som ska visas i Filterhanteraren. |
| 12 | Delad ikon | Anger att filtret delas av dig eller med dig. |
| 13 | Godkänd ikon | Anger att filtret har godkänts av en administratör. |
| 14 | Andra filter | Gör att du kan se filter med taggar, rapportpaket, ägare och annat (Visa alla, Min, Delad med mig, Godkänd, Favoriter). |

## Planfilter

Genom att ägna lite tid åt att planera segment ökar risken för att de kommer att vara användbara för din organisation och att deras nummer kommer att hållas under kontroll.

* Titta på publiken: Vem konsumerar den? Vem kommer ni att dela den med? Vilka grupper kommer att använda detta filter och hur ska jag märka det i enlighet med detta? Detta innebär också att man måste ge en bra filterbeskrivning. Beskrivningen bör åtminstone besvara följande frågor:

   * Vad är filtret användbart för?

   * När ska jag använda det här filtret?

* Kontrollera filteromfånget. som [filterbehållare](/help/components/filters/filters-overview.md) är det bäst som representerar räckvidden? Använd minsta möjliga behållare.

* Bestäm vilka element som ska ingå i filterdefinitionen och vilka värden.

* Tänk på hur du vill att godkännandeprocessen ska utvecklas. Kommer en enda person att granska och godkänna filter eller kommer det att vara ett kommittébeslut?

* Definiera filtren för att visa ett filterbibliotek som ger affärsanvändarna möjlighet att stapla och återanvända filterdelar eller -komponenter på ett modulärt sätt. Vilka &quot;moduler&quot; behöver du definiera för att biblioteket ska bli verklighet?

### Taggsfilter

I filterhanteraren kan du använda taggningsfilter för att ordna dem. Alla användare kan skapa taggar för filter och använda en eller flera taggar på ett segment. Du kan dock bara se taggar för de filter som du äger eller som har delats med dig.

Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:

* Taggar baserade på lagnamn, t.ex. Social Marketing, Mobile Marketing.

* Projekttaggar (analystaggar), t.ex. analys på startsidan.

* Kategoritaggar: Män geografi.

* Arbetsflödestaggar: Ska godkännas. Kursiv för (en specifik affärsenhet)

Så här lägger du till märkord i ett filter:

1. Markera kryssrutan bredvid filtret som du vill tagga i Filterhanteraren. Verktygsfältet för filterhantering visas.

1. Klicka **[!UICONTROL Tag]** och antingen

   * välja från befintliga taggar, eller

   * ange ett nytt taggnamn och tryck på **[!UICONTROL Enter]**.

1. Klicka **[!UICONTROL Tag]** igen för att tagga segmentet.

Taggen ska nu visas i kolumnen Taggar. (Klicka på redskapsikonen längst upp till höger för att hantera dina kolumner.)
Du kan också filtrera på taggar genom att gå till **[!UICONTROL Filters > Tags]**.

### Godkänn filter

I Filterhanteraren kan du konfigurera ett arbetsflöde som innehåller godkännande av filter för olika programnivåer, för specifika avdelningar eller grupper och som är kompatibelt med rapporteringsprinciper.

Så här flaggar du ett filter som godkänt:

1. Markera kryssrutan till vänster om filtertiteln i Filterhanteraren.

1. Klicka **[!UICONTROL Approve]** i uppgiftsfältet för filterhantering.

1. Överväg att dela de godkända segmenten med din organisation.

1. Klicka på **[!UICONTROL OK]**.

   Observera godkännandeikonen bredvid filtret i listan:

   ![](assets/seg_approved.png)

1. Du kan också avvisa ett godkänt segment genom att klicka på **[!UICONTROL Unapprove]**.

### Dela filter

Beroende på dina behörigheter kan du dela filter med hela organisationen, grupper eller enskilda användare.

| Administratör | Icke-administratör |
|---|---|
| Kan dela filter med Alla, med Grupper och med Användare. Se [Dokumentation för administratörskonsol](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) för mer information. | Kan endast dela filter med enskilda användare. |

När ska du dela filter med hela företaget jämfört med bara en grupp användare eller individer? Här följer några exempel på bästa praxis:

* Som administratör kan du dela ett filter med All om det är till nytta för hela företaget och alla är nöjda med att använda det. I så fall bör du också överväga att göra det till ett godkänt filter.

* Som administratör delar du ett filter med en specifik produktprofil om filtret ger ett bra affärsvärde för det teamet. Godkänn inte denna typ av filter officiellt.

* Som administratör eller enskild användare delar du ett filter med andra individer för att kontrollera och validera ett filter. Om det inte visar sig användbart kan det kasseras. Godkänn inte denna typ av filter officiellt.

Så här delar du ett filter:

1. Markera kryssrutan bredvid filtret som du vill dela i Filterhanteraren.

1. I verktygsfältet för filterhantering klickar du på **[!UICONTROL Share]**.

1. Om du är administratör kan du markera Alla eller välja bland Grupper och Användare i organisationen. Som icke-administratör kan du bara se enskilda användare. Använd fältet Sök för att söka efter grupper eller användare. Klicka på **[!UICONTROL Share]**. Ikonen Delad visas bredvid filtret: ![](assets/share_icon.png)

1. Du kan filtrera på filter som delas med dig genom att gå till Filter > Andra filter > Delat med mig.

### Markera filter som favoriter

Att markera segment som favoriter är ett annat sätt att ordna dem så att de blir enkla att använda.

1. I Filterhanteraren markerar du stjärnan bredvid alla filter som du vill markera som favoriter. Stjärnan blir gul när du markerar den.

1. Du kan också filtrera efter favoriter under Filter > Andra filter > Favoriter.

