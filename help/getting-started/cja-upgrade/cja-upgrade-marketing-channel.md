---
title: Skapa ett härlett fält för marknadsföringskanal för Customer Journey Analytics
description: Lär dig skapa ett marknadsföringskanalhärlett fält för Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Skapa ett härlett fält för marknadsföringskanal för Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Skapa ett härlett fält för en marknadsföringskanal"
>abstract="Härledda fält skapas i en datavy.<br><br>Det tar bara några minuter att använda en standardinställning för marknadsföringskanal. Det kan ta flera timmar att skapa en mycket anpassad inställning för marknadsföringskanaler."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

När du använder Analytics-källkopplingen flödar marknadsföringskanalernas data till Customer Journey Analytics via den kopplingen. Reglerna för marknadsföringskanaler har konfigurerats i traditionella Adobe Analytics och vissa regler stöds inte. Mer information finns i [Använda mått för marknadsföringskanal](/help/use-cases/aa-data/marketing-channels.md).

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

{{upgrade-final-step}}
