---
layout: post
title:  Public Methods and Events
description:  Public Methods and Events
platform: Angular
control: Digital Gauge
documentation: ug
---


## Methods





### destroy()



To destroy the digital gauge


{% highlight ts %}

export class AppComponent {

destroy(){          
       
     this.digital.widget.destroy();
     
     }

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}
     
  {% endhighlight %}







### exportImage(fileName, fileType)


To export Digital Gauge as Image



{% highlight ts %}

export class AppComponent {

exportImage(){
     
     this.digital.widget.exportImage("myImage","jpeg");

}

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}






### getPosition(itemIndex)


Gets the location of an item that is displayed on the gauge.



{% highlight ts %}

export class AppComponent {

getPosition(){
     
     this.digital.widget.getPosition(0);

}

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}






### getValue(itemIndex)

ClientSideMethod getValue Gets the value of an item that is displayed on the gauge


{% highlight ts %}

export class AppComponent {

getValue(){
     
     this.digital.widget.getValue(0);

}

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}







### refresh()


Refresh the digital gauge widget



{% highlight ts %}

export class AppComponent {

refresh(){   
    
         this.digital.widget.refresh();
         
         }

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}





### setPosition(itemIndex, value)


ClientSideMethod Set Position Sets the location of an item to be displayed in the gauge


{% highlight ts %}

export class AppComponent {

setPosition(){
     
     this.digital.widget.setPosition(0,{x:10,y:10});

}

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}





### setValue(itemIndex, value)

ClientSideMethod SetValue Sets the value of an item to be displayed in the gauge.


{% highlight ts %}

export class AppComponent {

setValue(){
     
     this.digital.widget.setValue(0, "Welcome");

}

// Create digital gauge instance
@ViewChild('gauge') digital: EJComponents<any, any>;

}

{% endhighlight %}






## Events





### init

Triggers when the gauge is initialized.

{% highlight ts %}
 init(sender) {
    
    // Do something
    
    }

{% endhighlight %}

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" (init)="init($event)">
</ej-digitalgauge>

{% endhighlight %}







### itemRendering

Triggers when the gauge item rendering.


{% highlight ts %}
 itemRendering(sender) {
    
    // Do something
    
    }

{% endhighlight %}

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" (itemRendering)="itemRendering($event)">
</ej-digitalgauge>

{% endhighlight %}






### load

Triggers when the gauge is start to load.


{% highlight ts %} 
load(sender) {        
    
    // Do something      
    
      }
{% endhighlight %}
      {% highlight html %}
      
      <ej-digitalgauge id="DigitalGauge1" (load)="load($event)">
      </ej-digitalgauge>
      
      {% endhighlight %}




### renderComplete

Triggers when the gauge render is completed.


{% highlight ts %}
 complete(sender) {
    
    // Do something
    
    }

{% endhighlight %}

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" (renderComplete)="complete($event)">
</ej-digitalgauge>

{% endhighlight %}






