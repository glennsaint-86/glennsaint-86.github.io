---
layout: single
title:  "Windows Sandbox"
date:   2022-10-18 02:06:44 +0800
categories: blog
toc: true
toc_sticky: true
tags: Windows-Sandbox sandbox testing disposable-vm
#permalink:
published: true
---
Starting with Windows 10 Pro or Enterprise edition or later, there is a Windows Features called Windows Sandbox in which can be used to test untested software applications or installer that run on Windows PC / laptop.

Windows Sandbox is an ephemeral or disposable VM (virtual machine), any software installation / configuration made inside the Sandbox will be gone when the host PC is shutdown.  Only one running instance is allowed to run. Every time a Windows Sandbox is run, it is consider as a fresh or clean state.

# Enabling Windows Sandbox Feature
1. Click on Window Search 
2. Type-in Turn on Windows Features on or off, scroll down and look for Windows Sandbox.
3. Check the Windows Sandbox feature and click OK to continue<br/>
    
    ![windows sandbox feature](/assets/images/windows-sandbox-01.png)

4. Click on restart button when a dialog pop-up to Restart the PC / laptop in order the changes to take effect. 

# Creating configuration file for Windows Sandbox
1. Create a configuration file for the windows sandbox. Open your favorite text editor, copy and paste the following code below and save the file. Choose whatever filename you desire as long as the file extension is `.wsb`.
    ```
    <Configuration>
    </Configuration>
    ```
5. Once the file is saved, open the file in File Explorer and viola you have your Windows Sandbox running, see below for a sample screenshot<br/>

    ![windows sandbox](/assets/images/windows-sandbox-02.png)


# What's next?
* If you are a tech hobbyist trying new applications in Windows or QA / Test software engineer, Windows Sandbox comes in handy.   
* There are several configurations that can be made on a Windows Sandbox, most common that are being used are: vGPU (virtual GPU) and sharing of a host folder to the sandbox environment. To know more about the configuration setup see [Windows Sandbox Configuration](https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-configure-using-wsb-file)
* To know more about Windows Sandbox see, [Windows Sandbox Overview](https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview)



 