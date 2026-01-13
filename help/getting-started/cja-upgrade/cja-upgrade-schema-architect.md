---
title: Skapa ett schema som kan användas med Customer Journey Analytics
description: Lär dig hur du utformar ett XDM-schema som frigör Customer Journey Analytics flexibilitet och stöder en praktisk migreringsväg från Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: b94c60c9832bc699212dda97ad634e8d3260c45c
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 0%

---

# Skapa ett schema som kan användas med Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Arkitekt a schema"
>abstract="Diskutera behovet av datainsamling inom organisationen och fastställ hur du vill skapa ett schema för användning i Adobe Experience Platform. Det här steget visas eftersom du vill använda den rekommenderade processen att använda ett schema som är anpassat till din organisation. Att utföra det här steget korrekt är avgörande eftersom ett schema som alla team i organisationen anpassar sig efter gör det betydligt enklare att få in data.<br><br>Den beräknade tiden för att sammanföra alla relevanta parter i organisationen så att de följer ett enhetligt schema är 1-2 månader. Den här tidsramen är mycket beroende av hur många team som behövs för att samordna och hur många dimensioner + mått som ska justeras efter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe rekommenderar att du skapar ett anpassat [Experience Data Model](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/home) (XDM)-schema för Customer Journey Analytics när du implementerar [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/sv/docs/experience-platform/collection/home). Det här schemat skapas vanligtvis innan implementeringsändringar eller kod ändras. Med ett anpassat schema kan du utforma ett koncist, organisationsspecifikt datakontrakt utan att ärva begränsningar från Adobe Analytics. Se [Välj ditt schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) om du vill veta mer om vilka schematyper som är tillgängliga för din organisation.

Scheman är avsedda att vara prydliga versioner av hur ni vill att era data ska struktureras på lång sikt. Förändringar av scheman är dyra eftersom de påverkar datainsamling, validering och tjänster längre fram i kedjan. Du kan lägga till i scheman över tid när affärskraven tillåter det, men schemafält kan inte tas bort när data börjar flöda in i dem.

## Jämför scheman med datavyer

Datalindelningen för Customer Journey Analytics innehåller separata områden för datainsamling och datatolkning. När du uppgraderar från Adobe Analytics försöker ett vanligt felsteg att återskapa props och eVars med sina beteenden i XDM. Använd istället Web SDK för att samla in data och använd [datavyer](/help/data-views/data-views.md) för att avgöra hur data tolkas i rapporter.

| Lager | Primärt syfte | Flexibilitet | Vad tillhör | Vad som inte hör till |
|---|---|---|---|
| **XDM-schema** | Definiera den varaktiga strukturen och innebörden av insamlade data | Rigid; betraktas som oföränderliga datapunkter | Händelse- och entitetsform, fältinnebörd, relationer, tillåtna värden, återanvändning över kanaler | Numrerade&quot;fack&quot; (eVar1/prop1), attribuerings-/beständighetslogik, rapportspecifika temporära lösningar |
| **Datavyer** | Definiera hur insamlade data fungerar i analysen | Flexibelt; kan ändras fritt och kan omtolka data retroaktivt | Komponentinställningar, attribuering och beständighetsbeteende, härledda fält, filtrerade mätvärden, beräknade värden | Fältens grundläggande betydelse. Den betydelsen bör vara stabil i schemat |

## Jämför scheman med Adobe Analytics datainsamling

Den Experience Data Model som Customer Journey Analytics använder ger betydligt större flexibilitet än de flesta andra Analytics-lösningar (inklusive Adobe Analytics). Att skapa ett stabilt schema är er organisations möjlighet att undvika att överföra begränsningar som finns i andra Analytics-produkter.

| Vanlig Adobe Analytics-vana | Bättre arbetssätt i XDM + Customer Journey Analytics |
|---|---|
| Utforma runt numrerade kortplatser (`eVar1`-`eVar250`, `prop1`-`prop75`) | Skapa fält med stabil innebörd (till exempel `search.term`, `content.category`, `user.membershipTier`) och återanvänd dem konsekvent |
| Kodning av beständighet/allokering/utgångsdatum i datamodellen | Hämta varaktiga fakta i schemat; tillämpa attribuering och beständighetsbeteende på datavynivå |
| Duplicera samma värde i flera variabler för att få rapportbeteenden | Lagra värdet en gång och skapa flera komponenter (mått/mått) från det i datavyer |
| Skapa ett unikt&quot;mätfält&quot; för varje antal som du kanske vill ha | Fånga in rätt fakta en gång (ofta som enum/booleans/strings) och definiera sedan mätvärden som filtrerade tal i datavyer |
| Utforma variabler för att&quot;lösa upp&quot;-rapportering | Utforma ditt schema för att fånga fakta och använda datavyer för att lösa rapporteringssemantik |

## Skapa ett schema med gemensamma attribut

Ett enhetligt schema över flera kanaler blir möjligt när du standardiserar en uppsättning återanvändbara attribut som visas i många händelser. Några exempel är:

* **Experience context:** plats-/appnamn, miljö, språkområde, kanal, varumärke
* **Resekontext:** kampanjidentifierare, refererande kontext, experimentidentifierare
* **Användartillstånd:** inloggad status, medlemsnivå, kontotyp
* **Interaktionsinformation:** interaktionsnamn/typ, gränssnittsområde, elementetikett, felkategori

Nyckeln är att standardisera det som fältet representerar oavsett kanal. Undvik att modellera samma koncept på olika sätt i olika kanaler om de inte representerar olika koncept. Det kan till exempel vara klokt att undvika separata schemafält för webbkampanjer-ID:n och mobilkampanjer-ID:n. Separata schemafält gör det svårare att upprätta kanalövergripande avkastning på annonsutgiftsdata. Om det krävs en differentiering i rapporteringen kan du segmentera efter kanal eller slå samman flera fält för att göra den skillnaden. Samma schemafält kan användas i valfritt antal dimensioner eller mätvärden.

Ett praktiskt sätt att stödja flera kanaler samtidigt som en enda schemastrategi behålls är att använda ett **core + extensions** -mönster:

* **Kärnfält:** fält som gäller i stort sett för alla kanaler och team
* **Tillägg:** kanal- eller domänspecifika fältgrupper som endast gäller där det behövs (webbinteraktion, handel, mobillivscykel, serversidesinformation)

Det här mönstret stöder en enda strategi för organisationsscheman utan att tvinga team att fylla i onödiga fält.

## Föredra standardfältgrupper där de passar

Adobe rekommenderar att du använder standardiserade fältgrupper där de passar dina behov och utökar dem med anpassade fält för organisationsspecifika koncept.

Standardfältgrupper hjälper dig vanligtvis:

* Minska tvetydigheten genom att använda känd fältsemantik
* Enklare justering mellan team
* Stöd för samverkan mellan olika Adobe Experience Platform-program

Anpassade fält är lämpliga när:

* Din organisation har koncept som inte mappas korrekt till standardfält
* Du behöver ytterligare attribut för att uppfylla kraven på rapportering, styrning eller aktivering
* Du vill representera en företagsspecifik taxonomi (till exempel interna innehållskategorier)

## Bestäm hur mätvärden räknas

I Adobe Analytics behandlar många team variabeln `events` som det enda sättet att spåra mätvärden. I Customer Journey Analytics kan du spåra mätvärden på flera sätt beroende på vad du behöver räkna och hur du vill tolka dem.

När du skapar ett schema måste du hålla dig till fakta. Exempel: `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Definiera mätvärden i datavyn som antal och filtrerade räkningar över dessa fakta. Exempel:

* `checkout.step` (enum/string) kan strömma:
   * &quot;Utcheckning: Leveranssteget har nåtts&quot; (räkna där `checkout.step == "shipping"`)
   * &quot;Utcheckning: Betalningssteget har nåtts&quot;
* `error.type` (enum/string) kan strömma:
   * &quot;Valideringsfel&quot;
   * &quot;Auktoriseringsfel&quot;
* `user.isLoggedIn` (boolesk) kan strömma:
   * &quot;Autentiserade sessioner&quot;
   * &quot;Autentiserade konverteringar&quot;

>[!TIP]
>
>När du bestämmer dig för om något ska vara ett dedikerat fält i schemat eller ett härlett fält senare, bör du föredra att fånga den varaktiga uppgiften i schemat om det är praktiskt och stabilt. Du kan använda härledda fält för att korrigera eller ändra form på data efter insamlingen.

## Bevara paritet med Adobe Analytics under övergång utan schemabagage

Vissa organisationer måste fortsätta rapportera från Adobe Analytics medan de uppgraderar till Customer Journey Analytics. Du kan behålla paritet utan att införa analysspecifika artefakter i din långsiktiga schemadedesign enligt följande:

1. **Använd XDM-fältsökvägar som Adobe Analytics känner igen och automatiskt mappar:** När du skickar identifierade XDM-fält via Edge Network till Adobe Analytics [mappas de automatiskt](https://experienceleague.adobe.com/sv/docs/analytics/implementation/aep-edge/xdm-var-mapping) utan extra konfiguration.
1. **Använd anpassade XDM-fält för organisationsspecifika koncept:** Alla XDM-fält som inte automatiskt mappas till en Analytics-variabel vidarebefordras som [Kontextdatavariabler](https://experienceleague.adobe.com/sv/docs/analytics/implementation/vars/page-vars/contextdata) i Adobe Analytics.
1. **Använd Adobe Analytics bearbetningsregler för att mappa dessa kontextdatavariabler till props/eVars:** [Med bearbetningsregler](https://experienceleague.adobe.com/sv/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) kan du till slut mappa anpassade XDM-fält till alla eVar eller prop. Detta koncept stöder paritetsrapportering i Adobe Analytics samtidigt som ditt schema hålls rent och fokuserat på Customer Journey Analytics.

## Identifiera intressenter och definiera ägarskap

Schemadesignen lyckas när fältinnebörden avtalas och upprätthålls. Organisationsstrukturen varierar, men följande roller är vanliga:

* **Analysadministratör/analytiker**: definierar rapportfrågor, validerar att fält representerar meningsfulla begrepp och granskar analyssemantik i datavyer.
* **Utvecklare/implementeringsägare**: Ser till att fält kan samlas in på ett tillförlitligt sätt med Web SDK och justeras mot datalagret/appinstrumenteringen.
* **Dataarkitekt/ingenjör**: Säkerställer schemakompatibilitet, återanvändning över domäner och kompatibilitet med underordnade tjänster.
* **Intresserad av sekretess- och styrningsfrågor**: Granska datamängdsminimering, förväntat samtycke och begränsningar för dataanvändning.

Definiera en tydlig ägare för schemaändringar. Ett stabilt schema med disciplinerad ändringskontroll förhindrar att längre fram i kedjan bryts och minskar omarbetningen. Överväg att använda ett arbetsflöde för spårning av styrning eller verktyg för att demokratisera förfrågningar och hantera ändringskontroll över tid.

## Sekretess- och styrningsaspekter

Schemadesignen bör återspegla förväntningarna på integritet och styrning, enligt din organisations sekretesspolicy. Tänk på följande när du skapar ditt schema:

* Samla bara in det du behöver för att få stöd för definierade användningsfall.
* Se till att kraven på samtycke och dataanvändning återspeglas i er insamlingsstrategi. Mer information finns i [Använd SDK för att bearbeta kundens medgivandedata](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/consent/sdk).
* Tänk på hur känsliga fält är märkta och styrda med Adobe Experience Platform styrningsverktyg. Mer information finns i [Adobe Customer Journey Analytics och datastyrning](/help/privacy/privacy-overview.md).

## Nästa steg

När du väl har etablerat och kommit överens om en schemaarkitektur kan du börja skapa den i Adobe Experience Platform. Mer information finns i [Skapa ett anpassat schema att använda med Customer Journey Analytics](cja-upgrade-schema-create.md).
