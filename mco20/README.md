# MCO20: Azure Governance and Management

[![Learning Path](https://img.shields.io/badge/Learning%20Path-MCO-fe5e00?logo=microsoft)](https://github.com/microsoft/ignite-learning-paths-training-mco)


## Session Abstract
Tailwind Traders' deployments are ocuring in an ad hoc manner, primarily driven by lack of protocol and unapproved decisions by various operators or employees. Some deployments even violate the organization's compliance obligations, such as being deployed in a manner that violates PCI DSS rules. After bringing their existing IaaS VM fleet under control, Tailwind Traders  wants to ensure that future deployments comply with policy and organizational requirements. In this session, walk thruogh the processes and technologies that will keep Tailwind Trader's deployments in good standing with the help of Azure Blueprints, Azure Policy, Locks and more.


## Table of Content

| Resources          | Links                            |
|-------------------|----------------------------------|
| PowerPoint        | - [Presentation](presentations.md) |
| Videos            | - [Dry Run Rehearsal](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-RUNTHROUGH-1-NOV.mp4) <br/>- [Microsoft Ignite Orlando Recording](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO_20_IGNITE.mp4) |
| Demos             | - [Demo 1 - Resource Graph Explorer](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO1-RESOURCE-GRAPH.mp4) <br/>- [Demo 2 - Locks and Tags](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO2-LOCKS-TAGS.mp4) <br/>- [Demo 3 - Tag Remediation](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO3a-TAGS-REMEDIATION.mp4) <br/>- [Demo 4 - PCI DSS Audit](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO4-PCI-DSS-AUDIT.mp4) <br/>- [Demo 5 - PCI DSS Blueprints](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO5-PCI-DSS-BLUEPRINTS.mp4) |



## Session Story

In this session you’ll demonstrate how Tailwind Traders applied governance and management techniquest using the tools that are built into Azure. You’ll be using the fictional company “Tailwind Traders” as a narrative device. Tailwind Traders represents “everyone”. In this case they’ve deployed resources to the cloud, but they don’t have much understanding of what they need to do to ensure that those resources meet the organizations governance and compliance requirements.
- You’ll start the session by providing an overview of the elements of governance and management technologies available in Azure.
- You’ll move on to show in a demonstration how to locate resources in a sprawling set of Azure subscriptions by demonstrating Azure resource explorer and how the tool can be used to create dashboards.
- You’ll next show how to prevent the accidental deletion of critical resource by applying locks and tags.
- The next step is demonstrating how to automatically apply tags to resources that should be tagged but are currently without identifying information.
- You’ll then show attendees how to perform a PCI DSS audit against resources in an existing subscription.
- The final demonstration will allow you to show how to use blueprints to ensure that PCI DSS compliance rules are applied to new subscriptions.

Many organizations are like Tailwind Traders are unaware how technologies built into Azure can help them achieve compliance and governance objectives. In presenting this session you’ll help attendees understand how they can that it is their organization’s responsibility under the shared responsibility model to leverage the tools that are provided for them, and that Microsoft does not enable these features by default.

## How to use this repository

Welcome! 

We're glad you are here and look forward to your delivery of this amazing content. As an experienced presenter, we know you know HOW to present so this guide will focus on WHAT you need to present. It will provide you a full run-through of the presentation created by the presentation design team. 

Along with the video of the presentation, this document will link to all the assets you need to successfully present including PowerPoint slides and demo instructions &
code.

1.  Read document in its entirety.
2.  Watch the video presentation
3.  Ask questions of the Lead Presenter


## Get Started

This training repository is divided in to the following sections:

| **Slides** | [Demos](demos.md) |  
|-------------------|---------------------------|
| 32 slides  | 5 demos  |


### Deployment

Almost all sessoins can be performed from a trial Azure subscription. Instructions for configuring the subscription with specific assets such as Virtual Machines and resource groups can be found in the Demo/Lab instructions document linked above, often in the form of a script that can be run from Cloud Shell. 

### Demo Videos


- [Demo 1: Resource Graph Explorer](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO1-RESOURCE-GRAPH.mp4)
- [Demo 2: Locks and Tags](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO2-LOCKS-TAGS.mp4)
- [Demo 3: Tag Remediation](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO3a-TAGS-REMEDIATION.mp4)
- [Demo 4: PCI DSS Audit](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO4-PCI-DSS-AUDIT.mp4)
- [Demo 5: PCI DSS Blueprints](https://globaleventcdn.blob.core.windows.net/assets/mco/mco20/MCO-20-DEMO5-PCI-DSS-BLUEPRINTS.mp4)



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