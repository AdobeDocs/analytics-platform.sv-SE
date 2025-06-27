---
description: Läs mer om några exempel på hur man använder kohortanalyser.
keywords: Analysis Workspace
title: Kohortanalyser använder XAS
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 0%

---

# Användningsexempel för kohortanalyser

I den här artikeln beskrivs några exempel på hur man använder en kohortanalys.

## Användningsexempel för appengagemang

Anta att du vill analysera hur användare som installerar din app interagerar med den med tiden. Installerar de den och använder den aldrig? Använder de den en stund och faller sedan bort? Eller förblir de förlovade med tiden?

Du kan skapa en sexmånaders kohortanalys.

**Kornighet**: Månadsvis, från januari 2015 till juni 2015.

**Inkluderingsmått**: Appinstallationer.

**Returmått**: Sessioner eller starter

Personer räknas inte som *engagerade* under de följande månaderna, såvida de inte har en session eller åtminstone startar appen. [!UICONTROL Cohort Analysis] visar sedan mönster som används där *Programinstallation* alltid sker i månad 0. Du kan märka att användningen minskar i månad 2, oavsett när användarna installerade appen. (För de användare som installerade programmet i januari 2015 är månad 2 mars 2015. För dem som installerade appen i februari 2015 är månad 2 april 2015 och så vidare.) Med den här analysen kan du skicka ett e-postmeddelande eller ett push-meddelande till alla användare under den andra månaden efter att de har installerat appen för att påminna dem om att använda appen.

## Användningsexempel för prenumeration

Du arbetar på Adobe.com och erbjuder en kostnadsfri prenumeration på Creative Cloud. Målet är att man ska uppgradera från den kostnadsfria versionen till den 30-dagars testversionen eller, i slutändan, den betalda versionen.

**Kornighet**: Månadsvis

**Inkluderingsmått**: Hämta länk

**Returmått**: Köp betald Creative Cloud

Om du använder [!UICONTROL Cohort Analysis] kan du till exempel se att mellan 8 % och 10 % av de kostnadsfria Creative Cloud-användarna uppgraderar var som helst under den första månaden efter installationen. Oavsett när användarna installerades. 12-15 % uppgradering under den andra månaden. Efter det kommer uppgraderingen att minska avsevärt: 4-5 % under den tredje månaden, 3-4 % under den fjärde månaden och 1-2 % under den femte månaden.

Ni vill inte förlora potentiella kunder under den tredje månaden. Så ni har skapat en e-postkampanj som är utformad för att gå ut mitt i den tredje månaden till ett urval av användare. Ger 50 USD rabatt till användare som ännu inte har uppgraderat.

Kolla in era kohortanalysrapporter några månader senare. För kohorter som bildas efter lanseringen av kampanjen har konverteringen till betalda Creative Cloud-prenumerationer under den tredje månaden ökat från 4-5 % till 13-14 %. Denna ökning av konverteringsgraden resulterar i hundratusentals dollar per kohort för varje månadskohort som kommer tre månader framåt från den tidpunkten.

## Komplexa kohortsegment använder skiftläge

En stor hotellkedja vänder sig till flera kundgrupper för att få kampanjer och hålla koll på resultatet. För att identifiera de bästa grupperna med användarkohorter att rikta sig till, vill de skapa mycket specifika kohortgrupper. Med hjälp av de utökade [!UICONTROL Inclusion]- och [!UICONTROL Return]-kriterierna i [!UICONTROL Cohort]-tabellerna kan hotellkedjan definiera precis rätt kohortgrupper med flera mätvärden och segment. Hotellkedjan kan identifiera underpresterande kundgrupper för att rikta sig till kunder med kampanjer och erbjudanden för att öka bokningarna.

## App Version Adobes användningsexempel

Ett stort försäkringsföretag driver kundengagemanget genom att använda sin mobilapp. Men när nya funktioner läggs till i appen är det viktigt att kunderna uppgraderar till den senaste appversionen. De kan analysera och jämföra alla sina appversioner sida vid sida med hjälp av [!UICONTROL Custom Dimension] Cohort för att se vilka kunder som målversionen är avsedd för. Dessutom kan de spåra både lojalitet och bortfall för att se om specifika appversioner gör att kunderna slipper använda appen över tid. Tack vare mobilmeddelanden kan de återengagera dessa användare för att få dem att uppgradera till den senaste versionen och dra nytta av de senaste funktionerna.

## Användningsexempel för kampanjfokus

Ett multinationella medieföretag använder riktade kampanjer för att locka användare till olika plattformar för att öka engagemanget. Annonskostnaderna per plattform baseras på kundengagemang och kundlojalitet. Därför är framgångsrika kampanjer avgörande för att deras verksamhet ska lyckas. De använder den nya kohortfunktionen [!UICONTROL Custom Dimension] i [!UICONTROL Cohort]-tabeller för att jämföra olika kampanjer sida vid sida för att identifiera vilka kampanjer som är mest effektiva när det gäller att värva och behålla användare för att öka engagemanget. De kan sedan identifiera vilka aspekter som gör en kampanj framgångsrik och använda den på andra kampanjer för att öka engagemanget på deras olika plattformar.

## Produktstartexempel

En stor klädhandlare har många specifika kundsegment som genererar stora delar av intäkterna för sin verksamhet. Varje segment har specifika produkter som är utformade och skapade med segmentet i åtanke. När de lanserar en produkt vill de veta hur den nya produkten har ökat försäljningen till olika kohorter med tiden. Med den nya [!UICONTROL Latency Table]-inställningen i [!UICONTROL Cohort Analysis] kan de analysera ett visst kundsegments beteende och intäkter före och efter lanseringen. Med hjälp av den här informationen kan de identifiera vilka produkter som genererar nya intäkter och vilka som inte drar nytta av kundernas intresse.

## Individuell tröghet - De flesta lojala användare använder skiftläge

Ett stort flygbolag får större delen av sin framgång och sina intäkter från återkommande och lojala kunder. I många fall utgör deras lojala resenärer merparten av intäkterna och att behålla dessa kunder är avgörande för deras långsiktiga framgång. Det kan ofta vara svårt att identifiera sina mest lojala och enhetliga kunder. Med den nya [!UICONTROL Rolling Calculation]-inställningen i [!UICONTROL Cohort Analysis] kan flygbolaget analysera lojala kundsegment och ta reda på vilka resenärer som upprepade köpare varje månad. Flygbolaget kan även inrikta sig på resenärerna med belöningar och förmåner för deras lojalitet. Genom att byta från kundlojalitet till bortfall kan flygbolaget dessutom identifiera vilka kunder som inte är återkommande köpare varje månad och inrikta sig på dessa kunder med kampanjer. Så att flygbolaget kan återta kontakten med dessa kunder och se till att de fortsätter att vara lojala kunder i framtiden.
