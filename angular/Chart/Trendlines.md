---
layout: post
title: Trendlines in Essential Angular 2 Chart
description: What are the different types of trendlines available in chart.
platform: Angular
control: Chart
documentation: ug
---

# Trendlines

EjChart can generate Trendlines for Cartesian type series *(Line, Column, Scatter, Area, Candle, HiLo etc.)* except bar type series. You can add more than one trendline object to the `trendlines`(../api/ejchart#members:series-trendlines) option.

{% highlight ts %}

this.ChartTrendlines= [{
     //Enable Trendline to chart series
     visibility: "visible", type: "linear"
   }];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img1.png)


## Customize the trendline styles

A trendline can be customized by using the properties such as `fill`, `width`, **dashArray** and **opacity**. The default type of trendline is **"linear"**.

{% highlight ts %}

this.ChartTrendlines = [{
    //...
    //Customize the Trendline styles
    fill: '#99CCFF', width: 3, opacity: 1, dashArray: '2,3'
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img2.png)



## Types of Trendline

EjChart supports the following type of Trendlines.

* Linear
* Exponential
* Logarithmic
* Power 
* Polynomial
* MovingAverage

### Linear

To render Linear Trendline, you have to set the `type` as **"linear"**. 

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type
    type: "linear"
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img3.png)


### Exponential

Exponential Trendline can be rendered by setting the `type` as **"exponential"**. 

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type
    type: "exponential"
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Trendlines_images/Trendlines_img4.png)


### Logarithmic

Logarithmic Trendline can be rendered by setting the `type` as **"Logarithmic"**.  

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type
    type: "logarithmic"
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Trendlines_images/Trendlines_img5.png)


### Power

Power Trendline can be rendered by setting the `type` of the trendline as **"power"**. 

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type
    type: "power"
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Trendlines_images/Trendlines_img6.png)


### Polynomial

Polynomial Trendline can be rendered by setting the trendline `type` as **"polynomial"**.  You can change the polynomial order by using the **polynomialOrder** of the trendlines. It ranges from 2 to 6.

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type
    type: "polynomial"
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}


![](Trendlines_images/Trendlines_img7.png)



### MovingAverage

MovingAverage Trendline can be rendered by setting the `type` of the trendline as **"movingAverage"**. 

{% highlight ts %}

this.ChartTrendlines = [{
    //Change Trendline type and set period for moving average
    type: "movingAverage", period: 3
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img8.png)

## Forecasting

**Trendline forecasting** is the prediction of future/past situations.  **Forecasting** can be classified into two types as follows.

  * Forward Forecasting
  * Backward Forecasting

### Forward Forecasting

The value set for `forwardForecast` is used to determine the distance moving towards the future trend.

{% highlight ts %}

this.ChartTrendlines = [{
    //...
    //Set forward forecasting value
    forwardForecast: 5
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img9.png)



### Backward Forecasting

The value set for the `backwardForecast` is used to determine the past trends.

{% highlight ts %}

this.ChartTrendlines = [{
    //...
    //Set forward forecasting value
    backwardForecast: 5
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img10.png)


## Trendlines Legend

To display the legend item for trendline, use the `name` property. You can interact with the trendline legends similar to the series legends *(show/hide trendlines on legend click)*.  

{% highlight ts %}

this.ChartTrendlines = [{
    //...
    //Set Trendline name to display in the legend
    name: 'Linear'
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer">
    <e-seriescollection>
        <e-series [trendlines]="ChartTrendlines"> 		
		</e-series>		
    </e-seriescollection>
</ej-chart>

{% endhighlight %}

![](Trendlines_images/Trendlines_img11.png)
