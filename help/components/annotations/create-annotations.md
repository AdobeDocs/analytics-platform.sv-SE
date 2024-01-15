---
title: Skapa anteckningar
description: Så här skapar du anteckningar i Workspace.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: e1815cad331b47b281f61d427ef342ea3b5b5d87
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Skapa anteckningar

Som standard kan bara administratörer skapa anteckningar. Användare har rätt att visa anteckningar på samma sätt som andra Analytics-komponenter (t.ex. filter, beräknade värden).

Administratörer kan dock ge [!UICONTROL Annotation Creation] behörighet (analysverktyg) till användare via [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html).

1. Du kan komma igång på flera olika sätt om du vill skapa anteckningar:

| Skapandemetod | Information |
| --- | --- |
| **Gå till [!UICONTROL Components] > [!UICONTROL Annotation].** | Sidan Annotations Manager öppnas. Klicka [!UICONTROL Create New Annotation] och [!UICONTROL Annotation builder] öppnas. |
| **Högerklicka på en punkt i en tabell.** | [!UICONTROL The Annotation builder] öppnas. Observera att som standard visas anteckningar som skapats på det här sättet bara i det projekt där de skapades. Men du kan göra dem tillgängliga för alla projekt. Lägg även märke till att datum och mätvärden redan har fyllts i.<p>![](assets/annotate-table.png) |
| **Högerklicka på en punkt i en [!UICONTROL Line] diagram.** | The [!UICONTROL Annotation builder] öppnas. Observera att som standard visas anteckningar som skapats på det här sättet bara i det projekt där de skapades. Men du kan göra dem tillgängliga för alla projekt. Lägg även märke till att datum och mätvärden redan har fyllts i.<p>![](assets/annotate-line.png) |
| **Gå till [!UICONTROL Components] > [!UICONTROL Create annotation].** | The [!UICONTROL Annotation builder] öppnas. |
| **Använd den här snabbtangenten** för att öppna Annotation Builder: (PC) `ctrl` `shift` + o, (Mac) `shift` + `command` + o | Observera, att när du använder snabbtangenten för att skapa en anteckning, skapar du en endagarsanteckning för det aktuella datumet, utan något förvalt omfång (mått eller mått). |
| **Använd [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | Med API:erna för Customer Journey Analytics-anteckningar kan du skapa, uppdatera eller hämta anteckningar via Adobe Developer. Dessa API:er använder samma data och metoder som Adobe använder i produktgränssnittet. |

{style="table-layout:auto"}

1. Fyll i [!UICONTROL Annotation builder] -element.

   ![Fönstret Anteckningsinformation med fält och alternativ som beskrivs i nästa avsnitt.](assets/ann-builder.png)

   | Element | Beskrivning |
   | --- | --- |
   | [!UICONTROL Title] | Namnge anteckningen, t.ex.&quot;Memorial Day&quot; |
   | [!UICONTROL Description] | (Valfritt) Ange en beskrivning av anteckningen, t.ex.&quot;Offentlig semester observerad i USA&quot;. |
   | [!UICONTROL Tags] | (Valfritt) Ordna anteckningar genom att skapa eller använda en tagg. |
   | [!UICONTROL Applied date] | Välj det datum eller datumintervall som måste finnas för att anteckningen ska kunna visas. |
   | [!UICONTROL Color] | Använd en färg på anteckningen. Anteckningen visas i projektet med den valda färgen. Färg kan användas för att kategorisera anteckningar, t.ex. allmänna helgdagar, externa händelser, spårningsproblem. |
   | [!UICONTROL Scope] | (Valfritt) Dra och släpp mätvärdena som utlöser anteckningen. Dra och släpp sedan de dimensioner eller filter som fungerar som filter (d.v.s. som anteckningen ska vara synlig med). Om du inte anger ett omfång kommer anteckningen att gälla för alla dina data.<ul><li>**[!UICONTROL Any of these metrics are present]**: Dra och släpp upp till 10 mätvärden som utlöser den anteckning som ska visas.</li><li>**[!UICONTROL With all of these filters]**: Dra och släpp upp till 10 dimensioner eller filter som ska filtreras när anteckningen visas.</li></ul><p>Användningsexempel: En eVar har slutat samla in data för ett visst datumintervall. Dra eVarna till **[!UICONTROL Any of these metrics are present]** -dialogrutan. Eller [!UICONTROL Visits] inga data rapporteras. Följ samma process.<p>**Obs!** Alla anteckningar som tillämpas på en komponent som sedan används som en del av ett beräknat mått eller en filterdefinition ärver INTE automatiskt anteckningen. Det önskade beräknade måttet måste också läggas till i omfångsavsnittet för att anteckningen ska kunna visas. En ny anteckning bör dock skapas för alla filter som du vill kommentera med samma information.<p>Exempel: Du använder en anteckning på [!UICONTROL Orders] på en viss dag. Sedan använder du [!UICONTROL Orders] i ett beräknat mått för samma datumintervall. Det nya beräknade måttet visar inte automatiskt anteckningen för order. Det beräknade måttet måste också läggas till i omfångsavsnittet för att anteckningen ska visas. |
   | [!UICONTROL Apply to all data views] | Anteckningen gäller som standard för den ursprungliga datavyn. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla datavyer i företaget. |
   | [!UICONTROL Apply to all projects] | Som standard gäller anteckningen det aktuella projektet. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla projekt som du äger. Observera att den här kryssrutan bara visas när du startar Anteckningsverktyget från Anteckningsverktyget? |

   {style="table-layout:auto"}

1. Klicka på **[!UICONTROL Save]**.
