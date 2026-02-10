---
layout: default
title: Attribute Table
nav_order: 1
parent: Hands On
---

# The **Attribute Table**
The Attribute Table is where you can view the tabular data associated with vector datasets. Here, you can query your data by running complex selections, directly edit individual features, and perform mathematical analysis on your layers. 

To Do
{: .label .label-green }

Add `vanBigTrees` to your map canvas. This is a geojson file containing a subset of [Vancouver Street Trees](https://opendata.vancouver.ca/explore/dataset/public-trees/map/?disjunctive.common_name&disjunctive.species_name&location=12,49.24773,-123.08842&basemap=jawg.streets). The reason it is only a subset is because the original dataset contains over 180,000 features and is 72MB — too large to work with in today's workshop. 

![vanBigTrees](./images/vanBigTrees.png)



## Exploring the Attribute Table 

To Do
{: .label .label-green }
Now, open the **Attribute Table** for `vanBigTrees`. 

![vanBigTrees open attribute table](./images/vanBigTrees-open-attribute-table.png)

![vanBigTrees attribute table](./images/vanBigTrees-attribute-table.png)

The column headings are called **Attributes** and each row is a **Feature**. Each Feature corresponds to one point on the map. At the top of the Attribute Table you can see there are 3,224 features, or trees, in this dataset. Each feature, or tree, has 10 attributes, including the `common_name` and `height_m`. Notice that text values are left-justified whereas numerical values are right-justified. Very few trees have information for the data planted. 

You can order features in descending or ascending order by clicking on the attribute. For example, clicking `height_m` will sort all features from shortest to tallest. Clicking `height_m` again will sort from tallest to shortest. (Notice some of the shortest trees were planted just last month.) Clicking `common_name` will sort the trees in alphabetical order. 
<!-- Sometimes numbers are read-in to QGIS as text, disabling mathematical calculations. If you are ever trying to perform such a   -->


form and table view ~~

## Selecting by Attribute
There are many ways to make selections in QGIS. select - click. select by location. select by attribute. 

remember, our goal is to discover how many douglas fir street trees in each neighborhood and then visualize that through two thematic maps. So, we are not interested in all big trees, only in douglas firs. This means we need to run a selection. we will build an expression to for only features where the common name is douglas fir. 

### Select only the Douglas Fir trees

*1*{: .circle .circle-purple} From the Attribute Table of `vanBigTrees`, click on the **Select features using an expression** button.


![select features using expression](./images/select-features-using-expression.png)


We will use this tool to query and select only features that have a `common_name` value of “Douglas Fir”. Rather than writing an expression by hand, we will select the appropriate fields, values, and operators from the drop-downs provided. This ensures no syntax errors are made and our selection runs smoothly. 


*2*{: .circle .circle-purple} From the middle panel, expand **Fields and Values**. Double click on `common_name` to add it to the Expression panel. 

<img src="./images/common_name.png" style="width:90%">


*3*{: .circle .circle-purple} Then click the `=` operator. You will get a warning saying your expression is invalid. That's okay! We aren't finished building it.

<img src="./images/equals-operator.png" style="width:90%">


*4*{: .circle .circle-purple} Finally, we need to indicate what the common name is equal to. In the right-hand panel, click the button for **All Unique** to display all the unique values for common name in the dataset. Double-click on "Douglas Fir" to add it to the expression. 


<img src="./images/all-unique.png" style="width:90%">


*5*{: .circle .circle-purple} Now click **Select Features** on the bottom-right. Close the expression builder and return to the Attribute table. You will see that 2,396 features have been selected. Selected features will be highlighted in the Attribute Table. If you the Attribute Table indicates a selection was made but you don't see any highlighted features, try ordering the Attribute Table by `common_name`, and then scrolling down to the letter "D". 

<img src="./images/selection-made1.png" style="width:100%">

Alternatively, you can change the Attribute Table view to view *only selected features*. Just be sure to change the view back afterwords, or next time you open the attribute table without a selection it will look empty. 

<img src="./images/show-selected-features1.png" style="width:100%">


*6*{: .circle .circle-purple} Now close the Attribute Table and return to the main QGIS interface. In the Map View, you should see your selection highlighted. These are all the douglas fir street trees.

<img src="./images/selection-made2.png" style="width:100%">


## Exporting selections as a new dataset

We want to create a new dataset that is just Douglas Firs. To do this, we can "export" our selection. 

Right-click on the layer `vanBigTrees` in the Layers Panel. Choose **Export** and then be sure to choose **Save *selected* Features As**. 

<img src="./images/export-selection.png" style="width:100%">

In the window that opens, give the new file both a name and location. To do this, click on the three dots and navigate to the `thematic-mapping-workshop/data` folder. Call this file `vanDougFirs`. Everything else can remain as default.  Click **OK**. 

<img src="./images/save-selection-as-layer.png" style="width:70%">


The new layer should add automatically to your map. If not, add it now. 

<img src="./images/new-layer-added.png" style="width:100%">



Remove `vanBigTrees` (by right-clicking the layer) and **save your project**. 

<img src="./images/remove-layer.png" style="width:100%">


<!-- # Layer Properties

open project

refer to mapping introduction for gui overview and data management

update symbology of neighborhoods and outline

add basemap 

-- -->

