---
title: Inställningar för Persistence-komponent
description: Bestäm hur eller om dimensionsvärdena ska behållas från en händelse till nästa.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: e8f372692e60158ce7f30837ee4da0f922e1d752
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 6%

---


# [!UICONTROL Persistence] komponentinställningar

[!UICONTROL Persistence] är möjligheten för ett givet dimensionsvärde att relatera till ett mätvärde efter händelsen det är inställt på. Den använder en kombination av allokering och förfallodatum.

* **Allokering** I kan du bestämma vilket värde som ska behållas när mer än en dimensionspost kan finnas i taget i en enda kolumn.
* **Förfaller** I kan du bestämma hur länge ett dimensionsobjekt kvarstår efter den händelse det är inställt på.

[!UICONTROL Persistence] är bara tillgängligt för dimensioner och är retroaktivt för de data som det tillämpas på. Det är en omedelbar dataomvandling som sker innan filtrering eller andra analysåtgärder tillämpas.

![Persistence](../assets/persistence.png)

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Set persistence] | Aktivera beständighet för dimensionen. Om persistence inte är aktiverat, relaterar dimensionen endast till mått som finns i samma händelse. Den här inställningen är inaktiverad som standard. |
| [!UICONTROL Allocation] | Här kan du ange den allokeringsmodell som används för en dimension för beständighet. Alternativen är: [!UICONTROL Most recent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL All]. Från och med den 28 oktober 2021 kommer ett uppslagsfönster på upp till 90 dagar att läggas till i [!UICONTROL Allocation] inställning. |
| [!UICONTROL Expiration] | Gör att du kan ange det beständiga fönstret för en dimension. Alternativen är: [!UICONTROL Session] (standard), [!UICONTROL Person], [!UICONTROL Custom Time], [!UICONTROL Metric]. Du kanske måste kunna förfalla dimensionen på ett köp (till exempel interna sökvillkor eller andra användningsfall för varuexponering). Den maximala förfallotiden som du kan ange är 90 dagar. Om du väljer en tilldelning av [!UICONTROL All], endast [!UICONTROL Session] eller [!UICONTROL Person] kan förfalla. |

## [!UICONTROL Allocation] inställningar

Information om tillgängliga allokeringsinställningar.

* **[!UICONTROL Most Recent]**: Bevarar det senaste (med tidsstämpel) värdet i dimensionen. Eventuella efterföljande värden som inträffar inom dimensionens förfalloperiod ersätter det tidigare beständiga värdet. Om Behandla &#39;Inget värde&#39; som ett värde&#39; är aktiverat för den här dimensionen under [Inga värdealternativ](no-value-options.md), tomma värden skriver över tidigare beständiga värden. Ta till exempel följande tabell med [!UICONTROL Most recent] tilldelning och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden |  | C | B |  | A |
   | Senaste allokering |  | C | B | B | A |

* **[!UICONTROL Original]**: Bevarar det ursprungliga värdet med en tidsstämpel som finns i dimensionen under förfalloperioden. Om den här dimensionen har ett värde skrivs den inte över när ett annat värde visas för en efterföljande händelse. Ta till exempel följande tabell med [!UICONTROL Original] tilldelning och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden |  | C | B |  | A |
   | Ursprunglig allokering |  | C | C | C | C |

* **[!UICONTROL All]**: Fungerar på liknande sätt som [!UICONTROL Participation] attribueringsmodell för mätvärden. Bevarar alla värden lika så att alla får full uppskattning för måttet i rapporteringen. Ta till exempel följande tabell med [!UICONTROL All] tilldelning och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden | A | B | C |  | A |
   | Alla allokeringar | A | A,B | A, B, C | A, B, C | A, B, C |

## [!UICONTROL Expiration] inställningar

Information om tillgängliga förfalloinställningar.

* **Session**: Upphör att gälla efter en viss session. Standardförfallotid.
* **Person**: Upphör att gälla i slutet av rapporteringsfönstret.
* **Tid**: Du kan ange att dimensionsvärdet ska förfalla efter en angiven tidsperiod (upp till 90 dagar). Det här förfalloalternativet är endast tillgängligt för allokeringsmodellerna Original och Senaste. När du använder tidsbaserad förfallotid beaktas värden som ligger före rapportfönstrets början (upp till 90 dagar).
* **Mått**: När det här måttet visas i en träff upphör det beständiga värdet i dimensionen omedelbart att gälla. Du kan använda valfritt mätvärde som förfallodatum för den här dimensionen. Det här förfalloalternativet är bara tillgängligt för allokeringsinställningarna Original och Senaste.
