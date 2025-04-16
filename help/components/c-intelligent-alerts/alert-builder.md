---
description: Få aviseringar när projektkomponenterna når vissa tröskelvärden.
title: Skapa aviseringar
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 0%

---

# Skapa aviseringar {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Tidsgranularitet"
>abstract="Tidsgranularitet avser både hur ofta varningen kontrolleras och vad som kommer att ingå"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Det går bara att använda aviseringar med avvikelseidentifiering (kallas även _Intelligent Alerts_) för organisationer som har ett Customer Journey Analytics Prime- eller Ultimate-paket.

Med varningar i Customer Journey Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter. Beroende på ditt Customer Journey Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar.

Mer detaljerad översiktsinformation om aviseringar finns i [Översikt över aviseringar](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Så här skapar du en varning:

1. I Customer Journey Analytics väljer du <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** i [Alerts Manager](alert-manager.md) om du vill skapa en ny avisering, eller välj någon av de aviseringar som visas om du vill ändra en befintlig avisering.

   Gränssnittet [Varningsverktyget](#alert-builder) visas.

1. Välj **[!UICONTROL Save]** om du vill spara aviseringen. Välj **[!UICONTROL Save as]** om du vill spara en kopia av aviseringen.


## Varningsverktyg

Gränssnittet i Alert Builder är bekant för dem som har byggt segment eller beräknade värden i Customer Journey Analytics:

![](assets/alert-builder.png)

Ange följande information i varningsverktyget för en avisering:

| Element | Beskrivning |
|---------|----------|
| **[!UICONTROL Title]** | Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde. |
| **[!UICONTROL Description (optional)]** | Ange en beskrivning för aviseringen. |
| **[!UICONTROL Time granularity]** | Välj hur ofta du vill att måttet ska kontrolleras: Varje dag, Varje vecka eller Varje månad.<p><b>Obs!</b>För datavyer med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.<!--true?--></p> |
| **[!UICONTROL Recipients]** | Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.<p><b>Viktigt!</b>Telefonnumret måste föregås av ett plustecken och en [landskod](https://countrycode.org/).</p><p>Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:</p><p>![Varningsmeddelande](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Expiration date]** | Ange det datum och den tidpunkt då du vill att aviseringen ska förfalla. |
| **[!UICONTROL Delay]** | Den tid som krävs innan data är fullständiga och tillgängliga för att rapporteras i Customer Journey Analytics varierar beroende på organisation, vanligtvis mellan 3 och 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste händelsedata för ett givet händelseintervall vara fullständiga, vilket innebär att Adobe inte längre tar emot några händelsedata för det angivna händelseintervallet.<p>Om du vill ta hänsyn till den här fördröjningen av inmatningstiden har aviseringar en standardfördröjning på 9 timmar innan de skickas.</p><p>Du kan justera standardfördröjningen på 9 timmar till valfri plats mellan 0 och 24 timmar. Om du minskar fördröjningen till under 9 timmar kan det dock innebära att du rapporterar ofullständiga data, vilket leder till felaktig varningsinformation.</p><p>Tänk på följande när du minskar fördröjningstiden:</p><ul><li>**Förstå datatillgänglighet jämfört med datafullständighet**: Vissa data kan vara tillgängliga att rapportera tidigare, men alla batchdata importeras till en plattformsdatauppsättning först efter en period på 3 till 9 timmar. För att varningarna ska vara korrekta måste datainmatningen vara fullständig, med alla batchdata tillgängliga i datauppsättningen.</li><li>**Bestäm hur lång tid det tar för dina data att bli fullständiga och tillgängliga i datauppsättningen**: Dataöverföringstiderna skiljer sig åt i olika organisationer. Se till att fördröjningen som du väljer för varningsleverans är samma eller mindre frekvent än den tid det tar för batchdata att vara tillgängliga i plattformsdatauppsättningen <!--add link? -->.</li><p>**Tips!** Det mest korrekta sättet att veta hur lång tid det tar för alla batchdata att slutföras och hämtas till plattformsdatauppsättningen är att rådfråga datateknikerna i organisationen.</p><p>Du kan också få en allmän uppfattning om hur lång tid det tar för batchleveransen i organisationen att vara tillgänglig i plattformsdatauppsättningen genom att skapa följande friformstabell i Analysis Workspace:</p><ol><li>I en frihandstabell i Analysis Workspace lägger du till måtten [!UICONTROL **Händelser**] och [!UICONTROL **Dag**] .</li><li>Dela upp dimensionen [!UICONTROL **Dag**] med en [!UICONTROL **Timmar**]-dimension.<p>Timmar utan data visas som 0.</p></li></ol><li>**Ta hänsyn till fel i dina beräkningar**: Om du minskar standardfördröjningstiden rekommenderar vi att du konfigurerar fördröjningen i minst en timme längre än den tid det tar för organisationen att slutföra dataimporten. Om det till exempel finns en 3-timmars fördröjning innan dataimporten är klar bör du ange fördröjningen till 4 timmar.</li></ul><p>Mer information finns i [Tidsåtgången för dataöverföring varierar i Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) i artikeln [Jämförelse av aviseringsfunktioner: Customer Journey Analytics och Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Send an alert when]** | [!UICONTROL **Någon av dessa mätvärden utlöser**]: Dra och släpp mätvärden (inklusive beräknade värden) här för att skapa utlösare för aviseringen.<p>Ett **&quot;inkompatibla komponenter&quot;**-meddelande visas om inte alla mått, dimensioner eller segment i aviseringen är kompatibla med den datavyn som är vald.</p><p>Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:</p><ul><li>avvikelse finns</li><li>avvikelsen är större än förväntat</li><li>avvikelsen är under förväntad</li><li>är över eller lika med</li><li>är under eller lika med</li><li>ändras med</li><li>Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.</li></ul><p>[!UICONTROL **Med alla dessa segment**]: Dra och släpp segment eller dimensioner för att lägga till segment. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter. Du kan lägga till ytterligare segment med en AND-sats. Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.</p><p>Se [Varningar - användningsfall](/help/components/c-intelligent-alerts/alerts-use-cases.md) använder till exempel fall.</p> |
| **[!UICONTROL Preview]** | I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.<p>Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.</p><p>Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Hantera aviseringar](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
