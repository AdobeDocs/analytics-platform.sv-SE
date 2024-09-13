---
description: Få aviseringar när projektkomponenterna når vissa tröskelvärden.
title: Skapa varningar (Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f866d47ef0caccb91bd0e9cb9043bb1e16e0d89
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 0%

---

# Skapa aviseringar

>[!NOTE]
>
>Intelligenta aviseringar är tillgängliga för alla kunder. Om du vill använda avvikelseidentifiering i intelligenta aviseringar måste du ha Customer Journey Analytics Select, Prime eller Ultimate.

Med intelligenta aviseringar (eller bara &quot;aviseringar&quot;) i Customer Journey Analytics kan du få meddelanden direkt när onormala händelser inträffar i dina data.

Mer detaljerad översiktsinformation om intelligenta aviseringar finns i [Översikt över intelligenta aviseringar](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

Så här skapar du en varning:

1. Börja skapa en avisering med hjälp av varningsverktyget. Du kan öppna varningsverktyget på något av följande sätt:

   * Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Öppna ett projekt i Analysis Workspace och använd sedan följande kortkommando:

     `ctrl (or cmd) + shift + a`
   * Öppna ett projekt i Analysis Workspace, markera ett eller flera linjeobjekt i en frihandstabell, högerklicka och välj **[!UICONTROL Create alert from selection]**.

     Varningsbyggaren fylls i automatiskt för att skapa en avisering med rätt mätvärden och filter.
   * I Customer Journey Analytics väljer du **[!UICONTROL Components]** > [!UICONTROL **Varningar**] > **[!UICONTROL Create new alert]**.

   Varningsbyggaren visas. Det här gränssnittet är bekant för dem som har skapat segment eller beräknade värden i Analytics:

   ![](assets/alert-builder.png)

1. Ange följande alternativ för att konfigurera varningen:

   | Alternativ | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Titel**] | Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde. |
   | [!UICONTROL **Beskrivning (valfritt)**] | Ange en beskrivning för aviseringen. |
   | [!UICONTROL **Tidsgranularitet**] | Välj hur ofta du vill att måttet ska kontrolleras: Varje dag, Varje vecka eller Varje månad.<p><b>Obs!</b>För datavyer med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.<!--true?--></p> |
   | [!UICONTROL **Mottagare**] | Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.<p><b>Viktigt!</b>Telefonnumret måste föregås av ett plustecken och en [landskod](https://countrycode.org/).</p><p>Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:</p><p>![Varningsmeddelande](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Förfallodatum**] | Ange det datum och den tidpunkt då du vill att aviseringen ska förfalla. |
   | [!UICONTROL **Fördröjning**] | Den tid som krävs innan data är fullständiga och tillgängliga att rapporteras i Customer Journey Analytics varierar beroende på organisation, vanligtvis från 3 till 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste händelsedata för ett givet händelseintervall vara fullständiga, vilket innebär att Adobe inte längre tar emot händelsedata för det angivna händelseintervallet.<p>Om du vill ta hänsyn till den här fördröjningen av inmatningstiden har aviseringar en standardfördröjning på 9 timmar innan de skickas.</p><p>Du kan justera standardfördröjningen på 9 timmar till valfri plats mellan 0 och 24 timmar. Om du minskar fördröjningen till under 9 timmar kan det dock innebära att du rapporterar ofullständiga data, vilket leder till felaktig varningsinformation.</p><p>Tänk på följande när du minskar fördröjningstiden:</p><ul><li>**Förstå datatillgänglighet jämfört med datafullständighet**: Vissa data kan vara tillgängliga att rapportera tidigare, men alla batchdata importeras till en plattformsdatauppsättning först efter en period på 3 till 9 timmar. För att varningarna ska vara korrekta måste datainmatningen vara fullständig, med alla batchdata tillgängliga i datauppsättningen.</li><li>**Bestäm hur lång tid det tar för dina data att bli fullständiga och tillgängliga i datauppsättningen**: Dataöverföringstiderna skiljer sig åt i olika organisationer. Se till att fördröjningen som du väljer för varningsleverans är samma eller mindre frekvent än den tid det tar för batchdata att vara tillgängliga i plattformsdatauppsättningen <!--add link? -->.</li><p>**Tips!** Det mest korrekta sättet att veta hur lång tid det tar för alla batchdata att slutföras och hämtas till plattformsdatauppsättningen är att rådfråga datateknikerna i organisationen.</p><p>Du kan också få en allmän uppfattning om hur lång tid det tar för batchleveransen i organisationen att vara tillgänglig i plattformsdatauppsättningen genom att skapa följande friformstabell i Analysis Workspace:</p><ol><li>I en frihandstabell i Analysis Workspace lägger du till måtten [!UICONTROL **Händelser**] och [!UICONTROL **Dag**] .</li><li>Dela upp dimensionen [!UICONTROL **Dag**] med en [!UICONTROL **Timmar**]-dimension.<p>Timmar utan data visas som 0.</p></li></ol><li>**Ta hänsyn till fel i dina beräkningar**: Om du minskar standardfördröjningstiden rekommenderar vi att du konfigurerar fördröjningen i minst en timme längre än den tid det tar för organisationen att slutföra dataimporten. Om det till exempel finns en 3-timmars fördröjning innan dataimporten är klar bör du ange fördröjningen till 4 timmar.</li></ul><p>Mer information finns i [Tidsåtgången för dataöverföring kan variera i Customer Journey Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) i artikeln [Funktionsjämförelse för intelligenta aviseringar: Customer Journey Analytics och Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md). |
   | [!UICONTROL **Skicka en avisering när**] | [!UICONTROL **Någon av dessa mätvärden utlöser**]: Dra och släpp mätvärden (inklusive beräknade värden) här för att skapa utlösare för aviseringen.<p>Ett **&quot;inkompatibla komponenter&quot;**-meddelande visas om inte alla mått, dimensioner eller segment i aviseringen är kompatibla med den datavyn som är vald.</p><p>Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:</p><ul><li>avvikelse finns</li><li>avvikelsen är större än förväntat</li><li>avvikelsen är under förväntad</li><li>är över eller lika med</li><li>är under eller lika med</li><li>ändras med</li><li>Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.</li></ul><p>[!UICONTROL **Med alla dessa filter**]: Dra och släpp segment eller dimensioner för att lägga till filter. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter. Du kan lägga till ytterligare filter med en AND-programsats. Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.</p><p>Se [Intelligenta aviseringar - användningsfall](/help/analysis-workspace/c-intelligent-alerts/alerts-use-cases.md), t.ex. fall.</p> |
   | [!UICONTROL **Förhandsgranska**] | I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.<p>Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.</p><p>Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Varningshanteraren](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Välj [!UICONTROL **Spara**].

