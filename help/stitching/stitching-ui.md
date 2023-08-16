---
title: Stitlar
description: Förstå hur man skapar och hanterar sammanfogade datauppsättningar
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
source-git-commit: 7ae94bb46d542181c6438e87f204bd49c2128c8c
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Skapa och hantera sammanslagna datauppsättningar

{{select-package}}

Med hjälp av häftning kan administratörer sätta ihop identiteter på datauppsättningar som finns i Customer Journey Analytics. Med hjälp av datauppsättningar ökar exaktheten i en profils representation, vilket i slutänden ger bättre analys och rapportering.

Med sammanfogningsprocessen kan du definiera en befintlig **beständigt ID** i en datauppsättning. Häfta sedan ihop den beständiga identifieraren för ett angivet uppspelningsfönster (varje dag, varje vecka) med den mest korrekta **tillfälligt ID** (person eller autentiserad identifierare) tillgänglig för den datauppsättningen. Exempel på transienta identifierare är e-post, telefonnummer, CRM-id eller andra identiteter som lagras i diagrammet. Se [Ökning](overview.md) för mer information om häftning.

## Skapa

Om du vill börja sammanfoga fogar skapar du en eller flera sammanfogade datauppsättningar. Så här skapar du en sammanfogad datauppsättning:

1. Välj **[!UICONTROL ** Stitlar **]** från **[!UICONTROL ** Datahantering **]** i det övre fältet.

2. I [!UICONTROL Stitched datasets] skärm, välja **[!UICONTROL ** Skapa sammanfogad datauppsättning **]**.

   Du får en dialogruta som förklarar ditt ansvar.

3. Välj **[!UICONTROL ** Fortsätt **]** om du accepterar dessa skyldigheter.

   >[!NOTE]
   >
   >    Om du väljer **[!UICONTROL ** Avbryt **]** kan du inte skapa en sammanfogad datauppsättning.

4. I [!UICONTROL Stitched datasets > Untitled stitched dataset] skärm:

   1. Definiera en **[!UICONTROL ** Namn på datauppsättning **]** och (valfritt) **[!UICONTROL ** Beskrivning **]**,

   2. Välj sandlådan i dialogrutan **[!UICONTROL ** Sandbox **]** lista där händelsedatamängden lagras.

      ![Skärm för inledande skapande](./assets/create-initial.png)

   3. Välj **[!UICONTROL ** Välj källdatauppsättning **]** -knappen.

      I [!UICONTROL Select one dataset to stitch] popup-fönster:

      ![Välj en datauppsättning](./assets/select-one-dataset.png)

      - Välj en datauppsättning och välj **[!UICONTROL ** Välj **]** för att fortsätta.

   4. Välj en beständig identifierare på menyn **[!UICONTROL ** Beständigt ID **]** lista.

   5. Välj en transient identifierare i **[!UICONTROL **&#x200B;Övergående ID **]** lista.

      Du ser att en förhandsvisningspanel visas för att beräkna mättnadsgraden (antal gånger det finns ett värde för var och en av de angivna identifierarna över antalet händelser) under de senaste sju dagarna. När beräkningen är klar visas färgerna på panelen om de minimala villkoren för att fästa bilden uppfylls (grönt) eller inte uppfylls (rött).

      ![Skapa sammanfogad datamängd med statureringshastigheter](./assets/create-before-experimenting.png)

      Minimivillkoren är:

      - beständig identifierarmättnad: frekvens >= 95 %

      - transient identifier saturation: rate >= 5%

        Om minimivillkoren uppfylls kan du experimentera med provvärden.

      - Välj **[!UICONTROL ** Skapa sammanfogade ID:n för demo **]**.

        I [!UICONTROL Experiment with sample values] visas en tabell med exempelvärden för [!UICONTROL timestamp], [!UICONTROL Persistent ID], [!UICONTROL Transient ID], [!UICONTROL Stitched ID (Live)], [!UICONTROL Stitched ID (1-day replay)]och [!UICONTROL Stitched ID (7-day replay)].

            ![Experimentera med exempelvärden](./assets/experiment-sample-values.png)
            
            1.  Ange ett värde för **[!UICONTROL **Persistent ID**]**.
            
            2.  Välj **[!UICONTROL **Refresh stitched IDs**]** om du vill se effekten av sammanfogningsprocessen på data i datauppsättningen.
            
            3.  Välj **[!UICONTROL **Close**]** när du är klar med att experimentera med provvärden.
        

        Tillbaka i [!UICONTROL Stitched datasets > _Namn på datauppsättning_] skärm:

   6. Välj ett alternativ för frekvens och period för omräkning av historiska data från **[!UICONTROL ** Uppspelningsfönster **]** lista.

      Du kan välja mellan standardvärdena **[!UICONTROL ** Föregående dag, dagligen **]** eller **[!UICONTROL ** Föregående 7 dagar, varje vecka **]**.

   7. Välj ett värde på menyn **[!UICONTROL ** Genomsnittligt antal dagliga händelser **]** lista.

   8. Ange ett värde (mellan `0` och `12`) i **[!UICONTROL ** Antal månader att fylla på igen **]**.

   9. Välj **[!UICONTROL ** Spara **]** för att spara din sammanfogade datauppsättning och initiera sammanfogningen.

## Visa status

Du kan visa status för häftning i dialogrutan [!UICONTROL Stitched datasets] lista.

- Välj **[!UICONTROL ** Stitlar **]** från **[!UICONTROL ** Datahantering **]** i det övre fältet.

  Du ser en lista över sammanfogade datauppsättningar, som alla identifieras med [!UICONTROL Sandbox], [!UICONTROL Source dataset], [!UICONTROL Status], [!UICONTROL Backfill status], [!UICONTROL Owner]och [!UICONTROL Date created].

  ![Översikt över sammanslagna datauppsättningar](./assets/overview-stitched-datasetts.png)

  Möjliga värden för [!UICONTROL Status] är:

  | Värde | Förklaring |
  |-----|-----|
  | **[!UICONTROL ** Köad **]** | Begäran tas emot och behandlas snart. |
  | **[!UICONTROL ** Skapande **]** pågår | Resurser och nyligen sammansatta datauppsättningar håller på att skapas. |
  | **[!UICONTROL ** Teckning pågår **]** | Det finns resurser och sammanfogade datauppsättningar och sammanfogning pågår |
  | **[!UICONTROL ** Fel **]** | Det är problem med att sy ihop. Ett schema kanske har ändrats mellan källdatauppsättningen och sammanfogade datauppsättningar, den dagliga volymen är för stor eller.. (_**behöver mer information här...**_) |

  >[!INFO]
  >
  >    När en status ändras skickas ett meddelande med meddelandet **[!UICONTROL ** Stitled dataset _datauppsättningens namn_ har ändrats till status _namn på status _**]**.


  The [!UICONTROL Backfill status] kan ha följande värden: 0 %, 25 %, 50 %, 75 % eller 100 %.

  Du kan välja informationsikonen om du vill visa ett popup-fönster med mer information om den valda sammanfogade datauppsättningen.


## Ta bort

>[!NOTE]
>
>Du kan bara ta bort datauppsättningar som har status [!UICONTROL Stitching in progress], [!UICONTROL Error], eller [!UICONTROL Queued].


Så här tar du bort en sammanfogad datauppsättning:

- Välj **[!UICONTROL **...**]** för den sammanslagna datauppsättningen och välj **[!UICONTROL ** Ta bort **]** på menyn.

  ![Ta bort en sammanfogad datauppsättning](./assets/delete-stitched-dataset.png)

Så här tar du bort flera sammanfogade data:

- Markera flera sammanfogade datauppsättningar med kryssrutan i början av varje listad datauppsättning.

- Välj **[!UICONTROL **...**]** från en av de markerade sammanfogade datauppsättningarna och välj **[!UICONTROL ** Ta bort **]** på menyn.
