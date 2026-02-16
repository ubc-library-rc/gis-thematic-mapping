---
layout: default
title: 3. Make a Choropleth map
nav_order: 3
parent: Hands On
---

# Making a Choropleth Map

As it is, we can't glean any information regarding the number of Douglas Firs by simply looking at `vanHoodsCount`. However, as we saw in the Attribute Table, `vanHoodsCount` *does* contain this information. So, what we need to do is change the **Symbology** of `vanHoodsCount` to render visible the values in the `DougFirs` field. We can use either color or symbols to convey the range of total trees. Let's begin by making a choropleth map, using a color gradient to visualize the number of Douglas Fir street trees in each Vancouver neighbourhood.

![demo choropleth map here](./images/demo-choropleth-map.jpeg)

---- 
<!-- 
Remember, a choropleth map visualizes different values across standard geographic areas through gradations in color. So, what we need to do is change the **Symbology** of `vanHoodsCount` to render visible values in the `chestnut-trees` column. 

To create a choropleth map, we need to update the **symbology** of the layer `vanHoodsCount`.  Symbology is a layer property that governs the color, transparency, and line thickness of the features displayed. -->


*1*{: .circle .circle-yellow} In the Layers Panel, right-click on `vanHoodsCount` and go to **Properties**. Then, in the Layer Properties window, navigate to the **Symbology** tab. 


<img src="./images/layer-properties.png" style="width:100%">

<img src="./images/layer-properties-single-symbol.png" style="width:80%">

<br>

*2*{: .circle .circle-yellow} At the very top, we can see that the symbology is set to **Single Symbol**. This means every feature in the dataset is rendered in the same color. Since we want to show a range of values, we need to change the symbology. Click on Single Symbol and from the drop-down, choose **Graduated**. This will allow you to symbolize each neighbourhood along a gradient of color, with darker colors representing more trees and lighter colors representing fewer. 

<img src="./images/graduated-symbology.png" style="width:90%">

<br>

*3*{: .circle .circle-yellow} Set the **Value** to DougFirs. (Or Count, if you didn't specify the attribute back when you ran the Count Points in Polygon tool.) This tells QGIS which numerical field to visualize. 

<img src="./images/symbology-value.png" style="width:90%">

<br>

*4*{: .circle .circle-yellow} **Precision** refers to how many decimals you want to include, and checking the **Trim** box removes trailing zeros from the legend. Because we are dealing with whole numbers of trees, so long as Trim is checked it doesn’t matter the precision.

<br>

*5*{: .circle .circle-yellow} You can select a color ramp from the given options, or design your own. Hover over “All Color Ramps” to see all options. For now, change the color ramp to **greens**. 
<img src="./images/symbology-greens.png" style="width:90%">

<br>

*6*{: .circle .circle-yellow} So far, we’ve set up the symbology but we have to apply it to our values. Click **Classify** to classify the `DougFirs` values. (If nothing shows up, check the attribute table of `vanHoodsCount` to ensure `DougFirs` is a numerical field.) 

<img src="./images/symbology-classify.png" style="width:90%">

Then, click **Apply** to see your map change. Only after clicking **Classify** and then **Apply** will you see the results.

<br>

*7*{: .circle .circle-yellow} While the default classification mode is set to Equal Count (Quantile), you can choose amongst different classification modes. Classification modes determine how the distribution of data are grouped or “classified”, and therefore which values are associated with which colors. Read more about different classification modes [here](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/data-classification-methods.htm). 

- Change the classification **Mode** to **Natural Breaks (Jenks)**. 
- You can also increase or decrease the number of classes, though between 5 and 7 is best practice. For today, keep the number of **Classes** set to **5**. 

<img src="./images/symbology-complete.png" style="width:90%">

 

- If you toggle to the **Histogram** tab, you can click **Load Values** to see the distribution of `DougFirs` values. The X-axis indicates number of chestnut trees whereas the Y-axis, “Count”, refers to the number of neighborhoods with this number of chestnut trees. The number of bins refers to how granularly the number line is broken down. 
<!-- Currently there are 30 bins, from 0 to 300—meaning any neighborhood with a count that isn’t a multiple of ? will be split. -->

<!-- Set the following inputs

- **Value**: DougFirs (what this does)
- **Precision**: 0 (what this does)
- Check the box for Trim
- **Color Ramp**: pick a color ramp that looks like it would represent the prevalence of Douglas Firs.
-  **Mode** : Natural Breaks (Jenks) (see more on classification)
- **Classes**: 5 -->

<br>

*8*{: .circle .circle-yellow} Click **Apply** again and drag/resize your symbology window so you can see your map canvas. When you are satisfied, click **OK** and close the Layer Properties/Symbology window.

<img src="./images/choropleth-symbology.png" style="width:100%">





<!-- ## Field calculator - though this would be after count points in polygon... 
3. also do math in attribute table to normalize. - number of douglas firs as percentage of street trees - (would have needed to include total number of street trees per neighborhood earlier. still can do but need to update dataset) -->
