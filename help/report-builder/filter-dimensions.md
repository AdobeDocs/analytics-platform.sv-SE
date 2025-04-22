---
title: Filtrera dimensioner i Report Builder
description: Beskriver hur du använder filterdimensioner i Report Builder för Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 1%

---


# Filterdimensioner

Som standard returnerar varje dimensionsartikel i tabellen de 10 översta artiklarna för den dimensionen.

Ändra dimensionsobjekten som returneras för varje dimension

1. Markera ett datablock och klicka på Redigera datablock på kommandopanelen.

1. Välj **[!UICONTROL Next]** om du vill visa fliken Dimensioner.

1. Välj ![MoreSmall](/help/assets/icons/MoreSmall.svg) bredvid ett komponentnamn i tabellen.

   ![Alternativ för ellipsikoner.](./assets/image27.png)

1. Välj **Filterdimension** på snabbmenyn för att visa rutan **Filterdimension**.

1. Välj **Mest populära** eller **Specifik**.

   ![Det specifika alternativ som har valts i rutan Filterdimension.](./assets/image28.png)

1. Välj lämpliga alternativ baserat på vald filtertyp.

1. Klicka på **Använd** för att lägga till filtret.

   Report Builder visar ett meddelande som bekräftar det tillagda filtret.

Håll pekaren över en dimension om du vill visa använda filter. Dimensioner med tillämpade filter visas med en ![Filter](/help/assets/icons/Filter.svg)-filterikon bredvid Dimension-namnet.

## Ändra filter och sorteringsordning

En pil visas bredvid mätvärdet som används för att filtrera och sortera datablocket. Pilens riktning anger om måttet är sorterat i stigande eller fallande ordning.

Om du vill ändra sorteringsriktning markerar du pilen bredvid måttet.

Om du vill ändra måtten som används för att filtrera och sortera datablocket

1. Håll pekaren över den önskade måttkomponenten i tabellverktyget för att visa ytterligare alternativ.

2. Välj pilen på det önskade måttet.

   ![Tabellverktyget och måtten.](./assets/image30.png)



## Filtertyp

Det finns två sätt att filtrera dimensionsobjekt: De vanligaste och specifika.

### Mest populära

Det vanligaste alternativet gör att du dynamiskt kan filtrera dimensionsobjekt baserat på mätvärden. Den vanligaste filtreringen returnerar de högst rankade dimensionsobjekten baserat på måttvärden. Som standard listas de första 10 dimensionsobjekten, sorterade efter det första mätvärdet som lagts till i datablocket.

![Det populäraste alternativet.](./assets/image29.png)


**Alternativ för sidor och rader**

Använd fälten **Sida** och **Rader** för att dela in data i sekventiella grupper eller sidor. På så sätt kan du dra in andra rankade radvärden än de översta i rapporten. Den här funktionen är särskilt användbar när du vill hämta data över gränsen på 50 000 rader.

Standardvärdet för Sida är 1 och för Rader 10. Dessa standardvärden innebär att varje sida har 10 rader med data. Sidan 1 returnerar de 10 översta objekten, sidan 2 returnerar de 10 efterföljande objekten och så vidare.

Tabellen nedan innehåller exempel på sid- och radvärden och resultatet.

| Sida | Rad | Utdata |
|------|--------|----------------------|
| 1 | 10 | De 10 viktigaste objekten |
| 2 | 10 | Objekt 11-20 |
| 1 | 100 | Top 100 items |
| 2 | 100 | Posterna 101-200 |
| 2 | 50 000 | 50 001-100 000 |

Minsta och högsta värden är:

- Startsida: Min = 1, Max: 50 miljoner
- Antal rader: Min = 1, Max: 50 000

### Inkludera &quot;Inget värde&quot;

I Customer Journey Analytics samlar vissa dimensioner in en&quot;Inget värde&quot;-post. Med det här filtret kan du exkludera dessa värden från rapporter. Du kan t.ex. skapa en klassificering som produktnamnsklassificeringen baserat på SKU-nyckeln för produkten. Om en specifik produkt-SKU inte har ställts in med sin specifika produktnamnsklassificering, anges värdet för produktnamnet till&quot;inget värde&quot;.

**[!UICONTROL Include "No value"]** är markerat som standard. Avmarkera det här alternativet om du vill utesluta poster utan värde.

### Filtrera efter villkor

Du kan filtrera dimensionsobjekt baserat på om alla villkor är uppfyllda eller om något villkor är uppfyllt.

Ange filtervillkor

1. Välj en operator i listrutan.

   ![Operatorlistan.](./assets/image31.png)

1. Ange ett värde i sökfältet.

1. Välj ![Lägg till](/help/assets/icons/Add.svg) **[!UICONTROL Add row]** för att bekräfta markeringen och lägga till ett annat villkorsobjekt.

1. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort ett villkorsobjekt.

   Du kan inkludera upp till 10 villkorsobjekt.

### Specifik filtrering

Med alternativet Specifik kan du skapa en fast lista med dimensionsobjekt för varje dimension. Använd filtreringstypen **Specifik** för att ange exakt vilka dimensionsobjekt som ska inkluderas i filtret. Du kan markera objekt från en lista eller från ett cellintervall.

![Specifika alternativ och markerade objekt.](./assets/image32.png)

#### Från lista

1. Välj alternativet **Från lista** om du vill söka efter och välja dimensionsobjekt.

   När du väljer alternativet **Från lista** fylls listan med dimensionsobjekt med de flesta händelser först.

   ![Alternativet Från lista och tillgängliga objekt.](./assets/image33.png)

   Listan **Tillgängliga objekt** ordnas från dimensionsobjekt med de flesta händelser till de med minst.

1. Ange en sökterm i fältet **Lägg till objekt** för att söka i listan.

1. Om du vill söka efter ett objekt som inte ingår i de senaste 90 dagarna klickar du på **Visa objekt för de senaste 6 månaderna** för att utöka sökningen.

   ![Visa objekt från listan med de senaste sex månaderna.](./assets/image34.png)

   När data från de senaste 6 månaderna har lästs in uppdaterar Report Builder länken till **Visa objekt de senaste 18 månaderna**.

1. Välj en dimensionsartikel.

   Valda dimensionsobjekt läggs automatiskt till i listan **Markerade objekt**.

   ![](./assets/image35.png)

   Om du vill ta bort ett objekt från listan klickar du på ikonen Ta bort för att ta bort objektet från listan.

   Om du vill flytta ett objekt i listan drar och släpper du objektet eller klickar på ... för att visa flyttmenyn.

   ![Dimensionsobjektslistan.](./assets/image36.png)

1. Klicka på **Använd**

   Report Builder uppdaterar listan så att den specifika filtrering som du tillämpade visas.

#### Från cellintervall

Välj alternativet **Från cellintervall** om du vill välja ett cellintervall som innehåller listan med dimensionsobjekt som ska matchas.

![Alternativet Från cellintervall och fältet för att markera ett cellintervall.](./assets/image37.png)

När du markerar ett cellintervall bör du tänka på följande begränsningar:

- Intervallet måste innehålla minst en cell.
- Intervallet får inte innehålla fler än 50 000 celler.
- Intervallet måste finnas i en enda oavbruten rad eller kolumn.

Markeringen kan innehålla tomma celler eller celler med värden som inte matchar ett visst dimensionsobjekt.

### Från fliken Dimensioner i tabellverktyget

På fliken **Dimensioner** klickar du på ikonen för att visa en lista med dimensionsobjekt bredvid ett dimensionsnamn.

![Fliken Dimensioner och listan över dimensioner.](./assets/dimensions_chevron.png)

Du kan dra och släppa objekt på **tabellen** eller dubbelklicka på ett objektnamn för att lägga till det i **tabellverktyget**.
