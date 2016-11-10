---
localizationpriority: low
ms.mktglfcycl: deploy
description: How to fix potential installation problems with Internet Explorer 11
author: eross-msft
ms.prod: ie11
ms.assetid: 3ae77745-86ac-40a9-a37d-eebbf37661a3
title: Install problems with Internet Explorer 11 (Internet Explorer 11 for IT Pros)
ms.sitesec: library
---


# Install problems with Internet Explorer 11
Most Internet Explorer 11 installations are straightforward and work the way they should. But it's possible that you might have problems.

If you do, you can:

-   Check that you meet the minimum operating system requirements and have the prerequisites installed.

-   Check that there are no other updates or restarts waiting.

-   Temporarily turn off your antispyware and antivirus software.

-   Try another IE11 installer. For example from [Windows Update](https://go.microsoft.com/fwlink/p/?LinkId=302315) or from the [Download Internet Explorer 11](https://go.microsoft.com/fwlink/p/?linkid=327753) website.

-   Make sure you use the same download server URLs that you entered during the Setup process.

-   Review the `IE11_main.log` file in the `\Windows` folder. This log file has information about each installation and is appended for each subsequent installation.

- If you find that the 'IE11_main.log' shows the following error:
ERROR:   Neutral package installation failed (exit code = 0x00000003 (3)).

Please follow the steps below to install Internet Explorer 11.

Step 0. Open an elevated Command Prompt and copy (without the quotes '') the following: 
‘mklink /D c:\Windows\SysNative c:\Windows\system32’ 

Step 1. Download the offline installer of IE11 from Microsoft, run the IE11 installer and wait until it gets to the ‘Install Internet Explorer 11’ prompt. DO NOT close this window.

Step 2. Go into ‘C:\Windows\temp’ and look for the most recently created folder with ‘IE’ at the beginning of it’s name. E.g. ‘IE1CF18.tmp’.

Step 3. Go into that folder and verify that you can see the following two .cab files: 
‘IE11-neutral.Downloaded.cab’ and ‘IE11-neutral.Extracted.cab’. If you do, then carry onto the next step. If you don’t, then go back a level and try one of the other similarly named folders.

Step 4. Use that folder name to create the path for the .cab files to be installed from in the next step. E.g.: C:\Windows\temp\IE1CF18.tmp

Step 5. Now, substituting the example path with the one you determined in the last step, run an elevated Command Prompt and enter the following commands in the order listed:
dism.exe /online /add-package /packagepath:C:\Windows\temp\IE1CF18.tmp\IE11-neutral.Extracted.cab /quiet /norestart
dism.exe /online /add-package /packagepath:C:\Windows\temp\IE1CF18.tmp\IE11-neutral.Downloaded.cab /quiet /norestart

Step 6. When done, return to the ‘Install Internet Explorer 11’ prompt and click ‘Install’. With a bit of luck it should successfully install.

-  If by any chance you get the following error message using dism:
C:\Windows does not appear to be a valid Windows directory

You will have to move the 10.0.xxx folder in C:\Windows\servicing\Version\ to your Desktop and run dism after.

You may have to take ownership of the folder to move it. 

To Modify File/Folder Permissions of the correct folder, follow the steps below: 

Step 1. Go to C:\Windows\servicing\Version\ 
Step 2. Find the folder that starts with '10.0.xxxx.xxx' E.g.: 10.0.14393.0
Step 3. Right click the '10.0.xxx' folder
Step 4. Under the Security tab, click Advanced.
Step 5. Under the Owner tab, click Edit.
Step 6. Click "Other Users and Groups".
Step 7. Click Advanced.
Step 8. Click "Find Now".
Step 9. Scroll down and double click on Everyone.
Step 10. Click OK THREE times.
Step 11. Click on the Permissions tab.
Step 12. Under type Deny, single click on any entries and click Remove. (There may not be any Deny entries, in which case just ignore this step. Just remove any that do exist)
Step 13. Click OK.
Step 14. Click Edit (now on the standard file Property window under the Security tab).
Step 15. Click Add.
Step 16. Click Advanced.
Step 17. Click "Find Now".
Step 18. Scroll down and double click on Everyone.
Step 19. Click OK.
Step 20. Single click on Everyone and then tick the "Full Control" box under Allow.
Step 21. Click OK TWO times.

You're done. Now move the folder to your desktop and then run dism. 


## Internet Explorer didn't finish installing
If Internet Explorer doesn't finish installing, it might mean that Windows Update wasn't able to install an associated update, that you have a previous, unsupported version of IE installed, or that there's a problem with your copy of IE. We recommend you try this:

 ![](images/wedge.gif) **To fix this issue**

1.  Uninstall IE:

    1.  In the Control Panel, open the **Programs and Features** box, scroll down to IE11, and then click **Uninstall**.

    2.  After the uninstall finishes, restart your computer.

2.  Run [Windows Update](https://go.microsoft.com/fwlink/p/?LinkId=302315), clicking **Check for updates**.

3.  Check the list for IE11. If it's included in the list of updates for download, exclude it before you update your computer.<p>
If you get an error during the Windows Update process, see [Fix the problem with Microsoft Windows Update that is not working](https://go.microsoft.com/fwlink/p/?LinkId=302316).

4.  Restart your computer, making sure all of your the updates are finished.

5.  Try to reinstall IE11 from either Windows Update (if you saw it in Step 3) or from the [Download Internet Explorer 11](https://go.microsoft.com/fwlink/p/?linkid=327753) website.

If these steps didn't fix your problem, see [Troubleshooting a failed installation of Internet Explorer 11](https://go.microsoft.com/fwlink/p/?LinkId=304130).

 

 



