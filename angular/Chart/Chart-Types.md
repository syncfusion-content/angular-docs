---
layout: post
title: Chart types
description: What are the different types of Charts available in Essential Angular 2 Chart.
platform: Angular
control: Chart
documentation: ug
---

# ChartTypes

## Line Chart

To render a Line Chart, set the series `type` as **"line"** in the chart series. To change the line segment color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="line" fill="#E94649">
		      <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img1.png)


### Change the line width

To change the width of the line segment, you can use the `width` property in the series.

{% highlight html %}


<ej-chart id="chartcontainer">
 <!-- Write series code here-->
    <e-seriescollection>
        <e-series [width]=3>
		 <!-- Add series points here-->
	  </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img2.png)



### Dashed lines

To render the line series with dotted lines, you can use the `dashArray` option of the series.

{% highlight html %}


  <ej-chart id="chartcontainer">
      <e-seriescollection>
         <e-series dashArray="5,5">
	  	    <!-- Add series points here-->
	       </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img3.png)



### Changing the line cap

For customizing the start and end caps of the line segment, you can use the `lineCap` property.  

{% highlight html %}

  <ej-chart id="chartcontainer">
      <e-seriescollection>
         <e-series lineCap="square">
	  	   <!-- Add series points here-->
	       </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img4.png)


### Changing the line join

You can use the `lineJoin` property to specify how two intersecting line segments should be joined.

{% highlight html %}

  <ej-chart id="chartcontainer">
      <e-seriescollection>
         <e-series lineJoin="round">
	  	   <!-- Add series points here-->
	    </e-series>
     </e-seriescollection>
  </ej-chart>


{% endhighlight %}


![](Chart-Types_images/Chart-Types_img5.png)

### MultiColor Line

You can change the color of the line segments by using the `fill` property of the each `points` in the series.

{% highlight html %}

  <ej-chart id="chartcontainer">
      <e-seriescollection>
         <e-series lineJoin="round">
	  	 <e-points>
		 <e-point x="2000" [y]="14" fill="red"></e-point>
		 <e-point x="2001" [y]="42" fill="red"></e-point>
		 <e-point x="2002" [y]="77" fill="red"></e-point>
		 <e-point x="2003" [y]="68" fill="green"></e-point>
		 <e-point x="2004" [y]="50" fill="green"></e-point>
		 <e-point x="2005" [y]="37" fill="green"></e-point>
		 <e-point x="2006" [y]="64" fill="green"></e-point>
         </e-points>
	    </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img81.png)
 
## Step Line Chart

To render a Step Line Chart, set the series `type` as **"stepline"** in the chart series. To change the StepLine segment color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="stepline" fill="#E94649">
		      <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img6.png)


### Changing the line width

To change the line width, you can use the **width** property.  

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="stepline" [width]=3>
		      <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img7.png)


### Dashed lines

To render the step line series with dotted lines, you can use the `dashArray` option of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="stepline" dashArray="5,5">
		      <!-- Add series points here-->
	       </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img8.png)


### Changing the line cap

For customizing the start and end caps of the line segment, you can use the `lineCap` property.  

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="stepline" lineCap="square">
		      <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img9.png)


### Changing the line join

You can use the `lineJoin` property to specify how two intersecting line segments should be joined.

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="stepline" lineJoin="round">
		       <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img10.png)


## Area Chart

To render an Area chart, you can specify the series `type` as **"area"** in the chart series. To change the Area color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
      <e-seriescollection>
          <e-series type="area">
		       <!-- Add series points here-->
	        </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img11.png)


## Range Area Chart

To render a Range Area Chart, set the `type` as **"rangeArea"** in the chart series. To change the RangeArea color, you can use the `fill` property of the series.

Since the RangeArea series requires two y values for a point, you have to add the `high` and `low` value. High and Low value specifies the maximum and minimum range of the points.

* When you are using the `points` option, specify the high and low values by using the `high` and `low` option of the point.

* When you are using the `dataSource` option to assign the data, map the fields from the dataSource that contain high and low values by using the `series.high` and `series.low` options. 

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
      <e-series type="rangeArea" fill="Indigo">
		     <e-points>
		        <e-point x="1935" high="80" low="70"></e-point>
         </e-points>
	    </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img12.png)

## Step Area Chart

To render a Step Area Chart, set the `type` as **"stepArea"** in the chart series. To change the StepArea color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stepArea" fill="#69D2E7">
		      <e-points>
		          <e-point x="1935" high="80" low="70"></e-point>
         </e-points>
	     </e-series>
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img13.png)


## Spline Area Chart

To render a Spline Area Chart, set the `type` as **"splineArea"** in the chart series. To change the SplineArea color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="splineArea" fill="#C4C24A">
	      </e-series>
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img14.png)

## Stacked Area Chart

To render a Stacked Area Chart, set the `type` as **"stackingArea"** in the chart series. To change the StackingArea color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stackingArea" fill="#69D2E7">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img15.png)


## 100% Stacked Area Chart  

To render a 100% Stacked Area Chart, set the `type` as **"stackingArea100"** in the chart series. To change the StackingArea100 color, you can use the `fill` property of the series.   

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stackingArea100" fill="#C4C24A">
    	  </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img16.png)


## Column Chart

To render a Column Chart, set the `type` as **"column"** in the chart series. To change the color of the column series, you can use the `fill` property.  

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="column" fill="#E94649">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img17.png)


### Change a point color

You can change the color of a column by using the `fill` property of the point.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="column">
           <e-points>
		           <e-point fill="skyblue"></e-point>
           </e-points>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img18.png)

### Column width customization

Width of the column type series can be customized by using the `columnWidth` property. Default value of `columnWidth` is 0.7. Value ranges from 0 to 1. Here 1 corresponds to 100% of available width and 0 corresponds to 0% of available width.

N> Width of a column also depends upon the `columnSpacing` property, because `columnSpacing` will reduce the space available for drawing a column. This is also applicable for StackingColumn, StackingColumn100, Bar, StackingBar, StackingBar100, RangeColumn, HiLo, HiLoOpenClose, Candle and Waterfall charts.

{% highlight html %}

<!-- Width of columns in column type series-->
<ej-chart id="chartcontainer" [commonSeriesOptions.columnWidth]=0.7>
     <e-seriescollection>
        <e-series type="column">       
	      </e-series>
        <!--Settings specific to individual series-->
        <e-series type="column" [columnWidth]=0.7>       
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img86.png)

### Column with rounded corners
Corners of the column chart can be customized by setting value to the `cornerRadius` property.

{% highlight html %}

<ej-chart id="chartcontainer" [commonSeriesOptions.cornerRadius]=20>
     <e-seriescollection>
        <e-series type="column">       
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img88.png)

### Spacing between column series

Spacing between column type series can be customized using the `columnSpacing` property. Default value of `columnSpacing` is 0. Value ranges from 0 to 1. Here 1 corresponds to 100% available space and 0 corresponds to 0% available space.

N> Column spacing will also affect the width of the column. For example, setting 20% spacing and 100% width will render columns with 80% of total width. This is also applicable for StackingColumn, StackingColumn100, Bar, StackingBar, StackingBar100, RangeColumn, HiLo, HiLoOpenClose, Candle and Waterfall charts.

{% highlight html %}

<!-- Common settings for all series-->
<ej-chart id="chartcontainer" [commonSeriesOptions.columnSpacing]=0>
     <e-seriescollection>
        <e-series type="column">       
	      </e-series>
        <!--Settings specific to individual series-->
        <e-series type="column" [columnSpacing]=0>       
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img87.png)


### Cylindrical Chart

To render a cylindrical chart, set the `columnFacet` property as "cylinder" in the chart series along with the series type. 

The following chart types can be rendered as cylinder in both 2D and in 3D view.

* Column Chart, Bar Chart, Stacked Column Chart, Stacked Bar Chart, 100% Stacked Column Chart, 100% Stacked Bar Chart.


{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series type="column" columnFacet="cylinder">
	      </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img89.png)

## RangeColumn Chart

To render a Range Column Chart, set the `type` as **"rangeColumn"** in the chart series. To change the RangeColumn color, use the `fill` property of the series.

Since, the RangeColumn series requires two y values for a point, add the `high` and `low` value. High and Low value specifies the maximum and minimum range of the points.

* When you are using the `points` option, specify the high and low values by using the `high` and `low` option of the point.

* When you are using the `dataSource` option to assign the data, you have to map the fields from the dataSource that contains high and low values by using the `series.high` and `series.low` options.  

{% highlight html %}

 <ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series type="rangeColumn" fill="#E94649">
		      <e-points>
		        <e-point x="1935" high="6.1" low="0.7"></e-point>
         </e-points>
	     </e-series>
   </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img19.png)


### Change a point color 

To change the color of a range column, you can use the `fill` property of point. 

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series>
		        <e-points>
		            <e-point fill="skyblue"></e-point>
            </e-points>
	     </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img20.png)

## Stacked Column Chart

To render a Stacked Column Chart, set the `type` as **"stackingColumn"** in the chart series. To change the StackingColumn color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series type="stackingColumn" fill="#E94649">
	  </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img21.png)


### Cluster / Group stacked columns

You can use the `stackingGroup` property to group the stacked columns. Columns with same group name are stacked on top of each other.

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <!--For grouping stacked columns-->
        <e-series type="stackingColumn" stackingGroup="GroupOne">
	      </e-series>
	      <e-series type="stackingColumn" stackingGroup="GroupTwo">
	      </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img22.png)


### Change a point color

To change the color of a stacking column, you can use the `fill` property of the point. 

{% highlight html %}

   <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
           <e-points>
               <!--Change the color of a stacking column-->
		           <e-point fill="skyblue"></e-point>
           </e-points>
	  </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img23.png)


## 100% Stacked Column Chart    

To render a 100% Stacked Column Chart, set the `type` as **"stackingColumn100"** in the chart series. To change the StackingColumn100 color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stackingColumn100" fill="#E94649">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img24.png)


### Cluster / Group 100% stacked columns

By using the `stackingGroup` property, you can group the 100% stacking columns. Columns with same group name are stacked on top of each other. 

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <!--For grouping 100% stacked columns-->
        <e-series stackingGroup="GroupOne">
	      </e-series>
	      <e-series  stackingGroup="GroupTwo">
	      </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img25.png)


### Change a point color

To change the color of a 100% stacking column, you can use the `fill` property of the point. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
             <!--Change the color of a 100% stacking column-->
	         	 <e-point fill="skyblue"></e-point>
          </e-points>
   	   </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img26.png)


## Bar Chart

To render a bar Chart, set the `type` as **"bar"** in the chart series. To change the bar color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="bar" fill="#E94649">
    	  </e-series>
     </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img27.png)


### Change the color of a bar

By using the `fill` property of the point, you can change the specific point of the series. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
            <!--Change the color of a bar series point-->
		        <e-point fill="skyblue"></e-point>
         </e-points>
	     </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img28.png)


## Stacked Bar Chart

To render a Stacked Bar Chart, set the `type` as **"stackingBar"** in the chart series. To change the StackingBar color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stackingBar" fill="#E94649">
	      </e-series>
        <e-series type="stackingBar" fill="#AFE3A3">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img29.png)


### Cluster / Group stacked bars

You can use the `stackingGroup` property to group the stacking bars with the same group name. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
          <e-series stackingGroup="GroupOne">
	        </e-series>
          <e-series stackingGroup="GroupTwo">
	        </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img30.png)


### Change a point color

You can change the color of a stacking bar by using the `fill` property of the point.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
            <!--Change the color of a stacking bar series point-->
		        <e-point fill="skyblue"></e-point>
         </e-points>
	     </e-series>
     </e-seriescollection>
   </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img31.png)


## 100% Stacked Bar Chart

To render a 100% Stacked Bar Chart, set the `type` as **"stackingBar100"** in the chart series. To change the StackingBar100 color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="stackingBar100" fill="#E94649">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img32.png)


By using the `stackingGroup` property, you can group the 100% stacking bars with the same group name. 

{% highlight html %}


<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series stackingGroup="GroupOne">
	      </e-series>
        <e-series stackingGroup="GroupTwo">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img33.png)


### Change a point color

To change the color of a 100% stacking bar, you can use the `fill` property of the point. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
            <!--Change the color of a 100% stacking bar series point-->
		        <e-point fill="skyblue"></e-point>
          </e-points>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img34.png)



## Spline Chart

To render a Spline Chart, set the `type` as **"spline"** in the chart series. To change the Spline segment color, you can use the `fill` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="spline" fill="#6ADCB0">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img35.png)


### Change the spline width

To change the spline segment width, you can use the `width` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
         <e-series width="3">
         </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img36.png)


### Dashed lines

To render the spline series with dotted lines, you can use the `dashArray` option of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series dashArray="5,5">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img37.png)


## Pie Chart

You can create a pie chart by setting the series `type` as **"pie"** in the chart series.


{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="pie">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img38.png)


### Change the pie size

You can use the `pieCoefficient` property to change the diameter of the Pie chart with respect to the plot area. It ranges from 0 to 1 and the default value is **0.8**.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series [pieCoefficient]=0.4>
  	    </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img39.png)


### Explode a pie segment

You can explode a pie segment on the chart load by using the `explodeIndex` of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series [explodeIndex]=1>
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img40.png)


### Explode all the segments

To explode all the segments of the Pie chart, you can enable the `explodeAll` property.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series [explodeAll]="true">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img41.png)


### Explode a pie segment on mouse over

To explode a pie segment on a mouse over, you can enable the `explode` property of the series.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series [explode]="true">
	      </e-series> 
      </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img42.png)


### Sector of Pie

EjChart allows you to render all the data points/segments in the semi-pie, quarter-pie or in any sector by using the `startAngle` and `endAngle` options.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [startAngle]=-90 [endAngle]=90>
 	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img43.png)


## Doughnut Chart

To create a Doughnut chart, you can specify the series `type` as **"doughnut"** in the chart series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="doughnut">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img44.png)

### Change Doughnut inner radius

You can change the doughnut chart inner radius by using the `doughnutCoefficient` with respect to the plot area. It ranges from 0 to 1 and the default value is **0.4**.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [doughnutCoefficient]=0.6>
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img45.png)


### Change the doughnut size

You can use the `doughnutSize` property to change the diameter of the Doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is **0.8**.

{% highlight html %}

   <ej-chart id="chartcontainer">

     <e-seriescollection>
        <e-series  [doughnutSize]=0.4>
	    </e-series>
     </e-seriescollection>
   </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img46.png)


### Explode a doughnut segment

To explode a specific doughnut segment, set the index to be exploded by using the `explodeIndex` option of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [explodeIndex]=1>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img47.png)


### Explode all the segments

To explode all the segments, you can enable the `explodeAll` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [explodeAll]="true">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img48.png)


### Explode a doughnut segment on mouse over

To explode a doughnut segment on a mouse over, you can enable the `explode` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [explode]="true">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img49.png)


### Sector of Doughnut

EjChart allows you to render all the data points/segments in the semi-doughnut, quarter- doughnut or in any sector by using the `startAngle` and `endAngle` options.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [startAngle]=-90 [endAngle]=90>
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img50.png)


## Multiple Pie Chart

EjChart provides support to render more than one series in pie and in doughnut chart. Radius of each series is calculated based on the radius of the previous series. And in addition legend is displayed according to the list of chart series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="pie">
        <!-- Add Points here-->
	    </e-series>
        <e-series  type="pie">
        <!-- Add Points here-->
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

**Multiple Pie** 

![](Chart-Types_images/Chart-Types_img82.png)

**Multiple Doughnut** 

![](Chart-Types_images/Chart-Types_img83.png)

### Start and End Angle Support

In the Multiple Pie chart, the start and end angle property is also supported.

**Sector of Multiple Pie**

![](Chart-Types_images/Chart-Types_img84.png)

**Sector of Multiple Doughnut**

![](Chart-Types_images/Chart-Types_img85.png)


## Pyramid Chart

To create a Pyramid chart, you can specify the series `type` as **"pyramid"** in the chart series.  

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="pyramid">
         <!-- Add Points here-->
  	    </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img51.png)

### Pyramid Mode

Pyramid mode has two types, *linear* and *surface* respectively. The default **"pyramidMode"** type is "linear".

{% highlight html %}

   <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  pyramidMode="surface">
        <!-- Add Points here-->
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img52.png)


### Gap between the segments

You can control the gap between the segments by using the `gapRatio` option of the series. Its ranges from 0 to 1.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [gapRatio]=0.1>
        <!-- Add Points here-->
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img53.png)


### Explode a pyramid segment

You can explode a pyramid segment on the chart load by using the `explodeIndex` of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [explodeIndex]=4>
          <!-- Add Points here-->
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img54.png)


## Funnel Chart

You can create a funnel chart by setting the series `type` as **"funnel"** in the chart series.  

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="funnel">
        <!-- Add Points here-->
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img55.png)


### Change the funnel width and height

Funnel segments height and width is calculated from the chart size, by default. You can change this height and width directly without changing the chart size by using the `funnelHeight` and `funnelWidth` property of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  funnelHeight="22%" funnelWidth="25%">
          <!-- Add Points here-->
	     </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img56.png)


### Explode a funnel segment

You can explode a funnel segment on the chart load by using the `explodeIndex` of the series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [explodeIndex]=3>
           <!-- Add Points here-->
	     </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img57.png)


## Bubble Chart

To create a Bubble chart, you can set the series `type` as **"bubble"** in the chart series. Bubble chart requires 3 fields (*x, y and size*) to plot a point. Here, **size** is used to specify the size of each bubble segment. 

{% highlight ts %}

this.chartData = [
         { month: 'Jan', sales: 35, profit: 1.34 },
         { month: 'Feb', sales: 28, profit: 1.05 },
         { month: 'Mar', sales: 34, profit: 0.45 },
         { month: 'Apr', sales: 32, profit: 1.10 },
        // ...     
];

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <!--Add datasource and set xName, yName and size to bubble chart-->
        <e-series  type="bubble" [dataSource]="chartData" xName="month" yName="sales" size="profit">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img58.png)


## Scatter

To create a Scatter chart, you can set the series `type` as **"scatter"**’ in the chart series. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="scatter">
           <!-- Add points here-->
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img59.png)


### Customize the scatter chart

You can change the scatter size by using the `size` property of the series marker. And you can change the scatter color by using the series `fill` property. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
         <!-- Change the scatter size and color-->
        <e-series   fill="#41F282" [marker.size.height]=13 [marker.size.width]=13>
         <!-- Add points here-->
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img60.png)


## HiLoOpenClose Chart 

To create a HiLoOpenClose chart, you can set the series `type` as **"hiloopenclose"** in the chart series. HiLoOpenClose chart requires 5 fields (`x`, `high`, `low`, `open` and `close`) to plot a segment.  


{% highlight ts %}

this.chartData = [
    { month: 'Jan', high: 38, low: 10, open: 38, close: 29 },
    { month: 'Feb', high: 28, low: 15, open: 18, close: 27 },
    { month: 'Mar', high: 54, low: 35, open: 38, close: 49 },
    { month: 'Apr', high: 52, low: 21, open: 35, close: 29 },
    // ...    
];

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
     <!--Add datasource and set xName, yName and size to hiloopenclose chart-->
        <e-series  type="hiloopenclose" [dataSource]="chartData" high="high" 
                                          low="low" open="open" close="close">
	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img61.png)


### DrawMode

You can change the HiLoOpenClose chart `drawMode` to `open`, `close` or *both*. The default value of `drawMode` is **"both"**. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series drawMode="open">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img62.png)


### Bull and Bear Color	

HiLoOpenClose chart `bullFillColor` is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and `bearFillColor` is used to specify a fill color for the segments that indicates a decrease in the stock price in the measured time interval. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
         <e-series bullFillColor="#FF6600" bearFillColor="#336600">
	       </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img63.png)


## Candle

You can create a Candle chart by specifying the series `type` as **"candle"** in the chart series. Candle chart requires 5 fields (`x`, `high`, `low`, `open` and `close`) to plot a segment.

{% highlight ts %}

this.chartData = [
    { month: 'Jan', high: 38, low: 10, open: 38, close: 29 },
    { month: 'Feb', high: 28, low: 15, open: 18, close: 27 },
    { month: 'Mar', high: 54, low: 35, open: 38, close: 49 },
    { month: 'Apr', high: 52, low: 21, open: 35, close: 29 },
    // ...    
];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <!--Add datasource and set xName, yName and size to candle chart-->
        <e-series  type="candle" [dataSource]="chartData" high="high" low="low" 
                                                      open="open" close="close">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img64.png)

### Bull and Bear Color

Candle chart `bullFillColor` is used to specify a fill color for the segments that indicates an increase in the stock price in the measured time interval and `bearFillColor` is used to specify a fill color for the segments that indicates a decrease in the stock price in the measured time interval.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series bullFillColor="#FF6600" bearFillColor="#336600">
	    </e-series>
     </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img65.png)


## HiLo

HiLo chart is created by setting the series `type` as **"hilo"** in the chart series. HiLo chart requires 3 fields (`x`, `high` and `low`) to plot a segment.  

{% highlight ts %}

this.chartData = [
        { month: 'Jan', high: 38, low: 34 },
        { month: 'Feb', high: 28, low: 15 },
        { month: 'Mar', high: 54, low: 45 },
        { month: 'Apr', high: 32, low: 21 },
        // ...     
];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <!--Add datasource and set xName, yName and size to hilo chart-->
        <e-series  type="hilo" [dataSource]="chartData" high="high" low="low">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img66.png)

## Polar

Polar chart is created by setting the series `type` as **polar** in the chart series. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  type="polar">
   	    </e-series>
     </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img67.png)

### DrawType

Polar `drawType` property is used to change the series plotting type to *line*, *column* or *area*. The default value of `drawType` is **"line"**.  

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
     <!-- Change polar series drawType-->
        <e-series  drawType="column">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img68.png)


### Stack columns in Polar chart

By using the `isStacking` property, you can specify whether the column has to be stacked when the `drawType` is column. Its default value is **false**.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series  [isStacking]="true">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img69.png)


## Radar Chart  

To create a Radar chart, you can specify the series `type` as **"radar"** in the chart series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="radar">
   	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img70.png)


### DrawType

Radar `drawType` property is used to change the series plotting type to *line*, *column* or *area*. The default value of `drawType` is **"line"**.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <!-- Change polar series drawType-->
        <e-series  drawType="column">
  	    </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img71.png)


### Stack columns in Radar chart

By using the `isStacking` property, you can specify whether the column has to be stacked when the `drawType` is set as *column*. Its default value is set to **false**.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
         <e-series  [isStacking]="true">
   	     </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img72.png)


## Waterfall Chart 

For rendering a Waterfall chart, set series `type` as **"waterfall"** in the chart series. To change the waterfall series segment color use `fill` option of series and use `positiveFill` property to differentiate the positive segments.

N> The inline property of the **series.positiveFill** has the first priority and override the **series.fill**.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="waterfall" fill="#C64E4A" positiveFill="#C64E4A">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img73.png)


**ShowIntermediateSum**

To display the summary of values since the last intermediate point of the waterfall series, set **showIntermediateSum** property as true in the specific point.


{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
		         <e-point x="Intermediate sum" [showIntermediateSum]="true"></e-point>
          </e-points>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}


**ShowTotalSum**

The sum of all previous point in the waterfall series is displayed on enabling the **showTotalSum** property for a specific point.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series>
          <e-points>
		           <e-point x="Total sum" [showTotalSum]="true"></e-point>
          </e-points>
	    </e-series>
     </e-seriescollection>
 </ej-chart>

{% endhighlight %}


### ConnectorLine

To customize the connector line color, width, opacity and dashArray of the waterfall series, you can use `connectorLine` option of series.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="waterfall" connectorLine.color="#333000" [connectorLine.width]=2 [connectorLine.opacity]=0.8 connectorLine.dashArray="3,2">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img74.png)


## Error bar Chart 

EjChart can generate Error bar for Cartesian type series *(Line, Column, Bar, Scatter, Area, Candle, HiLo, etc.)*. To render the Error bar for the series, set `visibility` as *"visible"* to `errorBar` in the series.


{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series type="line" errorBar.visibility="visible">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img75.png)


### Changing Error Bar Type

You can change the error bar rendering type using `type` *(like fixedValue, percentage, standardDeviation, standardError and custom)* option of errorBar. To change the error bar line length you can use `verticalErrorValue` property.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series errorBar.type="percentage" [errorBar.verticalErrorValue]=3>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img76.png)


#### Customizing error bar type              

To customize the error bar type, set error bar `type` as **"custom"** and then change the horizontal/vertical positive and negative value of error bar.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series errorBar.type="custom" [errorBar.verticalPositiveErrorValue]=5 
         [errorBar.horizontalPositiveErrorValue]=1 [errorBar.verticalNegativeErrorValue]=5 
          [errorBar.horizontalNegativeErrorValue]=1>
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img77.png)


### Changing Error Bar Mode

Error bar mode is used to define whether the error bar line has to be drawn *horizontally, vertically* or in *both* side.  To change the error bar mode use `errorBar.mode` option.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series errorBar.type="fixedValue" errorBar.mode="vertical">
	      </e-series>
     </e-seriescollection>
   </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img78.png)


### Changing Error Bar Direction

You can change the error bar direction to plus, minus or both side using `errorBar.directions` option.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series errorBar.type="fixedValue" errorBar.mode="vertical" errorBar.direction="minus">
	      </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img79.png)


### Customizing Error bar cap

To customize the error bar cap *visibility, length, width* and *fill* color, you can use `cap` option in the **series.errorBar**.

{% highlight html %}

 <ej-chart id="chartcontainer">
     <e-seriescollection>
        <e-series [errorBar.cap.visible]="true" [errorBar.cap.length]=20
                      [errorBar.cap.width]=5 errorBar.cap.fill="#0000FF">
  	    </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img80.png)


## Box and Whisker Chart 

To render a Box and Whisker Chart, set the series `type` as **"boxandwhisker"**.Box and Whisker chart requires
2 fields (x and y) to plot a segment. The feild y requires n number of data or it contains minimum five values to plot a segment.

{% highlight html %}

         this.chartData = 
         [ { x: 'Development',
           y: [22,22,23,25,25,25,26,27,27,28,28,29,30,32,34,32,34,36,35,38]  }, 
         { x: 'Testing', y: [22,33,23,25,26,28,29,30,34,33,32,31,50]  }, 
         { x: 'HR', y: [22,24,25,30,32,34,36,38,39,41,35,36,40,56]  }, 
         { x: 'Finance', y: [26,27,28,30,32,34,35,37,35,37,45]  }, 
         { x: 'R&D',y: [26, 27, 29, 32, 34, 35, 36, 37, 38, 39, 41, 43, 58] }, 
         // ...
       ];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
         <!--Add datasource and set xName, yName -->
           <e-series type="boxandwhisker" [datasource]="chartData">
           </e-series>
     </e-seriescollection>
  </ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img90.png)

### BoxPlotMode

You can change the rendering mode of the  Box and Whisker series using the `boxPlotMode` property. The default value of `boxPlotMode` is **"exclusive"**.The other boxPlotModes available are `inclusive` and `normal`. 

{% highlight html %}

<ej-chart id="chartcontainer">
        <e-seriescollection>
            <e-series boxPlotMode="inclusive">
            </e-series>
        </e-seriescollection>
</ej-chart>

{% endhighlight %}

### ShowMedian

Box and Whisker `showMedian` property is used to show the box and whisker average value. The default value of `showMedian` is **"false"**.  

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series showMedian="true">
        </e-series>
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img91.png)

###  Customize the Outlier

Outlier symbol, width and height can be customized using outlierSettings through `outlierSettings` property. By default Outlier symbol is displayed as circle with a height and width of 6 pixels.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
           <e-series outlierSettings.shape="triangle" 
                   [outlierSettings.size.width]=10 
                   [outlierSettings.size.height]=10>
           </e-series>
     </e-seriescollection>
</ej-chart>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img92.png)

[Click](http://ng2jq.syncfusion.com/#/chart/box) here to view the Box and Whisker Chart online demo sample.

## Pie Of Pie Chart

To render the pie of pie chart, set the series `type` as **pieofpie**. Pie of pie chart is used for displaying the data of a pie slice as another pie chart. The values in the second pie is displayed based on the **splitMode**  property.

{% highlight html %}

 <ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series type="pieofpie" [splitvalue]="10">
		      <e-points>
		       <e-point x="Saudi Arabia" [y]="58" text='58%'></e-point>
		       <e-point x="Persian Gulf" [y]="15"  text='15%'></e-point>
		       <e-point x="Canada" [y]="13" text='13%'></e-point>
		       <e-point x="Venezula" [y]="8" text='8%'></e-point>
		       <e-point x="Mexico" [y]="3" text='3%'></e-point>
		       <e-point x="Russia" [y]="2" text='2%'></e-point>
		       <e-point x="Miscellaneous" [y]="1" text='1%'></e-point>
         </e-points>
	  </e-series>
   </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img93.png)

[Click](http://ng2jq.syncfusion.com/#/chart/pieofpie) here to view the Pie Of Pie Chart online demo sample.

### Split Mode and Split Value 

The points to be displayed in the second pie is decided based on the `splitMode`property.**SplitMode** property takes the following values. 
* Position – Have to split the data points based on its position
* Value – Have to split the data points based on its Y value
* Percentage – Have to split the points based on the percentage value
* Indexes – The data points with the specified indexes are split separately 
 By default, the splitMode is set to  **Value**. 

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
           <e-series splitMode="position" [splitValue]="3"> 
           </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img94.png)

### Changing Pie Of Pie Size

The size of the second Pie can be customized by using the `pieOfPieCoefficient` property. The default value of pieOfPieCoefficient is **0.6**.Its value ranges from 0 to 1.

{% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
           <e-series pieofpiecoefficient="1"> 
           </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

The following screenshot represents the pie of pie series with pieOfPieCoefficient as 1

![](Chart-Types_images/Chart-Types_img95.png)

#### Customizing the Gap

The distance between the two pies in the pie of pie chart can be controlled by using the `gapWidth` property. The default value is **50**.

 {% highlight html %}

<ej-chart id="chartcontainer">
     <e-seriescollection>
           <e-series gapWidth="150"> 
           </e-series>
     </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img96.png)






