## Step 1: Create an Event Hub and begin data ingestion

Azure IoT Time Series Insights preview supports both IoT Hub and Event Hubs as event sources. In this lab we'll be setting up an Event Hub and leverage a SPA client to generate and push wind mill sensor data to the hub.

### Create a resource group

1. Create an Azure resource group (RG) to collect and manage all the application resources we will be provisioning and using during the lab and for ease of resource clean-up once the lab concludes. You may also re-use an existing RG. 
\
![Resource Group](assets/01_Create_Resource_Group.png)

1. Click on **+ Add** button  
\
![Add Resource Group](assets/02_Create_Resource_Group_Create.png)

1. Enter **Resource group name**,  Select **subscription** and **region**. Click on **Review + Create**, and after reviewing, click on **Create**.

    > **_NOTE:_**  
    >
    > * **Resource Group Name**: Use name of your choice.  
    > * **Region**: During public preview, IoT Plug and Play is available in the North Europe, Central US, and Japan East regions. Although we are only creating a resource group at this stage, please make sure you create it in one of these regions to avoid potential mistakes later on.

![Create Resource Group Submit](assets/03_Create_Resource_Group_Submit.png)

### Create an Event Hubs namespace and an Event Hub


 resource group


https://tsiclientsample.azurewebsites.net/windFarmGen.html