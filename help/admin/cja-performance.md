---
title: Optimera CJA-prestanda
description: Bästa tillvägagångssätt för att optimera CJA-prestanda
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: a546c52d2a686c38f7a9a23e0c541568c2918495
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---


# Optimera CJA-prestanda

>[!NOTE]
>
>Information om hur du optimerar prestanda för arbetsytan finns i [Optimera [!UICONTROL Analysis Workspace] prestanda](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Dessa faktorer påverkar CJA:s allmänna prestanda:

| Faktor | Definition | Berörd av | Optimering |
| --- | --- | --- | --- |
| Filterkomplexitet | Intensifierade filter kan ha en betydande inverkan på projektets prestanda. | Faktorer som gör ett filter mer komplext (i fallande effektordning) är bland annat: <ul><li>Operatorer för &quot;contains&quot;, &quot;contains any of&quot;, &quot;match&quot;, &quot;starting with&quot; eller &quot;ends with&quot; </li><li>Sekventiell filtrering, särskilt när dimensionsbegränsningar (inom/efter) används </li><li>Antal unika dimensionsobjekt inom dimensioner som används i filtret (t.ex. Sida = &#39;A&#39; när sidan har 10 unika objekt blir snabbare än Sida = &#39;A&#39; när sidan har 100000 unika objekt) </li><li>Antal olika dimensioner som används (t.ex. Page = &#39;Home&#39; och Page = &#39;Search results&#39; är snabbare än eVar 1 = &#39;red&#39; och eVar 2 = &#39;blue&#39;)</li><li>Många OR-operatorer (i stället för AND)</li><li>Kapslade behållare som varierar i omfång (t.ex. &quot;Träff&quot; inuti &quot;Besök&quot; inuti &quot;Besök&quot;)</li></ul> | Vissa av komplexitetsfaktorerna kan inte förhindras, men leta efter möjligheter att minska komplexiteten i dina filter. Ju mer specifik du kan vara med filtervillkoren, desto bättre. Exempel:<ul><li>Med behållare blir det snabbare att använda en enda behållare högst upp i filtret än en serie kapslade behållare.</li><li>Med operatorer blir&quot;lika&quot; snabbare än&quot;innehåller&quot;, och&quot;är lika med&quot; är snabbare än&quot;innehåller något av&quot;.</li><li>Med många kriterier blir AND-operatorer snabbare än en serie OR-operatorer.</li></ul> Leta efter möjligheter att reducera många OR-satser till en enda &quot;motsvarar&quot;-programsats.<br> |
| Visualiseringskomplexitet (filter, mätvärden, filter) | Den typ av visualisering (t.ex. bortfall jämfört med frihandstabell) som läggs till i ett projekt påverkar inte projektets prestanda särskilt mycket. Det är komplexiteten i den visualisering som kommer att öka bearbetningstiden. | Faktorer som gör en visualisering mer komplicerad:<ul><li>Intervall med begärda data</li><li>Antal filter som använts. till exempel filter som används som rader i en frihandstabell</li><li>Användning av komplexa filter</li><li>[Statiskt objekt](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) rader eller kolumner i frihandstabeller</li><li>Filter som används på rader i frihandstabeller</li><li>Antal mätvärden som ingår, särskilt beräknade mätvärden som använder filter</li></ul> | Om dina projekt inte läses in så snabbt du vill kan du ersätta några filter med eVars och Filter där det är möjligt.<br><br>Om du hela tiden använder filter och beräknade värden för datapunkter som är viktiga för ditt företag bör du förbättra implementeringen för att hämta in dessa datapunkter mer direkt. Om du använder tagghanterare som Adobe Experience Platform Launch och Adobe kan implementeringsändringarna göras snabbt och enkelt. |
| Datacenterkapacitet | Den rapporteringskapacitet som ni och andra kunder delar inom ett datacenter i Adobe. | Detta påverkas av antalet samtidiga frågor som har ställts av din organisation och andra organisationer i ditt datacenter. | Din organisation har rätt till en fast kapacitet, och om systemet är belastat med ljus kommer Adobe att lägga mer kapacitet till dig, över och efter din rätt till ersättning. |



