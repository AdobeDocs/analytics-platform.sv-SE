---
title: Ett exempel på ett B2B-projekt
description: Lär dig konfigurera, konfigurera och rapportera om B2B-data
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 0%

---

# Ett exempel på ett personbaserat B2B-projekt

I den här artikeln visas ett exempel på hur du vill rapportera persondata i Customer Journey Analytics korrekt i samband med en vanlig personbaserad B2B-konfiguration. En sådan konfiguration underlättas av [Real-Time CDP B2B edition](https://experienceleague.adobe.com/sv/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview).  I användningsexemplet förklaras hur du konfigurerar, konfigurerar och rapporterar profilbaserade B2B-data i Customer Journey Analytics.

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} Ett separat avsnitt för kontobaserade användningsfall för rapportering publiceras med utgåvan av [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md).

## Anslutning

Definiera anslutningen så att den inkluderar alla relevanta B2B-datauppsättningar från Experience Platform. Datauppsättningar som du kan överväga att lägga till i anslutningen:

| Datauppsättning (valfritt) | Schema | Schematyp | Basklass | Beskrivning |
|---|---|---|---|---|
| B2B-aktivitetsdatauppsättning | B2B-aktivitetsschema | Händelse | XDM ExperienceEvent | En ExperienceEvent är ett faktaregister över vad som inträffat, inklusive tidpunkten och identiteten för den berörda personen. ExperienceEvents kan antingen vara explicita (direkt observerbara mänskliga åtgärder) eller implicita (upphöjda utan en direkt mänsklig åtgärd) och registreras utan aggregering eller tolkning. Experience-händelser är viktiga för tidsdomänanalys eftersom de gör det möjligt att observera och analysera ändringar som inträffar under ett visst tidsfönster och att jämföra flera tidsfönster för att spåra trender. |
| Persondatauppsättning för B2B | Personschema för B2B | Profil | Individuell XDM-profil | En enskild XDM-profil utgör en unik representation av både identifierade och delvis identifierade individers attribut och intressen. Mindre identifierade profiler får endast innehålla anonyma beteendesignaler, t.ex. cookies, medan högidentifierade profiler kan innehålla detaljerad personlig information som namn, födelsedatum, plats och e-postadress. När en profil växer blir den ett robust arkiv med personuppgifter, identifieringsinformation, kontaktuppgifter och kommunikationsinställningar för en individ. |
| B2B-kontodatauppsättning | B2B-kontoschema | Sök | XDM Business Account | Ett XDM-företagskonto är en XDM-klass (Experience Data Model) som samlar in de minsta nödvändiga egenskaperna för ett företagskonto. Den här XDM-klassen kan bara inkluderas i profilen för kunder med B2B- eller B2P-utgåvan. |
| Datamängd för B2B-säljprojekt | B2B-säljprojekt | Sök | XDM - affärsmöjlighet | XDM Business Opportunity är en XDM-klass (Experience Data Model) som samlar in de minsta nödvändiga egenskaperna för en affärsmöjlighet. Den här XDM-klassen kan bara inkluderas i profilen för kunder med B2B- eller B2P-utgåvan. |
| Kampanjdata för B2B | B2B-kampanjschema | Sök | XDM Business Campaign | XDM Business Campaign är en XDM-standardklass (Experience Data Model) som fångar de minsta nödvändiga egenskaperna för en företagskampanj. Den här XDM-klassen kan bara inkluderas i profilen för kunder med B2B- eller B2P-utgåvan. |
| Datamängd för B2B-marknadsföringslista | Schema för B2B-marknadsföringslista | Sök | XDM Business Marketing List | XDM Business Marketing List är en XDM-standardklass (Experience Data Model) som fångar upp de minsta nödvändiga egenskaperna för en marknadsföringslista. Med marknadsföringslistor kan ni prioritera kunder som är mest benägna att köpa er produkt. Den här XDM-klassen kan bara inkluderas i profilen för kunder med B2B- eller B2P-utgåvan. |
| Relationsdatauppsättning för B2B-kontoperson | Relationsschema för B2B-kontoperson | Sök | XDM Business Account Person Relation | XDM Business Account Person Relation är en XDM-klass (Standard Experience Data Model) som fångar de minsta nödvändiga egenskaperna för en person som är kopplad till ett företagskonto. |
| Datamängd för relationsdata för B2B-säljprojekt | Affärsschema för person i B2B-säljprojekt | Sök | XDM - affärsmöjlighet, personrelation | XDM Business Opportunity Person Relation är en XDM-klass (Standard Experience Data Model) som fångar de minsta nödvändiga egenskaperna för en person som är associerad med en affärsmöjlighet. |
| Medlemsdatauppsättning för B2B-marknadsföringslista | Medlemsschema för B2B-marknadsföringslista | Sök | XDM Marketing List-medlemmar | XDM Business Marketing List-medlemmar är en XDM-klass (Experience Data Model) som beskriver medlemmar, personer eller kontakter som är kopplade till en marknadsföringslista. |
| Datamängd för B2B-kampanjmedlem | Schema för B2B-kampanjmedlem | Sök | XDM Business Campaign-medlemmar | XDM Business Campaign-medlemmar är en XDM-klass (Experience Data Model) som beskriver en kontakt eller ett lead som är kopplat till en företagskampanj. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


Relationen mellan B2B-sökscheman, profilschemat och händelseschemat definieras i B2B-konfigurationen i Experience Platform. Se Scheman i [Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/sv/docs/experience-platform/rtcdp/schemas/b2b) och [Definiera en många-till-ett-relation mellan två scheman i Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/tutorials/relationship-b2b).


Om du vill se till att en anslutning som stöder personbaserade sökningar av dina B2B-data är korrekt konfigurerad använder du följande bild för en översikt och följer dessa steg:

![B2B-scheman kommenterade](assets/b2b-schemas-annotated.svg)

1. Lägg till datauppsättningar från tabellen ovan i anslutningen.
1. För varje uppslagsdatauppsättning som du lägger till i anslutningen måste du uttryckligen definiera relationen till en händelsedatamängd med hjälp av **[!UICONTROL Key]** och **[!UICONTROL Matching key]** i dialogrutan **[!UICONTROL Edit dataset]**.
1. Aktivera **[!UICONTROL Transform dataset]** för varje uppslagsdatauppsättning som du vill omforma för personbaserade B2B-uppslag, så att informationen omformas för personbaserade uppslag. Mer information finns i [Omforma datauppsättningar för B2B-sökningar](/help/connections/transform-datasets-b2b-lookups.md).

   ![Nyckel - Matchande nyckel](assets/key-matchingkey.png)

   Tabellen nedan innehåller en exempelöversikt över exempelvärdena [!UICONTROL Person ID], [!UICONTROL Key] och [!UICONTROL Matching key] för var och en av datauppsättningarna.

   >[!IMPORTANT]
   >
   >Värdena för **person-ID**, **nyckel** och **matchande nyckel** i tabellen nedan är **exempelvärden** och kan vara olika i din specifika miljö.
   >


   | Datauppsättning (valfritt) | Person-ID | Nyckel <br/> | Matchande nyckel <br/> (i händelsedatamängd)<br/> |
   |---|---|---|---|
   | B2B-aktivitetsdatauppsättning | SourceKey <br/>**personKey.sourceKey** | | |
   | Persondatauppsättning för B2B | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | B2B-kontodatauppsättning | | SourceKey <br/>**accountKey.sourceKey**&#x200B;❶ | SourceKey<br>(B2B-persondatauppsättning)<br/>**b2b.accountKey.sourceKey**&#x200B;❶ |
   | Datamängd för B2B-säljprojekt | | Source Key <br/>**OpportunityKey.sourceKey**&#x200B;❷ | SourceKey<br/>(B2B-säljprojektsrelationsdatauppsättning)<br/>**OpportunityKey.sourceKey**&#x200B;❷ |
   | Kampanjdata för B2B | | SourceKey <br/>**campaignKey.sourceKey**&#x200B;❸ | SourceKey<br/>(B2B Campaign Member-datauppsättning)<br/>**campaignKey.sourceKey**&#x200B;❸<br/> |
   | Datamängd för B2B-marknadsföringslista | | SourceKey <br/>**marketingListKey.sourceKey**&#x200B;❹ | SourceKey<br/>(B2B Marketing List Member Dataset)<br/>**marketingListKey.sourceKey**&#x200B;❹ |
   | Relationsdatauppsättning för B2B-kontoperson | | SourceKey <br/>**personKey.sourceKey**&#x200B;❺ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❺ |
   | Datamängd för relationsdata för B2B-säljprojekt | | SourceKey <br/>**personKey.sourceKe** y❻ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❻ |
   | Datamängd för B2B-kampanjmedlem | | SourceKey <br/>**personKey.sourceKey**&#x200B;❼ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❼ |
   | Medlemsdatauppsättning för B2B-marknadsföringslista | | SourceKey <br/>**personKey.sourceKey**&#x200B;❽ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❽ |

{style="table-layout:auto"}

Mer information om hur du konfigurerar inställningar för en datauppsättning finns i [Lägg till och konfigurera datauppsättningar](../../connections/create-connection.md).


## Datavy

För att få tillgång till relevanta B2B-dimensioner och mätvärden när du skapar ditt Workspace-projekt måste du definiera datavyn utifrån detta.

Du kan till exempel lägga till följande komponenter i datavyn för att säkerställa att du kan rapportera personbaserade nivåer på dina B2B-data. Komponentnamnen ändras ibland så att de blir tydligare jämfört med de ursprungliga schemanamnen.

+++Mätvärden 

>[!IMPORTANT]
>
>Måtten och deras värden (**Komponentnamn**, **Datauppsättning**, **Datauppsättningstyp** och **[!UICONTROL Schema path])** i tabellen nedan är **exempel**. Definiera relevanta B2B-mått (komponentnamn, datauppsättning, datatyp och schemasökväg) för din specifika situation.
>

| Komponentnamn | Datauppsättning | Datatyp | Schemasökväg |
|---|---|---|---|
| Årsintäkt | B2B-kontodatauppsättning | Dubbel | accountOrganization.annualRevenue.amount |
| Antal anställda | B2B-kontodatauppsättning | Heltal | accountOrganization.numberOfEmployees |
| Faktisk kampanjkostnad | Kampanjdata för B2B | Dubbel | actualCost.amount |
| Budgeterad kampanjkostnad | Kampanjdata för B2B | Dubbel | budgetedCost.amount |
| Förväntad omsättning för affärsmöjlighet | Datamängd för B2B-säljprojekt | Dubbel | expectedRevenue.amount |
| Förväntade kampanjintäkter | Kampanjdata för B2B | Dubbel | expectedRevenue.amount |
| Affärsmöjlighet - belopp | Datamängd för B2B-säljprojekt | Dubbel | opportunityAmount.amount |

+++

+++Mått

>[!IMPORTANT]
>
>Dimensionerna och deras värden (**Komponentnamn**, **Datauppsättning**, **Datauppsättningstyp** och **[!UICONTROL Schema path])** i tabellen nedan är **exempel**. Definiera relevanta B2B-dimensioner (komponentnamn, datauppsättning, datatyp och schemasökväg) för din specifika situation.
>

| Komponentnamn | Datauppsättning | Datatyp | Schemasökväg |
|---|---|---|---|
| Kontonamn | B2B-kontodatauppsättning | Sträng | accountName |
| Kampanjnamn | Kampanjdata för B2B | Sträng | campaignName |
| Kanalnamn | Kampanjdata för B2B | Sträng | channelName |
| Land | B2B-kontodatauppsättning | Sträng | accountBillingAddress.country |
| Prognoskategorinamn | Datamängd för B2B-säljprojekt | Sträng | prognoskategoriNamn |
| Bransch | B2B-kontodatauppsättning | Sträng | accountOrganization.industry |
| Efternamn | Persondatauppsättning för B2B | Sträng | person.name.lastName |
| Namn på marknadsföringslista | Datamängd för B2B-marknadsföringslista | Sträng | marketingListName |
| Affärsmöjlighetens namn | Datamängd för B2B-säljprojekt | Sträng | OpportunityName |
| Affärsmöjlighet | Datamängd för B2B-säljprojekt | Sträng | opportunityStage |
| Typ av affärsmöjlighet | Datamängd för B2B-säljprojektstyp | Sträng | opportunityType |
| Namn på webbseminariesession | Kampanjdata för B2B | Sträng | webbinarSessionName |

+++

## Workspace

Med komponenterna korrekt definierade i datavyn kan du nu skapa specifika B2B-rapporter och visualiseringar i ditt Workspace-projekt.

Nedan visas en skärmbild från ett exempelprojekt som är beroende av anslutningen och datavyn som beskrivs ovan. I visualiseringsbeskrivningarna förklaras vilken av frihandstabellens visualisering som är beroende av de omformade B2B-sökningsdata.

![Exempelprojekt](assets/sample-workspace-project.png)

