---
layout: post
title: Quantitative-Scale
description: quantitative scale
platform: Angular
control: BulletGraph	
documentation: ug
---

# Quantitative Scale

The **Quantitative Scale** appearance is customized using **quantitativeScaleSettings** property. It has properties to customize labels, major ticks, minor ticks, comparative measure and performance measure of the bullet graph

## Range for Quantitative Scale

**Quantitative Scale** range is set using the properties **minimum**, **maximum** and **interval** of **quantitativeScaleSettings** property. **Minimum** specifies the start range of the scale, **maximum** specifies the end range of scale and **interval** specifies the number of intervals between start and end range. Default values of **minimum**, **maximum** and **interval** are 0, 10 and 1 respectively. The number of minor ticks (ticks between intervals) are specified using **minorTicksPerInterval** property.

{% highlight html %}

<ej-bulletgraph id="bullet1" [quantitativeScaleSettings.minimum]=0 
 [quantitativeScaleSettings.maximum]=10 [quantitativeScaleSettings.interval]=1 
 [quantitativeScaleSettings.minorTicksPerInterval]=4>         
       
</ej-bulletgraph>

{% endhighlight %}



The following screenshot displays a **Bullet Graph** with start range 0, end range 10 and interval 1 with 4 minor ticks per interval

![](Quantitative-Scale_images/Quantitative-Scale_img1.png) 

## Quantitative scale location

Bullet Graph does not position Quantitative scale automatically based on its size or space required for caption text, etc. By default Quantitative scale is positioned at 10 pixels from left and 10 pixels from top. Quantitative scale location is customized as per the requirement using the location property available in quantitativeScaleSettings.

{% highlight html %}

<ej-bulletgraph id="bullet1" [quantitativeScaleSettings.location.x]=20 
                                  [quantitativeScaleSettings.location.y]=20>         
       
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** with Quantitative scale at 20 pixels from left and 20 pixels from top

![](Quantitative-Scale_images/Quantitative-Scale_img2.png) 

## Major ticks

Color, size and width of **Major tick** lines are customized using **majorTickSettings** property in **quantitativeScaleSettings**. Default value of **size** and **width** properties are 13 and 2 respectively. **Ticks** are drawn in black color by default. The property **size** represents the height of **tick** lines and **width** represents the width of **tick** lines and **ticks** color are customized using **stroke** property.

{% highlight html %}

<ej-bulletgraph id="bullet1" [quantitativeScaleSettings.majorTickSettings.size]=15 
                          [quantitativeScaleSettings.majorTickSettings.width]=3 
                        quantitativeScaleSettings.majorTickSettings.stroke="gray">         
       
</ej-bulletgraph>

{% endhighlight %}



The following screenshot displays **Major ticks** in **gray** color with a width of 3 pixels and height 15 pixels.

![](Quantitative-Scale_images/Quantitative-Scale_img3.png) 

## Minor ticks

Minor ticks can also be customized similar to major ticks. The properties stroke, width and size of minorTickSettings are used to customize Minor ticks in quantitative scale. Stroke specifies the color of ticks, width specifies the width of ticks and size specifies the height of the ticks.

{% highlight html %}

<ej-bulletgraph id="bullet1" [quantitativeScaleSettings.minorTickSettings.size]=7 
                             [quantitativeScaleSettings.minorTickSettings.width]=3 
                             quantitativeScaleSettings.minorTickSettings.stroke="gray">         
       
</ej-bulletgraph>

{% endhighlight %}



The following screenshot displays **Bullet Graph** with customized **Minor ticks** in quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img4.png) 

## Tick position

**Ticks** are positioned below, above or inside the quantitative scale. By default **ticks** are positioned below the quantitative scale. The **tickPosition** property is used to customize the position of ticks in quantitative scale. **Ticks** can be placed inside the quantitative scale by setting **tickPosition** to **cross**.

{% highlight html %}

<ej-bulletgraph id="bullet1" quantitativeScaleSettings.tickPosition="above">         
       
</ej-bulletgraph>

{% endhighlight %}



The following screenshot displays **Bullet Graph** with ticks positioned above quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img5.png) 

## Tick Placement

**Quantitative****scale****ticks** can be placed either inside or outside the scale using ???**tickPlacement**??? property. By default ticks are placed outside the scale.



{% highlight ts %}


this.caption = {
    textAngle: 0, location: { x: 17, y: 28 }, text: "Revenue YTD",
    subTitle: {
        textAngle: 0,
        text: "$ in Thousands", location: { x: 10, y: 42 }
    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [value]=8 [captionSettings]="caption" 
      [comparativeMeasureValue]=50 quantitativeScaleSettings.tickPlacement="inside"
      [quantitativeScaleSettings.location.x]=108 [quantitativeScaleSettings.location.y]=10
      [quantitativeScaleSettings.labelSettings.offset]=5 
      [quantitativeScaleSettings.labelSettings.size]=10 
      quantitativeScaleSettings.labelSettings.labelPrefix="$">         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** ticks inside **Quantitative Scale**

![](Quantitative-Scale_images/Quantitative-Scale_img6.png) 

## Quantitative scale labels

**Quantitative****scale****labels** are customized with prefix, suffix, font, color and size using **labelSettings** property. By default, label text is displayed in black color with 12 pixel ???Segoe UI??? font and there is a padding of 20 pixels space between quantitative scale and labels.

{% highlight html %}

<ej-bulletgraph id="bullet1" [quantitativeScaleSettings.labelSettings.offset]=15 
       [quantitativeScaleSettings.labelSettings.size]=12 
       quantitativeScaleSettings.labelSettings.labelPrefix="$" 
       quantitativeScaleSettings.labelSettings.labelSuffix="K" 
       quantitativeScaleSettings.labelSettings.stroke="blue" 
      [quantitativeScaleSettings.labelSettings.font]="{fontFamily: 'Segoe UI', 
                     fontStyle: 'bold', fontWeight: 'regular', opacity: 0.8 }">         
       
</ej-bulletgraph>


{% endhighlight %}


The following screenshot displays **Bullet Graph** labels in blue color

![](Quantitative-Scale_images/Quantitative-Scale_img7.png) 

## Label Placement

**Quantitative****scale****labels** can be placed either inside or outside the scale using ???**labelPlacement**??? property. By default labels are placed 15 pixels outside the scale.

{% highlight ts %}

this.quantitativeScale = {
    location: { x: 108, y: 10 },
    labelSettings: {
        offset: 5, size: 10, labelPrefix: '$', labelSuffix: ' K', font: { fontWeight: 'bold' },
        labelPlacement: 'inside'
    },
};

this.caption = {
    textAngle: 0, location: { x: 17, y: 28 }, text: "Revenue YTD",
    subTitle: {
        textAngle: 0,
        text: "$ in Thousands", location: { x: 10, y: 42 }
    }
}; 

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [value]=8 [comparativeMeasureValue]=50 
   [quantitativeScaleSettings]="quantitativeScale" [captionSettings]="caption">         
       
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** labels inside **Quantitative Scale.**

![](Quantitative-Scale_images/Quantitative-Scale_img8.png) 

## Performance measure bar

Performance measure bar is customized using featuredMeasureSettings in quantitativeScaleSettings property. Color of the bar is customized using stroke property and width using width property. By default bar is drawn in black color with 6 pixels of width.

{% highlight html %}

<ej-bulletgraph id="bullet1" [value]=5 
 quantitativeScaleSettings.featuredMeasureSettings.stroke="blue" 
  [quantitativeScaleSettings.featuredMeasureSettings.width]=4>         
       
</ej-bulletgraph>

{% endhighlight %}


The following screenshot displays **Bullet Graph** with customized **Performance measure bar**.

![](Quantitative-Scale_images/Quantitative-Scale_img9.png) 

## Comparative measure symbol

Comparative symbol color and width are customized using comparativeMeasureSettings through quantitativeScaleSettings property. Color of the symbol is customized using stroke property and width using width property. By default Comparative measure symbol is displayed in black color with a width of 5 pixels.

{% highlight html %}

<ej-bulletgraph id="bullet1" [comparativeMeasureValue]=5 
   quantitativeScaleSettings.featuredMeasureSettings.stroke="blue" 
           [quantitativeScaleSettings.featuredMeasureSettings.width]=5>         
       
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** with customized **Comparative measure value**.

![](Quantitative-Scale_images/Quantitative-Scale_img10.png) 

## Multiple performance measures comparison

**Bullet Graph** supports comparing more than one performance at a time, given that all the comparisons are related using **featureMeasure** in **quantitativeScaleSettings** property.

{% highlight ts %}

this.quantitativeScale = {
    featureMeasures: [
        { value: 6, comparativeMeasureValue: 3, category: 2010 },
        { value: 9, comparativeMeasureValue: 6, category: 2011 },
        { value: 5, comparativeMeasureValue: 5, category: 2012 },
    ]
};


{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [qualitativeRangeSize]=60 [height]=120 [quantitativeScaleSettings]="quantitativeScale">         
       
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** that compares 3 related performance measures.

![](Quantitative-Scale_images/Quantitative-Scale_img11.png) 

