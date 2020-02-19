## Step 5: Create a Time Series Model

In this section, you will add time series model entities to contextualize your IoT data. Time Series Model (preview) has 3 components: Types, Hierarchies and Instances.

* Types allow users to define calculations, aggregates, and categories over raw telemetry data, as well as define a tag for the sensor (example: Temperature sensor, Pressure sensor). This is achieved by authoring type variables.
* Hierarchies allow users to specify the structure of their assets. For example, an organization has buildings and buildings have rooms which contain IoT devices. 
* Instances enrich incoming IoT data with device metadata. An instance links to 1 type definition and multiple hierarchy definitions.

1. In the upper left part of the explorer select the Model tab:

![01_TSM_Authoring](../assets/01_TSM_Authoring.png)

1. In the Hierarchies section, select “+ Add”.

A modal will open. Add the following values:

Name: Delivery Routes.
Levels:
Name the first level “Route Name”.
Click “+ Add Level” and add another sub-level named “ParcelID”.