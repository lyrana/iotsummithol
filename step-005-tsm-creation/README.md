## Step 5: Create a Time Series Model

In this section, you will add time series model entities to contextualize your IoT data. Time Series Model (preview) has 3 components: Types, Hierarchies and Instances.

* Types allow users to define calculations, aggregates, and categories over raw telemetry data, as well as define a tag for the sensor (example: Temperature sensor, Pressure sensor). This is achieved by authoring type variables.
* Hierarchies allow users to specify the structure of their assets. For example, an organization has buildings and buildings have rooms which contain IoT devices. We will leverage the ability to create multiple hierarchical views to see the Contoso Wind Farm data organized in both a physical and sematic structure.
* Instances enrich incoming IoT data with device metadata. An instance links to 1 type definition and multiple hierarchy definitions.

1. In the upper left part of the explorer select the Model tab:

![01_TSM_Authoring](../assets/01_TSM_Authoring.png)

2. In the Hierarchies section, select “+ Add”.

A modal will open. Add the following values:

Name: Wind Farm - Physical
Levels:
Name the first level “Location”.
Click “+ Add Level” and add another sub-level named "Windill".
Add two more levels: "Group" and "Name".

![02_TSM_Authoring](../assets/02_TSM_Authoring.png)

3. If you don't see the hierarchy listed refresh the page. 

4. Repeate the steps above to add antoher hierarchy named "Wind Farm - Semantic" with the following levels: 

Group > Name > Location > Windmill

![Image](../assets/03_TSM_Authoring.png)

5. Now that there are two hierarchies navigate to the Types section. For the lab we will be adding variables to the default type. Click the pencil icon to open the editor, and select the Variables tab. Click "+ Add variable" and enter the following fields:

Name: "Value"
Kind: "Numeric"
Value: Select from preset
In the drop-down menu select "Value (Double)"

We will not be using the advanced variable options, however, you can expand the section to view the options offered, including modifying the aggregation and configuring interpolation or a value filter.

Click "Apply"

Next we will add a categorical variable. Categorical variables allow you to set a descriptive label or category to a discrete value. For example, 0 or 1 might be sent in an event payload, but an operations manager may instead prefer to see "On" and "Off" in the explorer. Note that there is an error in the lab for this varaible example--0 and 1 were intended to be in the event payload, but you'll see in the example below that the actual text is sent instead. Given time constraints, please "squint your eyes" to see these numeric values categorized, and this will be fixed for future labs.

Click "Add" and enter the following fields:

Name: "Status"
Kind: "Categorical"
Value: Custom
In the input box enter "$event.[Status].String"
Kind: String

![Image](../assets/04_TSM_Authoring.png)


Categories:
Label: Good
Values: Good
Color: Select a color

Label: Bad
Values: Bad
Color: Select a color

Default category: Unknown

![Image](../assets/05_TSM_Authoring.png)

Click Apply and then click Save.





