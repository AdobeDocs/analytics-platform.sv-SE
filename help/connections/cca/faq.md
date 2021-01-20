---
title: Vanliga frågor om flerkanalsanalys
description: Frågor och svar om flerkanalsanalys
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Frågor och svar

## Hur kan jag använda CCA för att se hur människor flyttar från en kanal till en annan?

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in [analytics.adobe.com](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Datauppsättning-ID&quot; till mittplatsen med etiketten &quot;Dimension eller Artikel&quot;.
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

Om du vill byta namn på dimensionsobjekt för datauppsättnings-ID kan du använda en uppslagsdatauppsättning.

## Hur långt tillbaka kan CCA skicka besökare?

Uppslagsfönstret för att skriva in data igen beror på hur ofta du vill använda data [replay](replay.md). Om du t.ex. konfigurerar CCA att spela upp data en gång i veckan, är uppslagsfönstret för inmatning sju dagar. Om du konfigurerar CCA att spela upp data varje dag är uppslagsfönstret för manuell inmatning 1 dag.

## Hur hanteras delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

Det tillfälliga ID:t åsidosätter det beständiga ID:t, så delade enheter betraktas som separata personer (även om de kommer från samma enhet).

## Hur hanterar CCA situationer där en person har ett stort antal beständiga ID:n?

I vissa fall kan en enskild användare associera med ett stort antal beständiga ID:n. Exempel är en person som ofta tar bort webbläsarcookies eller använder webbläsarens privata läge/inkognito-läge.

Antalet beständiga ID:n är irrelevant för det tillfälliga ID:t. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CCA:s möjlighet att sammanfoga enheter.

## När jag har kontaktat min kontoansvarige med den önskade informationen, hur lång tid tar det innan den inmatade datauppsättningen blir tillgänglig?

Liveutjämning är tillgänglig cirka en vecka efter att Adobe har möjliggjort kanalövergripande analys. Tillgängligheten för förifyllning beror på mängden befintliga data. Små datauppsättningar (mindre än 1 miljon händelser per dag) tar normalt några dagar, medan stora datauppsättningar (1 miljard händelser per dag) kan ta en vecka eller mer.

## Hur hanterar flerkanalsanalys GDPR- och CCPA-begäranden?

Adobe hanterar förfrågningar om GDPR och CCPA i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka begäran om dataåtkomst och borttagning. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.
