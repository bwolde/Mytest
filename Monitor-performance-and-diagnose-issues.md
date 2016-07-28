# Monitor performance and diagnose issues

Overview
========

This article explains how to diagnose performance issues in a web or mobile application in Microsoft
Azure by using Visual Studio Application Insights, HockeyApp and the diagnostic
tools in Visual Studio 2015. 

Sign up for Microsoft Azure
===========================

You need an Azure account to use Application Insights. You can:

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

Alternatively, and depending on the type of target project that you want to monitor,
install the [Xamarin
platform](https://xamarin.com/download) and also those platforms which
are part of the project, or [Visual Studio Tools for Apache
Cordova](https://www.visualstudio.com/en-us/features/cordova-vs.aspx).

HockeyApp for client apps, Application Insights for web apps and services
=========================================================================

There are two separate performance monitoring offerings that meet the differing requirements of device and server apps:

* [HockeyApp for device apps](https://hockeyapp.net/) helps you with app versioning and distribution as well as collecting user feedback, crash reports, and app telemetry. This is ideal for phone apps and Windows Store apps.
* [Application Insights for web apps and services](https://azure.microsoft.com/documentation/articles/app-insights-overview/) monitors usage and performance and provides powerful performance diagnostic tools. In this demo, Application Insights is ideal both for the [web app in Azure app service](https://github.com/Microsoft/HealthClinic.biz/wiki/Create-and-deploy-an-ASP.NET-web-app-in-Azure-App-Service) and the [Azure mobile app service](https://github.com/Microsoft/HealthClinic.biz/wiki/Create-and-deploy-a-mobile-app-in-Azure-App-Service), which provides the back end for your mobile client apps.


Add Application Insights to your web app
========================================

### Open your web app in Visual Studio. 

As a sample, you can use our demo app, which is an example of the web service component that supports a mobile client. 

1. Download and extract the code from: https://github.com/Microsoft/HealthClinic.biz
2. Open 06_Demos_MobileApp.sln in Visual Studio. 

### Configure Application Insights 

In Solution Explorer, right-click the web app project.

* Select **Add Application Insights**; or
* Choose **Application Insights > Configure Application Insights**.
 * Under Register your app with Application Insights, click **Change**
 * Sign in to Azure in this window if required.
 * Click **Update resource**

This does two things:

1. Sets up a new Application Insights resource in Azure, where your telemetry will be stored, analyzed and displayed.
2. Adds the Application Insights SDK to your code, and configures it to send to the new resource. 

### Publish the app to Azure. 

1. Use the Visual Studio 'publish' feature to upload and start the app.
2. To get more comprehensive telemetry, link the app in Azure to its Application Insights resource:
 1. In the [Azure portal](https://portal.azure.com/) open your web app's control panel. 
 2. Choose **Tools > Performance monitoring > Click here > Application Insights** and then select the Application Insights resource.


### View app telemetry in Application Insights

1. Make some use of the app, so as to generate some telemetry.

2. In the [Azure portal](https://portal.azure.com/), open the Application Insights resource of your web app.

    ![example Application Insights display](https://whitepapershealth.blob.core.windows.net/diagnose/image1.png) 

3. Click through any of the charts that shows data, to get more detail.

Here are some more things you can do to analyze your data:

* Open the [Search blade](https://azure.microsoft.com/documentation/articles/app-insights-diagnostic-search/) to find and inspect individual requests, or exceptions
* Use [Metrics explorer](https://azure.microsoft.com/documentation/articles/app-insights-metrics-explorer/) to make customized charts of request counts, success rates, response times, dependency calls, and exceptions.
* Go to [Analytics](https://azure.microsoft.com/documentation/articles/app-insights-analytics-tour/) to create powerful queries over your app's telemetry.
* Create [Dashboards](https://azure.microsoft.com/documentation/articles/app-insights-dashboards/) showing the metric and analytics charts that are most important to you and your team.

Application Insights will send you alert emails:

* [Smart alerts](https://azure.microsoft.com/documentation/articles/app-insights-proactive-detection/) are automatically configured by Application Insights (after a few days of substantial traffic). They will email you to warn of unusual changes in your web app's failed response rate. 
* [Alerts on metric thresholds](https://azure.microsoft.com/documentation/articles/app-insights-alerts/) can be set manually on metrics of your choice.
* [Availability web tests](https://azure.microsoft.com/documentation/articles/app-insights-monitor-web-app-availability/) send test requests to your web app at frequent intervals from our points of presence around the world.


Diagnose an application in Visual Studio
========================================

You can analyze the data that is reported by Application Insights in
Azure in the Azure portal. By doing this, you can see metrics and debug
data from the application.

You can also analyze this data from Visual Studio. To do this, click the
**Application Insights** button that is available on the menu bar. This
displays a window with the Application Insights loading screen.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image14.png)

After Application Insights starts, Application Insights information
about the latest project is displayed. To change the project or Azure
subscription, select the project or existing subscription in the window.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image15.png)

From this window, you can view information about the project that is
saved in Application Insights.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image16.png)

You can view detailed information, browse different dates, or filter
different types of saved events from this window.

![](https://whitepapershealth.blob.core.windows.net/diagnose/image17.png)

HockeyApp for device apps
=========================

To monitor the client apps, use [HockeyApp](https://support.hockeyapp.net/kb).

* [HockeyApp for iOS](http://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/hockeyapp-for-ios)
* [HockeyApp for Android](http://support.hockeyapp.net/kb/client-integration-android/hockeyapp-for-android-sdk)
* [HockeyApp for Universal Windows apps](http://support.hockeyapp.net/kb/client-integration-windows-and-windows-phone)
* [HockeyApp and Xamarin](https://support.hockeyapp.net/kb/client-integration-cross-platform/how-to-integrate-hockeyapp-with-xamarin)
* [HockeyApp and Cordova](https://support.hockeyapp.net/kb/client-integration-cross-platform/how-to-integrate-hockeyapp-with-phonegapcordova)


### HockeyApp and Visual Studio

For some types of app, you can right-click the project in Solution Explorer, and use HockeyApp tools:

* **Enable crash reporting** - adds the HockeyApp SDK to the app, so that telemetry is sent back to HockeyApp
* **Distribute with HockeyApp** - publish the app to HockeyApp so that you can supervise distribution to test and beta users, and collect feedback from them.

To use these tools, make sure you have the latest update of Visual Studio, and the latest version of the Developer Analytics Tools extension. In **Tools** > **Extensions and updates**, open **Updates** and run any that are available.




### Other suggested topics to explore
=================================

-   [Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/)
    overview 
-   [Azure Developer Tools](http://azure.com/tools) for more information
    about the tools and for the recently released installers
-   [HockeyApp](https://support.hockeyapp.net/kb)


