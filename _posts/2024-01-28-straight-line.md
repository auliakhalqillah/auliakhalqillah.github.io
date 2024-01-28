---
layout: post
title: "How to Create Line Projection Given a Coordinate Point Using QGIS"
description: Creating a simple straight-line
tags: QGIS
---
Let’s imagine that you want to create a projection straight line based on the coordinate point. For example in the simple fault geometry (length of fault) of the seismic hazard source model,
we have information such as the epicenter of the earthquake (longitude and latitude coordinates), the length of the simple fault, and the strike angle of simple fault. We can create the projection
using these parameters through the Quantum GIS (QGIS) platform.

Let’s open your QGIS. Assume that we have a coordinate point at 0.2040817842 of longitude and 0.07281577911 of latitude. This point has a strike of 30o from the north direction and
a fault length of 20 Km. Type these parameters into the text editor using a comma separator and save it as Point.csv. Load this file into the QGIS and then the point will show as
depicted in Figure 1.

![Sample Point](/img/1%20Sample%20Point.png)
Figure 1. Sample Point

![Km2degree](img/2%20Km%20to%20degree.png)
Figure 2. Converting the Km to Degree for fault length

The fault length must be converted to degrees unit. We assume the 1 degree is equal to 111.1 Km. So, the field of length_km of 20 Km is divided by 111.1 Km/degree. We can calculate
this by using the Open Field Calculator toolbox as depicted in Figure 2. We set the name of the column field as length_degrees and the output field type is Decimal Number (real).
This process will generate a new field after we click on the OK button. We select the Point layer and click on Open Attribute Table, the converted length has been calculated as
depicted in Figure 3.

![Field Table](/img/3%20Table%20Field.png)

Figure 3. The new field of fault length in degree has been calculated

Now, you can search Geometry by expression in the Processing Toolbox and double-click on it. It will show a window of Geometry by expression as depicted in Figure 4. 
Select the Point layer in the Input Layer. Then, select Line in `Output geometry type`. Then, click the  icon and it will show the new window as depicted in Figure 5. Type the following
code to create the straight line in the Geometry expression window and click on OK. Then, click on the bottom arrow on the Modified Geometry and select Save to File as depicted in Figure 6. 
Save the generated straight line to the directory that we specified and then click on the Run.

```
extend(make_line($geometry,project($geometry,"length_degree"/2,radians("strike"))),"length_degree"/2,0)
```
![Geometry expression window](/img/4%20Geometry%20by%20expression.png)

Figure 4. Geometry by expression window

![Geometry expression](/img/5%20Geometry%20expression.png)

Figure 5. Geometry expression window

![Save to file](/img/6%20Save%20to%20file.png)

Figure 6. Save to file

As a result, the straight line is depicted in Figure 7. The concept is that the straight line is generated from the center of the point. Because we use the fault length of 20 Km, that means
the line was generated 10 Km to the left and the right of the point.

![The straight line](/img/7%20Result.png)
Figure 7. The straight line has been generated

I hope this article is useful for you. Keep in touch ☕😄
