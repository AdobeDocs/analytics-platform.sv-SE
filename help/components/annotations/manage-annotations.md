---
title: Hantera anteckningar
description: Hantera anteckningar i Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 1%

---

# Hantera anteckningar

Hanteraren [!UICONTROL Components] > [!UICONTROL Annotations] erbjuder många sätt att hantera anteckningar, som att dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Hanteraren för [!UICONTROL Annotations] visar alla anteckningar du äger som har omfattats av alla dina projekt och som har delats med dig.

>[!NOTE]
>
>[!UICONTROL Annotations] som du bara skapade för ett visst projekt visas inte i hanteraren.

## Annotations Manager-användargränssnitt

![Anteckningsalternativ som delning, taggning eller kopiering som beskrivs i nästa avsnitt.](assets/annotation-mgr.png)

| Gränssnittselement | Beskrivning |
| --- | --- | 
| [!UICONTROL Title and Description] | Finns i Annotations Builder. Om du vill redigera titeln och beskrivningen klickar du på titellänken. Då återgår du till Anteckningsverktyget. |
| [!UICONTROL Data view] | Datavyn/datavyerna som den här anteckningen gäller för. |
| [!UICONTROL Owner] | Anger vem som äger anteckningen. Som icke-administratör kan du bara se anteckningar som du äger eller de som delats med dig. |
| [!UICONTROL Applied Date Range] | Det datum eller datumintervall som den här anteckningen gäller för. |
| [!UICONTROL Shared with] | Visar hur många personer eller grupper som du har delat anteckningen med. Klicka för mer information. |
| [!UICONTROL Date Modified] | Visar datum och tid då anteckningen senast ändrades. |

{style="table-layout:auto"}

## Redigera anteckningar

Att redigera en anteckning innebär att du kan justera datumintervall, färger, omfång eller om det gäller för alla datavyer eller projekt. Du kan redigera anteckningar på två sätt:

* Håll pekaren över anteckningen i ett linjediagram och klicka på pennikonen i pekaren.

* Klicka på anteckningens titel i [!UICONTROL Annotations Manager].

Båda dessa alternativ ger dig tillbaka i Annotations Builder. Där kan du göra nödvändiga justeringar och spara den nya versionen.

## Dela anteckningar

När du delar anteckningar eller arbetar med anteckningar som delats med dig bör du tänka på följande:

* Anta att du skapar ett projekt med enbart projektkommentarer och sedan delar projektet med en annan användare. De här anteckningarna visas, men de kan inte redigeras eller tas bort av någon som delar projektet med.

* Om du sparar en anteckning och delar den direkt med en användare, kan han/hon bara redigera/ta bort anteckningen om han/hon har administratörsbehörighet.

* Om projektet delas med dig visas det bara i det projektet. Om anteckningen delas direkt med dig visas den i alla projekt där anteckningen kan visas.

## Anteckningar och tidszoner

Alla anteckningar skapas med en tidsstämpel, men ingen timinformation eller tidszonsinformation. Vid rapporttillfället används alltid tidszonen för panelens datavy. Så en anteckning som skapats för juldagen inträffar den 25 december - oavsett vilken tidszon du befinner dig i i datavyn.

Ett annat exempel är nyårsdagen. Varje timme sätter olika tidszoner igång för fyrverkerier när det nya året börjar. På 10.00 amerikanska Mountain Time startar USA:s östkust brandarbeten eftersom det redan är 12.00 Eastern Time.

## Andra anteckningsuppgifter

Med Annotations Manager kan administratörer redigera, lägga till, tagga, ta bort, byta namn på, godkänna, kopiera, exportera och filtrera anteckningar. Den är inte synlig för användare som inte är administratörer.

Välj bara en eller flera av anteckningarna så visas Aktivitetsfältet.

| Uppgift | Beskrivning |
| --- | --- |
| Lägg till | Gå till Anteckningsverktyget där du kan skapa nya anteckningar. |
| Tagg | Alla användare kan skapa taggar för anteckningar och använda en eller flera taggar för en anteckning. Men du kan bara se taggar för de filter som du äger. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:<ul><li>Taggar baserade på teamnamn, som social marknadsföring, mobilmarknadsföring</li><li>Projekttaggar (analystaggar), t.ex. analys på ingångssidan</li><li>Kategoritaggar: Män; geografi</li><li>Arbetsflödestaggar: Kuraterad för (en specifik affärsenhet); Godkänd</li></ul> |
| Ta bort | Om du tar bort en anteckning tas den bort från alla projekt i organisationen. |
| Byt namn | Om du ändrar namn på en anteckning ändras namnet i alla projekt som den används i. |
| Kopiera | Skapar en distinkt kopia med sitt eget antecknings-ID, men med samma namn och definition. |
| Exportera till CSV | Exportera anteckningsdefinitionen till en CSV-fil. |
| Filter (vänster remsa) | Filtrera efter taggar, datavy, owners och andra filter (Min, Godkänd, Favoriter, Delad med mig och Visa alla). |

{style="table-layout:auto"}
