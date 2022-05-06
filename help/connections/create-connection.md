---
title: Create a connection
description: Describes how to create a connection to a Platform dataset in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: b17bdb20b120ec37a9f11425062bc7f8bcebd7e7
workflow-type: tm+mt
source-wordcount: '1896'
ht-degree: 2%

---

# Create a connection

[!DNL Adobe Experience Platform][!UICONTROL Workspace] [!DNL Experience Platform][!DNL Experience Platform][!UICONTROL Workspace]

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Required permissions

[](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html)

Adobe Experience Platform:
* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources

Customer Journey Analytics
* Product Admin Access

>[!IMPORTANT]
>
>[!DNL Experience Platform]

## Select sandbox and datasets

1. [](https://analytics.adobe.com)

1. [!DNL Customer Journey Analytics]

1. **[!UICONTROL Connections]**

1. **[!UICONTROL Create new connection]**

   ![](assets/create-connection0.png)

1. Choose a sandbox in Experience Platform that contains the dataset/s to which you want to create a connection.

   [](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) You can think of sandboxes as &quot;data silos&quot; that contain data sets. Sandboxes are used to control access to data sets.  Once you have selected the sandbox, the left rail shows all the datasets in that sandbox that you can pull from.

   >[!IMPORTANT]
   >
   >You cannot access data across sandboxes, i.e., you can only combine datasets that are located within the same sandbox.

1. [!UICONTROL Customer Journey Analytics]**[!UICONTROL Add]**

   **[!UICONTROL Search datasets]**

## Configure dataset

On the right-hand side, you can now configure the dataset/s you have added.

![](assets/create-connection.png)

1. **[!UICONTROL Dataset type]**[!UICONTROL Customer Journey Analytics]

   >[!IMPORTANT]
   >
   >You need to add at least one event dataset as part of a connection.


   [!UICONTROL Event][!UICONTROL Profile][!UICONTROL Lookup]

   | Dataset Type | Beskrivning | Timestamp | Schema | Person ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). For example, this could be typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, you have flexibility as to which ID is used as the Person ID. | [!UICONTROL Experience Platform] | Any built-in or custom schema that is based on an XDM class with the &quot;Time Series&quot; behavior. Examples include &quot;XDM Experience Event&quot; or &quot;XDM Decision Event.&quot; | You can pick which Person ID you want to include. Each dataset schema defined in the Experience Platform can have its own set of one or more identities defined and associated with an Identity Namespace. Any of these can be used as the Person ID. Examples include Cookie ID, Stitched ID, User ID, Tracking Code, etc. |
   | [!UICONTROL Lookup] | This data is used to look up values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names. [](/help/use-cases/b2b.md) | Ej tillämpligt | Any built-in or custom schema that is based on an XDM class with the &quot;Record&quot; behavior, except for the &quot;XDM Individual Profile&quot; class. | Ej tillämpligt |
   | [!UICONTROL Profile] | [!UICONTROL Event] For example, allows you to upload CRM data about your customers. | Ej tillämpligt | Any built-in or custom schema that is based on the &quot;XDM Individual Profile&quot; class. | You can pick which Person ID you want to include. [!DNL Experience Platform]<br>![](assets/person-id.png)**** To really merge datasets, you need use the same Person ID. |

1. **[!UICONTROL Dataset ID]**

1. **[!UICONTROL Time stamp]**[!UICONTROL Experience Platform]

1. **[!UICONTROL Schema]**[](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html)

1. **[!UICONTROL Person ID]** These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.

   >[!IMPORTANT]
   >
   >If there are no person IDs to choose from, that means one or more person IDs have not been defined in the schema. [](https://youtu.be/G_ttmGl_LRU)

1. **[!UICONTROL Next]**[!UICONTROL Enable Connection]

### Use Identity Map as a Person ID

Customer Journey Analytics now supports the ability to use the Identity Map for its Person ID. Identity Map is a map data structure that allows someone to upload key -> value pairs. Nycklarna är ID-namnutrymmen och värdet är den struktur som innehåller identitetsvärdet. The Identity Map exists on each row/event uploaded and is populated for each row accordingly.

[](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) When you select such a dataset to be included in a CJA Connection, you have the option of selecting either a field as the primary ID or the Identity Map:

![](assets/idmap1.png)

If you select Identity Map, you get two additional configuration options:

| Alternativ | Beskrivning |
|---|---|
| [!UICONTROL Use Primary ID Namespace] | This instructs CJA, per row, to find the identity in the Identity Map that is marked with a primary=true attribute and use that as the Person ID for that row. This means that this is the primary key that will be used in Experience Platform for partitioning. It is also the prime candidate for usage as CJA&#39;s visitor ID (depending on how the dataset is configured in a CJA Connection). |
| [!UICONTROL Namespace] | (This option is only available if you do not use the Primary ID Namespace.) [](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) If you specify a namespace, CJA will search each row&#39;s Identity Map for this namespace key and use the identity under that namespace as the person ID for that row. Note that since CJA cannot do a full dataset scan of all rows to determine which namespaces are actually present, all possible namespaces are listed in the dropdown. You need to know which namespaces are specified in the data; this cannot be auto-detected. |

### Identity Map edge cases

This table shows the two configuration options when edge cases are present and how they are handled:

| Alternativ | No IDs are present in Identity Map | No IDs are marked as primary | Multiple IDs are marked as primary | Single ID is marked as primary | Invalid namespace with an ID marked as primary |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | The row is dropped by CJA. | The row is dropped by CJA, as no primary ID is specified. | All IDs marked as primary, under all namespaces, are extracted into a list. They are then alphabetically sorted; with this new sorting, the first namespace with its first ID is used as the Person ID. | The single ID marked as primary is used as the Person ID. | Even though the namespace may be invalid (not present in AEP), CJA will use the primary ID under that namespace as the Person ID. |
| **[!UICONTROL Specific Identity Map namespace]** | The row is dropped by CJA. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. (Only a valid namespace can be selected at Connection creation time, so it is not possible for an invalid namespace/ID to be used as Person ID) |

## Enable connection

![](assets/create-connection2.png)

1. To enable a connection, define these settings for the entire connection, i.e. all the datasets in the connection:

   | Alternativ | Beskrivning |
   | --- | --- |
   | [!UICONTROL Name Connection] | Give the connection a descriptive name. The connection cannot be saved without a name. |
   | [!UICONTROL Description] | Add more detail to distinguish this connection from others. |
   | [!UICONTROL Datasets] | The datasets that are included in this connection. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | [!UICONTROL Workspace] |
   | [!UICONTROL Import all existing data] | [!DNL Experience Platform] In the future, all existing historical data for any new dataset(s) added to this saved connection will also be automatically imported. [](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#backfill-historical-data)<br>**** |
   | [!UICONTROL Average number of daily events] | **** Select one option from the drop-down menu. This is so that Adobe can allocate sufficient space for this data.<br>[](https://experienceleague.adobe.com/docs/experience-platform/query/home.html)<br> |

1. Klicka på **[!UICONTROL Save and create data view]**. [](/help/data-views/create-dataview.md)

### Backfill historical data

**[!UICONTROL Import all existing data]** Keep this in mind:

* We have removed the backfill (historical data import) limitation. Previously, you could backfill a maximum of 2.5 billion rows on your own and otherwise required engineering involvement. Now, you can backfill data on your own, without any limitations.
* We prioritize new data added to a dataset in the connection, so this new data has the lowest latency.
* Any backfill (historical) data is imported at a slower rate. **[!UICONTROL Average number of daily events]** For example, if you have more than one billion rows of data per day, plus 3 years of historical data, that could take multiple weeks to import. On the other hand, if you have less than a million rows per day and one week of historical data, that would take less than an hour.
* Backfilling applies to the whole connection, not to each dataset individually.
* [](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/ingest-data-from-adobe-analytics.html)

### Calculate the average number of daily events

This calculation has to be done for every dataset in the connection.

1. [](https://experienceleague.adobe.com/docs/experience-platform/query/home.html)

   The query would look like this:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In this example, &quot;analytics_demo_data&quot; is the name of the dataset.

1. `Show Tables`
