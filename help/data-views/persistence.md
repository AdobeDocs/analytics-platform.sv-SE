---
title: Vad är dimensionskonsistens i Customer Journey Analytics?
description: Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de hur eller om dimensionsvärdena kvarstår från en händelse till nästa.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 5%

---

# Persistence

Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de hur eller om dimensionsvärdena kvarstår från en händelse till nästa. Dimensionens beständighet är konfigurerad för en dimension i datavyer och är retroaktiv och icke-förstörande för data som den tillämpas på. Dimensionens beständighet är en omedelbar dataomvandling som tillämpas på en dimension som inträffar innan filtrering eller andra analysåtgärder utförs vid rapportering.

* Som standard har ett dimensionsvärde inte någon beständighet aktiverad.
* När en allokeringsmodell aktiveras för en dimension används som standard ett förfallodatum på [!UICONTROL Session].

## Allokering

Allokering använder en omformning på det underliggande värdet som du använder. Följande allokeringsmodeller stöds:

* Senaste
* Original
* Alla

### [!UICONTROL Most recent] allokering

Den senaste allokeringen kommer att behålla det senaste (efter tidsstämpel) värdet i dimensionen. Eventuella efterföljande värden som förekommer i samma session ersätter det tidigare beständiga värdet. Observera att om&quot;Inget värde&quot; har valts för den här dimensionen ersätts de tomma värdena med&quot;Inget värde&quot; innan persistence används. Här följer ett före och efter-exempel på [!UICONTROL Most recent]-allokering, förutsatt att [!UICONTROL Session] används för förfallodatum och att alla händelser inträffar inom en [!UICONTROL Session]:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| datauppsättningsvärden |  | C | B |  | A |
| Senaste allokering |  | C | B | B | A |

### [!UICONTROL Original] allokering

Ursprunglig allokering kommer att behålla det ursprungliga värdet (med tidsstämpel) som finns i dimensionen för en förfalloperiod. Här följer ett före och efter-exempel på [!UICONTROL Original]-allokering:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| datauppsättningsvärden |  | C | B |  | A |
| Ursprunglig allokering |  | C | C | C | C |

### [!UICONTROL All] allokering

Denna dimensionsallokering kan användas för både matrisbaserade dimensioner och dimensioner med ett värde. Den fungerar ungefär som [!UICONTROL Participation]-attribueringsmodellen för mått. En viktig skillnad är att dimensioner med Alla-allokering kan användas i filterdefinitioner. Vi har t.ex. 5 händelser i ett strängfält med allokeringen inställd på &quot;Alla&quot; och förfallotiden inställd på 5 minuter:

| Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
| --- | --- | --- | --- | --- | --- |
| datauppsättningsvärden | A | B | C |  | A |
| after-persistence | A | A,B | A, B, C | A, B, C | A, B, C |

## Förfaller

[!UICONTROL Expiration] gör att du kan ange det beständiga fönstret för en dimension.

Det finns fyra sätt att förfalla ett dimensionsvärde:

* Session (standard): Upphör att gälla efter en viss session.
* Person: Upphör att gälla i slutet av rapportfönstret.
* Tid: Du kan ange att dimensionsvärdet ska förfalla efter en angiven tidsperiod (upp till 90 dagar). Det här förfalloalternativet är endast tillgängligt för allokeringsmodellerna Original och Senaste. Vid tidsbaserad förfallotid beaktas värden som ligger före rapportfönstrets början (upp till 90 dagar).
* Mått: Du kan ange vilken som helst av de definierade måtten som förfallodatum för den här dimensionen (t.ex. ett köpmått). Den här förfallotiden är endast tillgänglig för allokeringsmodellerna Original och Senaste.

### Vad är skillnaden mellan allokering och attribuering?

**Allokering**: Tänk på allokering som en dataomvandling till dimensionen. Allokering sker före filtrering. Om du skapar ett filter avaktiveras den omformade dimensionen.

**Attribution**: Hur fördelar jag krediten för ett mätresultat till den dimension som det tillämpas på? Attribuering är inte en dataomvandling, används under dataaggregering och påverkar inte vilka data som inkluderas med ett filter.
