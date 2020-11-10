---
wts:
    title: '02 - Create a Web App'
    module: 'Module 02 - Core Azure Services (Workloads)'
---
# 02 - Create a Web App

In this walkthrough, we will create a new web app that runs a Docker container. The container displays a Welcome message. 

# Task 1: Create a Web App

Azure App Service is actually a collection of four services, all of which are built to help you host and run web applications. The four services (Web Apps, Mobile Apps, API Apps, and Logic Apps) look different, but in the end they all operate in very similar ways. Web Apps are the most commonly used of the four services, and this is the service that we will be using in this lab.

In this task, you will create an Azure App Service Web App. 

1. Sign-in to the [Azure portal](http://portal.azure.com/). 

2. From the **All services** blade, search for and select **App Services**, and click **+ Add**

3. On the **Basics** tab of the **Web App** blade, specify the following settings (replace **xxxx** in the name of the web app with letters and digits such that the name is globally unique). Leave the defaults for everything else, including the App Service Plan. 

    | Setting | Value |
    | -- | -- |
    | Subscription | **Choose your subscription** |
    | Resource Group | **myRGWebApp1** (create new) |
    | Name | **myDockerWebAppxxxx** |
    | Publish | **Docker Container** |
    | Operating System | **Linux** |
    | Region | **East US** (ignore any service plan availability warnings) |
    | | |	

4. Click **Next > Docker** and configure the container information. The startup command is optional and not needed in this exercise. 

    **Note:** This is same container that was used in the Container Instances walkthrough to display a hello world message. 

    | Setting | Value |
    | -- | -- |
    | Options | **Single container** |
    | Image Source | **Docker Hub** |
    | Access Type | **Public** |
    | Image and tag | **microsoft/aci-helloworld** |
    | | |	


5. Click **Review + create**, and then click **Create**. 

# Task 2: Test the Web App

In this task, we will test the web app.

1. Wait for the Web App to deploy.

2. From **Notifications** click **Go to resource**. 

3. On the **Overview** blade, locate the **URL** entry. 

    ![Screenshot of the web app properties blade. The URL is highlighted.](../images/0801.png)

4. Click on the **URL** to open the new browser tab and display the Welcome to Azure Container Instances page.

    ![Screenshot of the Welcome to Azure Container Instance page.](../images/0802.png)

5. Switch back to the **Overview** blade of your web app and note that it includes several charts. If you repeat step 4 a few times, you should be able to see correspoding telemetry being displayed in the charts. This includes number of requests and average response time. 

**Note**: To avoid additional costs, you can remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.

