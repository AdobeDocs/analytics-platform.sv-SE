---
description: Radinställningarna varierar beroende på vilken komponent du har dragit in i tabellen.
title: Radinställningar
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: df326581abbbd0dd0d29638962ccb71bb0aee837
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---


# Radinställningar

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Radinställningarna varierar beroende på vilken komponent du har dragit in i tabellen. Om du vill komma åt tabellradsinställningar klickar du på ikonen Inställningar bredvid en dimension, ett segment, ett mått, en tidsperiod eller en uppdelning inom var och en av dessa:

![](assets/row-settings.png)

| Inställning | Beskrivning |
|--- |--- |
| Justera datum | Detta är en inställning på tabellnivå som justerar datum från varje kolumn till alla början på samma rad. Datumjustering aktiveras som standard när en tidsdimension används på raderna i tabellen och olika datumintervall används i kolumnerna. I en daglig tabell där oktober och september tillämpas på kolumnerna börjar den vänstra kolumnen med den 1 oktober och den högra kolumnen börjar med den 1 september. |
| Uppdelning efter position | Som standard är den här inställningen inaktiverad och uppdelningar är fasta på statiska radobjekt. Du kan t.ex. dela upp de tre främsta dimensionsobjekten (hemsida, sökresultat, utcheckning) efter marknadsföringskanal. Då lämnar du projektet och återvänder två veckor senare. När du öppnar projektet igen har de tre översta sidorna ändrats, och nu är startsidan, Sökresultat och Utcheckning de 4-6 översta sidorna i stället. Som standard visas indelningarna för marknadsföringskanal fortfarande under Hemsida, Sökresultat och Utcheckning, även om de nu finns på raderna 4-6. <br> Däremot **Uppdelning efter position** kommer alltid att dela upp de tre viktigaste posterna, oavsett vad de är. När du öppnar ditt projekt igen, som ett exempel, binds uppdelningarna för marknadsföringskanal till de tre översta sidorna i tabellen, inte till hemsida, sökresultat och utcheckning som nu finns på raderna 4-6. |
| Procentsatser | **Beräkna procentandelar per kolumn** är standardinställningen, de procenttal som visas i en kolumn beräknas utifrån kolumnsumman. <br>**Beräkna procentandelar per rad** tvingar Freeform-tabellen att beräkna cellprocenten över raden i stället för nedåt i kolumnen, med stor summa som nämnare. Detta är särskilt användbart när du vill flytta procentandelar. Den här inställningen är aktiverad som standard när du använder ikonen Visualisera. |
| Kolumnsummor | Dessa inställningar är endast tillgängliga för [statiska rader](manual-vs-dynamic-rows.md). <br> **Visa som summan av aktuella rader** visar en summa på klientsidan av raderna i tabellen, vilket betyder att summan kommer att *inte* Avduplicerade mått som besök eller besökare. <br> **Visa totalsumma** visar en summa på serversidan som innebär att summan kommer att dubblera mått. |
