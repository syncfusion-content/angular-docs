---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: Angular
control: RangeNavigator
documentation: ug
---


## Methods








### _destroy ()









destroy the range navigator widget



{% highlight ts %}

destroy(){
     
     //Do something
     this.range.widget.destroy();

}

{% endhighlight %}








## Events








### load









Fires on load of range navigator.


{% highlight ts %}

load(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (load)="load($event)">
</ej-rangenavigator>

{% endhighlight %}








### loaded









Fires after range navigator is loaded.


{% highlight ts %}

onLoaded(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (loaded)="onLoaded($event)">
</ej-rangenavigator>

{% endhighlight %}








### rangeChanged









Fires on changing the range of range navigator.


{% highlight ts %}

onRangeChanged(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (rangeChanged)="onRangeChanged($event)">
</ej-rangenavigator>

{% endhighlight %}






### scrollChanged



Fires on changing the scrollbar position of range navigator.




{% highlight ts %}

onScrollChanged(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (scrollChanged)="onScrollChanged($event)">
</ej-rangenavigator>

{% endhighlight %}




### scrollStart



Fires on when starting to change the scrollbar position of range navigator.



{% highlight ts %}

onScrollStart(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (scrollStart)="onScrollStart($event)">
</ej-rangenavigator>

{% endhighlight %}


### selectedRangeStart




Fires on when starting to change the slider position of range navigator.






{% highlight ts %}

onSelectedRangeStart(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (selectedRangeStart)="onSelectedRangeStart($event)">
</ej-rangenavigator>

{% endhighlight %}

### selectedRangeEnd 




Fires when the selection  ends in the range navigator





{% highlight ts %}

onSelectedRangeEnd(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (selectedRangeEnd)="onSelectedRangeEnd($event)">
</ej-rangenavigator>

{% endhighlight %}



### scrollEnd



Fires on changes ending the scrollbar position of range navigator.





{% highlight ts %}

onScrollEnd(sender){
     
     //Do something

}

{% endhighlight %}


{% highlight html %}

<ej-rangenavigator id="events" (scrollEnd)="onScrollEnd($event)">
</ej-rangenavigator>

{% endhighlight %}


