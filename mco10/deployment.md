# Deployment

The labs associated with the MCO 10 Iaas VM Operations session can be completed in a trial Azure subscription. 

## Lab Deployment

With these preparation steps, you will deploy the necessary environment that will allow you to perform the demo exercises present in the MCO 10 videos.

1.	When signed in to a newly created Azure subscription, create the prime.admin account. Assign this account global administrator permissions. Make a note of the yoursubscription.onmicrosoft.com suffix and substitute where appropriate when running the setup code below.
2.	Navigate to portal.azure.com and sign into the demo Azure tenancy with the prime.admin@yoursubscription.onmicrosoft.com account.
3.	To create the VMs used in this session’s labs, open Cloud Shell and enter the following commands at the prompt, pressing Enter after each line:

    ```
    adminPassword=88Tailwind88Tailwind
    ```

    ```
    az group create --name TT-VMs --location southeastasia
    ```

    ```
    az storage account create \
        --name detritusephemera \
        --resource-group TT-VMs \
        --location southeastasia
    ```

    ```
    az network vnet create \
    --name TTVirtualNetwork \
    --resource-group TT-VMs \
    --address-prefixes 10.0.0.0/16
    ```

    ```
    az network vnet subnet create \
    --vnet-name TTVirtualNetwork \
    --resource-group TT-VMs \
    --name TTSubnet \
    --address-prefix 10.0.0.0/24 
    ```

    ```
    az vm create \
        --resource-group TT-VMs \
        --name TT-2019-A \
        --image win2019datacenter \
        --vnet-name TTVirtualNetwork \
        --subnet TTSubnet \
        --admin-username prime \
        --admin-password $adminPassword
    ```

    ```
    az vm create \
        --resource-group TT-VMs \
        --name TT-2019-B \
        --image win2019datacenter \
        --vnet-name TTVirtualNetwork \
        --subnet TTSubnet \
        --admin-username prime \
        --admin-password $adminPassword
    ```

    ```
    az vm create \
        --resource-group TT-VMs \
        --name TT-UBU-A \
        --image UbuntuLTS \
        --vnet-name TTVirtualNetwork \
        --subnet TTSubnet \
        --admin-username prime \
        --admin-password $adminPassword
    ```

    ```
    az vm create \
        --resource-group TT-VMs \
        --name TT-UBU-B \
        --image UbuntuLTS \
        --vnet-name TTVirtualNetwork \
        --subnet TTSubnet \
        --admin-username prime \
        --admin-password $adminPassword
    ```

4.	Use RDP to connect to TT-2019-A and open an elevated PowerShell prompt. Run the following commands:

    ```
    Set-executionpolicy bypass
    Iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
    choco install -y sql-server-express
    choco install -y sql-server-management-studio
    ```

5.	Open SQL Server Management Studio and connect to the local SQL Server Express instance.
6.	Right click on the Databases node, click New Database and enter the database name as TailwindTraders and click OK.
7.	Expand the Databases node, expand the TailwindTraders database, right click on the Tables node, click New and then click Table.  
8.	In the Column Name column, type Hovercraft
9.	In the Data Type column, accept the default as nchar(1)
10.	Right click on the tab and click Save Table_1
11.	On the Enter a name for the table page, type Hovercraft_Inventory and click OK

