---
description: Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.
title: Radinställningar
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Radinställningar

Visa en video om rad- och kolumninställningar här:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen. Om du vill komma åt inställningarna för tabellrader klickar du på [!UICONTROL Settings] -ikon bredvid en dimension, ett filter, ett mått, en tidsperiod eller en uppdelning i var och en av dessa:

![Frihandstabell som markerar inställningsikonen för mått](assets/row-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| Justera datum | Det här är en inställning på tabellnivå som justerar datum från varje kolumn så att alla börjar på samma rad. Datumjustering är aktiverat som standard när en tidsdimension används i tabellraderna och olika datumintervall används i kolumnerna. I en daglig tabell där oktober och september tillämpas på kolumnerna börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september. |
| Uppdelning efter position | Som standard är den här inställningen inaktiverad och uppdelningar är fasta på statiska radobjekt. Låt oss till exempel säga att du har delat upp de tre viktigaste sidobjekten (startsida, sökresultat, utcheckning) efter marknadsföringskanal. Sedan lämnar du projektet och återvänder två veckor senare. När du öppnar projektet igen har de tre översta sidorna ändrats, och nu är startsidan, sökresultaten och utcheckningen de 4-6 översta sidorna istället. Som standard visas dina Marketing Channel-indelningar fortfarande under Hemsida, Sökresultat och Utcheckning, även om de nu finns på raderna 4-6. <br> I motsats till **Uppdelning efter position** alltid bryts de tre översta objekten, oavsett vad de är. När du öppnar ditt projekt på nytt, som en hänvisning till vårt exempel, kommer de tre främsta sidorna i tabellen att vara kopplade till Marketing Channel-uppdelningarna, inte till Hemsida, Sökresultat och Utcheckning, som nu finns på raderna 4-6. |
| Procenttal | **Beräkna procentandelar per kolumn** är standardinställningen. Procentsatserna som visas i en kolumn beräknas utifrån kolumnsumman. <br>**Beräkna procentandelar per rad** tvingar friformstabellen att beräkna cellprocenten över raden i stället för nedåt i kolumnen, med totalsumman som nämnare. Detta är särskilt användbart för att hantera procentsatser. Den här inställningen är aktiverad som standard när du använder ikonen Visa. |
| Kolumnsummor | De här inställningarna är bara tillgängliga för [statiska rader](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Visa som summan av aktuella rader** visar en summa av raderna i tabellen på klientsidan, vilket innebär att summan *not* avduplicera mätvärden som besök eller personer. <br> **Visa totalsumma** visar en serversidessumma vilket innebär att summan kommer att dubblera måtten. |

## Ändra radantal

Så här ändrar du antalet rader som visas:

1. Klicka på siffran bredvid [!UICONTROL Rows] längst upp på bordet.

   ![Friformstabell som visar listrutan för det antal rader som visas. 400 rader är markerade.](assets/row-number.png)

1. I listrutan väljer du det antal rader som du vill att tabellen ska visa.