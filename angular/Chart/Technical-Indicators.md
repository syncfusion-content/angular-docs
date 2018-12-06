---
layout: post
title: Syncfusion EJ1 Chart - Technical Indicators
description: What are the different types of technical indicators supported in Essential Chart for financial analysis.
platform: Angular
control: Chart
documentation: ug
---

# Technical Indicators

EjChart control supports 10 types of technical indicators. 

## Bind data to render the indicator

You can bind the series `dataSource` to the indicator by setting the specific series name to the indicator by using the `indicators.seriesName` property.

{% highlight ts %}

this.chartIndicators = [{
    //Set HiLo series dataSource to indicator using seriesName
    seriesName: "Hilo"
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series type="hiloopenclose" name="Hilo" [dataSource]="chartData" 
             xName= "xDate" high="High" low="Low" open="Open" close="Close">
	    </e-series>
  </e-seriescollection>
</ej-chart>

{% endhighlight %}


Also, you can add data to the indicator directly by using the `dataSource` option of the indicator.  

{% highlight ts %}
   
this.chartIndicators = [{
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

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
</ej-chart>

{% endhighlight %}
	
## Indicator Types

### Accumulation Distribution

To create an Accumulation Distribution indicator, set the `indicators.type` as **"accumulationDistribution"**. Accumulation Distribution require **‘volume’** field additionally with the `dataSource` to calculate the signal line.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "accumulationDistribution",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
            high="High"  low="Low" open="Open" close="Close" volume="Volume">
	    </e-series>
   </e-seriescollection>
   
</ej-chart>

{% endhighlight %}

![Accumulation Distribution](Technical-Indicators_images/Technical-Indicators_img1.png)

### Average True Range (ATR)

You can create an ATR indicator by setting the `indicators.type` as **"ATR"** in the `indicators`. 

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "ATR",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                       high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![ATR](Technical-Indicators_images/Technical-Indicators_img2.png)

### Bollinger Band 

Bollinger Band indicator is created by setting the `indicators.type` as **"bollingerBand"**. It contains three lines, namely upper band, lower band and signal line. Bollinger Band default value of the period is 14 and standardDeviations is 2.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "bollingerBand",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![Bollinger Band](Technical-Indicators_images/Technical-Indicators_img3.png)

### Exponential Moving Average (EMA)

To render an EMA indicator, you have to set the `indicators.type` as **"EMA"**.  

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "EMA",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![EMA](Technical-Indicators_images/Technical-Indicators_img4.png)

### Momentum 

Momentum Technical indicator is created by setting the `indicators.type` as **"momentum"**. The momentum indicator renders two lines, namely upper band and signal line. Upper band always rendered at the value 100 and the signal line is calculated based on the momentum of the data.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "momentum",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
         high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![Momentum](Technical-Indicators_images/Technical-Indicators_img5.png)

### Moving Average Convergence Divergence (MACD)

To render an MACD indicator, you have to set the `indicators.type` as **"macd"**.  MACD indicator contains MACD line, Signal line and Histogram column. Histogram is used to differentiate MACD and signal line.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "macd",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                    high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![MACD](Technical-Indicators_images/Technical-Indicators_img6.png)


#### macdType

By using the `macdType` enumeration property, you can change the MACD rendering as *line*, *histogram* or *both*. 

{% highlight ts %}
         
//Initializing Indicators    
this.chartIndicators = [{
    type: "macd",
    //Set macd draw type
    macdType: "histogram",
    //  ...
}];

{% endhighlight %}

![MACD Type](Technical-Indicators_images/Technical-Indicators_img7.png)


### Relative Strength Index (RSI)

To render the RSI indicator, set the `indicators.type` as **"RSI"**. It contains three lines, namely upper band, lower band and signal line. Upper and lower band always render at value 70 and 30 respectively and signal line is calculated based on the **RSI** formula.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "RSI",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                   high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}


![RSI](Technical-Indicators_images/Technical-Indicators_img8.png)


### Simple Moving Average (SMA)

To render the SMA indicator, you should specify the `indicators.type` as **"SMA"**.  

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "SMA",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                   high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![SMA](Technical-Indicators_images/Technical-Indicators_img9.png)


### Stochastic 

For the Stochastic indicator, you need to set the `indicators.type` as **"stochastic"**. The Stochastic indicator renders four lines namely, upper line, lower line, stochastic line and the signal line. Upper line always rendered at value 80 and the lower line is rendered at value 20. Stochastic and Signal Lines are calculated based on the stochastic formula.

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "stochastic",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                     high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![Stochastic](Technical-Indicators_images/Technical-Indicators_img10.png)


### Triangular Moving Average (TMA)

To render the TMA indicator, you should specify the `indicators.type` as **"TMA"**. 

{% highlight ts %}

//Initializing Indicators    
this.chartIndicators = [{
    seriesName: "Hilo",
    //Set indicator type
    type: "TMA",
    //  ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [indicators]="chartIndicators">
    <e-seriescollection>
        <e-series name="Hilo" [dataSource]="chartData" xName= "xDate"
                     high="High" low="Low" open="Open" close="Close">
	    </e-series>
   </e-seriescollection>   
</ej-chart>

{% endhighlight %}

![TMA](Technical-Indicators_images/Technical-Indicators_img11.png)

## Enable Tooltip 

To display the indicator tooltip, use `visible` option of the `indicators.tooltip`. Also, you can change and customize the tooltip color, border, format and font properties similar to the series tooltip.

{% highlight ts %}
           
//Initializing Indicators    
this.chartIndicators = [{
    //  ...
    tooltip: {
        //Enable tooltip for indicator
        visible: true
    },
}];

{% endhighlight %}

![Indicator Tooltip](Technical-Indicators_images/Technical-Indicators_img12.png)



