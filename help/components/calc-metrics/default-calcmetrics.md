---
description: Adobe tillhandahåller olika beräknade värden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Standardberäknade värden
feature: Calculated Metrics
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Standardberäknade värden

Customer Journey Analytics tillhandahåller olika beräknade värden som täcker de vanligaste användningsfallen. Dessa beräknade värden är tillgängliga som standard i Analysis Workspace.

Här följer en lista över alla beräknade mätvärden som tillhandahålls av Adobe, med dess avsedda funktion och den underliggande formel som används för att beräkna dem:

>[!NOTE]
>
>Förutom de standardvärden för beräknade värden som beskrivs på den här sidan kan du även lägga till ytterligare beräknade värden i en rapportserie.
>
>Ni kan:
> * Lägg till beräknade standardvärden för direktuppspelningsmedia, enligt beskrivningen i [Beräknade mått](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Skapa anpassade beräknade mätvärden från befintliga mätvärden, vilket beskrivs i [Beräknade och avancerade beräknade (härledda) mätvärden](/help/components/calc-metrics/cm-adv-functions.md).



| Namn på beräknat mätvärde |  -funktion | Formel |
|---------|----------|---------|
| Studsfrekvens | Andelen besök som innehöll exakt en träff jämfört med antalet besök på den sidan. Detta kan hjälpa dig att förstå vilka dimensionsobjekt som har den högsta studsfrekvensen eller att se en sammanlagd totalstuds för din webbplats över tiden. | `[Bounces] / [Entries]` |
| Intäkter/besökare | Det genomsnittliga intäktsbelopp som genereras av varje enskild besökare på webbplatsen. | `[Revenue] / [Unique Visitors]` |
| Beställningar/besökare | Genomsnittligt antal order eller transaktioner som genererats av varje enskild besökare på platsen | `[Orders] / [Unique Visitors]` |
| Intäkter/besök | Den genomsnittliga intäkten från ett enda besök på webbplatsen. | `[Revenue] / [Visits]` |
| Intäkter/order | Det genomsnittliga intäktsbelopp som genereras av varje slutförd transaktion eller order på webbplatsen. | `[Revenue] / [Orders]` |
| Beställningar/besök | Procentandel besök på platsen som resulterar i en slutförd transaktion. | `[Orders] / [Visits]` |
| Sidvyer/besök | Genomsnittligt antal sidor som en användare visar under ett enda besök på webbplatsen. | `[Page Views] / [Visits]` |
| Besök/besökare | Genomsnittligt antal besök som en unik besökare gör på webbplatsen. | `[Visits] / [Unique Visitors]` |
| Läser in igen/Sidor | Procentandelen sidvyer som resulterade i en omladdning eller uppdatering av sidan. | `[Reloads] / [Page Views]` |
| Viktad studs-hastighet |  -funktion | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Orderassistenter | Antalet gånger en kanal eller källa bidrog till kundens resa mot ett köp, men resulterade inte i det slutliga köpet. | `[Orders (Visit Participation)] - [Orders]` |
| Utgångshastighet | Andelen besökare som lämnar webbplatsen efter att ha visat en viss sida. | `[Exits] / [Visits]` |
| Ankomstfrekvens | Andelen besökare som kom in på webbplatsen på en viss sida, jämfört med det totala antalet sessioner på webbplatsen. | `[Entries] / [Visits]` |
| Genomsnittlig tid på plats | Den genomsnittliga tid en besökare tillbringar på webbplatsen innan han/hon lämnar eller navigerar. | `[Average Time Spent on Site (Seconds)]` |
| Tid/användare (tillstånd) | Den tid som den genomsnittliga besökaren tillbringar i ett visst läge under tiden som han/hon befinner sig på webbplatsen | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Användare (mobil) | Det totala antalet användare i en mobilapp | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Appanvändare | Det totala antalet användare i en mobilapp | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Lägesvyer | Antalet vyer till olika lägen eller skärmar i appen | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Åtgärder | Det totala antalet åtgärder som har vidtagits i appen | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Länkklickningar för förvärv | Antalet gånger som personer klickar på en länk som är avsedd att köra trafik till platsen. | `[Campaign Click-throughs]` |
| Sidhastighet | Antalet ytterligare sidvyer som genereras av ett innehållsavsnitt. Detta kan hjälpa er att avgöra vilket innehåll som ökar engagemanget. | `[Page Views] / [Visits]` |
| Konverteringsgrad | Andelen besökare som vidtagit en önskad åtgärd, till exempel gjort ett köp. | `[Orders] / [Visits]` |
| Genomsnittlig sessionslängd (mobil) | Genomsnittlig tid som besökare tillbringar på webbplatsen under en enda session. | Tom |
| Experience Cloud ID-täckning | Andelen besökare som har ett Experience Cloud-ID. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Innehållshastighet | Hur snabbt nytt innehåll skapas och publiceras på webbplatsen och hur snabbt det genererar användarengagemang. | `[Page Views] / [Visits]` |
| ITP 2.1 Unika besökare/unika besökare | Andelen unika besökare som använder en webbläsare som påverkas av ITP 2.1-cookie-begränsningar. Kunder som inte använder en CNAME-implementering. (Detta gäller kunder som ställer in cookies via JavaScript på klientsidan.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Unika besökare/unika besökare som återvänder efter 7 dagar | Andelen unika besökare som återvänder efter en period på 7 dagar eller mer. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Sidvyer/unik besökare | Genomsnittligt antal sidor som visas för varje unik besökare på webbplatsen. | `[Page Views] / [Unique Visitors]` |
| Besök/besökare | Genomsnittligt antal besök som en unik besökare gör på webbplatsen. | `[Visits] / [Unique Visitors]` |
| Beräknade unika besökare (ITP 2.1) | För ITP-besökare (användare i Safari-webbläsare), dividera unika besökare med 2 eller mindre. Detta beräknade mått förutsätter att du anger cookies med JavaScript på klientsidan (inte med en CNAME-implementering). Implementeringar som anger cookies med JavaScript på klientsidan påverkades från och med ITP 2.1. Se [Förebyggande av intelligent spårning](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) för mer information. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Sidvyer/beräknade unika besökare (ITP 2.1) | Genomsnittligt antal sidor som visas för beräknade unika besökare (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
