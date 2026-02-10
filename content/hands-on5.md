---
layout: default
title: 5. Add Labels
nav_order: 5
parent: Hands On
---
# Adding Labels
Now we have two layers, one choropleth and one proportional symbol, visualizing the number of Douglas Fir street trees in each Vancouver neighbourhood. However, some context information might be useful, such as name of neighbourhood and/or number of Douglas Firs. 

## Add neighbourhood labels
First, let's add the names of neighbourhoods to our choropleth map. 

Turn the proportional symbol layer off so it isn't distracting. 

Open the Layer Properties for `vanHoodsCount` and navigate to **Labels**. Currently, no labels are set. 

Set labelling to **Single Labels** and set the **Value** to `NAME`. Click **Apply** and see what the map looks like.

<img src="./images/neighbourhood-labels1.png" style="width:100%">

While labels appear for the neighbourhoods, they are a bit difficult to see. There are a couple things we can do to make the labels more visible. 

Back in the Layers properties, increase the font size to at least 12 Points. 

<img src="./images/add-neighbourhood-labels1.png" style="width:80%">

Add a buffer around the text, something light colored like white but then drop the opacity a bit. 

<img src="./images/add-neighbourhood-labels2.png" style="width:80%">

then go down to Placement and change the placement to horizontal. 

<img src="./images/add-neighbourhood-labels3.png" style="width:80%">



<img src="./images/neighbourhood-labels2.png" style="width:100%">


<br>

## Add count labels 
Now, let's add the total number of Douglas Firs in each neighbourhood to our proportional symbol map. 


You can add Labels from the layer Properties as well, setting Single Labels according to the Value chestnut-trees. Adding a Buffer or adjusting the font color, and changing the Placement mode to “Offset from Point” will allow you to visualize the number above the symbol.