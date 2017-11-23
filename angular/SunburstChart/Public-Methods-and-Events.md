---
layout: post
title: Public Methods and Events
description: Public Methods and Events in Sunburst Chart.
platform: Angular 
control: SunburstChart
documentation: ug
---

## Methods


### redraw()

Redraws the entire sunburst. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight ts %}

export class AppComponent {

redraw(){
          
     this.sunburst.widget.redraw();

}

// Create sunburst instance
@ViewChild('animation') sunburst: EJComponents<any, any>;

}

{% endhighlight %}




### _destroy ()


destroy the sunburst



{% highlight ts %}

export class AppComponent {

destroy(){
          
     this.sunburst.widget.destroy();

}

// Create sunburst instance
@ViewChild('animation') sunburst: EJComponents<any, any>;

}

{% endhighlight %}




## Events

### load

Fires before loading.



{% highlight ts %}

onLoad(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (load)="onLoad($event)">   
</ej-sunburstchart>

{% endhighlight %}





### preRender


Fires before rendering sunburst. 


{% highlight ts %}

onPreRender(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (preRender)="onPreRender($event)">   
</ej-sunburstchart>

{% endhighlight %}



### loaded

Fires after rendering sunburst. 


{% highlight ts %}

onLoaded(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (loaded)="onLoaded($event)">   
</ej-sunburstchart>

{% endhighlight %}



### dataLabelRendering

Fires before rendering the data label 


{% highlight ts %}

onDrawLabelRendering(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (drawLabelRendering)="onDrawLabelRendering($event)">   
</ej-sunburstchart>

{% endhighlight %}



### segmentRendering


Fires before rendering each segment


{% highlight ts %}

onSegmentRendering(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (segmentRendering)="onSegmentRendering($event)">   
</ej-sunburstchart>

{% endhighlight %}



### titleRendering


Fires before rendering sunburst title. 


{% highlight ts %}

onTitleRendering(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (titleRendering)="onTitleRendering($event)">   
</ej-sunburstchart>

{% endhighlight %}



### tooltipInitialize


Fires during initialization of tooltip. 


{% highlight ts %}

onTooltipInitialize(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (tooltipInitialize)="onTooltipInitialize($event)">   
</ej-sunburstchart>

{% endhighlight %}



### pointRegionClick


Fires after clicking the point in sunburst



{% highlight ts %}

onPointRegionClick(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (pointRegionClick)="onPointRegionClick($event)">   
</ej-sunburstchart>

{% endhighlight %}



### pointRegionMouseMove

Fires while moving the mouse over sunburst points


{% highlight ts %}

onPointRegionMouseMove(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (pointRegionMouseMove)="onPointRegionMouseMove($event)">   
</ej-sunburstchart>

{% endhighlight %}



### drillDownClick

Fires when clicking the point to perform drilldown. 


{% highlight ts %}

onDrillDownClick(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (drillDownClick)="onDrillDownClick($event)">   
</ej-sunburstchart>

{% endhighlight %}



### drillDownBack


Fires when resetting drilldown points. 


{% highlight ts %}

onDrillDownBack(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (drillDownBack)="onDrillDownBack($event)">   
</ej-sunburstchart>

{% endhighlight %}



### drillDownReset


Fires after resetting the sunburst points 


{% highlight ts %}

onDrillDownReset(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-sunburstchart  id="events" (drillDownReset)="onDrillDownReset($event)">   
</ej-sunburstchart>

{% endhighlight %}


