## Step 3: Create an Azure Time Series Insights Preview environment

1. Click the toolbar and search the Azure marketplace for Time Series Insights. Click create and set the following parameters:


![Create an environment](../assets/createTsiEnvironment.png)

![Create an environment 02](../assets/createTsiEnvironment02.png)

**Parameter**|**Action**
-----|-----
Environment name|Enter a unique name for the Azure Time Series Insights Preview environment.
Subscription|Select the subscription you're using for the lab.
Resource group|Select your RG.
Location|Select a datacenter region for your Azure Time Series Insights Preview environment. To avoid additional latency, it's best to create your Azure Time Series Insights Preview environment in the same region as your IoT or Event Hub created in the previous step.
Tier|Select PAYG (pay-as-you-go). This is the SKU for the Azure Time Series Insights Preview product.
Time Series ID Property name| Enter "Id" as this is the TS ID used by the data simulator. Note that the value you select for your TS ID is immutable. You can't change it later.
Storage account name|Enter a globally unique name for a new storage account.
Enable Warm Store?|Select Yes to enable warm store.
Data Retention (days)|Choose the default option of 7 days


4. Click on “Next: Event Source” to establish a connection between your Event Hub and TSI:

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
