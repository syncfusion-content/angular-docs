---
layout: post
title: Chart Axis
description: How to customize the grid lines, tick lines, labels and title of chart axis
platform: angular2
control: Chart
documentation: ug
---

# Axis

**Charts** typically have two axes that are used to measure and categorize data: a vertical (y) axis, and a horizontal (x) axis.

Vertical axis always uses numerical or logarithmic scale. Horizontal(x) axis supports the following types of scale:

* Category
* Numeric
* DateTime
* DateTime Category
* Logarithmic

## Category Axis

Category axis displays the text labels instead of numbers. To use the categorical axis, you can set the `valueType` property of the axis to the **category**. Default value of `valueType` is **double**.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.valueType="category">
   
</ej-chart>


{% endhighlight %}



![](Axis_images/axis_img1.png)


### Place labels on ticks

Labels in the category axis can be placed on the ticks by setting the `labelPlacement` property of axis to the **onticks**. The default value of the `labelPlacement` property is **betweenticks** i.e. labels are placed between the ticks, by default.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.valueType="category" primaryXAxis.labelPlacement="onticks">
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img2.png)


### Display labels after a fixed interval

To display the labels after a fixed interval n, you can set the `interval` property of the axis range as **n**. The default value of the interval is 1 i.e. all the labels are displayed.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.range.interval]=2>
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img3.png)


### Indexed Category Axis

Category axis can also plot points based on index value of data points. Index based plotting can be enabled by setting `isIndexed` property to true in the axis.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.isIndexed]="true">
  <e-seriescollection>
   <e-series>
		  <e-points>
		      <e-point x="Monday" [y]="50"></e-point>
      		<e-point x="Tuesday" [y]="40"></e-point>
		      <e-point x="Wednesday" [y]="70"></e-point>
		      <e-point x="Thursday" [y]="60"></e-point>
		      <e-point x="Friday" [y]="50"></e-point>
          <e-point x="Monday" [y]="40"></e-point>
		      <e-point x="Monday" [y]="30"></e-point>
      </e-points>
	  </e-series>
  </e-seriescollection>
	
</ej-chart>

{% endhighlight %}


![](Axis_images/axis_img50.png)

**While Category axis isIndexed value false**

![](Axis_images/axis_img51.png)


## Numeric Axis 

Numeric axis uses numerical scale and displays numbers as labels. To use numeric axis, you can set the `valueType` property of the axis to **double**. 

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.valueType="double">
   
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img4.png)


### Customize numeric range

To customize the range of an axis, you can use the `range` property of the axis to set the `minimum`, `maximum` and `interval` values. Nice range is calculated automatically based on the provided data, by default.


{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.range.min]=0 [primaryYAxis.range.max]=60>
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img5.png)


#### Customizing numeric interval

Axis interval can be customized by using the `interval` property of the axis range. Nice interval is calculated based on the minimum and maximum value of the provided data, by default.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.range.interval]=5>
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img6.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the axis range by using the `rangePadding` property. Numeric axis supports the following types of padding

* None
* Round
* Additional
* Normal

**None**

When the value of the `rangePadding` property is **none**, padding can not be applied to the axis. This is also the default value of the rangePadding. 

{% highlight html %}

<ej-chart id="chartcontainer" primaryYAxis.rangePadding="none">
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img7.png)


#### Round

When the value of `rangePadding` property is **round**, the axis range is rounded to the nearest possible value divided by the interval.

{% highlight html %}

<ej-chart id="chartcontainer" primaryYAxis.rangePadding="round">
   
</ej-chart>


{% endhighlight %}

**Chart before rounding axis range**

![](Axis_images/axis_img8.png)



**Chart after rounding axis range**

![](Axis_images/axis_img9.png)

**Additional**

When the value of the `rangePadding` property is **additional**, the axis range is rounded and an interval of the axis is added as padding to the minimum and maximum values of the range.

{% highlight html %}

<ej-chart id="chartcontainer" primaryYAxis.rangePadding="additional">
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img10.png)


**Normal**

When the value of the `rangePadding` property is **normal**, the padding is applied to the axis based on the range calculation.

{% highlight html %}

<ej-chart id="chartcontainer" primaryYAxis.rangePadding="normal">
   
</ej-chart>


{% endhighlight %}

![](Axis_images/axis_img11.png)

#### Customizing the starting range of the axis

By default the Y axis will be always calculated from the value 0 for column, bar, stacking column and stacking bar series types. You can modify this behavior by setting false to the property `startFromZero` in the axis. On setting this the axis minimum value will be calculated based on the value for the data points.

{% highlight html %}


<ej-chart id="chartcontainer" primaryYAxis.rangePadding="none" primaryYAxis.startfromZero="false">
   
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img66.png)

## DateTime Axis

Date time axis uses date time scale and displays the date time values as axis labels in the specified format. To use date time axis, set the `valueType` property of the axis to **datetime**.

{% highlight html %}

<ej-chart id="chartcontainer" primaryYAxis.valueType="datetime">
   
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img12.png)


### Customizing date time range
 
 Axis range can be customized by using the `range` property to set the `minimum`, `maximum` and `interval` values. Nice range is calculated automatically based on the provided data, by default.
 
 {% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.range.min]="2000/6/1" 
                                  [primaryXAxis.range.max]="2010/6/1">
   
</ej-chart>
      

{% endhighlight %}

![](Axis_images/axis_img13.png)


### Date time intervals

Date time intervals can be customized by using the `interval` and `intervalType` properties of the axis. For example, when you set *interval* as **2** and `intervalType` as **years**, it considers the 2 years as interval.

Essential Chart supports the following types of interval for date time axis.

* Days
* Hours
* Milliseconds
* Minutes
* Months
* Seconds
* Years

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.intervalType="years" [primaryXAxis.range.interval]=2>
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %}


![](Axis_images/axis_img14.png)


### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the range by using the `rangePadding` property. Date time axis supports the following types of padding

* None
* Round
* Additional

**None**

When the value of the `rangePadding` property is **none**, padding is applied to the axis. This is also the default value of the rangePadding. 

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.rangePadding="none">
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %} 

![](Axis_images/axis_img15.png)

**Round**

When the value of the `rangePadding` property is **round**, the axis range is rounded to the nearest possible date time value.

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.rangePadding="round">
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %} 

**Chart before rounding axis range**

![](Axis_images/axis_img16.png)


**Chart after rounding axis range**

![](Axis_images/axis_img17.png)

**Additional** 

When the value of the `rangePadding` property is **additional**, the range is rounded and date time interval of the axis are added as padding to the minimum and maximum extremes of the range.

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.rangePadding="additional">
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %} 

![](Axis_images/axis_img18.png)


## DateTime Category Axis

DateTime category axis takes date time value as input but behaves like category axis. This is used to display the date time values with nonlinear intervals (used to depict the business days by skipping holidays). To use date time axis, set the `valueType` property of the axis to **datetimeCategory**.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.valueType="datetimecategory">
   
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img63.png)

 [Click](http://ng2jq.syncfusion.com/#/chart/datetimeCategory) here to view our online demo sample for date time axis.

### Customizing DateTime Category range

Axis range can be customized by using the `range` property to set the `minimum`, `maximum` and `interval` values. Datetime category axis takes numeric input for minimum and maximum property.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.range.min]="0" 
                                  [primaryXAxis.range.max]="4">
   
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img64.png)

### DateTime Category intervals

Date time category intervals can be customized by using the `interval`and `intervalType` properties of the axis. For example, when you set the intervalType as months, it displays only the first label of all the months from the data.

Essential Chart supports the following types of interval for date time category axis.
* Days
* Hours
* Milliseconds
* Minutes
* Months
* Seconds
* Years
* Auto

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.intervalType="months" >
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %}

![](Axis_images/axis_img65.png)


## Logarithmic Axis

Logarithmic axis uses logarithmic scale and it is very useful in visualizing when the data has values with both lower order of magnitude **(eg: 10<sup>-6</sup>)** and higher order of magnitude **(eg: 10<sup>6</sup>)**. To use logarithmic axis, set the `valueType` property of the axis to **logarithmic**.  

{% highlight html %}

 <ej-chart id="chartcontainer" primaryXAxis.valueType="logarithmic">
   <!-- Write series code here-->
 </ej-chart>

{% endhighlight %}


![](Axis_images/axis_img19.png)


### Customize Logarithmic range

Logarithmic range can be customized by using the `range` property of the axis to change the `minimum`, `maximum` and `interval` values. Nice range is calculated automatically based on the provided data, by default.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.range.min]="1" [primaryYAxis.range.max]="5">
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img20.png)


### Logarithmic base

Logarithmic base can be customized by using the `logBase` property of the axis. The default value of the **logBase** is **10**.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.logBase]=2>
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img21.png)


### Logarithmic interval

Logarithmic axis interval can be customized by using the `interval` property of the axis. When the logarithmic base is 10 and logarithmic interval is 2, then the axis labels are placed at an interval of 10<sup>2</sup>. The default value of the interval is 1. 

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.range.interval]=2>
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img22.png)


## Label Format

### Format numeric labels

Numeric labels can be formatted by using the `labelFormat` property. Numeric values can be formatted with n (number with decimal points), c (currency) and p (percentage) commands.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.labelFormat="c">
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img23.png)

The following table describes the result of applying some commonly used label formats on numeric values. 
 
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>        
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The Number is rounded to 1 decimal place</td>
</tr> 
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The Number is rounded to 2 decimal place</td>
</tr> 
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1,000.0</td>
<td>The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1,000.00</td>
<td>The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
</table>


### Format date time values

Date time labels can be formatted by using the `labelFormat` property of the axis.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.labelFormat="dd/MMMM/yyyy">
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img24.png)


The following table describes the result of applying some common date time formats to the labelFormat property

<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format Property Value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>        
<tr>
<td>new Date(2000, 03, 10)</td>
<td>dddd</td>
<td>Monday</td>
<td>The Date is displayed in day format</td>
</tr> 
<tr>
<td>new Date(2000, 03, 10)</td>
<td>MM/dd/yyyy</td>
<td>04/10/2000</td>
<td>The Date is displayed in month/date/year format</td>
</tr> 
<tr>
<td>new Date(2000, 03, 10)</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>MMM</td>
<td>Apr</td>
<td>The Shorthand month for the date is displayed</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>t</td>
<td>12:00 AM</td>
<td>Time of the date value is displayed as label</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>hh:mm:ss</td>
<td>12:00:00</td>
<td>The Label is displayed in hours:minutes:seconds format</td>
</tr>
</table>

### Custom label format

Prefix and suffix can be added to the category labels by using the `labelFormat` property. You can use the *{value}* as placeholder text in your custom text, it is replaced with the corresponding axis label at the runtime.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.labelFormat="${value} K">
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img25.png)


## Common axis features

Customization of features such as axis crossing, title, labels, grid lines and tick lines are common to all the axis. Each of these features are explained in this section.


### Axis Crossing

Axis can be positioned anywhere in chart area using the `crossesAt` property of axis. This property specifies where the horizontal axis should intersect or cross the vertical axis and vice versa. Default value of **crossesAt** property is null.

{% highlight html %}

<!--Crosses primary Y axis at 0 -->
<ej-chart id="chartcontainer" [primaryXAxis.crossesAt]=0>
   <!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img52.png)


#### Crossing a specific Axis

The `crossesInAxis` property takes axis name as input and determines the axis used for crossing. By default all the horizontal axes crosses in primary Y axis and all the vertical axes crosses in primary X axis.

{% highlight ts %}

//  Creating a secondary axis
this.chartAxes = [{name:"secondaryYAxis", orientation: "vertical"}];

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.crossesAt]=-0.2 
       primaryXAxis.crossesInAxis="secondaryYAxis" [axes]="chartAxes">

</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img53.png)

Axis will be placed in the opposite side if value of `crossesAt` property is greater than the maximum value of crossing axis (axis name provided through `crossesInAxis` property or primary Y axis for horizontal axis).

{% highlight html %}
   
<!--Crosses primary Y axis at 200 -->
<ej-chart id="chartcontainer" [primaryXAxis.crossesAt]=200>
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img54.png)


#### Crossing in DateTime Axis

For crossing in a date time horizontal axis, date object should be provided as value for `crossesAt` property of vertical axes.

{% highlight html %}


<!--Crosses primary Y axis at "2010/4/29" -->
<ej-chart id="chartcontainer" primaryXAxis.crossesAt="2010/4/29">
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img55.png)


#### Crossing in Category Axis

For crossing in a category type horizontal axis, either a string object or a number corresponding to the index of category value can be used for `crossesAt` property of vertical axes.

W> String value provided for `crossesAt` property is case-sensitive. 


{% highlight html %}

<!--Crosses horizontal axis at category value "Third" -->
<ej-chart id="chartcontainer" primaryXAxis.crossesAt="Tuesday">
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img56.png)

#### Positioning the axis elements while crossing

The `showNextToAxisLine`property is used for controlling the axis elements movement along with the axis line while axis crossing is performed. When the showNextToAxisLine is set as false only the axis line and the tick lines are placed at the crossing Value and the axis elements will be placed outside the chart area. The default value of `showNextToAxisLine` is **true**.  

{% highlight html %}

 <!--Crosses horizontal axis at category value "zero" -->
<ej-chart id="chartcontainer" primaryXAxis.crossesAt="0" primaryXAxis.showNextToAxisLine="false">
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img67.png)


### Axis Visibility

Axis visibility can be controlled by using the `visible` property of the axis. The default value of the *visible* property is **true**. 

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.visible]="false" >
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img26.png)


### Axis title

The `title` property in the axis provides options to customize the text and font of the axis title. Axis does not display the title, by default. Title text can also be trimmed based on the title text length or specified length.

{% highlight ts %}

//Customize title font style
this.titleFont={fontFamily:"Segoe UI", fontWeight: "bold", size: "16px", color: "grey"};

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.title.text="Month"  
                             [primaryXAxis.title.font]="titleFont">
<!-- Write series code here -->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img27.png)

You can modify the position of the axis title either inside or outside the chart area using the property `position`. By default, it will be placed outside the chart area. In addition, you can also change the alignment of the title to near, far and center by `alignment` property, using `offset` property you can change the position with respect to pixels.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.title.text="Month" primaryXAxis.title.position="inside" primaryXAxis.title.alignment="near" [primaryXAxis.title.offset]=10>

 <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img62.png)

### Label customization

The `font` property of the axis provides options to customize the `font-family`, `color`, `opacity`, `size` and `font-weight` of the axis labels.  

{% highlight html %}


<ej-chart id="chartcontainer" primaryXAxis.font.size="16px" 
          primaryXAxis.font.fontFamily="Segoe UI" primaryXAxis.font.fontWeight="bold" 
          primaryXAxis.font.color="blue">

  <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img28.png)


### Label and tick positioning
 
Axis labels and ticks can be positioned inside or outside the chart area by using the `labelPosition` and `tickPosition` properties. The labels and ticks are positioned outside the chart area, by default.
 
{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.labelPosition="inside"
                          primaryXAxis.tickLinesPosition="inside">
   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img29.png)


### Edge labels placement

Labels with long text at the edges of an axis may appear partially outside the chart. The `edgeLabelPlacement` property can be used to avoid the partial appearance of the labels at the corners. 

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.edgeLabelPlacement="shift">

  <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

**Chart before setting edge label placement to X-axis**

![](Axis_images/axis_img30.png)


**Chart after setting edge label placement to X-axis**

![](Axis_images/axis_img31.png)


### Grid lines customization

The `majorGridLines` and `minorGridLines` properties in the axis are used to customize the major grid lines and minor grid lines of an axis. They provide options to change the width, color, visibility and opacity of the grid lines. The minor grid lines are not visible, by default.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.majorGridLines.color="blue" 
            [primaryXAxis.majorGridLines.visible]="true" [primaryXAxis.majorGridLines.width]=1
            primaryXAxis.minorGridLines.color="red" 
            [primaryXAxis.minorGridLines.visible]="false" [primaryXAxis.minorGridLines.width]=1
            [primaryXAxis.minorTicksPerInterval]=0 >

   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img32.png)


### Tick lines customization

The `majorTickLines` and `minorTickLines` properties in the axis are used to customize the major tick lines of an axis and minor tick lines of an axis. They provide options to change the width, size, color and visibility of the grid lines. The minor tick lines are not visible, by default.

{% highlight html %}


<ej-chart id="chartcontainer" primaryXAxis.majorTickLines.color="blue" 
          [primaryXAxis.majorTickLines.width]=1 [primaryXAxis.majorTickLines.size]=10
          primaryXAxis.minorTickLines.color="red" [primaryXAxis.minorTickLines.visible]="false" 
          [primaryXAxis.minorTickLines.width]=1 [primaryXAxis.minorTickLines.size]=5
					primaryXAxis.majorTickLines.visible]="true" [primaryXAxis.minorTicksPerInterval]=0 >

   <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

![](Axis_images/axis_img33.png)

  
### Inversing axis

Axis can be inversed by using the `isInversed` property of the axis. The default value of the `isInversed` property is **false**.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.isInversed]="true" >
      <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

**Chart before inversing the axes**

![](Axis_images/axis_img34.png)


**Chart after inversing the axes**

![](Axis_images/axis_img35.png)

   

### Place axes at the opposite side

The `opposedPosition` property of axis can be used to place the axis at the opposite side of its default position. The default value of the `opposedPosition` property is **false**. 

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.opposedPosition]="true" >
     <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

**Chart with X and Y axes at normal position**

![](Axis_images/axis_img36.png)


**Chart with Y-axis at opposed position**

![](Axis_images/axis_img37.png)


### Maximum number of labels per 100 pixels

A maximum of 3 labels are displayed for each 100 pixels in the axis, by default. The maximum number of labels that is present within the 100 pixels length can be customized by using the `maximumLabels` property of the axis. This property is applicable only for an automatic range calculation and it does not work when you set the value for **interval** property in the axis range.

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.maximumLabels]="true" >
     <!-- Write series code here-->
</ej-chart>

{% endhighlight %}

**Chart before setting maximum labels per 100 pixels**

![](Axis_images/axis_img38.png)


**Chart after setting maximum labels one per 100 pixels**

![](Axis_images/axis_img39.png)


## Multiple Axis

Multiple axes can be used in the Chart and chart area can be split into multiple panes to draw multiple series with multiple axes.

![](Axis_images/axis_img40.png)

An additional horizontal or vertical axis can be added to the chart by adding an axis instance to the **axes** collection and then you can associate it to a series by specifying the name of the axis to the `xAxisName` or `yAxisName` property of the series.

{% highlight ts %}

//  Creating a secondary X & Y - axis
this.chartAxes = [{name:"SecondaryXAxis"}, {name:"SecondaryYAxis"}];

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer" style="display:block;" [axes]="chartAxes" >

   <!-- Write series code here-->
      <e-seriescollection>
           <!-- Bind secondary axis name to series -->
           <e-series xAxisName="SecondaryXAxis" yAxisName="SecondaryYAxis">
	       </e-series>
      </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Axis_images/axis_img41.png)


## Smart Axis Labels

When the Axis labels overlap with each other based on the chart dimensions and label size, you can use the `labelIntersectAction` property of the axis to avoid overlapping. The default value of the *labelIntersectAction* is **none**. The other available values of the Label Intersect Actions are **rotate45**, **rotate90**, **trim**, **multipleRows**, **wrap**, **wrapByWord** and **hide**.

{% highlight html %}

<ej-chart id="chartcontainer" primaryXAxis.labelIntersectAction="multipleRows">
     <!-- Write series code here-->
</ej-chart>

{% endhighlight %}



![](Axis_images/axis_img42.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **rotate45**.

![](Axis_images/axis_img43.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **rotate90**.

![](Axis_images/axis_img44.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **wrap**.

![](Axis_images/axis_img45.png)


The following screenshot displays the result, when of setting the **trim** as value to the *labelIntersectAction* property.

![](Axis_images/axis_img46.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **hide**.

![](Axis_images/axis_img47.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **multipleRows **.

![](Axis_images/axis_img48.png)


The following screenshot displays the result, when the *labelIntersectAction* property is set as **wrapByWord**.

![](Axis_images/axis_img49.png)

## Multi-level Labels
Axis can be customized with multiple levels of labels using the `multiLevelLabels` property. These labels are placed based on the start and end range values and we can add any number of labels to an axis.

{% highlight ts %}       

this.multiLabels = [{ 
        visible: true,
        start: -0.5,
        end: 2.5,
        text: "Quater1"
   }]; 

{% endhighlight %}

{% highlight html %}       

<ej-chart id="chartcontainer" [primaryXAxis.multiLevelLabels]="multiLabels">
       <!-- Write series code here-->
</ej-chart> 

{% endhighlight %}

![](Axis_images/axis_img57.png)

### Customizing the multi-Level labels
The color, width and type of the border can be customized. The default border type is `Rectangle`. And the other supported border types are namely brace, curly brace, without top/bottom border and none. 

{% highlight ts %}

this.multiLabels = [{ 
        //...
        // customizing the border properties 
        border:{
           type: "brace",
           width: 2,
           color: "black"
         }
}]; 

{% endhighlight %}

{% highlight html %}       

<ej-chart id="chartcontainer" [primaryXAxis.multiLevelLabels]="multiLabels">
    <!-- Write series code here-->
</ej-chart> 

{% endhighlight %}

![](Axis_images/axis_img58.png)

The text of the labels can be customized using the `text` and `font` properties 

{% highlight ts %}

this.multiLabels = [{ 
      //...
      // customizing the text and font properties
      text: "Year - 2015",
      font:{
         fontFamily: "Algerian", 
         size: "12px",
         color: "black"                            
       }
   }];

{% endhighlight %}

{% highlight html %}       

<ej-chart id="chartcontainer" [primaryXAxis.multiLevelLabels]="multiLabels">
         <!-- Write series code here-->
  </ej-chart> 

{% endhighlight %}

![](Axis_images/axis_img59.png)

You can change the alignment of the text to far, near and center position using the `textAlignment` property. By default, the text will be center aligned. 

{% highlight ts %}

  this.multiLabels = [{ 
         //...
         // customizing the text alignment
         textAlignment: "far",
    }];

{% endhighlight %}

{% highlight html %}       

<ej-chart id="chartcontainer" [primaryXAxis.multiLevelLabels]="multiLabels">
    <!-- Write series code here-->
</ej-chart> 

{% endhighlight %}

![](Axis_images/axis_img60.png)

You can trim, wrap or wrapAndTrim the text if it exceeds the maximum text width value using the property `textOverflow`

{% highlight ts %}

this.multiLabels = [{ 
      //...
      // customizing the text overflow  
      textOverflow: “trim", 
      maximumtextWidth: 40 
  }];          

{% endhighlight %}

{% highlight html %}       

<ej-chart id="chartcontainer" [primaryXAxis.multiLevelLabels]="multiLabels">
         <!-- Write series code here-->
</ej-chart> 

{% endhighlight %}

The below screenshot shows the trimmed multi-level labels

![](Axis_images/axis_img61.png)

And these labels can be placed in various rows using the `level` property.