# Create and deploy a mobile app in Azure App Service

Azure App Service is the only cloud service that integrates everything
you need to quickly and easily build web and mobile apps for any
platform and any device. Built for developers, App Service is a fully
managed platform that has powerful capabilities such as built-in DevOps,
continuous integration with Visual Studio Team Services and GitHub,
staging and production support, and automatic patching.

This tutorial shows how to deploy an ASP.NET mobile app to a [mobile app
in *Azure App
Service*](https://azure.microsoft.com/en-us/documentation/articles/app-service-web-overview/)
as a notification service by using Visual Studio 2015 or *V*isual Studio
2013. After you complete the tutorial, you’ll have a notification
service that’s identical to the one that’s used in [Microsoft Connect();
//2015](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/)*,*
which will be executed in the cloud.

The following illustration shows the completed application:

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image1.png)

You’ll learn these procedures:

-   How to prepare your computer for Azure development by installing the
    [Azure SDK for .NET](https://azure.com/tools).

-   How to set up Visual Studio to create a new mobile app in Azure App
    Service while it creates an ASP.NET 5 mobile project.

-   How to compose the Demo project that is presented in Microsoft
    Connect(); //2015.

-   How to deploy a mobile project to a mobile app in App Service by
    using Visual Studio, and how to create a notification service.

<!-- -->

-   How to use the [Azure
    portal](https://azure.microsoft.com/overview/preview-portal/) to
    monitor and manage your mobile app.

Sign up for Microsoft Azure
===========================

You need an Azure account to complete this tutorial. You can:

-   [Open an Azure account for
    free](https://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A261C142F).
    You get credits that you can use to try paid Azure services. Even
    after the credits are used up, you can keep the account and use free
    Azure services and features, such as the Web Apps feature of Azure
    App Service.

-   [Activate Visual Studio subscriber
    benefits](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F).
    Your Visual Studio subscription gives you credits every month that
    you can use for paid Azure services.

-   Get credits every month by joining to [Visual Studio Dev
    Essentials](https://www.visualstudio.com/products/visual-studio-dev-essentials-vs).

If you want to get started with Azure App Service before you sign up for
an Azure account, go to [Try App
Service](http://go.microsoft.com/fwlink/?linkid=523751&clcid=0x409).
There, you can immediately create a short-lived starter web app in App
Service without a credit card or commitments.

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

Create a new project and an instance of App Service
===================================================

The first step is to create a mobile project in Visual Studio and a
mobile application in an instance of App Service. When it’s ready, you
must implement the project in the mobile app to make it available on the
Internet.

The following diagram shows what you need to do to follow the creation
and implementation steps.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image2.png)

Create a mobile app in Visual Studio
------------------------------------

1.  Open Visual Studio 2015 or Visual Studio 2013.

2.  On the File menu, click **New** &gt; **Project**.

3.  In the **New Project** dialog box, click **C\#** &gt; **Cloud** &gt;
    **Azure Mobile App**.

4.  Choose a good name for the project, for
    example, HealthDemo.MobileApp.

5.  You can deactivate or activate **Application Insights** if you want
    your application to be monitored in terms of availability and
    performance using [Azure Application
    Insights](https://azure.microsoft.com/es-es/documentation/articles/app-insights-overview/).

6.  Click **OK**.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image3.png){width="6.5in" height="4.510416666666667in"}

1.  In the **Select a template** window, select **Azure Mobile App**.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image4.png){width="6.489583333333333in"
height="5.0625in"}

1.  Click **OK**. The project will begin to be created.

Create a mobile app in Azure App Service
----------------------------------------

From Server Explorer in Visual Studio, you can create a mobile app in an
instance of Azure App Service. In case you have not signed in to Azure
yet, you can also sign in to an existing subscription in Server
Explorer.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image5.png){width="3.3541666666666665in"
height="3.46875in"}

1.  You can create a mobile application on in an instance of Azure App
    Service from Server Explorer.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image6.png){width="4.270833333333333in"
height="3.625in"}

1.  You need to fill in the required information. Select the type of App
    Service as **Mobile App**.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image7.png){width="6.489583333333333in"
height="4.875in"}

1.  Because your mobile application will have a SQL database, you can
    add one as a service in the configuration window.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image8.png){width="6.489583333333333in"
height="4.885416666666667in"}

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image9.png){width="6.489583333333333in"
height="4.875in"}

1.  When you click the **OK** button, Azure will begin to create the
    mobile app in Azure. After it is deployed, you can see all the
    information in the Azure portal and in Server Explorer in
    Visual Studio.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image10.png){width="5.59375in"
height="2.0208333333333335in"}

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image11.png){width="6.5in"
height="3.3958333333333335in"}

1.  From Azure portal, open the mobile application. From the
    **Settings** pane, click the **Push** button to create an instance
    of Azure Notification Hubs for the App Service that you
    are creating. This process makes the service send notifications to
    the different target applications.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image12.png){width="6.5in"
height="3.5520833333333335in"}

1.  Fill in the required information, and click **Create**. You now have
    the resource group created and prepared for the future deployment.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image13.png){width="6.5in"
height="3.5520833333333335in"}

> ![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image14.png){width="6.5in"
> height="3.5520833333333335in"}

Compose the Connect(); //2015 Demo mobile app
=============================================

After you have a basic mobile application, you can develop the mobile
application of the Demo presented at Microsoft Connect(); //2015. This
Demo creates a push notification service through an instance of
Notification Hubs. This can be created by following a few simple steps:

The base project start point is included in the following link. Start
with this project, which includes files and settings that are of no
interest to you but are important in the application: [Demo
solution](https://github.com/Microsoft/HealthClinic.biz)

Application start process
-------------------------

1.  Remove the App\_Start folder.

2.  In the Startup.cs file, replace the content in the namespace region
    with the following content:

This change produces quick application initialization. Remove the
initialized database in the absence of information because you do not
want the database to contain information from the beginning, and clear
the debug information that adds nothing to the application development.

Data model
----------

The data model, because of its simplicity and use of redundant elements
to the subject, is included in the base project. The files are in the
DataObjects folder.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image15.png){width="2.2083333333333335in"
height="1.5104166666666667in"}

Database context
----------------

Replace the code in the MobileServiceContext.cs class with the following
code:

The default constructor can be preserved and acts in a similar way to
get the string connection with the database.

Furthermore, the collection of entities that it will use from the
database for use in controllers is created.

Finally, shown in model creation, the default schema is dbo. We removed
the convention that sets the table name so that it is a pluralized
version of the entity type name. We added the convention to create
columns from the data model attributes that were previously created.

Controllers
-----------

### DoctorContoller

Add the DoctorController.cs controller to the Controllers folder. You
can perform operations with the Doctor entity and with its related
notifications. Add the following code to the controller:

### HomeAppointmentController

Add the HomeAppoinmentController.cs controller to the Controllers folder
with the following code to work with the HomeAppointment entity and its
related notifications.

### PatientController

Likewise, add the PatientController.cs controller to work with the
Patient entity and its related notifications.

### UpdateTagsController

With this controller, you can update available tags to send
notifications and connect to Notification Hubs. Because Notification Hub
is already configured for the Azure environment, you don’t need any more
information. Create the UpdateTagsController.cs controller in the
Controllers folder:

### NotifyDelayController

This controller will send notifications to customers. It obtains the
configured notification hubs and creates the push notification that will
be sent. To do this, simply create the NotifyDelayController.cs
controller, and add the following code:

You will have the completed Demo shown in Microsoft Connect(); //2015
regarding Mobile Applications in Azure, and thus a mobile application
that can send push notifications to different customers. The code is
available at the following link:
[HealthDemo.MobileApp](https://github.com/Microsoft/HealthClinic.biz/blob/master/06_Demos_MobileApp.sln)

Deploy the project to Azure App Service
=======================================

To have the mobile application available in Azure App Service, just
follow these steps.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image2.png)

You have already generated the necessary Azure resources to expedite
future deployments. You don’t have to create those resources again to
run the mobile application .

1.  In **Solution Explorer**, right-click on the HealthDemo.MobileApp
    project, and select **Publish**.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image16.png){width="5.40625in"
height="3.8645833333333335in"}

1.  The **Publish Web** page opens. The wizard shows you a list of
    available Publish Profiles. If you select **Microsoft Azure App
    Service**, you can see a list of available Azure subscriptions and
    the resource groups that were previously created. Among them is the
    resource group that you used to deploy the mobile application that
    you configured in previous steps.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image17.png){width="6.489583333333333in"
height="4.875in"}

1.  After you select the resource group, a page will show the
    connection information. The parameters will automatically fill with
    information, but you can modify the fields if necessary. To check
    that the connection works correctly, click **Validate Connection**.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image18.png){width="6.5in"
height="5.135416666666667in"}

1.  On the **Settings** page, you can choose whether to deploy in a
    production environment or a debug environment, and you can see the
    connection with the database.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image19.png){width="6.5in"
height="5.145833333333333in"}

1.  On the last page, **Preview**, you can determine the changes that
    affect the Azure environment.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image20.png){width="6.5in"
height="5.145833333333333in"}

1.  Finally, click **Publish**.

The **Output** window displays information about the deployment. When
the deployment is finished, a message that everything has been completed
successfully is displayed.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image21.png){width="6.5in"
height="2.0833333333333335in"}

You will see the final result in the browser that will open.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image22.png){width="6.5in"
height="3.9270833333333335in"}

Open remote files in Server Explorer
====================================

After the mobile application is deployed in Azure, you can make
temporary changes to the remote site. To test and debug in a quick way;
you only need to open and modify files in Server Explorer.

1.  You need to be signed in to Azure by using Server Explorer.

2.  In Server Explorer, expand the node at **Azure** &gt; **App
    Services** &gt; **HealthDemo.MobileApp.ResourceGroup**.

3.  Expand the node **Log Files** &gt; **kudu** &gt; **trace**, and open
    one of the files.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image23.png){width="6.4in" height="5.5in"}

1.  These files, for example, are log files to make debugging easy in
    the mobile application.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image24.png){width="6.5in" height="1.9in"}

It is also possible to access the configuration of the mobile
application from Visual Studio so that you can start a remote debugging
session and view logs on the application in real time. To do this, from
**Server Explorer**, right-click the **Application Service** node.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image25.png){width="5.1in" height="3.8in"}

Monitor and manage the App Service in the Azure portal
======================================================

You can manage and monitor the services covered by Azure from the [Azure
portal](https://portal.azure.com/). This includes the mobile application
that you just developed.

1.  In a web browser of your choice, go to the [Azure
    portal](https://portal.azure.com/), and sign in with your
    Azure credentials.

2.  Click **Resource Groups**. Here you can see resource groups for each
    of the parts that make up the Demo of Microsoft Connect(); //2015
    that you have created throughout this article. For this tutorial,
    it’s HealthDemo.MobileApp.ResourceGroup.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image26.png)

1.  When you click the resource group, you will see a summary of the
    resources that are part of the group, as well as the information
    about the group and its configuration.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image27.png)

1.  You can click the mobile application that is contained in the
    group*,* HealthDemoMobileApp, to view general resource information,
    statistics, and content about the configuration.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image28.png)

It is possible that statistics are not real or that no statistics are
displayed. Explore the application to start to show statistics on the
portal.

1.  In the list of configuration types, you can explore different
    configurations that are available in your application. One is
    **Application settings**. From here, you can modify some important
    aspects of the application.

![](https://whitepapershealth.blob.core.windows.net/mobilityservice/image29.png)

From the portal, you can perform many actions that are related to
applications and other Azure services, such as databases and virtual
machines.

Other suggested topics to explore
=================================

-   What are the Azure App Services, why to use them, their concepts,
    and a basic introduction to them.

-   Other ways to deploy a mobile project

For information about other ways to deploy mobile application projects
to mobile apps by using Visual Studio or by [automating
deployment](http://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/continuous-integration-and-continuous-delivery)
from a [source control
system](http://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/source-control),
see [How to deploy an Azure mobile
app](https://azure.microsoft.com/en-us/documentation/articles/web-sites-deploy/).

Visual Studio can also generate Windows PowerShell scripts that you can
use to automate deployment. For more information, see [Automate
everything (Building real-world cloud apps with
Azure)](http://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/automate-everything).

-   How to add a custom domain name and SSL

For information about how to use SSL and your own domain (for example,
www.healthdemo-mobileapp.com instead of
healthdemo-mobileapp.azurewebsites.net), see the following resources:

-   [Configure a custom domain name in Azure App
    Service](https://azure.microsoft.com/en-us/documentation/articles/web-sites-custom-domain-name/)

-   [Enable HTTPS for an Azure mobile
    app](https://azure.microsoft.com/en-us/documentation/articles/web-sites-configure-ssl-certificate/)

<!-- -->

-   How to add real-time features such as chat

If your mobile app will include real-time features (such as a chat
service, a game, or a stock ticker), you can get the best performance by
using [ASP.NET SignalR](http://www.asp.net/signalr) with the
[WebSockets](https://azure.microsoft.com/blog/2013/11/14/introduction-to-websockets-on-windows-azure-web-sites/)
transport method. For more information, see [Using SignalR with Azure
mobile
apps](http://www.asp.net/signalr/overview/signalr-20/getting-started-with-signalr-20/using-signalr-with-windows-azure-web-sites).

-   How to choose between App Service, Azure Cloud Services, and Azure
    virtual machines for mobile applications

In Azure, you can run mobile applications in App Service as shown in
this tutorial, or in cloud services or in virtual machines. For more
information, see [Azure mobile apps, cloud services, and VM*s*: When to
use
which?](https://azure.microsoft.com/manage/services/web-sites/choose-web-app-service/)

-   [How to choose or create an App Service
    plan](https://azure.microsoft.com/en-us/documentation/articles/azure-web-sites-web-hosting-plans-in-depth-overview/)

-   [How to choose or create a resource
    group](https://azure.microsoft.com/en-us/documentation/articles/resource-group-portal/)

-   [Azure Developer Tools](http://azure.com/tools) – Learn more about
    the tools and find the recently released installers.

