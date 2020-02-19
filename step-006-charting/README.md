## Step 6: Chart and Query Data

So now that we’ve created a model for our data, we can start querying it via the TSI Explorer.

Time Series Insights offers 3 query APIs: GetEvents, GetSeries and AggregateSeries. 
1. GetEvents lets you query for raw events for one TSID over a selected search span. 
1. GetSeries allows you to perform calculations on the raw events and retrieve the results for one TSID over a selected search span. 
1. AggregateSeries allows you to retrieve one aggregated result per interval for one TSID over a selected search span. 

To query your data, expand your model, select an instance and click on the instance itself to see which variables are available. Use the “Wind Farm – Physical” hierarchy to select the Outdoor Temperature tag from WM1 in Bristol and show the Value. 


       [!TIP]
       Make sure you’ve selected a region in the availability chart where there is data available for query. 

![Query 1](../assets/query_01.png)

You should see your time series displayed in the chart. When you display a time series, Time Series Insights makes an AggregateSeries call. Change the search span and intervals to see different results from the query. 


![Query 2](../assets/query_02.png)

Brush over a region and click Explore Events to make a GetEvents call and see the raw data for the selected region:

![Query 3](../assets/query_03.png)

![Query 4](../assets/query_04.png)

Create a time-shifted version of the trendline you just plotted by selecting the “Explorations” icon (shaped like a lighting bolt) to find any recurring patterns in the data: 


![Query 5](../assets/query_05.png)


![Query 6](../assets/query_06.png)

Change the chart type to view the temperature data as a heatmap:

![Query 7](../assets/query_07.png)

![Query 8](../assets/query_08.png)

Next, add another time series, Outdoor Pressure from WM1 in Bristol. 

![Query 9](../assets/query_09.png)

Use the scatter plot option to view the correlation between the Outdoor Temperature and the Atmospheric Pressure: 

![Query 10](../assets/query_10.png)

![Query 11](../assets/query_11.png)

Brush over a region to show some common statistics for a region:

![Query 12](../assets/query_12.png)

Add the values of Outdoor Temperature and Atmospheric Pressure from WM2 in Bristol. Use the Lane changers to move the time series from WM1 and WM2 into the same lanes:


![Query 13](../assets/query_13.png)

To export data, use the the “More actions” button. Some options include downloading the data as a CSV and generating a query to connect to PowerBI. 

![Query 14](../assets/query_14.png)

To try out the Power BI Connector, you must have the desktop version of Power BI installed. If you do, see [here](https://docs.microsoft.com/en-us/azure/time-series-insights/how-to-connect-power-bi) for steps on how to use it.

Some solutions require highly customized applications. We offer a JavaScript SDK for developers building their own front-end applications. Learn more [here](https://github.com/Microsoft/tsiclient).

Continue to section   [next step](../step-007-resource-links)