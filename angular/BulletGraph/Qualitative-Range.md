---
layout: post
title: Qualitative-Range
description: qualitative range
platform: Angular
control: BulletGraph	
documentation: ug
---

# Qualitative Range

**Qualitative Range** represents the quality of a specific range in quantitative scale like good, bad and satisfactory. Color for each qualitative range is customized using **rangeStroke** property. The **rangeEnd** property specifies the ending point of the qualitative range. Minimum value of quantitative scale is considered as the starting point of first qualitative range and previous end points are considered as starting point for other qualitative ranges.

{% highlight ts %}


this.quantitativeScale = {
    location: { x: 50, y: 20 },
    minimum: 0,
    maximum: 100,
    interval: 10,
    featureMeasures: [
        { value: 55, comparativeMeasureValue: 75, category: "Year 1" },
        { value: 65, comparativeMeasureValue: 70, category: "Year 2" },
        { value: 80, comparativeMeasureValue: 65, category: "Year 3" }
    ]
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [qualitativeRangeSize]="80" [quantitativeScaleSettings]="quantitativeScale">         
     <e-qualitativeranges>
         <e-qualitativerange rangeEnd="35" rangeStroke="darkred" [rangeOpacity]=0.5>
         </e-qualitativerange>
         <e-qualitativerange rangeEnd="50" rangeStroke="red" [rangeOpacity]=1>
         </e-qualitativerange>
         <e-qualitativerange rangeEnd="75" rangeStroke="blue" [rangeOpacity]=0.7>
         </e-qualitativerange>
		 <e-qualitativerange rangeEnd="90" rangeStroke="lightgreen" [rangeOpacity]=1>
         </e-qualitativerange>
		 <e-qualitativerange rangeEnd="100" rangeStroke="green" [rangeOpacity]=1>
         </e-qualitativerange>
     </e-qualitativeranges>        
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** with different qualitative ranges in different colors. In this image, range 0 to 35 represents bad performance, 35 to 50 represents average performance, 50 to 75 represents that the performance is above average, 75 to 90 represents good performance and above 90 represents excellent performance.

![](Qualitative-Range_images/Qualitative-Range_img1.png) 

