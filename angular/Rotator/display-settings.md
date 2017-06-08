---
layout: post
title: display settings
description: display settings
platform: Angular
control: rotator
documentation: ug
---

## Display settings

### Display Items count

This property specifies the number of Rotator Items to be displayed. The default value is ‘1’. The value set to this property is string or number.

{% highlight html %}

<ul ej-rotator id="sliderContent" slideWidth="200px" slideHeight="165px" displayItemsCount="3" frameSpace="4">

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"
                />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>


{% endhighlight %}



{% highlight js %}


    export class AppComponent {

    constructor() {

    }
}

   <style type="text/css" class="cssStyles">
      
      #sliderContent > li .image {
            width: 200px;
            height: 165px;
        }
    </style>


{% endhighlight %}


![](display settings_images\displayitemscount_img1.png)

### Navigation steps

This property specifies the number of Rotator Items to navigate on a single click (next/previous/play buttons). The **navigateSteps** property value must be less than or equal to the **displayItemsCount** property value. The default value is ‘1’. The value set to this property is string or number.

{% highlight html %}


<ul ej-rotator id="sliderContent" slideWidth="200px" slideHeight="165px" displayItemsCount="2" frameSpace="4" navigationSteps="2">

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"
                />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>



{% endhighlight %}



![](display settings_images\navigationsteps_img1.png)

### Set Starting index

This property **startIndex** sets the index of the slide that is displayed first. The default value is ‘1’. The value set to this property is string or number.

{% highlight html %}


<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" startIndex="3">

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"
                />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>



{% endhighlight %}



![](display settings_images\setstartingindex_img1.png)

### Frame space

This **frameSpace** property sets the space between the Rotator Items. The value set to this property is string or number.

{% highlight html %}


<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" displayItemsCount="2" frameSpace="10px" >

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"
                />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>



{% endhighlight %}



![](display settings_images\framespace_img1.png)

### Animation settings

This e-animationtype property specifies the Animation type for the Rotator Item. This  **animationType** property has animation options like slide, fastSlide, slowSlide. The default value is ‘slide’. The value set to this property is string.

{% highlight html %}

<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" animationType="slowSlide" >

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"/>
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>


{% endhighlight %}


#### Animation speed

This **animationSpeed** property sets the speed of slide transition. The default value is ‘600’. The value set to this property is string or number.

{% highlight html %}


<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" animationType="slowSlide" animationSpeed="300" >

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"/>
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>



{% endhighlight %}



#### Delay animation

This **delay** property sets the delay between the Rotator Items to move after the slide transition. The default value is 500. The value set to this property is string or number.

{% highlight html %}


<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" delay="5000" >

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"/>
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>

    </div>




{% endhighlight %}

### Image with Contents

This feature allows you to add text along with the image in Rotator component. This is achieved by splitting the content into two panels. In the following code example, image is given in the left panel and text is given in the right panel.



{% highlight html %}


        <ul id="slidercontent" ej-rotator slideWidth="700px" slideHeight="300px" displayItemsCount="1">
            <li>
               <div class="leftPanel">
                  <img src="../images/rotator/tablet.jpg" />
               </div>
               <div class="rightPanel blck">
                  <div class="contentPanel">Tablet </div>
                  <ul>
                     <li>A tablet computer, or simply tablet, is a mobile computer with display, circuitry and battery in a single unit.</li>
                     <li>
                        Tablets are equipped with sensors, including cameras, microphone, accelerometer and touchscreen,
                  </ul>
               </div>
            </li>
            <li>
               <div class="leftPanel">
                  <img src="../images/rotator/nature.jpg" />
               </div>
               <div class="rightPanel">
                  <div class="contentPanel">Nature </div>
                  <ul>
                     <li>The health of the natural environment is critical to the long-term future of the planet</li>
                     <li>Nature, in the broadest sense, is equivalent to the natural, physical, or material world or universe.</li>
                  </ul>
               </div>
            </li>
            <li>
               <div class="leftPanel">
                  <img src="../images/rotator/card.jpg" />
               </div>
               <div class="rightPanel credit">
                  <div class="contentPanel">Credit card </div>
                  <ul>
                     <li>A credit card is a payment card issued to users as a system of payment</li>
                     <li>It allows the cardholder to pay for goods and services based on the holder's promise to pay for them</li>
                  </ul>
               </div>
            </li>
            <li>
               <div class="leftPanel">
                  <img src="../images/rotator/rose.jpg" />
               </div>
               <div class="rightPanel">
                  <div class="contentPanel">Rose </div>
                  <ul>
                     <li>A rose is a woody perennial of the genus Rosa, within the family Rosaceae</li>
                     <li>Flowers vary in size and shape and are usually large and showy,
                        There are over 100 species
                     </li>
                  </ul>
               </div>
            </li>
            <li>
               <div class="leftPanel">
                  <img src="../images/rotator/snowfall.jpg" />
               </div>
               <div class="rightPanel rightSide">
                  <div class="contentPanel">Snowfall </div>
                  <ul>
                     <li>Mt. Baker ski area in Washington State has the world record for snowfall at 1,140 inches of snow in the 1998/1999 winter season</li>
                     <li>Mt. Baker ski area is located near but not on the real 10,781 Mount Baker</li>
                  </ul>
               </div>
            </li>
         </ul>


{% endhighlight %}


{% highlight css %}


<style type="text/css" class="cssStyles">
       #slidercontent > li {
        background-color: #9ee8d8;
    }

    #slidercontent > li .leftPanel {
        float: left;
        width: 700px;
        height: 300px;
        padding-right: 0px;
    }

    #slidercontent > li .leftPanel img {
        width: 700px;
        height: 300px;
    }

    #slidercontent .rightPanel {
        background-color: #FFFFFF;
        height: 259px;
        margin-left: 410px;
        margin-top: 21px;
        opacity: 0.5;
        padding-left: 10px;
        position: absolute;
        width: 260px;
    }

    #slidercontent .rightPanel.credit {
        opacity: 0.6;
    }

    #slidercontent .rightPanel.blck {
        background-color: black;
    }

    #slidercontent .rightPanel.blck li {
        color: white;
        list-style: none;
        line-height: 2;
    }

    #slidercontent .rightPanel.blck .contentPanel {
        padding-top: 30px;
        color: white;
    }

    #slidercontent .rightPanel .contentPanel {
        color: #000000;
        font-size: large;
        font-weight: bold;
        left: 16px;
        padding-top: 30px;
        position: relative;
    }

    #slidercontent .rightPanel li {
        color: black;
        list-style: none;
        line-height: 2;
    }

    #slidercontent .rightPanel.rightSide {
        margin-left: 20px;
        background-color: black;
    }

    #slidercontent .rightPanel.rightSide li {
        color: white;
        list-style: none;
        line-height: 2;
    }

    #slidercontent .rightPanel.rightSide .contentPanel {
        padding-top: 30px;
        color: white;
    }

    .rightPanel > ul {
        padding: 6px 17px 17px;  
		</style>


{% endhighlight %}



![](display settings_images\imagewithcontents_img1.png)




