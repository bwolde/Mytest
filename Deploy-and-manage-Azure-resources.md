# Deploy and manage Azure resources

Overview
========

This tutorial shows how Azure manages resources*.* You will create your
own My Azure Resources, which provides an environment for easy
deployments by using PowerShell. When you’re finished, Azure Resource
Manager will be able to deploy all the resources by using PowerShell.

The following illustration shows the current existing project resources
in Azure:

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image1.png)

You’ll learn these procedures:

-   How to prepare your computer for Azure development by installing the
    [Azure SDK for .NET](https://azure.com/tools).

-   How to set up Visual Studio to help you manage Azure resources.

-   How to create My Azure Resources for the creation of a simple
    deployment environment.

-   How to publish applications in a simple way after resources are
    deployed in Azure.

-   How to deploy My Azure Resources by using PowerShell.

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
Studio 2015, and Visual Studio will be installed along with the SDK for
Windows Universal Applications.

Alternatively, depending of the type of target project that will use
deployed resources, you might need to install [Xamarin
Platform](https://xamarin.com/download), including those platforms that
are part of the project, or [Visual Studio Tools for Apache
Cordova](https://www.visualstudio.com/en-us/features/cordova-vs.aspx).

For the correct operation of scripts that are created with PowerShell
and in case you want to deploy My Azure Resources by using PowerShell,
you need to install the extensions, [PowerShell Tools for Visual Studio
2015](https://visualstudiogallery.msdn.microsoft.com/c9eb3ba8-0c59-4944-9a62-6eee37294597)
or [PowerShell Tools for Visual Studio
2013](https://visualstudiogallery.msdn.microsoft.com/f65f845b-9430-4f72-a182-ae2a7b8999d7).

Azure Resource Manager Tools in Visual Studio Code
==================================================

The following tutorial shows how to manage Azure resources by using
Visual Studio 2015. You can also use Visual Studio Code to manually
create resources by using [an
extension](https://code.visualstudio.com/docs/editor/extension-gallery?pub=msazurermtools&ext=azurerm-vscode-tools)
that will integrate into IntelliSense and everything that’s related to
Azure resources. As a result, you can easily design the desired template
in Visual Studio Code. For more information, see [Azure Resource Manager
tools](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools).

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image2.png)

Create My Azure Resources
=========================

The first point to consider before you start to manage Azure resources
is the needs of the project. This tutorial will cover the creation of
resources that Azure Resource Manager manages for Demos presented in
[Microsoft Connect();
//2015](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/),
specifically ASPNET5 and MobileApp demos. When you finish this tutorial,
10\_Demos\_Deployment solution will be completed and you’ll have a
simple and effective way to deploy the necessary resources to publish
services on Azure later.

Create an Azure Resource project
--------------------------------

1.  In Visual Studio, go to **File** &gt; **New Project** &gt; **C\#**
    or **Visual Studio** &gt; **Cloud**, and choose an **Azure Resource
    Group** project.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image3.png){width="6.5in" height="4.510416666666667in"}

1.  Because you want to create a custom resource group, you should start
    with an empty template. Select **Blank Template** in the list
    of templates.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image4.png){width="6.489583333333333in"
height="4.895833333333333in"}

1.  You can see the files that were created in Solution Explorer.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image5.png){width="3.40625in"
height="3.2708333333333335in"}

-   ***Deploy-AzureResourceGroup.ps1***: A PowerShell script that
    invokes PowerShell commands to deploy to Azure Resource Manager.

-   **Azuredeploy.json**: The resource manager template that defines the
    infrastructure that you want to deploy to Azure and the parameters
    that you can provide during deployment. It also defines the
    dependencies between the resources so they are deployed in the
    correct order.

-   **Azuredeploy.parameters.json**: A parameters file that contains
    values that the template needs. These are the values that you pass
    on to customize each deployment.

-   **AzCopy.exe**: A tool that’s used by the PowerShell script to copy
    files from the local storage drop path to the storage
    account container. This tool is used only if you configure the
    deployment project to deploy your code along with the template.

Composing the Demo at Microsoft Connect(); //2015
-------------------------------------------------

1.  Include the parameters that are required for the template. Open
    azuredeploy.parameters.json and include the following code as
    parameters:

2.  Open azuredeploy.json, and the JSON code form deployment template
    will be deployed. On the left, you see a JSON Outline pane that has
    the same summary information.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image6.png){width="6.489583333333333in"
height="3.3541666666666665in"}

You can add and easily modify existing resources in the JSON document
from the JSON Outline pane.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image7.png){width="2.7604166666666665in"
height="1.6875in"}

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image8.png){width="6.489583333333333in"
height="4.895833333333333in"}

1.  Add the following parameters and variables to the template.

2.  Add the following resources to the template with the following
    information:

    a.  **App Service Plan (Server Farm)** with the name
        **HostingPlan**:

    b.  A **Web App** with the name **Website** and the **App Service
        plan** &gt; **HostingPlan** that you created before. Add an
        **Application Settings for Web Apps** with the name
        **connectionstrings** that’s associated to this **Web App**:

    c.  A SQL Server with the name **SqlServer**, and an instance of
        **Azure SQL Database** with the name **Database** that’s
        associated to this server:

    d.  A **Web App** with the name **MobileApp**, and the **App Service
        plan** &gt; **HostingPlan** that was created before.

> An **Application Setting for Web Apps** with the name **appsettings**
> that’s associated to **MobileApp**.
>
> An **Application Setting for Web Apps** with the name
> **connectionstrings** that’s associated to **MobileApp**.
>
> A **Nested Deployment** with the name
> **Microsoft.Resources/mobile-notificationhub** that’s associated with
> **MobileApp**.

a.  A **Nested Deployment** with the name **NotificationHub** with other
    **Nested Deployment** with the name
    **\[concat(variables('notificationHubNamespace'), '/',
    variables('notificationHubName'))\]** that’s associated to the
    **Notification Hub**:

<!-- -->

1.  Optionally, related **Application Insights** resources may be
    included:

> Add an **Application Insights for Web Apps** resource with the name
> **ApplicationInsights**, that’s associated with the **App Service
> plan** &gt; **HostingPlan** and the **Web App** &gt; **Website**:

1.  You have to organize the resources so that they’re generated in a
    specific order. Resources should be organized as follows:

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image9.png){width="5.927083333333333in"
height="6.46875in"}

With this, you will have all available resources to generate simple and
quick Azure deployments.

You can [download the
solution](https://github.com/Microsoft/HealthClinic.biz/blob/master/01_Demos_ASPNET5.sln).

Deploy My Azure Resources
=========================

After you prepare the resources for the deployment, you can deploy them
as many times as necessary.

1.  Right click the principal project, and select **Deploy** &gt; **New
    Deployment**.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image10.png){width="6.28125in" height="3.75in"}

1.  Sign in to Azure if necessary, and select the desired
    subscription type. Create a new resource group where all resources
    that will be created are grouped.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image11.png){width="5.145833333333333in"
height="4.458333333333333in"}

1.  Optionally, you can click **Edit Parameters** to modify the
    deployment parameters.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image12.png){width="4.020833333333333in"
height="3.40625in"}

The **Save passwords** option means that the passwords will be saved as
plain text in the JSON file. This option is not secure.

1.  Click **Deploy** to implement the project. The implementation may
    take several minutes. When it’s finished, you can see the deployed
    resources in the resource group in the Azure portal.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image13.png){width="6.489583333333333in"
height="4.958333333333333in"}

Deploy My Azure Resources by using Azure PowerShell
---------------------------------------------------

Before you start to work on the solution, you must be signed in.

To sign in your Azure account, use the **Login-AzureRmAccount** cmdlet.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image14.png){width="6.5in"
height="1.8020833333333333in"}

You can deploy manually by using PowerShell and have the possibility of
creating scripts by using the **New-AzureRmResourceGroupDeployment**
cmdlet*.*

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image15.png){width="6.5in"
height="1.8020833333333333in"}

You specify the resource group and the location of the template. If your
template is not local, you could use the **-TemplateUri** parameter and
specify a URI for the template. You can set the **-Mode** parameter to
either **Incremental** or **Complete**. Because Resource Manager
performs an incremental update during deployment by default, it is not
essential to set **-Mode** when you want **Incremental**.

If you are familiar with PowerShell, you can cycle through the available
parameters for a cmdlet by typing a minus sign (-) and then pressing the
TAB key. This same functionality also works with parameters that you
define in your template. As soon as you type the template name, the
cmdlet fetches the template, parses it, and adds the template parameters
to the command dynamically. This makes it very easy to specify the
template parameter values. If you forget a required parameter value,
PowerShell prompts you for the value.

You can check the Azure portal to see the deployed resources after the
implementation is finished.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image13.png){width="6.489583333333333in"
height="4.958333333333333in"}

Publish your application
========================

After the resources are deployed in Azure, the application will be
implemented in a simpler and quicker way.

In this tutorial, the two existing solutions, 01\_Demos\_ASPNET5 and
06\_Demos\_MobileApp, will be deployed in the cloud You can [download
the
solutions](https://github.com/Microsoft/HealthClinic.biz/blob/master/01_Demos_ASPNET5.sln)
from the GitHub repository.

01\_Demos\_ASPNET5
------------------

1.  Open the solution with Visual Studio. You can modify the parameters
    of the default credentials that you need to connect to the private
    website by modifying the appsettings.json file.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image16.png){width="6.5in" height="3.59375in"}

1.  Right-click the **MyHealth.Web** project, and then click
    **Publish**. Select **Microsoft Azure App Service** as a
    publish target.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image17.png){width="6.489583333333333in"
height="5.135416666666667in"}

1.  Select the desired Azure subscription and look for the resource
    group that you previously deployed and associated to **Web Site**.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image18.png){width="6.489583333333333in"
height="4.864583333333333in"}

1.  Click **OK**. Make sure that you have selected the correct version
    of **DNX (rc1-update1)** on the **Settings** tab.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image19.png){width="6.489583333333333in"
height="5.135416666666667in"}

1.  Click **Publish**. The web application will be implemented in
    **Azure**. When it’s finished, a web browser with the HealthClinic
    web site will open.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image20.png){width="6.489583333333333in"
height="4.260416666666667in"}

06\_Demos\_MobileApp
--------------------

1.  Open the solution with Visual Studio.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image21.png){width="6.5in" height="3.59375in"}

1.  Right-click the **MyHealth.MobileApp** project, and then click
    **Publish**. Select **Microsoft Azure App Service** as a
    publish target.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image17.png){width="6.489583333333333in"
height="5.135416666666667in"}

1.  Select the desired Azure subscription, and look for the resource
    group that you previously deployed and associated to **Mobile
    Site**.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image22.png){width="6.489583333333333in"
height="4.864583333333333in"}

1.  Click **OK**. You can see the different connection parameters on the
    **Connection** tab.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image23.png){width="6.489583333333333in"
height="5.135416666666667in"}

1.  Click **Publish**. The mobile application starts to implement
    in Azure. When it’s finished, a browser will indicate that the
    deployment is finished.

![](https://whitepapershealth.blob.core.windows.net/reosurcemanager/image24.png){width="6.5in"
height="3.9270833333333335in"}

After both backend services are deployed, you can use the created
service URLs in the client applications:

-   In the src\\MyHealth.Client.Core\\AppSettings.cs file, set the
    following parameters:

    -   **ServerUrl** to the web service **URL**.

    -   **MobileAPIUrl** to the mobile service **URL**.

-   In the
    src\\MyHealth.Client.Cordova\\content\\app\\modulers\\shared\\services\\configService.ts
    file, set the **Azure\_API\_URL** parameter to the mobile service
    **URL**.

Other suggested topics to explore
=================================

-   [Creation and deploying Azure resource groups through Visual
    Studio](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resource-groups-deployment-projects-create-deploy/).

<!-- -->

-   [Installation and management of extensions in Visual
    Studio Code.](https://code.visualstudio.com/docs/editor/extension-gallery?pub=msazurermtools&ext=azurerm-vscode-tools)

-   [Deployment of *Demo* presented at Microsoft Connect();
    //2015](https://github.com/Microsoft/HealthClinic.biz/wiki/Deployment-to-Azure)
    from the existing documentation in GitHub.

-   [Using Azure PowerShell with Azure Resource
    Manager](https://azure.microsoft.com/en-us/documentation/articles/powershell-azure-resource-manager/#prerequisites).

-   [Deploying a Resource Group with an Azure Resource Manager
    template](https://azure.microsoft.com/en-us/documentation/articles/resource-group-template-deploy/).

-   [Azure Developer Tools](http://azure.com/tools) – Learn more about
    the tools and find the recently released installers.

