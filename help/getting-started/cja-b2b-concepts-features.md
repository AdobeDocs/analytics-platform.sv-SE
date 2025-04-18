---
title: Customer Journey Analytics B2B edition koncept och funktioner
description: Koncept och funktioner för B2B edition i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# B2B edition koncept och funktioner

{{draft-b2b}}

I den här artikeln förklaras allmänna koncept och funktioner för datauppsättningar och behållare och hur dessa skiljer sig åt mellan standarden och B2B edition för Customer Journey Analytics.

Datauppsättningar är källor för en anslutning. Som en del av konfigurationen av en anslutning definierar du datauppsättningar som ska ingå i den anslutningen.

Behållare används i Customer Journey Analytics för att stödja och underlätta funktioner som segment, beräknade värden och avancerade analysfunktioner.




## Standardbehållare

*standardversionen* av Customer Journey Analytics bygger på konceptet med tre behållare: Person, Session och Event. I en standardkonfiguration av Customer Journey Analytics genereras dessa relevanta behållare implicit baserat på din konfiguration.

Du kan definiera om hur de här behållarna ska namnges när du konfigurerar en datavy, men konceptuellt sett använder standardversionen en personbaserad behållarhierarki.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

I anslutningen lägger du till datauppsättningarna Event, Profile och Lookup, och du väljer vilka identiteter som ska användas för att definiera anslutningen mellan dessa datauppsättningar. Som en del av anslutningen genereras en personbaserad behållarhierarki automatiskt. I den hierarkin definieras sessionsbehållaren av [sessionsinställningarna](/help/data-views/session-settings.md) i datavyn.


## B2B-behållare

I Customer Journey Analytics B2B edition läggs en kontobehållare till i listan över genererade behållare.  Och du kan konfigurera genereringen av ytterligare behållare, som t.ex. Global Account, Buying Group och Opportunity.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

I anslutningen lägger du till datauppsättningarna Event, Account, Global Account, Opportunity, Buying Group och annan Lookup. Du väljer Konto som primärt ID för anslutningen så att du kan använda kontobaserade identiteter för att definiera anslutningen mellan datauppsättningarna. Som en del av anslutningen genereras en kontobaserad behållarhierarki automatiskt. I den hierarkin definieras sessionsbehållaren mellan personbehållaren och händelsebehållaren av [sessionsinställningarna](/help/data-views/session-settings.md) i datavyn. Dessutom stöds inte sessionsbehållare, till exempel mellan konto och händelse.

Affärsmöjlighet, inköpsgrupp och person är alla jämställda behållare för kontobehållaren. Se tabellen nedan för en beskrivning och grundläggande användning.

| B2B-behållare | Beskrivning<br/>Grundläggande användningsfall |
|---|---|
| Konto | Ett företag som är kund eller potentiell kund till ditt företag. Detta kan vara ett dotterbolag eller en division i en större organisation. Kontot representerar den organisation som du säljer till och vill spåra på den organisationsnivån. |
| Globalt konto (valfritt) | Det översta moderföretaget i en grupp av närstående företag. Ett globalt konto har inget moderföretag, men kan ha dotterföretag eller divisioner som tillhör det globala kontot. Ett konto som inte har något överordnat eller dotterföretag ska listas både i kontofältet och i det globala kontofältet, om båda är aktiverade som en del av konfigurationen av en anslutning. |
| Möjligheter (valfritt) | En samling produkter och tjänster som säljs tillsammans. En affärsmöjlighet involverade ofta olika faser i säljprocessen som skulle avslutas som en försäljning.<br>Du använder affärsmöjlighetsdata för att mäta säljprojektets förlopp genom säljprocessen. Till exempel en rapport som ger information om de viktigaste möjligheterna som flyttades från affärsfas 3 till fas 4. |
| Köpgrupp (valfritt) | En samling personer inom en organisation som deltar i beslutsprocessen för att köpa en produkt eller tjänst. <br/>Du använder inköpsgruppdata för att spåra inköpsgrupper via kampanjhantering. Du kan till exempel köpa ett målgruppssegment av nyckelköpgrupper.<br/> Du vill troligen ha en sökning från inköpsgruppen till profildata, så att du kan rapportera om personerna i en inköpsgrupp. |
| Person | En person som ofta identifieras av en unik e-postadress som har interagerat med företaget. <br/>Du använder profildata för att identifiera personer som arbetar för ett konto. Till exempel: rikta alla personer på ett konto som har registrerat sig för en konferens. |


## Matcha efter behållare eller fält

När du definierar en anslutning i Customer Journey Analytics kan du definiera datamängden för varje post (profil eller sökning), oavsett om den datauppsättningen matchas av behållare eller matchas av fält.

### Matcha efter behållare

Om en postdatamängd matchas av en behållare, till exempel Buying Group, behandlas postdatamängden som en profildatamängdstyp och som en profildatamängd i användargränssnittet.

### Matcha efter fält

Om en postdatamängd matchas av fält, till exempel Marknadsföringslistmedlem, behandlas postdatamängden som en uppslagsdatatyp och som en uppslagsdatamängd i användargränssnittet.



## Rapport om person- och kontouppgifter

Om du vill rapportera om personbaserade behållare (och personidentiteter) och kontobaserade behållare (och kontoidentiteter) bör du skapa två separata anslutningar i Customer Journey Analytics. En anslutning där du väljer Person som primärt ID och en anslutning där du väljer Konto som primärt ID. Customer Journey Analytics stöder inte personbaserad och kontobaserad rapportering från samma behållare.
