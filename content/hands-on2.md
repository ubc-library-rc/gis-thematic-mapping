---
layout: default
title: 2. Spatial Analysis
nav_order: 2
parent: Hands On
---
# Spatial Analysis

Remember, [QGIS](https://docs.qgis.org/2.18/en/docs/gentle_gis_introduction/spatial_analysis_interpolation.html#:~:text=Overview,Geographic%20Information%20System%20(GIS).) defines spatial analysis as "the process of manipulating spatial information to extract new information and meaning from the original data." Today's workshop is only concerned with vector data, and therefore we will focus on **vector analysis**. 

Since our goal is to create thematic maps that visualize the spatial distribution of Douglas Fir street trees across Vancouver, we need to find out how many Douglas Firs are in each neighbourhood. While we could count up the many many points by hand, this would take a long time and could introduce human error. Instead, we will use QGIS vector analysis tools to do the counting for us. 


See our workshop on [Tools and Workflows in QGIS](https://ubc-library-rc.github.io/gis-tools-workflows/content/vector-tools.html#vector-tools) for further information on vector analysis tools.


## Processing Toolbox
There are two main ways to access the spatial analysis tools of QGIS: Through the **Vector** menu and through the **Toolbox** located in the **Processing** menu. 

Go ahead and open the **Processing Toolbox**. 


<img src="./images/processing-toolbox.png" style="width:100%">


If for some reason you can’t find the Processing Toolbox, you may have to enable the processing plugin. In the main menu bar at the top of your screen, click on **Plugins**, and then on **Manage and Install Plugins…**. In the search bar, type in "Processing". Select the Processing box and then click Close. You should now see the Toolbox icon and be able to proceed with the next steps.
{: .note} 
<!-- [Processing toolbox](https://docs.qgis.org/3.40/en/docs/user_manual/processing/toolbox.html) -->



## Count Douglas Firs
In the Processing Toolbox, search for the QGIS tool called **Count points in polygons**. It should be nested under **Vector analysis**. This tool will count the number of points (Douglas Firs) in each polygon (Vancouver neighbourhoods), and append the total to each neighbourhood.


In the tool window, select the following inputs:

- **Polygons**: `vanHoods` 
- **Points**: `vanDougFirs` 
- **Count field name**: `DougFirs` (the name of the attribute that will store the total number of Doug Firs for each neighbourhood)


<img src="./images/count-points-tool.png" style="width:100%">


Click **Run**, then **Close** when the process has finished. Note: you may see the caution ‘No spatial index exists for points layer, performance will be severely degraded’. You can ignore this.


*You should now have a new layer called `Count` in your Layers Menu*. This is because, unless you specify the output of a tool to be a permanent layer, it will create a temporary layer with the tool's name. 


Drag `Count` below `vanDougFirs` in Layers Panel so the distribution of Douglas Firs remains visible on your Map Canvas. Take a look at the Attribute Table for `Count`. You can now see the number of Douglas Firs in each Vancouver neighbourhood. Close the attribute table to continue.


<img src="./images/count-layer.png" style="width:100%">


Save `Count` as a permanent layer to your data folder by right-clicking it and selecting either **Make Permanent** or **Export - Save Features As..**. Save the file to the `thematic-mapping-workshop/data` folder and call it `vanHoodsCount`. Everything else can remain as default. Click **OK**. Note that if you have any trouble exporting the file, it's likely because you didn't specify a location, just a name for it. 

Be sure to add `vanHoodsCount` to your project if it doesn't add automatically. Then, remove `Count`, `vanHoods`, and `vanDougFirs`. **Save your project**. 



## Centroids: From polygon to point 

<!-- then run centroid on count (for proportional symbol map later) -->

