---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: Angular
control: BulletGraph	
documentation: ug
---


## Methods



### destroy ()


To destroy the bullet graph



{% highlight ts %}

export class AppComponent {

destroy(){
          
      this.bullet.widget.destroy();

}

// Create instance for bullet graph
@ViewChild('bullet1') bullet: EJComponents<any, any>;

}


{% endhighlight %}





### redraw()


To redraw the bullet graph



{% highlight ts %}

export class AppComponent {

redraw(){
     
     //Do something
     this.bullet.widget.redraw();

}

// Create instance for bullet graph
@ViewChild('bullet1') bullet: EJComponents<any, any>;

}

{% endhighlight %}





### setComparativeMeasureSymbol()


To set the value for comparative measure in bullet graph.


{% highlight ts %}

export class AppComponent {

setComparativeMeasureSymbol(){
     
     //Do something
     this.range.widget.setComparativeMeasureSymbol();

}

// Create instance for bullet graph
@ViewChild('bullet1') bullet: EJComponents<any, any>;

}

{% endhighlight %}






### setFeatureMeasureBarValue()


To set the value for feature measure bar.


{% highlight ts %}

export class AppComponent {

setFeatureMeasureBarValue(){
     
     //Do something
     this.range.widget.setFeatureMeasureBarValue();

}

// Create instance for bullet graph
@ViewChild('bullet1') bullet: EJComponents<any, any>;

}

{% endhighlight %}





## Events



### drawCaption


Fires on rendering the caption of bullet graph.


{% highlight ts %}

onDrawCaption(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawCaption)="onDrawCaption($event)"> 
</ej-bulletgraph>

{% endhighlight %}





### drawCategory


Fires on rendering the category.


{% highlight ts %}

onDrawCategory(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawCategory)="onDrawCategory($event)"> 
</ej-bulletgraph>

{% endhighlight %}









### drawComparativeMeasureSymbol

Fires on rendering the comparative measure symbol.


{% highlight ts %}

onDrawComparativeMeasureSymbol(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawComparativeMeasureSymbol)="onDrawComparativeMeasureSymbol($event)"> 
</ej-bulletgraph>

{% endhighlight %}






### drawFeatureMeasureBar

Fires on rendering the feature measure bar.


{% highlight ts %}

onDrawFeatureMeasureBar(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawFeatureMeasureBar)="onDrawFeatureMeasureBar($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawIndicator


Fires on rendering the indicator of bullet graph.


{% highlight ts %}

onDrawIndicator(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawIndicator)="onDrawIndicator($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawLabels

Fires on rendering the labels.


{% highlight ts %}

onDrawLabels(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawLabels)="onDrawLabels($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawQualitativeRanges


Fires on rendering the qualitative ranges.


{% highlight ts %}

onDrawQualitativeRanges(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawQualitativeRanges)="onDrawQualitativeRanges($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### load


Fires on loading bullet graph.



{% highlight ts %}

onLoad(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (load)="onLoad($event)"> 
</ej-bulletgraph>

{% endhighlight %}




