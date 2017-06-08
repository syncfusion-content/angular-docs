---
layout: post
title: Chart Striplines
description: Learn how to add horizontal or vertical lines in Chart.                                                  
platform: Angular
control: Chart
documentation: ug
---

# Striplines

EjChart supports horizontal and vertical striplines. 

## Horizontal Stripline

You can create horizontal stripline by adding the `stripline` in the **vertical axis** and set `visible` option to **true**. Striplines are rendered in the specified **start** to **end** range and you can add more than one stripline for an axis.


{% highlight ts %}

this.stripLine = [
    //Create horizontal Stripline using vertical Axis
    {
        //Enable Stripline
        visible: true,
        start: 30,
        end: 40,
    },
           // ...
];

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}


![](Striplines_images/Striplines_img1.png)


## Vertical Stripline

You can create vertical stripline by adding the `stripline` in the **horizontal axis** and set `visible` option to **true**.  

{% highlight ts %}

this.stripLine = [
          //Create vertical Stripline using vertical Axis
          {
              //Enable Stripline
              visible: true,
              start: 3,
              end: 7,
          },
           // ...
];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}

![](Striplines_images/Striplines_img2.png)


## Customize the Text

To customize the stripLine text, use the `text` and `font` options. 

{% highlight ts %}

this.stripLine = [
          //Create horizontal Stripline using vertical Axis
          {
              //Customize the stripLine text and font styles
              text: 'High Temperature',
              font: { size: '18px', color: 'white' }
              // ...  
     }];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}

![](Striplines_images/Striplines_img3.png)
	

**Text Alignment**

Stripline text can be aligned by using the `textAlignment` property.  

{% highlight ts %}

this.stripLine = [{
    //Set stripLine text alignment to top position
    textAlignment: 'middletop',
    // ...                         
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}

![](Striplines_images/Striplines_img4.png)


## Customize the Stripline

To customize the stripLine styles, use the `color`, `opacity`, `borderWidth` and `borderColor` properties. 

{% highlight ts %}

this.stripLine = [{
    //Customize the StripLine rectangle
    color: '#33CCFF',
    borderWidth: 2,
    opacity: 0.5,
    borderColor: 'red',
    // ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}

![](Striplines_images/Striplines_img5.png)


## Change the Z-order of the stripline

Stripline `zIndex` property is used to display the stripLine either behind or over the series.  

{% highlight ts %}

this.stripLine = [{
    //Change stripLine zIndex
    zindex: 'over',
    // ...
}];

{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryYAxis.stripLine]="stripLine">
</ej-chart> 

{% endhighlight %}

![](Striplines_images/Striplines_img6.png)
