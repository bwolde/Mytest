# Build cloud apps with Visual Studio Code

Overview
========

This tutorial shows you how to install Microsoft Visual Studio Code, and
also explains the information about it that was presented at the
Microsoft Connect(); //2015 developer event. Additionally, it shows you
how to work with extensions and TextMate Snippets. When you’re finished,
you’ll know how to use Visual Studio Code, and how to work with
extensions and TextMate Snippets in the tool.

The following shows the Visual Studio Code UI:

![](https://whitepapershealth.blob.core.windows.net/vscode/image1.png)

In this tutorial, you’ll learn these procedures:

-   How to install Visual Studio Code and open a project that already
    exists

-   How to work with extensions in Visual Studio Code

-   How to work with Snippets with TextMate

You’ll also learn information about Visual Studio Code that was
presented at Microsoft Connect(); //2015.

Requirements
============

Visual Studio Code is an open source code editor that was developed for
Windows, Linux, and OS X. It includes support for debugging, embedded
Git control, syntax highlighting, intelligent code completion, snippets,
and code refactoring. It is also customizable, so you can change the
theme, keyboard shortcuts, and preferences.

![](https://whitepapershealth.blob.core.windows.net/vscode/image2.png)

To install Visual Studio Code,
[download](https://code.visualstudio.com/) the appropriate version for
the development platform that you’re using. Then, follow the wizard
through the installation process.

![](https://whitepapershealth.blob.core.windows.net/vscode/image3.png)

Open a project
==============

Visual Studio Code supports a rich combination of languages. In the
following table, you can see the supported characteristics in each one.

  **Features**                        **Languages**
  ----------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Syntax coloring, bracket matching   Batch, C++, Clojure, Coffee Script, [Dockerfile](https://code.visualstudio.com/docs/languages/dockerfile), F\#, Go, Jade, Java, HandleBars, Ini, Lua, Makefile, Objective-C, Perl, PowerShell, Python, R, Razor, Ruby, Rust, SQL, Visual Basic, XML
  Snippets                            Groovy, [Markdown](https://code.visualstudio.com/docs/languages/markdown), PHP, Swift
  IntelliSense, linting, outline      [CSS](https://code.visualstudio.com/docs/languages/css), [HTML](https://code.visualstudio.com/docs/languages/html), [JavaScript](https://code.visualstudio.com/docs/languages/javascript), [JSON](https://code.visualstudio.com/docs/languages/json), [Less](https://code.visualstudio.com/docs/languages/css), [Sass](https://code.visualstudio.com/docs/languages/css)
  Refactoring, find all references    [TypeScript](https://code.visualstudio.com/docs/languages/typescript), [C\#](https://code.visualstudio.com/docs/languages/csharp)

If you need support for other languages, the community provides
extensions that you can install by using the shell that is included
within the editor. Press **F1** and type **ext inst** plus the language
that you want to include.

![](https://whitepapershealth.blob.core.windows.net/vscode/image4.png)

Additionally, you can get advice about the available languages at the
[Visual Studio
Marketplace](https://marketplace.visualstudio.com/vscode/Languages).

After the support for the defined language in your project is installed,
you can open the folder where it is included by clicking **File** &gt;
**Open Folder** &gt; **Open Project**.

![](https://whitepapershealth.blob.core.windows.net/vscode/image5.png)

If the project folder is included in a local Git repository, you can see
the changes, as well as the existing information in the repository, by
using the **Git** option in the editor: **View** &gt; **Git**.

![](https://whitepapershealth.blob.core.windows.net/vscode/image6.png)

You can debug the project by using the option **Debug** in the editor:
**View** &gt; **Debug**.

![](https://whitepapershealth.blob.core.windows.net/vscode/image7.png)

Work with extensions
====================

To look for extensions in Visual Studio Code, press **F1**, type
**extension**, and select **Install Extension** in the command list that
is shown.

![](https://whitepapershealth.blob.core.windows.net/vscode/image8.png)

**Tip:** Alternatively, press **Ctrl**+**P** and type **ext**
**install** followed by a space. This automatically deploys the
extension installer.

![](https://whitepapershealth.blob.core.windows.net/vscode/image9.png){width="6.3125in" height="2.4375in"}

A list of available extensions will be displayed. By typing more
parameters, you can filter the list according to the search. If you
don’t know which extensions are most related to your editor, see the
[Visual Studio Code
Marketplace](https://marketplace.visualstudio.com/VSCode).

To install an extension, click the desired extension. You’ll be notified
when it is installed. In some cases, it will be necessary to restart the
editor.

![](https://whitepapershealth.blob.core.windows.net/vscode/image10.png)

Check installed extensions
--------------------------

To see which extensions have already been installed, press **F1** and
use the command **Extensions: Show Installed Extensions**. Or press
**Ctrl**+**P** and type **ext** followed by a space.

![](https://whitepapershealth.blob.core.windows.net/vscode/image11.png)

Uninstall an extension
----------------------

To remove an extension, display the list of installed extensions in the
editor, as seen in the previous step, and click the **X** on the right
side of each of the extensions. You might need to restart the editor for
the changes to take effect.

![](https://whitepapershealth.blob.core.windows.net/vscode/image12.png)

Update an extension
-------------------

To update an extension, display the list of installed extensions in the
editor, as seen in the previous step, and press the button **Update
Extension**, which is located on the right. The button only appears if
the extension is outdated. You might need to restart the editor for the
changes to take effect.

Snippets with TextMate
======================

You can quickly insert ready-made snippets of code in your source code.
For example, a *for* snippet creates an empty *for* loop.

Each snippet defines a prefix (which will appear in IntelliSense via
**Ctrl**+**Space**), as well as a body that is inserted when the snippet
is selected. The snippet syntax follows the [TextMate snippet
syntax](https://manual.macromates.com/en/snippets) with the exception of
*regular expression replacements*, *interpolated shell code*, and
*transformations*, which are not supported.

Snippets can be loaded by the community in the [Visual Studio Code
Extension Gallery](https://marketplace.visualstudio.com/VSCode). You can
use them as if they were extensions.

![](https://whitepapershealth.blob.core.windows.net/vscode/image13.png){width="6.28125in" height="2.46875in"}

You can also add TextMate snippets (.tmSnippets) to your Visual Studio
Code editor by using the [Yo
Code](https://code.visualstudio.com/docs/tools/yocode) extension
generator. You can use the **New Code Snippets** option in the generator
to gather some .tmSnippets files and create a snippet package of the
Visual Studio Code extension.

The generator creates two files: an extension manifest (package.json)
that has the metadata to integrate the snippets in Visual Studio Code,
and a file snippets.json that includes the Visual Studio Code
format-converted snippets.

.

├── snippets // VS Code integration

│   └── snippets.json // The JSON file w/ the snippets

└── package.json // extension's manifest

To use this extension, drag the generated folder to a new folder in the
Visual Studio Code extensions folder (.vscode/extensions) and restart
Visual Studio Code.

Azure Resource Manager Tools in Visual Studio Code
==================================================

You can use Visual Studio Code for manually creating resources for Azure
Resource Manager. To do this, you can use [an
extension](https://code.visualstudio.com/docs/editor/extension-gallery?pub=msazurermtools&ext=azurerm-vscode-tools)
that integrates into IntelliSense and everything related to Azure
resources. This helps you to easily create the template you want in
Visual Studio Code. For more information, see [Azure Resource Manager
Tools](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)
in the Visual Studio Marketplace.

![](https://whitepapershealth.blob.core.windows.net/vscode/image14.png)

Docker with Visual Studio Code
==============================

Visual Studio Code supports using extensions to create Docker-related
files. As with other extensions, press **F1** and type **ext install**
to run **Extensions: Install Extension**. This displays the list of
extensions that are available to use. If you also type **docker**, you
can filter results to find the extension [Dockerfile and Docker Compose
File (yml)
Support](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker).
Select the extension to install it. You might need to restart Visual
Studio Code for the changes to take effect.

![](https://whitepapershealth.blob.core.windows.net/vscode/image15.png)

This extension provides syntax highlighting, snippets, and other
Intellisense features to Dockerfiles and Docker Compose files.

Other suggested topics to explore
=================================

-   [Publishing to the
    Gallery](https://code.visualstudio.com/docs/tools/vscecli): Publish
    your own customization or extension to the Visual Studio
    Code Gallery.

-   [Yo Code](https://code.visualstudio.com/docs/tools/yocode): Learn
    how the Yo Code extension generator can scaffold out new extensions
    and package existing TextMate files.

-   [Extending Visual Studio
    Code](https://code.visualstudio.com/docs/extensions/overview): Start
    learning about Visual Studio Code extensibility.

-   [Your First
    Extension](https://code.visualstudio.com/docs/extensions/example-hello-world):
    Try creating a simple Hello World extension.

-   [User/Workspace
    Settings](https://code.visualstudio.com/docs/customization/userandworkspace):
    Learn how to configure Visual Studio Code to your preferences
    through user and workspace settings.

-   [Debugging](https://code.visualstudio.com/docs/editor/debugging):
    Learn how to debug your projects in Visual Studio Code.

-   [Azure Developer Tools](http://azure.com/tools): Learn more about
    the tools and find the recently released installers.

