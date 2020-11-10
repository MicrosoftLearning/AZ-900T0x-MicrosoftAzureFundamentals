---
wts:
    title: '04 - Create blob storage'
    module: 'Module 02 - Core Azure Services'
---
# 04 - Create blob storage

In this walkthrough, we will create a storage account, then work with blob storage files.

# Task 1: Create a storage account

In this task, we will create a new storage account. 

1. Sign in to the Azure portal at <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. From the **All services** blade, search for and select **Storage accounts**, and then click **+ Add**. 

3. On the **Basics** tab of the **Create storage account** blade, fill in the following information (replace **xxxx** in the name of the storage account with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Choose your subscription** |
    | Resource group | **myRGStorage** (create new) |
    | Storage account name | **storageaccountxxxx** |
    | Location | **(US) East US**  |
    | Performance | **Standard** |
    | Account kind | **StorageV2 (general purpose v2)** |
    | Replication | **Locally redundant storage (LRS)** |
    | Access tier (default) | **Hot** |
    | | |

5. Click **Review + Create** to review your storage account settings and allow Azure to validate the configuration. 

6. Once validated, click **Create**. Wait for the notification that the account was successfully created. 

7. From the Home page, search for and select **Storage accounts** and ensure your new storage account is listed.

    ![Screenshot of the newly created storage account in the Azure portal .](../images/0401.png)

# Task 2: Work with blob storage

In this task, we will create a Blob container and upload a blob file. 

1. Click the name of the new storage account, scroll to the **Blob service** section, and then click **Containers**.

2. Click **+ Container** and complete the information. Use the Information icons to learn more. When done click **OK**.


    | Setting | Value |
    | --- | --- |
    | Name | **container1**  |
    | Public access level| **Private (no anonymous access)** |
    | | |

    ![Screenshot of the newly created blob container in the storage account in the Azure portal.](../images/0402.png)

4. Click the **container1** container, and then click **Upload**.

5. Browse to a file on your local computer. 

    **Note**: You can create an empty `.txt` file or use any existing file. Consider chooosing a file of a small size to minimize the upload time.

6. Click the **Advanced** arrow, leave the default values but review the available options, and then click **Upload**.

    **Note**: You can upload as many blobs as you like in this way. New blobs will be listed within the container.

7. Once the file is uploaded, right-click on the file and notice the options including View/edit, Download, Properties, and Delete. 

8. As you have time, from the storage account blade, review the options for Files, Tables, and Queues.

# Task 3: Monitor the storage account

1. If needed, return to the storage account blade and click **Diagnose and solve problems**. 

2. Explore some of the most common storage problems. Notice there are multiple troubleshooter.

3. On the storage account blade, scroll down to the **Monitoring** section and click **Insights**. Notice there is information on Failures, Performance, Availability, and Capacity. Your information will be different.

    ![Screenshot of the storage account Insights page.](../images/0403.PNG)

Congratulations! You have created a storage account, then worked with storage blobs.

**Note**: To avoid additional costs, you can remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
