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


To Do
{: .label .label-green }
Now, open the **Attribute Table** for `vanBigTrees`. 

![vanBigTrees open attribute table](./images/vanBigTrees-open-attribute-table.png)

![vanBigTrees attribute table](./images/vanBigTrees-attribute-table.png)

In the **Attribute Table**, the column headings are called **Attributes** and each row is a **Feature**. Each Feature corresponds to one point on the map. At the top of the Attribute Table you can see there are 3,224 features, or trees, in this dataset. Each feature, or tree, has 10 attributes, including the `common_name` and `height_m`. Notice that text values are left-justified whereas numerical values are right-justified. Very few trees have information for the data planted. 

You can order features in descending or ascending order by clicking on the attribute. For example, clicking `height_m` will sort all features from shortest to tallest. Clicking `height_m` again will sort from tallest to shortest. (Notice some of the shortest trees were planted just last month.) Clicking `common_name` will sort the trees in alphabetical order. 
<!-- Sometimes numbers are read-in to QGIS as text, disabling mathematical calculations. If you are ever trying to perform such a   -->



