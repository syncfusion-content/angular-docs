---
layout: post
title: appearance and styling
description: appearance and styling
platform: angular-2
control: rotator
documentation: ug
---

## Appearance and Styling

### Adjusting rotator item size

#### Slide width

This **slideWidth** property sets the width of a Rotator Item. The value set to this property is string or number.

#### Slide height

This **slideHeight** property sets the height of a Rotator Item. The value set to this property is string or number.



{% highlight html %}
  <ul id="sliderContent" ej-rotator slideWidth="500px" slideHeight="250px">
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="green" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title="snow" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet"/></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>
        </ul>

{% endhighlight %}


![](appearance and styling_images\slideheight_img1.png)

### Showing Play button

The **showPlayButton**  property enables play / pause button on Rotator. The default value is ‘false’. The value set to this property is Boolean.

{% highlight js %}

<ul id="sliderContent" ej-rotator slideWidth="500px" slideHeight="250px" [showPlayButton]=true>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="green" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title="snow" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet"/></li>
            <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>
        </ul>


{% endhighlight %}



![](appearance and styling_images\showingplaybutton_img1.png)

### Showing Navigate button

The **showNavigateButton** property turns on or off the slide buttons (next and previous) in the Rotator Items. Slide buttons are used to navigate the Rotator Items. The default value is ‘false’. The value set to this property is Boolean.

{% highlight html %}

<ul id="sliderContent" ej-rotator [dataSource]="datalist" slideWidth="500px" slideHeight="250px" [showNavigateButton]=true>
           
        </ul>
 


{% endhighlight %}



![](appearance and styling_images\showingnavigatebutton_img1.png)

### Image captions

When the Rotator Item is an image, you can specify a caption for the Rotator Item. The caption text for each Rotator Item is set by using the title attribute of the respective &lt;image&gt; tag. The caption cannot be displayed when multiple Rotator Items are present. The default value is ‘false’ and the property is **showCaption**. 

{% highlight html %}
  <ul id="sliderContent" ej-rotator [dataSource]="datalist" slideWidth="500px" slideHeight="250px" [showCaption]=true></ul>
{% endhighlight %}



![](appearance and styling_images\imagecaptions_img1.png)


### Supported Themes

Rotator component’s style and appearance are controlled based on CSS classes. In order to apply styles to the Rotator component, you can refer 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.web.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project.

By default, there are 16 themes support available for Rotator component as follows,

•	flat-azure
•	flat-azure-dark
•	fat-lime
•	flat-lime-dark
•	flat-saffron
•	flat-saffron-dark
•	gradient-azure
•	gradient-azure-dark
•	gradient-lime
•	gradient-lime-dark
•	gradient-saffron
•	gradient-saffron-dark
•	high-contrast-01
•	high-contrast-02
•	material
•	office-365

### Customize using CSS Class

This property **cssClass** is used to set root class for Rotator component theme. The value set to this property is string type.

{% highlight html %}


<ul id="sliderContent" ej-rotator slideWidth="500px" slideHeight="300px" cssClass="flat-lime">
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title=" snow " /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="f" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>
    </ul>



{% endhighlight %}

Add the following code in your CSS.

{% highlight css %}


<style>
    .flat-lime {
        background-color: yellowgreen;
    }
</style>


{% endhighlight %}



![](appearance and styling_images\CustomizeusingCSSClass_img1.png)



