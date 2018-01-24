---
layout: post
title: Title
description: title
platform: Angular
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Title

## Title Text
By using the `text` property, you can add the title text for PivotChart.
 
 
{% highlight html %}

<ej-pivotchart [title]="title">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public title;
    constructor() {
      //..
      this.title = { text: "PivotChart" };
    }
}

{% endhighlight %}

![](Title_images/Title_img1.png) 

## Title Alignment

By using the `textAlignment` property, you can align the PivotChart controls title text to center, far or near.

{% highlight html %}

<ej-pivotchart [title]="title">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public title;
    constructor() {
      //..
      this.title = { 
            text: "PivotChart", 
            //Change title text alignment
            textAlignment: "near"
       };
    }
}

{% endhighlight %}

![](Title_images/Title_img2.png) 

## Title Customization
By using the `title` property, you can add the title text for X-axis and Y-axis. Also title text can be customized by using the `text` and `font` properties. On setting `enableTrim` to true, title text could be trimmed based on its length.

{% highlight html %}

<ej-pivotchart [primaryXAxis]="primaryXAxis">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public primaryXAxis;
    constructor() {
      //..
      this.primaryXAxis = {
              //Customizing X-axis title
              title: {
                 text: "Country",
                 font: {
                    fontFamily: 'Segoe UI',
                    size: '16px',
                    fontWeight: 'bold',
                    color: 'grey',
                 },
                 enableTrim: true
              }
          }
    }
}

{% endhighlight %}

![](Title_images/Title_img3.png)
