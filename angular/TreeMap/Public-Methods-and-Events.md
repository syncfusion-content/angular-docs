---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: Angular
control: TreeMap
documentation: ug
---

## Methods

### refresh()


Method to reload treemap with updated values.



{% highlight ts %}

refresh(){
     
     //Do something
     this.treemap.widget.refresh();

}
 
{% endhighlight %}



## Events

### treeMapItemSelected


Triggers on treemap item selected.


{% highlight js %}
 
<ej-treemap id="treemap" (treeMapItemSelected)="treeMapitemselected($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
treeMapItemSelected(sender) {

  // do something 

  }

{% endhighlight %}

### drillStarted


Triggers when drilldown is started



{% highlight js %}
 
<ej-treemap id="treemap" (drillStarted)="drillStarted($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
drillStarted(sender) {

  // do something 

  }
{% endhighlight %}  

### drillDownItemSelected


Triggers on treemap  drilldown  item  selected.




{% highlight js %}
 
 <ej-treemap id="treemap" (drillDownItemSelected)="drilldownitemselected($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
drillDownItemSelected(sender) {

  // do something 

  }

{% endhighlight %}

### headerTemplateRendering


Triggers before rendering the treemap drilldown header template



{% highlight js %}
 
 <ej-treemap id="treemap" (headerTemplateRendering)="headerTemplateRenderer($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
headerTemplateRenderer(sender) {

  // do something 

  }

{% endhighlight %}


### refreshed


Triggers after refreshing the treemap items.


 
{% highlight js %}
 
 <ej-treemap id="treemap" (refreshed)="refreshed($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
refreshed(sender) {

  // do something 

  }

{% endhighlight %}


### treeMapGroupSelected


Triggers when the group selection is performed on treemap items.


{% highlight js %}
 
 <ej-treemap id="treemap" (treeMapGroupSelected)="treeMapGroupSelected($event)">
 </ej-treemap>

{% endhighlight %}


{% highlight ts %}
 
treeMapGroupSelected(sender) {

  // do something 

  }

{% endhighlight %}

