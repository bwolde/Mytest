# Integrate with DevOps / ALM lifecycle

Overview
========

This tutorial describes how to work with Visual Studio Team Services. It
describes how to create a project, upload the source code of a local
project, and compile and build the project automatically through a build
agent in Azure. After you finish the tutorial, you’ll have a project in
Visual Studio Team Services, with source code that’s available in a
source code controller, and an automatic build that’s available to use.

The following illustration shows Visual Studio Team Services with the
project added:

![](https://whitepapershealth.blob.core.windows.net/alm/image1.png)

You’ll learn these procedures:

-   How to prepare your machine for Azure development by installing the
    [Azure SDK for .NET](https://azure.com/tools)

-   How to create a project in Visual Studio Team Services

-   How to upload the source code to the source code controller in
    Visual Studio Team Services

-   How to add a build agent in Azure

-   How to add a build to Visual Studio Team Services to compile and
    build the code

Sign up for Microsoft Azure
===========================

You need an Azure account to complete this tutorial. You can:

-   [Open an Azure account for
    free](https://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A261C142F).
    You get credits that can be used to try out paid Azure services.
    Even after you use the credits, you can keep the account and use
    free Azure services and features, such as the Web Apps feature in
    Azure App Service.

-   [Activate Visual Studio subscriber
    benefits](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F).
    Your Visual Studio subscription gives you credits every month that
    you can use for paid Azure services.

-   Get credits every month by joining [Visual Studio Dev
    Essentials](https://www.visualstudio.com/products/visual-studio-dev-essentials-vs).

If you want to get started with Azure App Service before you sign up for
an Azure account, go to [Try App
Service](http://go.microsoft.com/fwlink/?linkid=523751&clcid=0x409). You
can immediately create a short-lived starter web app in App Service,
with no credit card required and no commitments necessary.

Set up the development environment
==================================

To get started, set up your development environment by installing the
latest version of the [Azure
SDK](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/VWDOrVs2015AzurePack.appids).

[Visual Studio
2015](https://go.microsoft.com/fwlink/?linkid=746481&clcid=0x409)▶

[Visual Studio
2013](https://go.microsoft.com/fwlink/?linkid=746482&clcid=0x409)▶

If you don't have Visual Studio installed, use the link for Visual
Studio 2015. Visual Studio will be installed along with the SDK.

Sign up for Visual Studio Team Services
=======================================

Create your Team Services account:

-   If you want to get started quickly and need minimal control over who
    can access your Team Services account, [sign up with a Microsoft
    account](https://www.visualstudio.com/get-started/setup/sign-up-for-visual-studio-team-services#MicrosoftAccount).

-   If you need more control over who can access your Team Services
    account, [sign up with a work or school
    account](https://www.visualstudio.com/get-started/setup/sign-up-for-visual-studio-team-services#orgaccount).

After you’ve created your team project, you can connect your development
tools and add code for your app to the cloud. You can also create work
items to start planning your work.

1.  [Sign in to Visual Studio Team
    Services](https://go.microsoft.com/fwlink/?LinkId=307137&clcid=0x409)
    with your Microsoft account or work/school account.

> If you have a Visual Studio subscription that includes Team Services
> as a benefit, use the Microsoft account that’s associated with your
> subscription.
>
> Give your account a name that’s easy to remember. Then choose which
> version control provider you want to use to manage your code.

1.  Not sure which to choose? Find the [version
    control](https://msdn.microsoft.com/library/vs/alm/code/overview#tfvc_or_git_summary)
    provider that works best for you.

> ![](https://whitepapershealth.blob.core.windows.net/alm/image2.png){width="6.489583333333333in"
> height="3.0in"}

1.  Confirm your account location.

> The default process template that’s used to manage your work is the
> **Agile** template. [Can I change the account location or process
> template?](https://www.visualstudio.com/get-started/setup/sign-up-for-visual-studio-team-services#AccountLocation)
>
> ![](https://whitepapershealth.blob.core.windows.net/alm/image3.png){width="5.833333333333333in"
> height="1.875in"}

Create a new project in Visual Studio Team Services
===================================================

After creating your account in Visual Studio Team Services, you will see
a panel that displays a summary of your projects. Since this is a new
account, you won’t have any projects.

To create a new project, select the **New project** button:

![](https://whitepapershealth.blob.core.windows.net/alm/image4.png){width="6.5in" height="4.28125in"}

Fill in the fields, such as name and description, with the project
information. Then choose a template and version control provider.

You can change the template and the version control provider later if
necessary. However, it’s a good idea to choose them carefully at first,
because it requires extra work to change them later.

![](https://whitepapershealth.blob.core.windows.net/alm/image5.png){width="6.489583333333333in"
height="4.53125in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image6.png){width="6.489583333333333in"
height="4.541666666666667in"}

After you create the project, it’s available on your panel. When you
access it for the first time, a new page displays a summary of the
project (which won’t have any information in it yet, since the project
is new). This panel can be customized to improve the developer
experience.

![](https://whitepapershealth.blob.core.windows.net/alm/image7.png){width="6.489583333333333in"
height="4.541666666666667in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image8.png){width="6.5625in"
height="3.7916666666666665in"}

Add code to the project
=======================

To add your code to the newly created project in Visual Studio Team
Services, and to keep it in a version control provider in the cloud, you
need to connect the project to Visual Studio 2013 or Visual Studio 2015.

To do this, go to the **Team Explorer** tab. Then select the Visual
Studio Team Services server that you just created. You’ll be connected
to the project in Visual Studio.

![](https://whitepapershealth.blob.core.windows.net/alm/image9.png){width="6.5in"
height="3.8333333333333335in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image10.png){width="6.489583333333333in"
height="3.8229166666666665in"}

When you use Git as the source code manager, you have to clone the
project locally for it to start working. Select **Close this
repository** in the window that automatically opened in the **Team
Explorer** tab, and then indicate where you want to put the local
repository.

![](https://whitepapershealth.blob.core.windows.net/alm/image11.png){width="4.833333333333333in"
height="4.020833333333333in"}

After you place the project in a local repository, you can put a
solution in the repository for upload to the cloud. You can also include
all the solutions that are available on the [GitHub
demo](https://github.com/Microsoft/HealthClinic.biz) , as shown during
the [Microsoft Connect ();
//2015](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/)
conference. To do this, select **Open ...**, and then indicate the
location of the solution.\
You can also add new solutions by selecting **New** …. This opens a
window where you can select what type of new solution you want.

![](https://whitepapershealth.blob.core.windows.net/alm/image12.png){width="4.864583333333333in"
height="3.6666666666666665in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image13.png){width="6.489583333333333in"
height="4.520833333333333in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image14.png){width="4.916666666666667in"
height="3.9895833333333335in"}

After the solution is in the local repository, you can upload the code
to the source code provider if you want to have this code in the cloud.
To do this, go to the **Changes** screen, and then select **Commit**. To
upload this commit to the repository, go to the **Synchronization**
screen, and then select **Push**.

![](https://whitepapershealth.blob.core.windows.net/alm/image15.png){width="4.90625in" height="4.0in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image16.png){width="4.885416666666667in"
height="4.010416666666667in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image17.png){width="4.875in"
height="3.9791666666666665in"}

You can verify that the code has been submitted by checking it in Visual
Studio Team Services:

![](https://whitepapershealth.blob.core.windows.net/alm/image18.png){width="6.5625in"
height="3.7916666666666665in"}

Add a build agent to Azure
==========================

It’s possible to generate a build automatically. You can generate a
build every so often, when an event occurs, or when a branch of the
repository is updated. It saves time to generate automatically builds.

With this you can check that your code works on another machine.

You do this on the **Build** tab.

![](https://whitepapershealth.blob.core.windows.net/alm/image19.png){width="6.5625in"
height="3.7916666666666665in"}

It’s important to note at this point that Visual Studio Team Services
also has a default build agent that’s useful for small projects or
projects that have few dependencies. This step that you’re taking now is
only necessary for projects that have external dependencies, or that are
too large for the default agent.

![](https://whitepapershealth.blob.core.windows.net/alm/image20.png){width="5.375in"
height="2.4479166666666665in"}

If necessary, you can also create build agents and agent pools (groups
of specialized agents) to manage the builds of individual projects that
make up the solution.

This requires a machine that has the tools that are necessary for
compiling the project. This machine might be found on-premises or hosted
on a server with Azure. This machine needs the following:

-   An operating system that supports IDE version development

-   The development IDE that performs the compilation

-   Windows PowerShell 3.0 or higher

The sample project that you’re developing is a Universal Windows
Platform application. You’ll need the following:

-   An operating system that supports Visual Studio 2015

-   The Visual Studio 2015 Universal Windows Platform application kit

-   PowerShell 3.0

Depending on the project, there might be more dependencies. Therefore,
you might need an extra machine.

[Demo for the Microsoft Connect ();
//2015](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/)

Before deploying a build agent, ensure that you have administrator
permissions for the **Agent pools** in the Team Services account. For
more information, see [Agent
pools](https://msdn.microsoft.com/Library/vs/alm/Build/agents/admin?f=255&MSPPError=-2147217396#agent-pools).

1.  On the machine where you want to run the build agent, open a web
    browser and go to:

    -   Team Services:

> Or go to

-   On-premises:

1.  Select **Download agent**.

2.  Unzip the .zip file into the folder from which you’d like to run
    the agent. To avoid "path too long" issues on the file system, keep
    the path short. For example, you can run this command: C:\\Agent\\

3.  Open the command prompt as administrator, and then run:

C:\\Agent\\ConfigureAgent.cmd

1.  Complete the required information. Then sign in with your Team
    Services account to complete the configuration.

You have now configured an agent that’s available to perform builds.

Run the agent
-------------

The agent can run in two ways:

-   **Run as a service**: Choose this option if you want to deploy the
    agent as a Windows service and control the status of the agent in
    Services Explorer. Run **services.msc**, and then search for **VSO
    Agent** &lt;*name of your agent*&gt;.

-   **Run interactively**: Choose this option if you want to deploy the
    agent interactively. You can run the agent by launching the
    **Agent\\VsoAgent.exe** file.

Now the agent is automatically configured in Visual Studio Team
Services, and a link to the machine that perform builds will be created.
To check that everything is working, go to:

Verify that the machine is registered in the pool of agents that’s
listed in the agent configuration on the machine. If it’s there, it
means it’s available to generate builds.

![](https://whitepapershealth.blob.core.windows.net/alm/image21.png){width="6.489583333333333in"
height="4.625in"}

Add a build to compile and deploy the project
=============================================

Now you can create a build to compile and deploy the project.

As an example, we’ll add one compilation build and deployment for the
Universal Windows Platform application project to Visual Studio Team
Services. Go to the build page of the project in Visual Studio Team
Services. Then select **Add new build definition**. and select the
**Universal Windows Platform** template. If you need another template,
there are several available. You can also create your
own.![](https://whitepapershealth.blob.core.windows.net/alm/image22.png){width="6.6in" height="3.8in"}

![](https://whitepapershealth.blob.core.windows.net/alm/image23.png){width="6.6in" height="3.8in"}

Next, a configuration window is displayed. Select the repository (in
this case, [Microsoft Connect(); //2015
Demo](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/),
the master branch). Next, select **Continuous integration** if you want
integration to happen each time the branch is updated a new build is
generated. The agent pool that you will use was configured in the
previous section.

![](https://whitepapershealth.blob.core.windows.net/alm/image24.png){width="6.5in" height="4.1in"}

Finally, select click on **Create**.

A new window with information about the build and its various settings
are displayed.

![](https://whitepapershealth.blob.core.windows.net/alm/image25.png){width="6.5in" height="4.1in"}

It’s important to select the **Save** button after creating the
definition so that all changes are saved.

If you make any changes in the elected branch, and have opted for
continuous integration, the build runs in the background on the machine
that you configured in the previous section.

If you need to run a build manually, select the **Queue** build on the
build definition page.![](https://whitepapershealth.blob.core.windows.net/alm/image26.png){width="6.5in"
height="3.5in"}

Once the build has been run, you’ll see information about the status of
the compilation and of previous builds. All of these parameters can be
configured.

![](https://whitepapershealth.blob.core.windows.net/alm/image27.png){width="6.5in" height="3.5in"}

To compile and create compilation builds for other solutions, such as
the [Demo of Microsoft Connect();
//2015](https://blogs.msdn.microsoft.com/visualstudio/2015/12/08/connectdemos-2015-healthclinic-biz/),
simply add dependencies and build steps for each of them.

Other topics to explore
=======================

-   Scale out and administer your build and deployment system:
    <https://msdn.microsoft.com/en-us/Library/vs/alm/Build/agents/admin>

-   Deploy a Windows build agent:
    <https://msdn.microsoft.com/en-us/Library/vs/alm/Build/agents/windows>

-   Sign up in Visual Studio Team Services:
    <https://www.visualstudio.com/get-started/setup/sign-up-for-visual-studio-online>

-   Connect to Visual Studio Team Services:
    <https://www.visualstudio.com/get-started/setup/connect-to-visual-studio-online>

-   Get started with Azure:
    <https://azure.microsoft.com/en-us/get-started/>

-   [Azure Developer Tools](http://azure.com/tools) – Learn more about
    the tools and find recently released installers.

