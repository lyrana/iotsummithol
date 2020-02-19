## Step 6: Chart and Query Data

So now that we’ve created a model for our data, we can start querying it via the TSI Explorer. 

Time Series Insights offers 3 query APIs: GetEvents, GetSeries and AggregateSeries. 
1. GetEvents lets you query for raw events for one TSID over a selected search span. 
1. GetSeries allows you to perform calculations on the raw events and retrieve the results for one TSID over a selected search span. 
1. AggregateSeries allows you to retrieve one aggregated result per interval for one TSID over a selected search span. 

To query your data, expand your model, select an instance and click on the instance itself to see which variables are available. Use the “Wind Farm – Physical” hierarchy to select the Outdoor Temperature tag from WM1 in Bristol and show the Value. 


 [!TIP]
> Make sure you’ve selected a region in the availability chart where there is data available for query. 

![Query 1](query_01.png)

