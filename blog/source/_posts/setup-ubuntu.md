---
title: Set Up Ubuntu
---
# Ubuntu Set-Up Guide


<img src="./images/ubuntu-logo.png" alt="Ubuntu Logo" width="150" />

***

## WSL2 Set-Up Tutorial for Windows
WSL: Windows Subsystem for Linux
### What you will need beforehand: 
- Windows 10/11 on virutal or physical machine
- Windows updated to most recent version

**1. Installing WSL2**
- The first step to installing Ubuntu on your machine is installing WSL2 on your computer. WSL2 stands for Windows Subsystem for Linux, and it allows you to run a Linux environment on your computer without having to have a separate virtual machine.
- To install WSL2, you have to open Windows Terminal on your device as an adminstrator. Then enter <code> wsl --install </code>. 
- Once it has installed, you must restart your device.
  
**2. Installing Ubuntu**
The second step for installing Ubuntu is installing a version of Ubuntu onto WSL. We will be using a method that allows you to install Ubuntu from the command line. 
- First, you must open Windows Terminal and enter <code> wsl --list --online </code> to see on the available versions of Ubuntu that you are able to install.
- Once you have found the version that you like, you must type the name of the version that you want and then enter the following: <code> wsl --install -d (name of installation) </code>
- If successful, you will see a progress bar appear showing that the installation is in progress.

**3. Running Ubuntu**
The final step for installing Ubuntu is running it on your machine and making sure it is functional. 
- To do that, you must open Powershell terminal and type in the version of Ubuntu you installed, for example: <code> ubuntu2404.exe </code>
- The Ubuntu terminal should start running, and if it has, then you have successfully installed Ubuntu!
- Once it is installed, the system will prompt you to create a username and password. Make sure to write the username and password somewhere secure so then if you forget your information, you are able to retrieve it.
- Optionally, you should also run updates for your Ubuntu terminal to make sure that it is up to date. You can run updates by entering the following:
<code> sudo apt update </code>
<code> sudo apt full-upgrade -y </code>
- It will prompt you to enter your password for the updates.

### After following these steps, you should have a fully functional Ubuntu system on your machine!
***


## Virtual Box Set-Up (macOS and Windows)
<img src="./images/virtualbox-logo.png" alt="VirtualBox Old Logo Logo" height="150" /> <img src="./images/virtualbox-logo-2024.png" alt="VirtualBox New 2024+ Logo" height="150" />
### Initial Set-Up
1. [Download Oracle Virtual Box](https://www.virtualbox.org/wiki/Downloads) for the machine you are currently using (e.g. MacBook would download the macOS package)
2. [Download Ubuntu [22.04.5 LTS (Jammy Jellyfish)]](https://releases.ubuntu.com/jammy/)
    - Select the image required. If unsure, download the **Desktop Image**
    - If you need both, you can always add server packages to a Desktop Image, and vice versa, so the order does not matter

### Set Up Ubuntu in Virtual Box
When you open your Oracle VM Virtual Box, it will look like this:

![Screenshot of Oracle VM Virtual Box, with no Virtual Machines (VMs) yet](./images/blank-virtual-box.png)


1. Click **'New'** to create a new Virtual Machine (VM)
First, you will choose and name your VM.

![Screenshot of Oracle VM Virtual Box new VM, first screen](./images/vm-setup-1.png)

  - **Name**: This is where you add an identifiable name/nickname for your VM
  - **Folder/Machine Folder**: This is where you select your VM's location. You can choose any location that has enough space
  - **ISO Image**: If this field is available, you may select the Ubuntu image that you downloaded in the previous steps, and it will automatically set the **Type** and **Version** for you. If not, continue to:
  - **Type**: This is where you select the desired OS for your VM. Choose **'Linux'**
  - **Version**: This is where you select the version of your OS. Choose **'Ubuntu (64-bit)'**
      
  Click **'Next'**

2. a. You may or may not get get a "Unattended Guest OS Install Setup" screen
   
![Screenshot of Oracle VM Virtual Box new VM, first screen](./images/vm-setup-2.png)
- If you get this screen, you may click **'Next'**
- Note: by default, username is **"vboxuser"** and password is **"changeme"**

2. b. Hardware / Memory Size
A portion of your machine's resources will be dedicated to the VM.

![Screenshot of Oracle VM Virtual Box Hardware setup page](./images/vm-setup-3.png)
- You may have different options depending on your machine
- For allocating resources, choose the highest amount possible within the green "reccomendation" zone
  
  Click **'Next'**

3. Virtual Hard Disk + location and size
- Select **'Create a Virtual Hard Disk Now'**
- If asked for a hard disk type, choose any
- If asked, leave default **'Dynamically allocated'** over **Fixed size**
- Choose **30.00 GB** as the maximum amount of file data that the VM may store on the hard drive

![Screenshot of Oracle VM Virtual Box new VM, first screen](./images/vm-setup-4.png)

  Click **'Next'**

4. Click **'Create'** or **'Finish'** to complete your new Ubuntu VM!
