---
layout: post
title: Dimensions
description: dimensions
platform: Angular
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Dimensions

## Set size in percentage

You can customize the PivotChart dimension by setting the width and height of the control in percentage.

{% tabs %}

{% highlight html %}
<ej-pivotchart [size]="size">
    </ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; 
    constructor() {
      //..
      this.size = { height: "80%", width: "80%" }; //Set size to Chart container  
    }
}

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    width:100%;
    height:450px;
}

{% endhighlight %}

{% endtabs %}

## Set size in pixels

You can customize the PivotChart dimension by setting the width and height of the control in pixels.

{% tabs %}

{% highlight html %}
<ej-pivotchart [size]="size">
    </ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; 
    constructor() {
      //..
      this.size = { height: "950px", width: "540px" }; //Set size to Chart container  
    }
}

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    width:950px;
    height:450px;
}

{% endhighlight %}

{% endtabs %}
 
![](Dimensions_images/Dimensions.png) 

## Responsive

PivotChart control supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotChart by setting `isResponsive` property to true.


{% tabs %}

{% highlight html %}
<ej-pivotchart [isResponsive]="true" [size]="size">
    </ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; 
    constructor() {
      //..
      this.size = { height: "950px", width: "540px" }; //Set size to Chart container  
    }
}

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    min-width:525px;
    min-height:460px;
    width: 100%;
    height:450px;
}

{% endhighlight %}

{% endtabs %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

