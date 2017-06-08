---
layout: post
title: Chart Title
description: How to customize the chart title.
platform: Angular
control: Chart
documentation: ug
---

# Chart Title & Subtitle

## Title

By using the title option, you can add the `text` as well as customize its `border`,  `background` color and `font`.

{% highlight ts %}

//Customize title font style
this.titleFont = {
    opacity: 1,
    fontFamily: "Arial",
    fontStyle: 'italic',
    fontWeight: 'regular',
    color: "#E27F2D",
    size: '23px'
};

{% endhighlight %}


{% highlight html %}

<ej-chart id="chartcontainer" title.text="Efficiency of oil-fired power production"
  title.background="lightblue" title.border.color="blue" [title.border.width]=2
    [title.border.opacity]=0.5 [title.border.cornerRadius]=4 [title.font]="titleFont">

</ej-chart>

{% endhighlight %}

![](Chart-Title_images/Chart-Title_img1.png)


We can trim, wrap and wrapAndTrim to the chart title using textOverflow property. The original text will be displayed as tooltip on mouse hover.


{% highlight html %}

<ej-chart id="chartcontainer" [title.enableTrim]="true" [title.maximumWidth]=150
                                                     title.textOverflow="trim">

</ej-chart>


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img5.png)


### Title Alignment

You can change the title alignment to *center*, *far* and *near* by using the `textAlignment` property of the chart title. 

{% highlight html %}


<ej-chart id="chartcontainer" title.textAlignment="near">

</ej-chart>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img2.png)


## Add Subtitle to the chart

By using the subTitle option, you can add the `subTitle` to the chart title and customize its `border`,  `background`. 

{% highlight ts %}

this.subTitle = {
    //Add subtitle to chart title 
    text: "( in a week )",
    //Change the title text background color
    background: "lightblue",
    //Customizing Chart subtitle border
    border: {
        color: "blue",
        width: 2,
        opacity: 0.2,
        cornerRadius: 4
    },

    //Customizing Chart subtitle font 
    font: {
        opacity: 1,
        fontFamily: "Arial",
        fontStyle: 'italic',
        fontWeight: 'regular',
        color: "#E27F2D",
        size: '12px'
    },
};

{% endhighlight %}

{% highlight html %}


<ej-chart id="chartcontainer" [title.subTitle]="subTitle">

</ej-chart>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img3.png)

We can trim, wrap and wrapAndTrim to the chart subtitle using textOverflow property. The original text will be displayed as tooltip on mouse hover.

{% highlight ts %}

this.subTitle = {
    //...
    //Add subtitle to chart title 
    text: "( in a week )",
    //To enable the sub-title trim, wrap and wrap and trim
    enableTrim: true,
    //Setting maximum width to the sub-title
    maximumWidth: 50,
    //To trim the sub-title
    textOverflow: "wrap"
};


{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [title.subTitle]="subTitle">

</ej-chart>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img6.png)

### Subtitle Alignment

You can change the subtitle alignment to *center*, *far* and *near* by using the `textAlignment` property of the subTitle.

{% highlight ts %}

this.subTitle = {
    //...
    //Change subtitle to text aligment
    textAlignment: "center"
};


{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [title.subTitle]="subTitle">

</ej-chart>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img4.png)

