---
title: Rapport om Google Analytics data i Customer Journey Analytics
description: Visar användbara rapporter om Google Analytics data i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# Rapport om Google Analytics data i Customer Journey Analytics

Nu när du har [inhämtat data från Google Analytics till Experience Platform och Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md) visar vi några användbara scenarier för rapportering av dessa data.

## Visualisera webbdata och appdata som kombinerade datauppsättningar

I det här Venndiagrammet visas hur många användare som finns på din webbplats (från dina Google Analytics-data) och i din mobilapp (från dina Firebase-data) och från ditt callcenter. Du kan också se de bästa produkterna - inte bara på webben, utan även i mobilappen. Du kan till och med få de totala intäkterna från båda, med hjälp av ett beräknat mätvärde. Lägg märke till hur de bästa produkterna berättar en annan historia när du tittar på de kombinerade intäkterna. Utan de kombinerade datauppsättningarna skulle du aldrig ha vetat att &quot;Twill cap&quot; var en sådan stark utförare.

![](assets/combined-datasets.png)

## Identifiera samtalsorsaker och minska samtalsvolymen

För att bekräfta att du har fått många samtal kan du trenda vår samtalscentertid under de senaste två månaderna. Det är enkelt att se den ökande trenden. Det här är oroligt, eftersom telefonsvararna varje minut betalar er pengar. Det här kan definitivt påverka resultatet.

Låt oss titta på de främsta anledningarna till att fler samtal ringer till callcenter. Observera att&quot;Kreditkort nekas&quot;,&quot;Ta bort kreditkort&quot; och&quot;Skadad produkt&quot; är de viktigaste skälen. Detta ger redan tips om hur man kan förbättra upplevelsen online. Du kan också trender för de här samtalsortimenten och se vilka som har bidragit mest till den övergripande ökningen. Det är intressant att se att kunder med&quot;Skadad produkt&quot; har tillbringat mer än 3 minuter per samtal.

![](assets/call-volume.png)

Låt oss titta närmare på vilka produkter som orsakar de flesta samtalen till ert callcenter och hur många kunder som har ringt dessa samtal. Bubbeldiagrammet visar att 20 000 personer ringde, spenderade mer än 4 timmar och 30 minuter och returnerade 33 enheter av produkten &quot;Men&#39;s short Sleeve Tee&quot;.

Vi kan bryta ned den insikten och se varför de personer som returnerade produkten genom att dra i dimensionen&quot;Anropsorsak&quot;. Som du ser beror det på&quot;Skadad produkt&quot; att den här produkten har fått så många samtal. Nästa steg är att kontakta avdelningen för kvalitetskontroll och se varför kunderna har fått skadade T-shirts.

![](assets/call-reason.png)

Nu ska vi titta på vilka webbsidor som ledde inkommande samtal till callcenter. På så sätt får ni veta var det finns underpresterande upplevelser på webbplatsen och kan hjälpa era produktchefer att lösa dessa utmaningar.

Vi gör det här

* Använder ett beräknat mätvärde för att filtrera data ner till endast sessioner som avslutades med ett anrop till en callcenter.
* Använder deltagarmodellen i CJA:s [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace).

Du ser enkelt vilka sidor som oftast deltar i en session som avslutas med ett samtal. Du ser att sidorna&quot;Kundvagn&quot; och&quot;Kassainformation&quot; ledde de flesta samtal. Eftersom du även har inkluderat data för mobilappen i Firebase kan du till och med se sidfel och appkrascher som genererar anropen. Detta är en mycket viktig datapunkt om ni vill leverera fantastiska upplevelser för webben och mobilappar.

![](assets/contributing-pages.png)

Med kohorttabellen i Analysis Workspace är det enkelt att se hur lång tid det normalt tar för användare att ringa vårt callcenter efter att de har besökt webbplatsen. Här ser du hur den genomsnittliga tiden är mellan 3 och 4 veckor.

![](assets/cohort.png)

## Använd avancerad marknadsattribuering

Med CJA kan ni använda sofistikerade attribueringsmodeller på era flerkanalsdata. I följande exempel kan du se en jämförelse mellan hur man använder sista handen, första beröringen, u-formad och algoritmisk attribuering av intäkterna för grupperingsdimensionen för Google Analytics-kanalen.

![](assets/mktg-attribution.png)

Med hjälp av beräknade mätvärden kan du använda attribueringen på dina webbintäkter, intäkter från mobilappar och till och med ta bort produktreturer. Resultatet blir en verklig nettointäkt för varje marknadsföringskanal.

![](assets/calc-metric.png)

Med Attribution IQ kan du enkelt filtrera data. Du kan bara se attribuering mot vissa användaruppsättningar, till exempel de som använder mer än en enhet.

![](assets/filter.png)

Slutligen kan du även tilldela dina webb- och appintäkter till ditt Google Ad-innehåll. Du kommer att märka att du har fått mer intäkter av att mobilappen drivs av våra Google Ads online än från webben. Genom att sortera annonser efter webb- och appintäkter får ni en helt annan bild av vad era främsta Google-annonser var.

![](assets/google-ad.png)

Utan CJA kunde du inte ha vetat att dina onlineannonser hade någon effekt på produkter som köpts i din mobilapp. Nu ser du att intäkterna från Google Ads för mobilappar utgör ytterligare 14 000-5 000 dollar jämfört med bara webben.

![](assets/google-ad2.png)