---
title: Vanliga frågor om hur länge medieuppspelning används
description: Vilka är de vanliga frågorna för Media Playback Time?
feature: Panels
role: User, Admin
exl-id: 5778c030-6790-42cb-a0f7-294d896fbbc2
source-git-commit: a9ba9def94a2f156f6d2d8e59c0155a492c3978c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 1%

---

# Vanliga frågor om hur länge medieuppspelning används


| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | <p></p><p>Frihandsregistret är inte tillgängligt i den här vyn. Du kan hämta datakällan genom att högerklicka på linjediagrammet och hämta CSV-filen.</p> |
| <p>Varför ändrades min granularitet?</p> | <p>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.</p><p></p><p>Om du ändrar från ett större datumintervall till ett mindre kommer granulariteten att uppdateras till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den.</p> |
| <p></p><p>Hur jämför jag videonamn, segment, innehållstyper osv.?</p> | <p>Om du vill jämföra dessa i en enda visualisering drar du segment, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.</p><p></p><p>Vyn är begränsad till tio uppdelningar. Om du vill visa mer än 10 måste du använda flera paneler.</p> |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall. Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | <p></p><p>På den här panelen kan du endast använda linjevisualisering för tidsserien.</p> |
| Kan jag köra avvikelseidentifiering? | <p></p><p>Nej. Anomalsidentifiering är inte tillgängligt för den här panelen.</p> |
