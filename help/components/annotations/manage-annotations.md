---
title: Hantera anteckningar
description: Hantera anteckningar i Workspace.
role: User, Admin
feature: Components
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: b4e65903c720ecd9e684f8b7a764e2ba8f74baed
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 1%

---

# Hantera anteckningar

>[!NOTE]
>
>Den här funktionen är för närvarande i begränsad testning.

The [!UICONTROL Components] > [!UICONTROL Annotations] kan hantera anteckningar på många olika sätt, t.ex. dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.

The [!UICONTROL Annotations] -hanteraren visar alla anteckningar du äger som har omfattats av alla dina projekt och som har delats med dig.

>[!NOTE]
>
>[!UICONTROL Annotations] som du bara skapade för ett visst projekt visas inte i hanteraren.

## Annotations Manager-användargränssnitt

![](assets/annotation-mgr.png)

| Gränssnittselement | Beskrivning |
| --- | --- | 
| [!UICONTROL Title and Description] | Finns i Annotations Builder. Om du vill redigera titeln och beskrivningen klickar du på titellänken. Då återgår du till Anteckningsverktyget. |
| [!UICONTROL Report Suite] | Rapportsviten/rapporterna som den här anteckningen gäller för. |
| [!UICONTROL Owner] | Anger vem som äger anteckningen. Som icke-administratör kan du bara se anteckningar som du äger eller de som delats med dig. |
| [!UICONTROL Applied Date Range] | Det datum eller datumintervall som den här anteckningen gäller för. |
| [!UICONTROL Shared with] | Visar hur många personer eller grupper som du har delat anteckningen med. Klicka för mer information. |
| [!UICONTROL Date Modified] | Visar datum och tid då anteckningen senast ändrades. |

## Redigera anteckningar

Att redigera en anteckning innebär att du kan justera datumintervall, färger, omfång eller om det gäller för alla rapportsviter eller projekt. Du kan redigera anteckningar på två sätt:

* Håll pekaren över anteckningen i ett linjediagram och klicka på pennikonen i pekaren.

* I [!UICONTROL Annotations Manager]klickar du på anteckningens titel.

Båda dessa alternativ ger dig tillbaka i Annotations Builder. Där kan du göra nödvändiga justeringar och spara den nya versionen.

## Andra anteckningsuppgifter

Med Annotations Manager kan administratörer redigera, lägga till, tagga, ta bort, byta namn på, godkänna, kopiera, exportera och filtrera anteckningar. Den är inte synlig för användare som inte är administratörer.

Välj bara en eller flera av anteckningarna så visas Aktivitetsfältet.

| Uppgift | Beskrivning |
| --- | --- |
| Lägg till | Gå till Anteckningsverktyget där du kan skapa nya anteckningar. |
| Tagg | Alla användare kan skapa taggar för anteckningar och använda en eller flera taggar för en anteckning. Men du kan bara se taggar för de segment som du äger. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:<ul><li>Taggar baserade på teamnamn, som social marknadsföring, mobilmarknadsföring</li><li>Projekttaggar (analystaggar), t.ex. analys på ingångssidan</li><li>Kategoritaggar: Män geografi</li><li>Arbetsflödestaggar: Kuraterad för (en specifik affärsenhet). Godkänd</li></ul> |
| Ta bort | Om du tar bort en anteckning tas den bort från alla projekt i organisationen. |
| Byt namn | Om du ändrar namn på en anteckning ändras namnet i alla projekt som den används i. |
| Kopiera | Skapar en distinkt kopia med sitt eget antecknings-ID, men med samma namn och definition. |
| Exportera till CSV | Exportera anteckningsdefinitionen till en CSV-fil. |
| Filter (vänster remsa) | Filtrera efter taggar, rapportsvit, ägare och andra filter (Min, Godkänd, Favoriter, Delad med mig och Visa alla). |
