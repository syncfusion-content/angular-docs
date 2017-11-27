---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: Angular
control: Sparkline
documentation: ug
---


## Methods


### redraw()


Redraws the entire sparkline. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight ts %}

export class AppComponent {

destroy(){
          
     this.sparkline.widget.destroy();

}

// Create sparkline instance
@ViewChild('line') sparkline: EJComponents<any, any>;

}

{% endhighlight %}








## Events



### load


Fires before loading the sparkline.



{% highlight ts %}

onLoad(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (load)="onLoad($event)">
</ej-sparkline>

{% endhighlight %}




### loaded


Fires after loaded the sparkline.



{% highlight ts %}

onLoaded(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (loaded)="onLoaded($event)">
</ej-sparkline>

{% endhighlight %}




### tooltipInitialize


Fires before rendering trackball tooltip. You can use this event to customize the text displayed in trackball tooltip.



{% highlight ts %}

onTooltipInitialize(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (tooltipInitialize)="onTooltipInitialize($event)">
</ej-sparkline>

{% endhighlight %}





### seriesRendering





Fires before rendering a series. This event is fired for each series in Sparkline.



{% highlight ts %}

onSeriesRendering(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (seriesRendering)="onSeriesRendering($event)">
</ej-sparkline>

{% endhighlight %}







### pointRegionMouseMove


Fires when mouse is moved over a point. 



{% highlight ts %}

onPointRegionMouseMove(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (pointRegionMouseMove)="onPointRegionMouseMove($event)">
</ej-sparkline>

{% endhighlight %}




### pointRegionMouseClick


Fires on clicking a point in sparkline. You can use this event to handle clicks made on points.



{% highlight ts %}

onPointRegionMouseClick(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (pointRegionMouseClick)="onPointRegionMouseClick($event)">
</ej-sparkline>

{% endhighlight %}






### sparklineMouseMove


Fires on moving mouse over the sparkline.



{% highlight ts %}

onSparkLineMouseMove(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (sparklineMouseMove)="onSparkLineMouseMove($event)">
</ej-sparkline>

{% endhighlight %}






### sparklineMouseLeave


Fires on moving mouse outside the sparkline.



{% highlight ts %}

onSparkLineMouseLeave(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sparkline id="events" (sparklineMouseLeave)="onSparkLineMouseLeave($event)">
</ej-sparkline>

{% endhighlight %}



