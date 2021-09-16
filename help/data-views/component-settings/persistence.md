---
title: Inställningar för Persistence-komponent
description: Bestäm hur eller om dimensionsvärdena ska behållas från en händelse till nästa.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 6%

---


# Inställningar för Persistence-komponent

Persistence är möjligheten för ett givet dimensionsvärde att relatera till ett mätvärde efter händelsen det är inställt på. Den använder en kombination av allokering och förfallodatum.

* **Med** Allokering kan du bestämma vilket värde som ska behållas när mer än en dimensionspost kan finnas i taget i en enda kolumn.
* **Med** Förfallotid kan du bestämma hur länge en dimensionspost ska vara kvar efter den händelse den är inställd på.

Persistence är bara tillgängligt för dimensioner och är retroaktivt för de data det tillämpas på. Det är en omedelbar dataomvandling som sker innan filtrering eller andra analysåtgärder tillämpas.

![Persistence](../assets/persistence.png)

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Set persistence] | Aktivera beständighet för dimensionen. Om persistence inte är aktiverat, relaterar dimensionen endast till mått som finns i samma händelse. Den här inställningen är inaktiverad som standard. |
| [!UICONTROL Allocation] | Här kan du ange den allokeringsmodell som används för en dimension för beständighet. Alternativen är: [!UICONTROL Most recent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL All]. |
| [!UICONTROL Expiration] | Gör att du kan ange det beständiga fönstret för en dimension. Alternativen är: [!UICONTROL Session] (standard), [!UICONTROL Person], [!UICONTROL Custom Time], [!UICONTROL Metric]. Du kanske måste kunna förfalla dimensionen på ett köp (till exempel interna sökvillkor eller andra användningsfall för varuexponering). Den maximala förfallotiden som du kan ange är 90 dagar. Om du väljer en allokering av [!UICONTROL All] är endast [!UICONTROL Session] eller [!UICONTROL Person] förfallodatum tillgängliga. |

## Allokeringsinställningar

Information om tillgängliga allokeringsinställningar.

* **Senaste**: Bevarar det senaste (med tidsstämpel) värdet i dimensionen. Eventuella efterföljande värden som inträffar inom dimensionens förfalloperiod ersätter det tidigare beständiga värdet. Om Behandla &#39;Inget värde&#39; som ett värde&#39; är aktiverat för den här dimensionen under [Inga värdealternativ](no-value-options.md), skriver tomma värden över tidigare beständiga värden. Ta till exempel följande tabell med [!UICONTROL Most recent]-allokering och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden |  | C | B |  | A |
   | Senaste allokering |  | C | B | B | A |

* **Original**: Bevarar det ursprungliga värdet med en tidsstämpel som finns i dimensionen under förfalloperioden. Om den här dimensionen har ett värde skrivs den inte över när ett annat värde visas för en efterföljande händelse. Ta till exempel följande tabell med [!UICONTROL Original]-allokering och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden |  | C | B |  | A |
   | Ursprunglig allokering |  | C | C | C | C |

* **Alla**: Fungerar ungefär som  [!UICONTROL Participation] attribueringsmodellen för mätvärden. Bevarar alla värden lika så att alla får full uppskattning för måttet i rapporteringen. Ta till exempel följande tabell med [!UICONTROL All]-allokering och [!UICONTROL Session] förfallodatum:

   | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datamängdsvärden | A | B | C |  | A |
   | Alla allokeringar | A | A,B | A, B, C | A, B, C | A, B, C |

## Inställningar för förfallodatum

Information om tillgängliga förfalloinställningar.

* **Session**: Upphör att gälla efter en viss session. Standardförfallotid.
* **Person**: Upphör att gälla i slutet av rapporteringsfönstret.
* **Tid**: Du kan ange att dimensionsvärdet ska förfalla efter en angiven tidsperiod (upp till 90 dagar). Det här förfalloalternativet är endast tillgängligt för allokeringsmodellerna Original och Senaste. När du använder tidsbaserad förfallotid beaktas värden som ligger före rapportfönstrets början (upp till 90 dagar).
* **Mått**: När det här måttet visas i en träff upphör det beständiga värdet i dimensionen omedelbart att gälla. Du kan använda valfritt mätvärde som förfallodatum för den här dimensionen. Det här förfalloalternativet är bara tillgängligt för allokeringsinställningarna Original och Senaste.
