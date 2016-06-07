# Work with Azure Storage

Overview
========

Microsoft Azure SQL Database is a relational database service in the
cloud that is based on the Microsoft SQL Server engine. SQL Database
delivers predictable performance, scalability with no downtime, business
continuity, and data protection—all with nearly no administrative
overhead. You can focus on rapid app development and accelerating your
time to market, rather than managing virtual machines and
infrastructure. Because it’s based on the [SQL
Server](https://msdn.microsoft.com/library/bb545450.aspx) engine, SQL
Database supports existing SQL Server tools, libraries, and APIs, which
makes it easier for you to move to and extend to the cloud.

This tutorial shows you how to work with Azure Storage by using the
Azure Storage Explorer tool to analyze a project that is available in
Azure. It supports Azure Blob storage, Azure Queue storage, and Azure
Table storage, so you can analyze blobs, queues, and tables. When you’re
finished, you will know how to use the Azure Storage Explorer tool to
analyze your available blobs, tables, and queues in Azure Storage.

The following shows the Azure Storage Explorer UI:

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image1.png)

In this tutorial, you’ll learn these procedures:

-   How to prepare your machine for Azure development by installing the
    [Azure SDK for .NET](https://azure.com/tools).

-   How to configure Visual Studio for the use of Azure Storage, and how
    to install Azure Storage Explorer.

-   How to use Azure Storage Explorer to analyze Azure Storage in
    a project.

Requirements
============

This document assumes that the user has a subscription in Azure and
knowledge about [Azure
Storage](https://azure.microsoft.com/es-es/documentation/articles/storage-introduction),
as well as the different types of related Storage services—Blob storage,
Table storage, Queue storage, and File storage.

In addition, we recommend that you have Azure Storage Account and the
related Storage services running, and that you learn how to use [Azure
Storage Explorer](http://storageexplorer.com/).

Set up the development environment
==================================

To start, set up your development environment by installing the latest
version of the [Azure
SDK](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/VWDOrVs2015AzurePack.appids).

[Visual Studio
2015](https://go.microsoft.com/fwlink/?linkid=746481&clcid=0x409)▶

[Visual Studio
2013](https://go.microsoft.com/fwlink/?linkid=746482&clcid=0x409)▶

If you don't have Visual Studio installed, use the link for Visual
Studio 2015, and Visual Studio will be installed along with the SDK.

Also, you need to [install the Azure Storage Explorer
tool](http://storageexplorer.com/).

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image2.png)

Click the **Download** button and open the installation file. The basic
wizard guides you through the installation.

Work with Azure Storage Explorer
================================

By using Azure Storage Explorer, you can maintain and analyze the Azure
Storage services that you’ve deployed in Azure.

After you’ve opened Azure Storage Explorer, you’ll see an empty window,
which shows no information—you must first add an Azure account to the
subscription list that is available in the application. To do this,
select the **Settings** button, and add the accounts and subscriptions
that you want to have.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image3.png)

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image4.png)

After you’ve added the accounts, select the subscriptions that you want,
and click **Apply** to load the data that relates to this account (such
as services that are available).

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image5.png)

The services that are registered in the Azure account will be displayed.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image6.png)

The application also has a resource filter and a search engine. When you
select a resource, some actions and properties that are related to this
resource will show.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image7.png)

Work with blobs, queues, and tables in Azure Storage Explorer
=============================================================

In Azure Storage Explorer, you can also work with Azure Storage services
that are already created in an Azure subscription—Blob storage, Queue
storage, and Table storage.

By right-clicking on the different categories of available services
within the available account, you can perform actions such as pasting
and creating new services.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image8.png)

In addition, when you double-click a service that was already created,
you can see information about the service, as well as available actions.
While blob containers have their own actions, currently this option
isn’t available for tables and queues.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image9.png)

Existing functions are like those in a similar file browser. You can
search and browse through existing directories in each of the services.
You can upload files and folders, download, open, copy and paste, and
delete.

![](https://whitepapershealth.blob.core.windows.net/azurestorage/image10.png)

Other suggested topics to explore
=================================

-   An [introduction to SQL
    Database](https://azure.microsoft.com/en-us/documentation/articles/sql-database-technical-overview/)

-   An [open-source version of Azure Storage Explorer on
    GitHub](https://github.com/Azure/deco/releases)

-   [Azure Storage Explorer main page](http://storageexplorer.com/) for
    downloads for different platforms, as well as the change log of
    previous versions

-   [Documentation about Azure Storage and
    services](https://azure.microsoft.com/en-us/documentation/services/storage/)

-   [Azure Developer Tools](http://azure.com/tools) for more information
    about the tools and for the recently released installers

