---
layout: post
title: Legend
description: legend
platform: Angular
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Legend

## Legend Visibility

You can enable or disable legend using the `visible` property inside the `legend` object.

N> By default, the legend is visible in PivotChart.

{% tabs %}

{% highlight html %}

<ej-pivotchart [legend]="legend">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true };
    }
}

{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img1.png) 

## Legend Shape

You can customize the legend `shape` in PivotChart control. Default value of legend shape is “rectangle”. Following legend shapes that are supported:

* rectangle
* circle
* cross
* diamond
* pentagon
* hexagon
* star
* ellipse
* triangle etc.

{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, shape: "Star" };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img2.png) 

## Legend Position

By using the `Position` property, you can place the legend at top, bottom, left or right of the PivotChart. 

N> Default value of legend position is "bottom" in PivotChart.

{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, shape: "Star", position: "top" };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img3.png) 

## Legend Title

To add the legend title, you have to specify the title text in `Title.text` property.

{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, title:{ text: "Countries" } };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img4.png) 

## Legend Alignment

You can align the legend to center, far and near based on its position in the Chart area using the `Alignment` option.
 
{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, alignment: "Near" };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img5.png)

## Legend Items - Size and Border

By using the legend `ItemStyle.Width`, `ItemStyle.Height` and `ItemStyle.Border` properties, you can change the legend items - size and border.
 
{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, itemStyle:
            {
                height: 12,
                width: 12,
                border:
                {
                    color: 'magenta',
                    width: 1.5
                }
            } 
        };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img6.png)
 
## Legend Border

By using the `Border` option in legend, you can customize border color and width.
 
{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, border:{
                color: "#FFC342",
                width: 2
            }
        };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img7.png)

## Legend Text

By using the `Font` option, you can customize the font family, font style, font weight and size of the legend text. 
 
{% highlight ts %}

//..

export class PivotChartComponent {
    public legend;
    constructor() {
      //..
      this.legend = { visible: true, font:
            {
                fontFamily: 'Segoe UI',
                fontStyle: 'italic',
                fontWeight: 'bold',
                size: '13px'
            }
        };
    }
}

{% endhighlight %}

![](Legend_images/Legend_img8.png)