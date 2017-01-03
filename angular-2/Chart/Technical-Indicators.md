---
layout: post
title: Technical Indicators
description: What are the different types of technical indicators supported in Essential Chart for financial analysis.
platform: angular2
control: Chart
documentation: ug
---

# Technical Indicators

EjChart control supports 10 types of technical indicators. 

## Bind data to render the indicator

You can bind the series `dataSource` to the indicator by setting the specific series name to the indicator by using the `indicators.seriesName` property.

{% highlight ts %}

this.chartindicators = [{
    //Set Hilo series dataSource to indicator using seriesName
    seriesName: "Hilo"
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series type="hiloopenclose" name="Hilo" [dataSource]="chartData" 
             xName= "xDate" high="High" low="Low" open="Open" close="Close">
	    </e-series>
  </e-seriescollection>
</ej-chart>

{% endhighlight %}


Also, you can add data to the indicator directly by using the `dataSource` option of the indicator.  

{% highlight ts %}
   
this.chartindicators = [{
    //Add dataSource to indicator directly
    dataSource: chartData,
    xName: "xDate",
    high: "High",
    low: "Low",
    open: "Open",
    close: "Close",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
</ej-chart>

{% endhighlight %}
	
## Indicator Types

### Accumulation Distribution

To create an Accumulation Distribution indicator, set the `indicators.type` as **"accumulationdistribution"**. Accumulation Distribution require **‘volume’** field additionally with the `dataSource` to calculate the signal line.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "accumulationdistribution",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
            high="High"  low="Low" open="Open" close="Close" volume="Volume">
	    </e-series>
   </e-seriescollection>
   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img1.png)

### Average True Range (ATR)

You can create an ATR indicator by setting the `indicators.type` as **"atr"** in the `indicators`. 

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "atr",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                       high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img2.png)

### Bollinger Band 

Bollinger Band indicator is created by setting the `indicators.type` as **"bollingerband"**. It contains three lines, namely upper band, lower band and signal line. Bollinger Band default value of the period is 14 and standardDeviations is 2.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "bollingerband",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img3.png)

### Exponential Moving Average (EMA)

To render an EMA indicator, you have to set the `indicators.type` as **"ema"**.  

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "ema",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img4.png)

### Momentum 

Momentum Technical indicator is created by setting the `indicators.type` as **"momentum"**. The momentum indicator renders two lines, namely upper band and signal line. Upper band always rendered at the value 100 and the signal line is calculated based on the momentum of the data.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "momentum",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img5.png)

### Moving Average Convergence Divergence (MACD)

To render an MACD indicator, you have to set the `indicators.type` as **"macd"**.  MACD indicator contains MACD line, Signal line and Histogram column. Histogram is used to differentiate MACD and signal line.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "macd",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                    high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img6.png)


#### macdType

By using the `macdType` enumeration property, you can change the MACD rendering as *line*, *histogram* or *both*. 

{% highlight ts %}
         
//Initializing Indicators    
this.chartindicators = [{
    type: "macd",
    //Set macd draw type
    macdType: "histogram",
    //  ...
}];

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img7.png)


### Relative Strength Index (RSI)

To render the RSI indicator, set the `indicators.type` as **"rsi"**. It contains three lines, namely upper band, lower band and signal line. Upper and lower band always render at value 70 and 30 respectively and signal line is calculated based on the **RSI** formula.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "rsi",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                   high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}


![](Technical-Indicators_images/Technical-Indicators_img8.png)


### Simple Moving Average (SMA)

To render the SMA indicator, you should specify the `indicators.type` as **"sma"**.  

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "sma",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                   high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img9.png)


### Stochastic 

For the Stochastic indicator, you need to set the `indicators.type` as **"stochastic"**. The Stochastic indicator renders four lines namely, upper line, lower line, stochastic line and the signal line. Upper line always rendered at value 80 and the lower line is rendered at value 20. Stochastic and Signal Lines are calculated based on the stochastic formula.

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "stochastic",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                     high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img10.png)


### Triangular Moving Average (TMA)

To render the TMA indicator, you should specify the `indicators.type` as **"tma"**. 

{% highlight ts %}

//Initializing Indicators    
this.chartindicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "tma",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartindicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                     high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img11.png)

## Enable Tooltip 

To display the indicator tooltip, use `visible` option of the `indicators.tooltip`. Also, you can change and customize the tooltip color, border, format and font properties similar to the series tooltip.

{% highlight ts %}
           
//Initializing Indicators    
this.chartindicators = [{
    //  ...
    tooltip: {
        //Enable tooltip for indicator
        visible: true
    },
}];

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img12.png)



