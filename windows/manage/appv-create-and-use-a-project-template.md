---
title: How to Create and Use a Project Template (Windows 10)
description: How to Create and Use a Project Template
author: MaggiePucciEvans
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
---


# How to Create and Use a Project Template

**Applies to**
-   Windows 10, version 1607

You can use an App-V project template to save commonly applied settings associated with an existing virtual application package. These settings can then be applied when you create new virtual application packages in your environment. Using a project template can streamline the process of creating virtual application packages.

> **Note**&nbsp;&nbsp;You can, and often should apply an App-V project template during a package upgrade. For example, if you sequenced an application with a custom exclusion list, it is recommended that an associated template is created and saved for later use while upgrading the sequenced application.

App-V project templates differ from App-V Application Accelerators because App-V Application Accelerators are application-specific, and App-V project templates can be applied to multiple applications.

Use the following procedures to create and apply a new template.

**To create a project template**

1.  To start the App-V sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.

    > **Note**&nbsp;&nbsp;If the virtual application package is currently open in the App-V Sequencer console, skip to step 3 of this procedure.

2.  To open the existing virtual application package that contains the settings you want to save with the App-V project template, click **File** / **Open**, and then click **Edit Package**. On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open. Click **Edit**.

3.  In the App-V Sequencer console, to save the template file, click **File** / **Save As Template**. After you have reviewed the settings that will be saved with the new template, click **OK**. Specify a name that will be associated with the new App-V project template. Click Save.

    The new App-V project template is saved in the folder you specified.

**To apply a project template**

> **Important**&nbsp;&nbsp;Creating a virtual application package using a project template in conjunction with a Package Accelerator is not supported.

1.  To start the App-V sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.

2.  To create or upgrade a new virtual application package by using an App-V project template, click **File** / **New From Template**.

3.  To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.

    Create the new virtual application package. The settings saved with the specified template will be applied to the new virtual application package that you are creating.

## Have a suggestion for App-V?

Add or vote on suggestions on the [Application Virtualization feedback site](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).<br>For App-V issues, use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=mdopappv).

## Related topics

[Operations for App-V](appv-operations.md)
