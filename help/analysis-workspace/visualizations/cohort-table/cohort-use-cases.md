---
description: Använd fallexempel för kohortanalys.
keywords: Analysis Workspace
title: Användningsexempel på kohortanalyser
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---


# [!UICONTROL Cohort Analysis] användningsfall

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Använd exempel på fall för [!UICONTROL Cohort Analysis].

## Användningsfall för programåtagande

Anta att du vill analysera hur användare som installerar din app hanterar den med tiden. Installerar de den och använder den aldrig? Använder de den ett tag och faller sedan bort? Eller är de fortfarande engagerade över tiden?

Du kan skapa en sexmånadersperiod [!UICONTROL Cohort Analysis]:

**Granularitet**: Månadsvis, från januari 2015 till juni 2015.

**Inkluderingsmått**: Appinstallationer.

**Returmått**: Sessioner eller starter

Besökare räknas inte som *`engaged`* under de följande månaderna, såvida de inte har en session eller åtminstone startar appen. [!UICONTROL Cohort Analysis] visar då mönster som används där *`App Install`* inträffar alltid månad 0. Du kanske märker att det händer att det händer något i månad 2, oavsett när användare installerar appen. (För dem som installerade appen i januari 2015 är månad 2 mars 2015. För dem som installerade appen i februari 2015 är månad 2 april 2015 och så vidare.) Med den här analysen kan du skicka ett e-postmeddelande eller ett push-meddelande till alla användare under den andra månaden efter att de har installerat appen för att påminna dem om att använda appen.

## Prenumerationsanvändningsfall

Du arbetar på Adobe.com och erbjuder en kostnadsfri Creative Cloud-prenumeration. Målet är att användarna ska kunna uppgradera från den kostnadsfria versionen till testversionen på 30 dagar eller, i sista hand, den betalda versionen.

**Granularitet**: Månadsvis

**Inkluderingsmått**: Hämta länk

**Returmått**: Köp betald kreativ moln

Använda detta [!UICONTROL Cohort Analysis]kan du t.ex. se att mellan 8 % och 10 % av de kostnadsfria Creative Cloud-användarna uppgraderar under den första månaden efter installationen, oavsett när de installeras. Uppgradera 12-15 % under den andra användningsmånaden. Efter detta avtar uppgraderingen betydligt: 4-5% i månad 3, 3-4% i månad 4 och 1-2% i månad 5.

Eftersom du inser att du inte behöver förlora potentiella kunder under månad tre, har du skapat en e-postkampanj som är utformad för att gå ut i mitten av månad tre till ett urval av användare och erbjuder en kupong på 50 dollar till användare som ännu inte har uppgraderat.

Kom tillbaka med din kohortanalysrapport några månader senare. För kohorter som bildades efter lanseringen av kampanjen har omvandlingen till betalda kreativa molnprenumerationer under månad tre ökat från 4-5 procent till 13-14 procent, vilket resulterat i hundratusentals dollar per kohort, för varje månatlig kohort som träffar månad tre från den punkten framåt.

## Fall för komplexa kohortsegment används

En stor hotellkedja riktar in sig på flera kundgrupper för befordran och spårning mot prestanda. För att identifiera de bästa grupperna av användarkohorter att nå målet vill de skapa mycket specifika kohortgrupper. Använda det ökade [!UICONTROL Inclusion] och [!UICONTROL Return] Kriterier inom [!UICONTROL Cohort] Tabellerna kan bara definiera rätt kohortgrupperingar med flera mått och segment för att identifiera kundgrupper som inte uppnår resultat, så att de kan få erbjudanden och erbjudanden om att öka bokningar.

## Användningsfall för programversion

Ett stort försäkringsföretag driver en hel del kundengagemang genom att använda sin mobilapp. När nya funktioner läggs till i appen är det dock viktigt att deras kunder uppgraderar till den senaste appversionen. De kan analysera och jämföra alla sina appversioner sida vid sida med hjälp av [!UICONTROL Custom Dimension] Kohort för att se vilka kunder som ska omfattas av vilken programversion. Dessutom kan de spåra både kvarhållning och churn för att se om specifika appversioner leder kunderna bort från att använda appen över tiden. Genom att arbeta med mobila meddelanden kan de ta nya kontakter med dessa användare för att få dem att uppgradera till den senaste versionen och utnyttja sina senaste funktioner.

## Användningsfall för kampanjskärpa

Ett multinationellt medieföretag använder riktade kampanjer för att driva användare till deras olika plattformar för att driva engagemang. Förbrukningsutgifter per plattform är baserade på kundengagemang och kvarhållande. Därför är framgångsrika kampanjer avgörande för att deras verksamhet ska lyckas. De använder våra nya [!UICONTROL Custom Dimension] Kohortfunktion i [!UICONTROL Cohort] Tabeller för att jämföra olika kampanjer sida vid sida för att identifiera vilka kampanjer som är mest effektiva när det gäller att skaffa och behålla användare för att öka engagemanget. De kan sedan identifiera vilka aspekter som gör en kampanj framgångsrik och tillämpa den på andra kampanjer för att öka engagemanget på olika plattformar.

## Användningsfall för produktlansering

En stor klädåterförsäljare har många specifika kundsegment som driver stora delar av intäkterna till sin verksamhet. Varje segment har specifika produkter som utformats och skapats med segmentet i åtanke. Med varje lansering av produkten vill de veta hur den nya produkten har ökat försäljningen till olika kohorter med tiden. Använda nya [!UICONTROL Latency Table] ange [!UICONTROL Cohort Analysis]kan de analysera ett visst kundsegments beteende och intäkter före och efter lanseringen. Med hjälp av denna information kan de identifiera vilka produkter som driver på nya intäkter och som inte drar nytta av kundkontakten.

## Individuell tröghet - de flesta lojala användare använder fall

Ett stort flygbolag får merparten av sina framgångar och intäkter från upprepade och lojala kunder. I många fall utgör deras lojala resenärer merparten av deras inkomster, och att behålla dessa kunder är avgörande för deras framgång på lång sikt. Det kan ofta vara svårt att identifiera sina mest lojala och konsekventa kunder. Med hjälp av det nya [!UICONTROL Rolling Calculation] ange [!UICONTROL Cohort Analysis], kunde de analysera lojala kundsegment och ta reda på vilka resenärer som var upprepade köpare månad över månad. De kunde då rikta in sig på dessa resenärer med belöningar och prestationer för sin lojalitet. Genom att byta från kvarhållningstyp till churn kunde de också identifiera vilka kunder som inte var upprepade köpare månad över månad och rikta in sig på dessa segment med erbjudanden för att återknyta kontakten med dem och se till att de förblir lojala kunder i framtiden.
