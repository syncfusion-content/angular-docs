---
layout: post
title: rtl support
description: rtl support
platform: Angular
control: rotator
documentation: ug
---

## RTL Support

This feature supports to change the left-to-right alignment of the Rotator to right-to-left (RTL). (i.e.) Sets the Rotator to do its actions from right to left. The property **enableRTL** sets the Rotator from right to left. The value set to this property is boolean type.

{% highlight html %}


<ul id="sliderContent" ej-rotator slideWidth="500px" slideHeight="300px" [enableRTL]="true">
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title=" snow " /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="f" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>
    </ul>



{% endhighlight %}





