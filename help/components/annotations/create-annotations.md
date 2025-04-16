---
title: Skapa anteckningar
description: Så här skapar du anteckningar i Workspace.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: 3cbf30778ff0fbb4198db16cbbabf3d62a87d384
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---

# Skapa anteckningar

Som standard kan bara administratörer skapa anteckningar. Användare har behörighet att visa anteckningar, ungefär som hur användare visar andra komponenter (till exempel segment, beräknade värden osv.).

Administratörer kan dock ge användare behörighet **[!UICONTROL Annotation Creation]** för **[!UICONTROL Reporting Tools]** i **[!UICONTROL Edit permissions for CJA Workspace Access]** via Admin Console. Mer information finns i [Åtkomstkontroll på användarnivå](/help/technotes/access-control.md#user-level-access).

Du kan skapa en anteckning på följande sätt:

![Skapa en anteckning](assets/create-annotation.png)

* **A**. I huvudgränssnittet väljer du **[!UICONTROL Components]** och sedan **[!UICONTROL Annotations]**. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] i [[!UICONTROL Annotations] manager](/help/components/annotations/manage-annotations.md).
* **B**. I ett Workspace-projekt väljer du **[!UICONTROL Create annotation from selection]** på snabbmenyn i en visualisering.
* **C**. I ett Workspace-projekt väljer du **[!UICONTROL Annotate Selection]** på snabbmenyn i ett linjediagram.
* **D**. I ett Workspace-projekt väljer du **[!UICONTROL Components]** på menyn och sedan **[!UICONTROL Create annotation]**.
* **E**.  Använd genvägen **[!UICONTROL ctrl+shift+o]** (Windows) eller **[!UICONTROL shift+command+o]** (macOS) i ett Workspace-projekt

Om du vill definiera anteckningen använder du [[!UICONTROL Annotation builder]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Anteckningsverktyget {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="Anteckningsinformation"
>abstract="Anteckningar gör att ni effektivt kan kommunicera kontextuella datanunkter och insikter till organisationen. De gör att du kan koppla kalenderhändelser till specifika mått/mätvärden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="Omfång"
>abstract="Med omfång kan du anpassa vilka data som ska kommenteras. Beräknade mått och segment ärver inte automatiskt anteckningar som tillämpas på komponenter som används i deras definitioner. Du kan lägga till nya beräknade värden i omfångsavsnittet i en befintlig anteckning. Nya segment kräver en ny anteckning."

<!-- markdownlint-enable MD034 -->


Dialogrutan **[!UICONTROL Annotations builder]** används för att skapa nya eller redigera befintliga anteckningar. Dialogrutan heter **[!UICONTROL New annotation]** eller **[!UICONTROL Edit annotation]** för anteckningar som du skapar eller hanterar från [[!UICONTROL Annotations]-hanteraren ](/help/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Anteckningsverktyget]

![Fönstret Anteckningsinformation med fält och alternativ som beskrivs i nästa avsnitt.](assets/annotation-builder.png)

>[!TAB Skapa/redigera anteckning]

![Fönstret Anteckningsinformation med fält och alternativ som beskrivs i nästa avsnitt.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Ange följande information (![Obligatorisk](/help/assets/icons/Required.svg) krävs):

   | Element | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Data view]** | Du kan välja datavyn för anteckningen. Anteckningen som du definierar är tillgänglig som en anteckning i Workspace-projekt baserat på den valda datavyn. Markeringen åsidosätts när du har aktiverat [!UICONTROL Apply to all data views]. |
   | **[!UICONTROL Project-only Annotation]** | En informationsruta som förklarar att den anteckning du skapar bara är synlig i det Workspace-projekt du arbetar med. Aktivera **[!UICONTROL Make this Annotation available to all your projects]** om du vill göra anteckningen synlig för alla dina projekt. Den här informationsrutan visas bara när du skapar en anteckning från ett Workspace-projekt. |
   | **[!UICONTROL Title]** ![Krävs](/help/assets/icons/Required.svg) | Namnge anteckningen, till exempel `Needs further investigation`. |
   | **[!UICONTROL Description]** | Ange en beskrivning för anteckningen, till exempel `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]** | Organisera anteckningen genom att skapa eller använda en eller flera taggar. Börja skriva för att hitta befintliga taggar som du kan markera. Eller tryck på **[!UICONTROL Enter]** för att lägga till en ny tagg. Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) om du vill ta bort en tagg. |
   | **[!UICONTROL Applied date]** ![Krävs](/help/assets/icons/Required.svg) | Välj det datum eller datumintervall som måste finnas för att anteckningen ska kunna visas. När du skapar en anteckning med kortkommandot blir anteckningen som standard ett datumintervall för endast dagen. När du skapar en anteckning med hjälp av en markering i en visualisering blir anteckningen som standard det datumintervall som baseras på datumintervallet från den panel som visualiseringen tillhör. |
   | **[!UICONTROL Color]** | Använd en färg på anteckningen. Anteckningen visas i projektet med den valda färgen. Färg kan användas för att kategorisera anteckningar, t.ex. allmänna helgdagar, externa händelser, spårningsproblem. |
   | **[!UICONTROL Scope]** | Dra och släpp mätvärden från komponentpanelen som utlöser anteckningen. Till exempel Personer, sessioner och händelser. Dra och släpp sedan de dimensioner eller segment på komponentpanelen som fungerar som segment för att bestämma om anteckningen ska visas eller inte. Om du inte anger ett omfång används anteckningen på alla dina data. <br/>Du har två alternativ:<ul><li>**[!UICONTROL Any of these metrics are present]**: Dra och släpp upp till 10 mätvärden som utlöser den anteckning som ska visas.<br/>Inkomstmåttet har till exempel slutat samla in data för ett visst datumintervall. Dra intäktsmåttet till den här rutan.</li><li>**[!UICONTROL With all of these segments]**: Dra och släpp upp till 10 dimensioner eller segment i segmentet oavsett om anteckningen visas.</li></ul><p><p>**Obs!** Alla anteckningar som används på en komponent som sedan används som en del av ett beräknat mått eller en segmentdefinition ärver INTE automatiskt anteckningen. Det önskade beräknade måttet måste också läggas till i omfångsavsnittet för att anteckningen ska kunna visas. En ny anteckning bör dock skapas för alla segment som du vill kommentera med samma information. Du kan till exempel använda en anteckning för [!UICONTROL Orders] på en viss dag. Du använder sedan [!UICONTROL Orders] i ett beräknat mått för samma datumintervall. Det nya beräknade måttet visar inte automatiskt anteckningen för order. Lägg även till det beräknade måttet i omfångsavsnittet för den anteckning som ska visas. |
   | **[!UICONTROL Apply to all data views]** | Anteckningen gäller som standard för den ursprungliga datavyn. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla datavyer i företaget. |

   {style="table-layout:auto"}

1. Välj
   * **[!UICONTROL Save]** om du vill spara anteckningen.
   * **[!UICONTROL Save As]** om du vill spara en kopia av anteckningen.
   * **[!UICONTROL Delete]** om du vill ta bort en anteckning.
   * **[!UICONTROL Cancel]** om du vill avbryta alla ändringar du har gjort i en anteckning eller avbryta skapandet av en ny anteckning.
