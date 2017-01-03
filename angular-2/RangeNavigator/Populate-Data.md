---
layout: post
title: Populate-Data
description: Populate Data
platform: angular2
control: RangeNavigator
documentation: ug
---

### Populate Data

When you provide data to **RangeNavigator**, it produces limited set of data. You can populate the **RangeNavigator** with data using the **dataSource** and **series** properties.

#### Add series to the RangeNavigator

The **Series** property provides access to a collection of all series that are defined explicitly within a **RangeNavigator** control. Each series is assigned with type and name. It contains collection of data point, each point contains x value and y values. You can add data points to the series through **dataSource** property.



{% highlight ts %}

this.rangeData = function GetData() {
    var series1 = [];
    var value = 100;
    for (var i = 1; i < 360; i++) {
        if (Math.random() > .5) {
            value += Math.random();
        } else {
            value -= Math.random();
        }
        var point1 = { XValue: new Date(2010, 0, i), YValue: value };
        series1.push(point1);
    }
    return data;
};

{% endhighlight %}

{% highlight html %}

<ej-rangenavigator align="center" id="rangecontainer" enableDefferedUpdate="true" padding="15" 
               (load)="onrnload($event)" [dataSource]="rangeData" xName="XValue" yName="YValue" 
               [allowSnapping]="true"    selectedRangeSettings.start="2010/5/1" padding="15" 
               selectedRangeSettings.end="2010/10/1" [isResponsive]="true" 
               sizeSettings.height="120" theme="azuredark">
</ej-rangenavigator>

{% endhighlight %}


The following screenshot illustrates the **RangeNavigator** that is populated with data using **dataSource** property in series.

![](Populate-Data_images/Populate-Data_img1.png) 
