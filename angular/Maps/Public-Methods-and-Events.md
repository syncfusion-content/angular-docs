---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: Angular
control: Maps
documentation: ug
---


## Methods

### navigateTo(latitude, longitude, level)


Method for navigating to specific shape based on latitude, longitude and zoom level.



{% highlight ts %}

export class AppComponent {

navigateTo(){
          
     this.map.widget.navigateTo();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}


### pan(direction)


Method to perform map panning


{% highlight ts %}

export class AppComponent {

pan(){
          
     this.map.widget.pan();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}


### refresh()


Method to reload the map.




{% highlight ts %}

export class AppComponent {

refresh(){
          
     this.map.widget.refresh();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}


### refreshLayers()


Method to reload the shapeLayers with updated values



{% highlight ts %}

export class AppComponent {

refreshLayers(){
          
     this.map.widget.refreshLayers();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}


### refreshNavigationControl(navigation)


Method to reload the navigation control with updated values.



{% highlight ts %}

export class AppComponent {

refreshNavigationControl(){
          
     this.map.widget.refreshNavigationControl();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}


### zoom(level, isAnimate)


Method to perform map zooming.



{% highlight ts %}

export class AppComponent {

zoom(){
          
     this.map.widget.zoom();

}

// Create map instance
@ViewChild('mapControl') map: EJComponents<any, any>;

}

{% endhighlight %}



## Events

### markerSelected


Triggered on selecting the map markers.


{% highlight ts %}

onMarkerSelected(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (markerSelected)="onMarkerSelected($event)">    
</ej-map>

{% endhighlight %}



### mouseLeave


Triggers while leaving the hovered map shape


{% highlight ts %}

onMouseLeave(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (mouseLeave)="onMouseLeave($event)">    
</ej-map>

{% endhighlight %}



### mouseover


Triggers while hovering the map shape.


{% highlight ts %}

onMouseOver(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (mouseover)="onMouseOver($event)">    
</ej-map>

{% endhighlight %}



### onRenderComplete


Triggers once map render completed.


{% highlight ts %}

onRenderComplete(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (onRenderComplete)="onRenderComplete($event)">    
</ej-map>

{% endhighlight %}



### panned


Triggers when map panning ends.


{% highlight ts %}

onPanned(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (panned)="onPanned($event)">    
</ej-map>

{% endhighlight %}



### shapeSelected


Triggered on selecting the map shapes.


{% highlight ts %}

onShapeSelected(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (shapeSelected)="onShapeSelected($event)">    
</ej-map>

{% endhighlight %}



### zoomedIn


Triggered when map is zoomed-in.


{% highlight ts %}

onZoomedIn(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (zoomedIn)="onZoomedIn($event)">    
</ej-map>

{% endhighlight %}



### zoomedOut


Triggers when map is zoomed out.



{% highlight ts %}

onZoomedOut(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-map id="events" (zoomedOut)="onZoomedOut($event)">    
</ej-map>

{% endhighlight %}

<a class="" href="http://www.syncfusion.com/copyright" target="_blank">Copyright &copy; 2001 - 2015 Syncfusion Inc. All Rights Reserved</a>

