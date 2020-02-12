# Azure IoT Time Series Insights IoT Summit 2020 Hands on Lab
-----------------------------------------

Welcome to the lab! Azure IoT Time Series Insights Azure Preview is an end-to-end platform-as-a-service (PaaS) offering. You can use it to collect, process, store, analyze, and query data at Internet of Things (IoT) scale--data that's highly contextualized and optimized for time series.

Time Series Insights is designed for ad hoc data exploration and operational analysis. It's an extensible and customized service offering that meets the broad needs of industrial IoT deployments. 

## Introduction and Scenario

## Outline

In this workshop, you will be building Contoso Art Shipping's IoT solution.

1. [Connecting an asset tracking device to Azure IoT](step-001-connecting-a-device/)
2. [Setting up a data pipeline](step-002-setting-up-data-pipeline/)
3. [Anomaly detection](step-003-anomaly-detection/)
4. [Map visualization - Where are my parcels?](step-004-map-visualization/)

The last part will showcase how to feed your insights (we'll learn how to trigger events on sudden temperature variations on our asset tracking devices) into Contoso's ERP and mobile application. It will be shown through a demo, as time constraints don't allow for this part to be included in this one-day workshop.

## Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at [http://go.microsoft.com/fwlink/?LinkID=254653](http://go.microsoft.com/fwlink/?LinkID=254653).

Privacy information can be found at [https://privacy.microsoft.com/en-us/](https://privacy.microsoft.com/en-us/)

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.



**Step 1: Create an Azure Time Series Insights Preview environment**

1. Sign-in to the Azure portal by using your subscription account.
2. Select Create a resource > Internet of Things > Time Series Insights.

![Create an environment](media/search-the-marketplace.png)

3. In the Create Time Series Insights environment pane, on the Basics tab, set the following parameters:

**Parameter**|**Action**
-----|-----
Environment name|Enter a unique name for the Azure Time Series Insights Preview environment.
Subscription|Enter the subscription where you want to create the Azure Time Series Insights Preview environment. A best practice is to use the same subscription as the rest of the IoT resources that are created by the device simulator.
Resource group|Select an existing resource group or create a new resource group for the Azure Time Series Insights Preview environment resource. A resource group is a container for Azure resources. A best practice is to use the same resource group as the other IoT resources that are created by the device simulator.
Location|Select a datacenter region for your Azure Time Series Insights Preview environment. To avoid additional latency, it's best to create your Azure Time Series Insights Preview environment in the same region as your IoT Hub created by the device simulator.
Tier|Select PAYG (pay-as-you-go). This is the SKU for the Azure Time Series Insights Preview product.
Property ID|Enter a value that uniquely identifies your time series instance. The value you enter in the Property ID box is immutable. You can't change it later. For this tutorial, enter iothub-connection-device-id. To learn more about Time Series ID, see Best practices for choosing a Time Series ID.
Storage account name|Enter a globally unique name for a new storage account.
Enable Warm Store?|Select Yes to enable warm store.
Data Retention (days)|Choose the default option of 7 days

4. Click on “Next: Event Source” to establish a connection between your IoT Hub and TSI:

**Parameter**|**Action**
-----|-----
Create an event source?|Select Yes.
Name|Enter a unique value for the event source name.
Source type|Select IoT Hub.
Select a hub|Choose Select existing.
Subscription|Select the subscription that you're using for the lab.
IoT Hub name|Select the IoT Hub that was created in a previous step.
IoT Hub access policy|Select iothubowner.
IoT Hub consumer group|Select New, enter a unique name, and then select Add. The consumer group must be a unique value in Azure Time Series Insights Preview.
Timestamp property|This value is used to identify the Timestamp property in your incoming telemetry data. Leave this box empty. When left empty, Time Series Insights will default to the message enqueued timestamp set by IoT Hub or Event Hub. This is sufficient for the lab.

![Create an environment](media/createTsiEnvironment.png)

5. Click on “Review + create”

![Review and create](media/review-and-create.png)

6. Review the values entered and click “Create”

7. Once your deployment is complete, navigate to your new Time Series Insights resource in the Azure portal. You should have access to your environment by default. To verify, select "Data Access Policies" under "Settings." If you do not see your credentials listed, grant yourself access by clicking "Add" and searching for your identity.

![Verify access](media/verify-accesss.png)
