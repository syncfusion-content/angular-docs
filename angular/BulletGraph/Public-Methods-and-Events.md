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
@ViewChild('bulletgraph') bullet: EJComponents<any, any>;

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
@ViewChild('bulletgraph') bullet: EJComponents<any, any>;

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
@ViewChild('bulletgraph') bullet: EJComponents<any, any>;

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
@ViewChild('bulletgraph') bullet: EJComponents<any, any>;

}

{% endhighlight %}





## Events



### drawCaption


Fires on rendering the caption of bullet graph.


{% highlight ts %}

ondrawcaption(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawCaption)="ondrawcaption($event)"> 
</ej-bulletgraph>

{% endhighlight %}





### drawCategory


Fires on rendering the category.


{% highlight ts %}

ondrawcategory(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawCategory)="ondrawcategory($event)"> 
</ej-bulletgraph>

{% endhighlight %}









### drawComparativeMeasureSymbol

Fires on rendering the comparative measure symbol.


{% highlight ts %}

ondrawcomparativemeasuresymbol(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawComparativeMeasureSymbol)="ondrawcomparativemeasuresymbol($event)"> 
</ej-bulletgraph>

{% endhighlight %}






### drawFeatureMeasureBar

Fires on rendering the feature measure bar.


{% highlight ts %}

ondrawfeaturemeasurebar(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawFeatureMeasureBar)="ondrawfeaturemeasurebar($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawIndicator


Fires on rendering the indicator of bullet graph.


{% highlight ts %}

ondrawindicator(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawIndicator)="ondrawindicator($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawLabels

Fires on rendering the labels.


{% highlight ts %}

ondrawlabels(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawLabels)="ondrawlabels($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### drawQualitativeRanges


Fires on rendering the qualitative ranges.


{% highlight ts %}

ondrawqualitativeranges(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (drawQualitativeRanges)="ondrawqualitativeranges($event)"> 
</ej-bulletgraph>

{% endhighlight %}







### load


Fires on loading bullet graph.



{% highlight ts %}

onload(sender){
     
     //Do something

}

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="events" (load)="onload($event)"> 
</ej-bulletgraph>

{% endhighlight %}




