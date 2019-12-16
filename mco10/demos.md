# Demos

---


## Demo 1 - Azure Bastion

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure Azure Bastion and use it to connect to a virtual machine running in your subscription. To complete this demonstration, perform the following steps:

1.	Sign on to the Azure portal with the prime.admin account.
2.	In the Favorites area, lick Virtual Networks.
3.	In the list of virtual networks, click TTVirtualNetwork.
4.	On the TTVirtualNetwork page, click Subnets and then click +Subnet
5.	On the Add subnet page, provide the following information and click OK:
	- Name: AzureBastionSubnet
	- Address range: 10.10.1.0/24
6.	Click +Create a Resource
7.	In the Search the Marketplace search bar, type Bastion and press Enter.
8.	In the list of results, click on Bastion by Microsoft.
9.	On the Bastion page, click Create.
10.	On the Create a bastion page, configure the following settings:
	- Resource Group: TT-VMs
	- Name: TT-BASTION
	- Region: Southeast Asia.
	- Virtual Network: TTVirtualNetwork
	- Subnet: AzureBastionSubnet
	- Public IP address: Create New
	- Public IP address name: TTVirtualNetwork-vnet-ip
11.	Click Review and Create and then click Create.
12.	When the deployment completes, click on Virtual Machines under Favorites.
13.	Click on TT-2019-A
14.	Click Connect
15.	On the Connect to virtual machine dialog, click Bastion
16.	Enter the following information and click Connect.
	- Username: prime
	- Password: 88Tailwind88Tailwind
17.	Verify that you have been signed in to the VM through the browser.
18.	Keep the browser window open for the next demo.


---


## Demo 2 - Just In Time Access

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure Just In Time Access to an Azure IaaS VM. To complete this demonstration, perform the following steps:

1.	Sign on to the Azure portal with the prime.admin account.
2.	In the Search bar, type Security Center and then click on Security Center.
3.	In the Azure Security Center page, click on Just In Time VM Access under Advanced Cloud Defense.
4.	In the list of VMs, click Recommended
5.	Select TT-2019-A and TT-2019-B and then click Enable JIT on 2 VMs.
6.	On the JIT VM Access Configuration page, remove all ports except port 3389 by clicking on the ellipsis (…) and then clicking Delete.
7.	Click on port 3389. On the Add port configuration page, set the Max Request Time to 10 hours. Click OK and then click Save.
8.	On the Just in time VM Access page, ensure that Configured is selected. Enable the checkbox next to TT-2019-B and click Request Access.
9.	On the Request Access page, click On for port 3398 and My IP for Allowed Source IP and then click Open Ports.
10.	Once the JIT network access request is processed, click the virtual machines item in the list of favorites, click on TT-2019-B and on the overview page, click Connect. You will now only be able to make an RDP connection to this virtual machine once you have requested access through JIT. The current access window will remain open for the next 10 hours.
11.	Keep the browser window open for the next demo.


---


## Demo 3 & 4 - Azure IaaS VM and SQL Backup and Recovery

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will backup and recover both an Azure IaaS VM and a SQL Server instance running in an IaaS VM. To complete this demonstration, perform the following steps:

1.	Sign on to the Azure portal with the prime.admin account.
2.	In the Search bar, type Recovery Services vaults.
3.	In the Recovery Services Vaults page, click Add.
4.	On the Create Recovery Services Vault page, provide the following information:
	- Resource Group: TT-VMs
	- Vault Name: TT-VM-RSV
	- Region: Southeast Asia.
5.	Click Review and Create and then click Create.
6.	Click on Recovery Services Vaults in the list of Favorites and then click on TT-VM-RSV.
7.	On the TT-VM-RSV page, click Backup.
8.	On the Backup page, configure the following settings and then click Backup:
	- Where is your workload running? Azure
	- What do you want to backup? Virtual machine
9.	On the Backup Policy page, click Create New, configure the following settings, leave other settings at their default value, and then click OK.
	- Policy name: TTBackupVMPolicy
	- Schedule: Daily, 12:00am, Canberra/Melbourne/Sydney
	- Retain instant recovery snapshots for 5 days.
10.	On the Select Virtual Machines page, select TT-2019-B, TT-UBU-A, and TT-UBU-B and then click OK.
11.	Click Enable Backup.
12.	With TT-VM-RSV selected, click Backup 
13.	On the Backup page, configure the following settings and then click Start Discovery:
	- Where is your workload running? Azure
	- What do you want to backup? SQL Server in Azure VM.
14.	On the Select Virtual Machines page, select TT-2019-A and then click Discover DBs.
15.	On the Backup page, click Configure Backup.
16.	Expand the tt-2019-A\SQLEXPRESS instance and select the master, model, msdb, and TailwindTraders databases then click OK.
17.	Accept the default backup policy settings and then click OK. Click Enable backup.
18.	Click on the Recovery Services vaults item in the Favorites bar and then click on TT-VM-RSV.
19.	Under Protected Items, click Backup items.
20.	Click Azure Virtual Machine.
21.	Click on each VM in the list, click Backup Now, accept the default retention date and then click OK.
22.	Repeat this for the Azure SQL backup items listed in the SQL in Azure VM section by clicking on the ellipsis (…) next to each database and clicking Backup Now.
23.	Keep the browser open.
24.	Make and RDP connection to TT-2019-A and sign in using the username **prime** and the password **88Tailwind88Tailwind**.
25.	Open SQL Server Management studio and connect to the default instance.
26.	Expand the TailwindTraders Database, expand the Tables node, right click on dbo.Hovercraft_Inventory and then click Delete. Click OK.
27.	Keep the RDP connection to TT-2019-A open and switch back to the browser.
28.	In the Azure Console, in the Backup Items list in the TT-VM-RSV, click SQL in Azure VM.
29.	Click the ellipsis (…) next to tailwindtraders and then click Restore DB.
30.	On the Restore Configuration page, select Alternate location. Accept the default values and then click OK.
31.	On the Select restore point page, select the most recent restore point and then click OK.
32.	On the Advanced Configuration page, click OK again. Click Restore.
33.	Switch back to the RDP connection to TT-2019-A.
34.	In the SQL Server Management Studio window, right click on Databases and click Refresh.
35.	Verify that the restored database is now present and that the dbo.Hovercraft_Inventory table is present in the restored database.
36.	Switch back to the browser.
37.	In the Azure Console, in the Backup Items list in the TT-VM-RSV, click Azure Virtual Machine.
38.	In the list of VMs, click the ellipsis (…) next to TT-UBU-A and click Restore VM.
39.	On the Select Restore Point page, select the most recent file consistent backup and click OK.
40.	On the Restore Configuration page, click Create New and provide the following information and click OK:
	- Restore type: Create Virtual Machine
	- Virtual Machine Name: TT-UBU-RESTORE
	- Resource group: TT-VMs.
	- Virtual network: TTVirtualNetwork
	- Subnet: TTSubnet
	- Storage Account: detritusephemera
41.	Click Restore.
42.	Click Activity Log to view the restore operation.
43.	Click on the Virtual Machines section in the Favorites and verify that TT-UBU-RESTORE is now present and running.


---


## Demo 5 - Azure Update Management

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure and manage Azure Update Management to ensure that IaaS VMs are kept up to date. To complete this demonstration, perform the following steps:

1.	Ensure that you are signed in to the Azure portal with the prime.admin account.
2.	Click on the Virtual Machines item in the Favorites pane and then click on TT-2019-A.
3.	In the TT-2019-A blade, click Update Management under Operations.
4.	On the Update Management page, ensure that Enable for this VM is selected and then click Enable. Accept the default settings for Log Analytics workspace and automation account.
5.	After update management has been enabled, view the list of missing updates for the VM. The updates that are missing will depend on when the VM image was deployed and updates that are available at the point in time you perform the demonstration.
6.	Click on the Virtual Machines node and then click on TT-UBU-A.
7.	In the TT-UBU-A blade, click **Update Management** under Operations.
8.	On the Update Management page, click Enable for VMs in this subscription and then click **Click to select machines to enable**.
9.	Enable the checkbox next to the following VMs:
	- TT-2019-B
	- TT-UBU-A
	- TT-UBU-B
10.	Click Enable.
11.	Click the Virtual Machines blade
12.	Click TT-2019-A
13.	Click Update Management under Operations.
14.	Click Schedule Update Deployment.
15.	In the New Update Deployment page, provide the following information, keeping other settings at their default values:
	- Name: TT-2019-A-Update
	- Update Classifications: Select All
	- Schedule settings: Set a time approximately 15 minutes in the future from when you are presenting the demo. Recurrence: Once.
16.	Click Create.
17.	In the Update Management page, click Deployment Schedules and verify that the update deployment is currently scheduled.
18.	Click Manage Multiple Machines.
19.	Click Missing Updates and review which updates are missing for the Linux VMs.
20.	Click Schedule update deployment.
21.	On the New Update Deployment page, provide the following information, keeping other settings at their default values and click Create:
	- Name: TT-Ubuntu-UpdateRun
	- Operating System: Linux
	- Machines to Update: TT-UBU-A, TT-UBU-B.
	- Schedule settings: Set a time approximately 15 minutes in the future from when you are presenting the demo. Recurrence: Recurring. Recur every 1 week on Tuesday.
22.	Review the deployment schedules.
23.	Return to the console after approximately 60 minutes and use the Missing Updates tab to determine whether any Linux related updates are still missing from IaaS VMs. Some updates for Windows IaaS VMs will be listed as missing because TT-2019-B was not subject to an update deployment.
24.	Keep the browser window open for the next demonstration.


---


## Demo 6 - Inventory and change tracking.

> 💡 You must have completed the [deployment](deployment.md) before attempting to do the demo.

Introduction. In this demonstration, you will configure inventory and change tracking. To complete this demonstration, perform the following steps:

1.	Ensure that you are signed into the Azure portal with the prime.admin account.
2.	In the Favorites pane, click Virtual Machines.
3.	Click TT-2019-A and then click Inventory under Operations.
4.	Click Enable for this VM and use the default settings for location and log analytics workspace. Click Enable.
5.	Click on Virtual Machines.
6.	Click TT-2019-B and then click Inventory under Operations.
7.	Click Enable for VMs in this subscription.
8.	Click **Click to select machines to enable**.
9.	On the Inventory page, ensure that the checkbox next to TT-2019-B, TT-UBU-A and TT-UBU-B are selected and click Enable.
10.	Click the Virtual Machines node
11.	Click on TT-2019-A
12.	Click Connect
13.	On the Connect to virtual machine dialog, click Bastion
14.	Enter the following information and click Connect.
	- Username: prime
	- Password: 88Tailwind88Tailwind
15.	From an elevated PowerShell prompt type the following:
    ```
    Choco install firefox -y
    ```
16.	Run the newly installed Firefox.
17.	Return to the Azure console.
18.	Ensure that TT-2019-A is still selected and click Change Tracking.
19.	Review the changes and note that the installation of Mozilla Firefox has been detected.
20.	Click on Virtual Machines.
21.	Click on TT-UBU-A.
22.	Click on Networking and note the NIC Private IP.
23.	Open Cloud Shell and type the following commands, pressing Enter after each and providing the password 88Tailwind88Tailwind when prompted:
    ```
    Ssh prime@NIC.Private.IP.Address  
    #Provide Password 88Tailwind88Tailwind
    Sudo apt-get -y update
    Sudo apt-get -y install nginx
    ```
24.	Close Cloudshell.
25.	On the Inventory page on TT-UBU-A search for nginx. This will verify that the installation of this package has been recorded.

