---
wts:
    title: '01 - Create a virtual machine in the portal (10 min)'
    module: 'Module 02 - Core Azure Services (Workloads)'
---
# 01 - Create a virtual machine in the portal

In this walkthrough, we will create a virtual machine in the Azure portal, connect to the virtual machine, install the web server role and test. 

**Note**: Take time during this walk-through to click and read the Informational icons. 

# Task 1: Create the virtual machine (10 min)

1. Sign-in to the Azure portal: **https://portal.azure.com**

3. From the **All services** blade in the Portal Menu, search for and select **Virtual machines**, and then click **+Add, +Create, +New** and choose **+Virtual machine** from the drop down.

4. On the **Basics** tab, fill in the following information (leave the defaults for everything else):

    | Settings | Values |
    |  -- | -- |
    | Subscription | **Use default supplied** |
    | Resource group | **Use default in drop down** |
    | Virtual machine name | **myVM** |
    | Region | **(US) East US**|
    | Image | **Windows Server 2019 Datacenter - Gen1**|
    | Size | **Standard D2s v3**|
    | Administrator account username | **azureuser** |
    | Administrator account password | **Pa$$w0rd1234**|
    | Inbound port rules - | **Allow select ports **|
    | Select inbound ports | **RDP (3389)** and **HTTP (80)**| 

5. Switch to the Networking tab to ensure **HTTP (80) and RDP (3389)** are selected in section **Select inbound ports**.

6. Switch to the Management tab, and in its **Monitoring** section, select the following setting:

    | Settings | Values |
    | -- | -- |
    | Boot diagnostics | **Disable**|

7. Leave the remaining values on the defaults and then click the **Review + create** button at the bottom of the page.

8. Once Validation is passed click the **Create** button. It can take anywhere from five to seven minutes to deploy the virtual machine.

9. You will receive updates on the deployment page and via the **Notifications** area (the bell icon in the top menu bar).

# Task 2: Connect to the virtual machine

In this task, we will connect to our new virtual machine using RDP (Remote Desktop Protocol). 

1. Search for **myVM** and select your new virtual machine.

    **Note**: You could also use the **Go to resource** link on the deployment page or the link to the resource in the **Notifications** area.

2. On the virtual machine **Overview** blade, click **Connect** button and choose **RDP** from the drop down.

    ![Screenshot of the virtual machine properties with the Connect button highlighted.](../images/0101.png)

    **Note**: The following directions tell you how to connect to your VM from a Windows computer. On a Mac, you need an RDP client such as this Remote Desktop Client from the Mac App Store and on a Linux computer you can use an open source RDP client.

2. On the **Connect to virtual machine** page, keep the default options to connect with the public IP address over port 3389 and click **Download RDP File**. A file will download on the bottom left of your screen.

3. **Open** the downloaded RDP file (located on the bottom left of your lab machine) and click **Connect** when prompted. 

    ![Screenshot of the virtual machine properties with the Connect button highlighted. ](../images/0102.png)

4. In the **Windows Security** window, sign in using the Admin Credentials you used when creating your VM **azureuser** and the password **Pa$$w0rd1234**. 

5. You may receive a warning certificate during the sign-in process. Click **Yes** or to create the connection and connect to your deployed VM. You should connect successfully.

    ![Screenshot of the Certificate warning dialogue informing the user of an untrusted certificate, with the Yes button highlighted. ](../images/0104.png)

A new Virtual Machine (myVM) will launch inside your Lab. Close the Server Manager and dashboard windows that pop up (click "x" at top right). You should see the blue background of your virtual machine. **Congratulations!** You have deployed and connected to a Virtual Machine running Windows Server. 

# Task 3: Install the web server role and test

In this task, install the Web Server role on the server on the Virtual Machine you just created and ensure the default IIS welcome page will be displayed. 

1. In the virtual machine, launch PowerShell by searching **PowerShell** in the search bar, when found right click **Windows PowerShell** to **Run as administrator**.

    ![Screenshot of the virtual machine desktop with the start button clicked and PowerShell selected with run as an administrator highlighted.](../images/0105.png)

2. In PowerShell, install the **Web-Server** feature on the virtual machine by running the following command. 

    ```PowerShell
    Install-WindowsFeature -name Web-Server -IncludeManagementTools
    ```
  
3. When completed, a prompt will state **Success** with a value **True**. You do not need to restart the virtual machine to complete the installation. Close the RDP connection to the VM by clicking the **x** on the blue bar at the top center of your virtual machine. 

    ![Screenshot of the windows PowerShell command prompt with the command Install-WindowsFeature -name Web-Server -IncludeManagementTools successfully completed and output stating it was successful.](../images/0106.png)

4. Back in the portal, navigate back to the **Overview** blade of myVM and, use the **Click to clipboard** button to copy the public IP address of myVM, then open a new browser tab, paste the public IP address into the URL text box, and press the **Enter** key to browse to it.

    ![Screenshot of the Azure portal virtual machine property pane with the IP address copied.](../images/0107.png)

5. The default IIS Web Server welcome page will be displayed.

    ![Screenshot of the default IIS web server welcome page being accessed via the public ip address in a web browser.](../images/0108.png)

**Congratulations!** You have created a new VM running a web server that is accessible via its public IP address. If you had a web application to host, you could deploy application files to the virtual machine and host them for public access on the deployed virtual machine.


**Note**: To avoid additional costs, you can remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see verify that the deletion completed successfully. 
