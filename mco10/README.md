# MCO10: IaaS VM Operations

[![Learning Path](https://img.shields.io/badge/Learning%20Path-MCO-fe5e00?logo=microsoft)](https://github.com/microsoft/ignite-learning-paths-training-mco)


## Session Abstract

In recent months, Tailwind Traders has been having issues with keeping their sprawling IaaS VM deployment under control, leading to mismanaged resources and inefficient processes. In this session, look into how Tailwind Traders can ensure their VMs are properly managed and maintained with the same care in Azure as they were in Tailwind Trader's on-premises data centers.


## Table of Content

| Resources          | Links                            |
|-------------------|----------------------------------|
| PowerPoint        | - [Presentation](presentations.md) |
| Videos            | - [Dry Run Rehearsal](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/MCO-10-RunThrough.mp4) <br/>- [Microsoft Ignite Orlando Recording](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/MCO_10_IGNITE.mp4) |
| Demos             | - [Demo 1 - Azure Bastion](https://github.com/microsoft/ignite-learning-paths-training-mco/blob/master/mco10/demos.md#demo-1---azure-bastion) <br/>- [Demo 2 - JIT VM Access](https://github.com/microsoft/ignite-learning-paths-training-mco/blob/master/mco10/demos.md#demo-2---just-in-time-access) <br/>- [Demo 3 & 4 - Azure Backup VM & SQL](https://github.com/microsoft/ignite-learning-paths-training-mco/blob/master/mco10/demos.md#demo-3--4---azure-iaas-vm-and-sql-backup-and-recovery) <br/>- [Demo 5 - Update Management](https://github.com/microsoft/ignite-learning-paths-training-mco/blob/master/mco10/demos.md#demo-5---azure-update-management) <br/>- [Demo 6 - Inventory and Change Tracking](https://github.com/microsoft/ignite-learning-paths-training-mco/blob/master/mco10/demos.md#demo-6---inventory-and-change-tracking) |


## How to use this repository

Welcome! 

We're glad you are here and look forward to your delivery of this amazing content. As an experienced presenter, we know you know HOW to present so this guide will focus on WHAT you need to present. It will provide you a full run-through of the presentation created by the presentation design team. 

Along with the video of the presentation, this document will link to all the assets you need to successfully present including PowerPoint slides and demo instructions &
code.

1.  Read document in its entirety.
2.  Watch the video presentation
3.  Ask questions of the Lead Presenter



## Session Story

In this session you’ll demonstrate how Tailwind Traders was able to perform traditional virtual machine management tasks using the tools that are built into Azure. You’ll be using the fictional company “Tailwind Traders” as a narrative device. Tailwind Traders represents “everyone”. In this case they’ve deployed virtual machines to the cloud, but they don’t have much understanding of what they need to do to perform traditional VM management tasks with those resources. They have assumed, incorrectly, that by deploying a VM to the cloud, all of the traditional things, like VM backup and operating system updates are automatically taken care of for them by Microsoft.

- You’ll start the session by providing a reminder about the shared responsibility model. You do this to contextualize the session and to remind the audience that while the security of the underlying fabric and infrastructure is Microsoft’s responsibility, the management and security of the IaaS VM workloads that organizations deploy to Azure is the responsibility of the subscription owner. In other words, Tailwind Traders has it wrong and Microsoft doesn’t handle things such as automatically backing up their VMs and applying software updates as they become available.
- You’ll move on to showing attendees how Tailwind Traders was able to allow secure administrative connections to VMs running in their subscription without allowing access to any RDP or SSH client on the internet. You’ll demonstrate how secure connections can be made without a VPN to an IaaS VM that does not have a public IP address using Bastion and how Just In Time VM access is configured and functions. This solves a problem Tailwind Traders has where some administrators opened up RDP and SSH to every host on the internet.
- You’ll next show how the native backup and recovery functionality of Azure can be enabled to allow Tailwind Traders to automatically backup and recover entire VMs. You’ll also show how this functionality can be leveraged to backup and recover SQL instances running within VMs. This allows Tailwind Traders to recover VMs and SQL databases in the event of data corruption or other problems.
- The next step is demonstrating how you can configure and manage software updates for both Tailwind Trader’s Windows and Linux virtual machines running in Azure. This will allow Tailwind Traders to be sure that their VMs are as secure as possible when it comes to software updates.
- You’ll then show attendees how Tailwind Traders was able to ensure that changes made to virtual machines, such as the installation of applications and packages, can be tracked by enabling Inventory and Change Tracking. This allows Tailwind Traders to be notified if unusual software is deployed within their VMs.

Many organizations are like Tailwind Traders and assume that because they have heard the functionality to do things like automatically back up virtual machines and apply software updates exists within Azure, it is turned on by default. In presenting this session you’ll help attendees understand that it is their organization’s responsibility under the shared responsibility model to leverage the tools that are provided for them, and that Microsoft does not enable these features by default.


## Get Started

This training repository is divided in to the following sections:

| **Slides** | [Demos](demos.md) | [Deployment](deployment.md) | 
|-------------------|---------------------------|--------------------------------------
| 34 slides  | 6 demos  | 1 deployment process

- [Director's Cut of Presentation](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/MCO-10-Director-Cut.mp4)



## Deployment

Almost all sessions can be performed from a trial Azure subscription. Instructions for configuring the subscription with specific assets such as Virtual Machines and resource groups can be found in the Demo/Lab instructions document linked above, often in the form of a script that can be run from Cloud Shell. 



## Demo Videos

- [Demo 1: Create VM using CloudShell](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-01-CREATE-VM-CLOUDSHELL.mp4)
- [Demo 2: Azure Bastion](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-02-Bastion.mp4)
- [Demo 3: JIT VM RDP](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-03-JIT-VM-RDP.mp4)
- [Demo 4: PS Remoting from CloudShell](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-04-PS-Remoting-CloudShell.mp4)
- [Demo 5: Backup VM & SQL Server](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-05-Backup-VM-SQLServer.mp4)
- [Demo 6: Recover VM & SQL Database](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-06-Recover-VM-SQLDatabase.mp4)
- [Demo 7: Resize VM](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-07-RESIZE-VM.mp4)
- [Demo 8: Update Management](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-08-Update-Management.mp4)
- [Demo 9A: VM Password Reset](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-09A-VM-PASSWORD-RESET.mp4)
- [Demo 9B: Inventory & Change Tracking](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-09B-Enable-Inventory-Change-Tracking.mp4)
- [Demo 9C: VM Auto Shutdown](https://globaleventcdn.blob.core.windows.net/assets/mco/mco10/DEMO-09C-VM-AUTO-SHUTDOWN.mp4)



## Become a Trained Presenter

You don't need anything to present this content, it's all there to be used. However, by becoming a *Trained Presenter* the scalable content team will recognize you as well. *Trained Presenter* see their contact information (name, picture, website) in the bottom of each session.  
 
To become a *Trained Presenter*, contact [scalablecontent@microsoft.com](mailto:scalablecontent@microsoft.com). In your email please include:

- Complete name:
- The code of this presentation: \<Session Code (ex:MCO10)\>
- Link to an unlisted YouTube video of you presenting around 10 minutes of the content for this specific session.


## Trained Presenters

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->

<table>
<tr>
    <td align="center"><a href="http://orinthomas.com">
        <img src="https://avatars1.githubusercontent.com/u/44561273?s=460&v=4" width="100px;" alt="Orin-Thomas"/><br />
        <sub><b>Orin-Thomas</b></sub></a><br />
            <a href="https://github.com/microsoft/ignite-learning-paths-training-afun/commits?author=Orin-Thomas" title="talk">📢</a>
            <a href="https://github.com/microsoft/ignite-learning-paths-training-afun/commits?author=Orin-Thomas" title="Documentation">📖</a> 
    </td>
</tr></table>

<!-- ALL-CONTRIBUTORS-LIST:END -->
