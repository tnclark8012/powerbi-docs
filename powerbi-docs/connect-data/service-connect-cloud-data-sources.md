---
title: Connect to cloud data sources in the Power BI service (Preview)
description: Learn how to connect to cloud data sources and share connections in the Power BI service.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 08/31/2023
LocalizationGroup: Connect to data
---
# Connect to cloud data sources in the Power BI service (Preview)

With Power BI, you can share cloud connections for datasets and paginated reports, datamarts and dataflows, as well as Power Query Online experiences in *Get data*, enabling you to create multiple connection objects to the same cloud data source. For example, you can create separate connections to the same data source, with different credentials or privacy settings, and share the connections with others, alleviating the need for those users to manage their own separate cloud connections. 


## Types of data connections

The following table shows how various types of connections map to the two primary connection types: data gateway connections, and direct cloud connections. The new capability described in this article is **Shareable cloud connections**.

|Data gateway connections  |Direct cloud connections  |
|---------|---------|
|Connections using a personal data gateway     |Personal cloud connections |
|Connections using an enterprise or VNET data gateway     |Shareable cloud connections (new) |


## Advantages of shareable cloud connections

Connections using a personal cloud connection come with several limitations. For example, with a personal cloud connection you can only create a single personal cloud connection object to a given data source. All datasets that connect to the data source use the same personal cloud connection object, so if you change the credentials of the personal cloud connection, all datasets using that personal cloud connection are affected. Often that's not a desired outcome.

Another limitation of personal cloud connection is that they can't be shared with others, so other users can't bind their datasets and paginated reports to the personal cloud connection you own; users must maintain their own personal cloud connections. 

Shareable connections have no such limitations, and provide for more streamlined, more flexible connection management, including the following:

* **Support multiple connections to the same data source** - support for multiple connections on the same data source is particularly useful when you want to use different connection settings for different datasets, and other artifacts. It's also useful when you want to assign individual artifacts their own separate connections, to ensure their connection settings are isolated from each other.

* **You can share these connections with other users** - with shareable connections you can assign other users *Owner* permissions, enabling them to manage all aspects of the connection configuration, including credentials. You can provide other users with *Resharing* permissions so they can use and reshare the connection with others. You can also provide *User* permissions, enabling them to use the connection to bind their artifacts to the data source. 

* **Lower the overhead of maintaining data connections and credentials** - when combined with the data source and gateway management experience, you can centralize data source connection management for gateway and cloud connections. Such centralization and management is already common for enterprise and VNET data gateways, for which a gateway administrator creates, shares, and maintains the connections. With shareable connections, you can now extend such centralized connection management to cloud data sources as well.

## Compare shareable cloud connection to other connections

By default, when you create a Power BI Desktop report that connects to a cloud data source, then upload it into a workspace in the Power BI service, Power BI creates a personal cloud connection and binds it to your dataset, for which you must provide credentials. If an existing personal cloud connection is available, you likely provided the credentials previously. 

In contrast, if you have access to at least one shareable cloud connection to the same data source, you can use the shareable cloud connection, which has already been configured for you by its owner, instead of having to use your only available personal cloud connection for the data source. 

To use the shareable cloud connection, on the **Datasets** settings page, under **Gateway and cloud connections**, find **Cloud connections** and can select the shareable cloud connection you want to use for the connection, then select **Apply**. The following screenshot shows the settings.

:::image type="content" source="media/service-connect-cloud-data-sources/service-connect-cloud-data-sources-01.png" alt-text="Screenshot of connecting to a shareable cloud connection.":::


## Create a new shareable cloud connection

You can create a new shareable cloud connection directly from the **Dataset** settings page. Under **Gateway connections** > **Cloud connections**, select the **Maps to** dropdown and then select **Create a connection**.

:::image type="content" source="media/service-connect-cloud-data-sources/service-connect-cloud-data-sources-02.png" alt-text="Screenshot of selecting to create a new connection.":::

A pane appears called **New connection** and automatically populates the configuration parameters.

:::image type="content" source="media/service-connect-cloud-data-sources/service-connect-cloud-data-sources-03.png" alt-text="Screenshot of new connection settings.":::

Enabling the creation of new connections makes it easy to create separate shareable cloud connections for individual datasets, if needed. You can also display the connection management page from anywhere in the Power BI service by selecting the **Settings** gear in the upper right corner of the Power BI service, then select **Manage connections and gateways**. 


## Using shareable cloud connections with paginated reports

When you share your paginated report in the Power BI service, you can update the cloud connections from within the report itself. To modify the cloud connections for your paginated report, navigate to your workspace in the Power BI service, select the **More** button (ellipses) and then select **Manage**.

:::image type="content" source="media/service-connect-cloud-data-sources/service-connect-cloud-data-sources-04.png" alt-text="Screenshot of manage connections for paginated reports.":::

Selecting **Manage** presents a page with several tabs. Select the **Reports** tab from the top row, then you can update the connection from within the **Cloud connections** area, as shown in the following screenshot.

:::image type="content" source="media/service-connect-cloud-data-sources/service-connect-cloud-data-sources-05.png" alt-text="Screenshot of mapping a data connection for paginated reports.":::


## Limitations and considerations

* **Shareable cloud connections also share your credentials** - when you allow others to user your shareable cloud connections, it's important to understand that you're letting others connect their own datasets, paginated reports, and other artifacts to the corresponding data sources by using the connection details and credentials you provided. Make sure you only share connections (and their credentials) that you're authorized to share.


## Next steps

For more information about creating shareable cloud connections:

[Create and share cloud data sources in the Power BI service (Preview)](service-create-share-cloud-data-sources.md)


You can do all sorts of things with the Power BI service and Power BI Desktop. For more information on its capabilities, check out the following resources:

* [What is Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Query overview with Power BI Desktop](../transform-model/desktop-query-overview.md)
* [Data types in Power BI Desktop](desktop-data-types.md)
* [Shape and combine data with Power BI Desktop](desktop-shape-and-combine-data.md)
* [Common query tasks in Power BI Desktop](../transform-model/desktop-common-query-tasks.md)
