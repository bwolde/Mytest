# Diagnose your Azure application

Overview
========

This tutorial shows you how to diagnose an application in Microsoft
Azure by using Visual Studio Application Insights and the diagnostic
tool in Visual Studio 2015. After completing the tutorial, you will have
implemented Application Insights in each of the existing solutions from
the Microsoft Connect(); //2015 developer event, and you will know how
to diagnose cloud projects in Visual Studio 2015.

The following illustration shows Application Insights working:

![](https://whitepapershealth.blob.core.windows.net/diagnose/image1.png){width="5.020833333333333in"
height="3.3229166666666665in"}

You’ll learn the following procedures:

-   How to prepare your machine for Azure development by installing the
    [Azure SDK for .NET](https://azure.com/tools)

-   How to set up Visual Studio for the use of Application Insights and
    for debugging applications in the cloud

-   How to add Application Insights to a Universal Windows project

-   How to add Application Insights to a Xamarin project

-   How to add Application Insights to a Cordova project

-   How to diagnose an application in Visual Studio

-   How to use the [Azure
    portal](https://azure.microsoft.com/overview/preview-portal/) to
    monitor and manage your mobile app

Sign up for Microsoft Azure
===========================

You need an Azure account to complete this tutorial. You can:

-   [Open an Azure account for
    free](https://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A261C142F).
    You get credits that can be used to try out paid Azure services.
    Even after the credits are used up, you can keep the account and use
    free Azure services and features, such as the Web Apps feature in
    Azure App Service.

-   [Activate Visual Studio subscriber
    benefits](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F).
    Your Visual Studio subscription gives you credits every month that
    you can use for paid Azure services.

-   Get credits every month by joining [Visual Studio Dev
    Essentials](https://www.visualstudio.com/products/visual-studio-dev-essentials-vs).

If you want to get started with Azure App Service before you sign up for
an Azure account, go to [Create your Azure App Service
app](http://go.microsoft.com/fwlink/?linkid=523751&clcid=0x409). There,
you can immediately create a short-lived starter web app in App
Service—a credit card is not required, and there are no commitments.

Set up your development environment
===================================

To start, set up your development environment by installing the latest
version of the [Azure
SDK](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/VWDOrVs2015AzurePack.appids).

[Visual Studio
2015](https://go.microsoft.com/fwlink/?linkid=746481&clcid=0x409)▶

[Visual Studio
2013](https://go.microsoft.com/fwlink/?linkid=746482&clcid=0x409)▶

If you don't have Visual Studio installed, use the link for Visual
Studio 2015, and Visual Studio will be installed along with the SDK for
Universal Windows applications.

Alternatively, and depending on the type of target project that will
implement Application Insights, you need to install the [Xamarin
platform](https://xamarin.com/download) and also those platforms which
are part of the project, or [Visual Studio Tools for Apache
Cordova](https://www.visualstudio.com/en-us/features/cordova-vs.aspx).

Create an Application Insights service in Azure
===============================================

To save the results and statistics that are collected by the
application, you must register an Application Insights service in Azure.
In the Azure portal, go to the **Application Insights** option and add a
new item by setting the necessary parameters. It’s important to select
the type of target application.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image2.png){width="4.7in" height="6.0in"}

![](https://whitepapershealth.blob.core.windows.net/diagnose/image3.png){width="6.5in" height="5.0in"}

After the service is created, open the resource from the Azure portal
and get the **Instrumentation Key**. You must save this key to use in
the next step.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image4.png){width="6.5in" height="5.5in"}

Add Application Insights to a Universal Windows project
=======================================================

In order to focus the reader on the goal, which is to add Application
Insights to a Universal Windows project, we prepared a basic project
based on the demo that was presented at Microsoft Connect(); //2015.
This means that you only need to apply the following instructions. You
can download the project from the following link:
[HealthDemo.UniversalWindows.Base](https://github.com/Microsoft/HealthClinic.biz/blob/master/10_Demos_Deployment.sln).

Because there is currently no support for adding Application Insights by
using a wizard (as there usually is in projects with another target,
like a web application or a Windows 8.1 application), you need to add
Application Insights to the project manually.

To install Application Insights in the project
**HealthDemo.UniversalWindows**, in Visual Studio, access the NuGet
packages manager and install the references:

-   **Microsoft.ApplicationInsights**

-   **Microsoft.ApplicationInsights.PersistenceChannel** (Only install
    this if you want to preserve the data when the application has no
    connection in the device, and then upload data when there is
    a connection.)

-   **Microsoft.ApplicationInsights.WindowsApps**

![](https://whitepapershealth.blob.core.windows.net/diagnose/image5.png){width="6.5in" height="3.3in"}

You must tell the application to use the platform. To do this, it is
sufficient to indicate the App.xaml.cs class within the class
constructor from Public App() {.

Run the following code:

![](https://whitepapershealth.blob.core.windows.net/diagnose/image6.png){width="6.5in" height="3.0in"}

In the root of the project, create a new file called
**ApplicationInsights.config** by using the following code:

Replace *YOUR\_INSTRUMENTATION\_KEY* with the Instrumentation Key that
you copied in the previous step. You must specify the properties of this
file, which are the content type and what is to be copied, if necessary.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image7.png){width="4.9in" height="4.8in"}

At this point, you have configured Application Insights on your
Universal Windows application.

If the application doesn’t have [network permissions for external
requests](https://msdn.microsoft.com/library/windows/apps/hh452752.aspx),
you must add them to the application manifest as a [required
capacity](https://msdn.microsoft.com/library/windows/apps/br211477.aspx).

After you run the application, test it, and use it, you can see how
different results are recorded in the Azure portal:

![](https://whitepapershealth.blob.core.windows.net/diagnose/image1.png){width="5.020833333333333in"
height="3.3229166666666665in"}

You can download the complete code from the following link:
[HealthDemo.UniversalWindows](https://github.com/Microsoft/HealthClinic.biz/blob/master/05_Demos_NativeApps.sln).

Add Application Insights to a Xamarin project
=============================================

By using a C\# shared codebase, you can use
[Xamarin](https://www.xamarin.com/) tools to write native Android, iOS,
and Windows apps with native user interfaces—and you can share code
across multiple platforms.

Because the demo project does not include Application Insights, you can
use this project as a base project. It’s available in
[GitHub](https://github.com/Microsoft/HealthClinic.biz).

To add Application Insights to a Xamarin project, you need to download
or clone the repository that is located in
[GitHub](https://github.com/Microsoft/ApplicationInsights-Xamarin).

It contains three folders—one with a demo project (DemoApp), one local
NuGet package (NuGet), and one with the SDK source code
(ApplicationInsightsXamarin). Extract the file to the location of your
choice.

There are several ways to include the SDK in a Xamarin project. We
recommend using the NuGet package.

1.  Right-click the project of the platform of your choice, and select
    **Manage NuGet Packages**.

2.  Click **Options** to view the list of available NuGet
    package sources.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image8.png){width="6.489583333333333in"
height="3.7395833333333335in"}

1.  Add the local repository of NuGet packages where you extracted the
    Application Insights SDK for Xamarin:
    **ApplicationInsightsXamarin/NuGet**.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image9.png){width="6.489583333333333in"
height="4.177083333333333in"}

1.  Indicate that you want to get packages from the local repository
    that you just added. Make sure that you have selected **Include
    prerelease**. Finally, select and add the package **Application
    Insights SDK for Xamarin.Forms**.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image10.png){width="6.489583333333333in"
height="3.7395833333333335in"}

1.  Repeat this process in each of the projects of the different
    platforms where you want to add **Application Insights for
    Xamarin.Forms**.

2.  Now, you just have to add a few lines of code to the project to set
    up Application Insights for use. Depending on the platform, you must
    configure and start the Application Insights SDK for Xamarin in some
    files:

    -   Xamarin.Forms (Android and iOS): Application class (for example,
        project\_name.cs in the shared project)

    -   iOS only: AppDelegate.cs in your iOS project

    -   Android only: Main activity of your Android project

3.  Add *using* statements:

> using AI.XamarinSDK.Abstractions;

1.  Add the following lines of code in one of the following methods:

    -   Xamarin.Forms (Android & iOS): *OnStart()*

    -   iOS only: *FinishedLaunching()*

    -   Android only: *OnStart()*

> ApplicationInsights.Setup(“YOUR\_INSTRUMENTATION\_KEY”);
>
> ApplicationInsights.Start();
>
> **NOTE:** If you plan to support iOS, you currently need to make a
> direct call to the iOS assembly so that it doesn't get stripped by the
> linker. Add the following line right after the *Xamarin.Forms
> init()-call* inside the *FinishedLaunching()* of your AppDelegate.cs.
>
> > AI.XamarinSDK.iOS.Applicationinsights.Init();

1.  Override *YOUR\_INSTRUMENTATION\_KEY* with the code Instrumentation
    Key that you copied in the previous step.

After you’ve done this, Application Insights will be installed in the
project. The entire project is available from the following link:
[HealthDemo.Xamarin](https://github.com/Microsoft/HealthClinic.biz/blob/master/04_Demos_NativeXamarinApps.sln)

![](https://whitepapershealth.blob.core.windows.net/diagnose/image1.png){width="5.020833333333333in"
height="3.3229166666666665in"}

Add Application Insights to a Cordova project
=============================================

[Apache Cordova](https://cordova.apache.org/) enables software
programmers to build applications for mobile devices using CSS3, HTML5,
and JavaScript instead of relying on platform-specific APIs like those
in Android, iOS, and Windows Phone. It enables CSS, HTML, and JavaScript
code to be wrapped up, depending upon the platform of the device. It
also extends the features of HTML and JavaScript to work with the
device. The resulting applications are hybrid. This means that they are
not truly native mobile applications (because all layout rendering is
done via web views instead of the platform's native UI framework), and
they are not purely web-based (because they are not just web apps—they
are packaged as apps for distribution and have access to native device
APIs).

Because the demo project does not have Application Insights installed,
this project can be used as a base project. It’s available in
[GitHub](https://github.com/Microsoft/HealthClinic.biz).

While you can add a Connected Service to a Cordova application,
Application Insights is not currently supported as a service.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image11.png){width="6.489583333333333in"
height="4.427083333333333in"}

However, you can install Application Insights by using a plug-in.

1.  Open the file config.xml, and go to the **Plug-ins** option.

2.  Add the following URL as a Git repository:
    <https://github.com/MSOpenTech/cordova-plugin-ms-appinsights>.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image12.png){width="6.489583333333333in"
height="3.7395833333333335in"}

1.  A new Application Insights window appears with a field to enter the
    **INSTRUMENTATION\_KEY** that you generated in previous steps
    in Azure. Enter the key, and click **Add**.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image13.png){width="6.489583333333333in"
height="3.3541666666666665in"}

After you’ve finished this, Application Insights will be installed on a
Cordova project. You can test the application and see the statistics
that are collected in the Azure portal. Note that Ripple might not be
able to collect these metrics and might generate errors when you test
the application.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image1.png){width="5.020833333333333in"
height="3.3229166666666665in"}

The complete code is available from the following link:
[HealthDemo.Cordova](https://github.com/Microsoft/HealthClinic.biz/blob/master/03_Demos_Cordova.sln)

Diagnose an application in Visual Studio
========================================

You can analyze the data that is reported by Application Insights in
Azure in the Azure portal. By doing this, you can see metrics and debug
data from the application.

You can also analyze this data from Visual Studio. To do this, click the
**Application Insights** button that is available on the menu bar. This
displays a window with the Application Insights loading screen.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image14.png){width="6.489583333333333in"
height="3.3541666666666665in"}

After Application Insights starts, Application Insights information
about the latest project is displayed. To change the project or Azure
subscription, select the project or existing subscription in the window.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image15.png){width="6.489583333333333in"
height="3.3541666666666665in"}

From this window, you can view information about the project that is
saved in Application Insights.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image16.png){width="6.489583333333333in"
height="3.3541666666666665in"}

You can view detailed information, browse different dates, or filter
different types of saved events from this window.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image17.png){width="6.489583333333333in"
height="3.3541666666666665in"}

Other suggested topics to explore
=================================

-   [Analytics for
    applications](https://azure.microsoft.com/documentation/articles/app-insights-windows-get-started/)
    with information about Application Insights and the recommendation
    of using HockeyApp in client-side projects

-   Information, tutorials, and news about the [installation of
    Application Insights in Xamarin
    applications](https://github.com/Microsoft/ApplicationInsights-Xamarin)

-   The [Application Insights SDK for Xamarin without Xamarin.Forms
    dependency](https://github.com/Microsoft/ApplicationInsights-Xamarin/tree/feature/remove-xamarin-forms)

-   Information, tutorials, and news about the [installation of
    Application Insights in Cordova
    applications](https://github.com/MSOpenTech/cordova-plugin-ms-appinsights)

-   [Azure Developer Tools](http://azure.com/tools) for more information
    about the tools and for the recently released installers

