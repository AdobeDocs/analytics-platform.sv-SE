---
title: Skapa ett härlett fält för marknadsföringskanal för Customer Journey Analytics
description: Lär dig hur du skapar ett marknadsföringskanalhärlett fält för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Skapa ett härlett fält för marknadsföringskanal för Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Skapa ett härlett fält för en marknadsföringskanal"
>abstract="Härledda fält skapas i en datavy.<br><br>Det tar bara några minuter att använda en standardinställning för marknadsföringskanal. Det kan ta flera timmar att skapa en mycket anpassad inställning för marknadsföringskanaler."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

När du använder Analytics-källkopplingen flödar marknadsföringskanalernas data in i Customer Journey Analytics via den kopplingen. Reglerna för marknadsföringskanaler har konfigurerats i traditionella Adobe Analytics och vissa regler stöds inte. Mer information finns i [Använda mått för marknadsföringskanal](/help/use-cases/aa-data/marketing-channels.md).

För att kunna använda marknadsföringskanaler i Customer Journey Analytics när du använder Experience Platform Web SDK kan du använda härledda fält i en datavy för att återskapa samma marknadsföringskanaler och bearbetningsregler för Customer Journey Analytics.

1. I Customer Journey Analytics väljer du datavyn där du vill lägga till marknadsföringskanaler.

1. Välj fliken **[!UICONTROL Components]** i datavyn.

1. Välj **[!UICONTROL Create derived field]** i den vänstra listen.

1. Välj **[!UICONTROL Function templates]** i listrutan i dialogrutan **[!UICONTROL Create derived field]**.

   ![Skapa härledda fältfunktionsmallar](assets/derived-field-create.png)

1. Dra mallen **[!UICONTROL Marketing channels]** till den tomma arbetsytan.

1. Anpassa logiken för varje marknadsföringskanal för att säkerställa att den matchar logiken du använder för att identifiera varje kanal i din Adobe Analytics-miljö.

   Du kan ändra namnen på utdatakanalerna eller lägga till logik för att identifiera ytterligare kanaler som är specifika för organisationen.

1. Ange ett namn och en beskrivning för marknadsföringskanalen i den högra kolumnen.

1. Välj **[!UICONTROL Save]**.

   Det nya härledda fältet läggs till i fältet Härledda fält > behållare, som en del av schemafälten i den vänstra listen i datavyn.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).
