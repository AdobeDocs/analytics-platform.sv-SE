---
title: Vanliga frågor om attribuering
description: Få svar på vanliga frågor om tilldelning.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 2%

---


# Vanliga frågor om attribuering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

**Vad är radobjektet &quot;Ingen&quot; när attributet används?**

Radelementet Inget är ett catch-all-objekt som representerar alla konverteringar som har skett utan några pekpunkter i uppslagsfönstret. Försök att inkludera ett längre tidsintervall i rapportfönstret.

**Varför ser jag ibland datum utanför mitt rapporteringsfönster när jag använder attributmodeller?**

De här extra datumen beror på besökarrapportuppslagsfönstret. Se [Data som visas utanför rapporteringsfönstret](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) I analysdatabasen finns mer information. Adobe planerar att filtrera bort dessa extra rader i en kommande version.

**När ska jag använda ett besök jämfört med besökarattributgranskning?**

Valet av återföringssökning beror på ditt användningsfall. Om konverteringar vanligtvis tar längre tid än ett besök rekommenderas ett besöksbesök. Att skapa en virtuell rapportsvit med en längre besöksdefinition är också en möjlig lösning.

**Hur är proportionerna mellan props och eVars när attributet används?**

Attributet beräknas på nytt vid rapportkörning, så det är ingen skillnad mellan en prop eller eVar (eller någon annan dimension) för attributmodelleringens skull. Props kan bestå med valfritt uppslagsfönster eller attributmodell, och eVar-allokerings-/förfalloinställningar ignoreras.

**Är attributmodeller endast tillgängliga om jag använder en virtuell rapportsvit med rapporttidsbearbetning aktiverad?**

Attributmodeller är tillgängliga utanför virtuella rapportuppsättningar. Medan de använder rapporttidsbearbetning på serverdelen är attributmodeller tillgängliga för både standardrapportpaket och virtuella rapportpaket.

**Vilka mått och mått stöds inte?**

Attributpanelen stöder alla dimensioner. Mått som inte stöds omfattar:

* Unika besökare
* Besök
* Förekomster
* Sidvisningar
* A4T-mått
* Förbrukade tidsmått
* Studsar
* Räntesats
* Första besökssida
* Sista besökssida
* Sidor som inte hittades
* Sökningar
* Ensidiga besök
* Enkelt besök

**Arbetar tilldelningen med klassificeringar?**

Ja, klassificeringar stöds helt.

**Arbetar tilldelningen med datakällor?**

Ja, de flesta datakällor stöds. Attribut är inte möjligt med datakällor på sammanfattningsnivå eftersom de inte är kopplade till en analytikerbesöksidentifierare. Datakällor för transaktions-ID stöds också, såvida de inte används i en virtuell rapportsvit där rapporttidsbearbetning är aktiverad.

**Fungerar tilldelningen med reklamanalytikintegrationen?**

Metadatadimensioner, till exempel matchningstyp och nyckelord, fungerar med attribut. Mått (inklusive imponeringar, kostnad, klick, genomsnittlig position och medelkvalitet) använder dock datakällor på sammanfattningsnivå och är därför inkompatibla.

**Hur fungerar tilldelningen med marknadsföringskanaler?**

När marknadsföringskanalerna först introducerades kom de bara med första och sista beröringspunkten. Uttryckliga första/sista pektydimensioner behövs inte längre med den aktuella versionen av attribut. Adobe tillhandahåller allmänna dimensioner för Marketing Channel och Marketing Channel Detail så att du kan använda dem med önskad attributmodell. Dessa allmänna dimensioner uppträder på samma sätt som Senaste Touch Channel-dimensioner, men märks på ett annat sätt för att förhindra förvirring när marknadsföringskanaler med en annan attributmodell används.

Eftersom marknadsföringskanalernas dimensioner är beroende av en traditionell besöksdefinition (som definieras av deras bearbetningsregler) kan deras besöksdefinition inte ändras med hjälp av virtuella rapportsviter.

**Hur fungerar attributet med variabler med flera värden, t.ex. listvarianter?**

Vissa dimensioner i Analytics kan innehålla flera värden på en enda träff. Vanliga exempel är listvariabeln och produktvariabeln.

När attributet används för multivärdeträffar får alla värden i samma träff samma kredit. Eftersom många värden kan få den här krediten kan rapportsumman vara annorlunda än om du summerade varje enskild radartikel. Rapportsumman har deduplicerats, medan varje enskild dimensionspost får rätt kredit.

**Hur fungerar tilldelningen med segmentering?**

Attributet körs alltid före segmentering och segmenteringen körs innan rapportfilter används. Det här konceptet gäller även virtuella rapportpaket som använder segment.

Om du t.ex. skapar ett VRS-segment med segmentet &quot;Bildskärmsträffar&quot; tillämpat kan du se andra kanaler i en tabell med hjälp av vissa attributmodeller.

![Virtuell rapportsvit som endast visas](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Om ett segment undertrycker träffar som innehåller måttet, kommer de metriska förekomsterna inte att tillskrivas någon dimension. Ett liknande rapportfilter döljer dock helt enkelt vissa dimensionsobjekt, utan att det påverkar de mått som bearbetas enligt attributmodellen. Ett segment kan därför returnera lägre värden än ett filter med en jämförbar definition.
