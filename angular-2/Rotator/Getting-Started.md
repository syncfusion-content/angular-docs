---
layout: post
title: getting-started
description: getting started
platform: angular2
control: rotator
documentation: ug
---

# Getting Started

This section helps to get started of the Rotator component in a Angular2 application

![](Getting-Started_images/Getting-Started_img1.png) 

## Create a Rotator

The following step by step guidelines will help you to add a Rotator component.

Refer the common Angular2 [Getting Started Documentation](https://help.syncfusion.com/js/angular2) to create an application and add necessary scripts and styles for rendering Essential JavaScript controls.

Create a simple Angular2 Rotator by adding ej-rotator attribute for initializing an empty Rotator component to the application. 

{% highlight html %}

    <ul ej-rotator width="500px" height="150px" slideWidth="600px" slideHeight="300px" >
    </ul>

{% endhighlight %}



## Configure data

To configure images for Rotator component, define data in an object array and fields in the component’s constructor file.

{% highlight typescript %}

    export class AppComponent {
        data:array;
        fieldList:object;
        autoPlay:boolean;
        constructor() {
            this.data=[
                { text: "snowfall", url: "http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" },
                { text: "tablet", url: "http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" },
                { text: "nature", url: "http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" },
                { text: "card", url: "http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" },
                { text: "bird", url: "http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" },
                { text: "wheat", url: "http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" },
                { text: "night", url: "http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" }
            ];
            this.fieldList={text:"text",url:"url"};
            this.autoPlay=true;   
        }
    }


{% endhighlight %}



Now assign the defined variables to field and dataSource properties. Add required properties to the component.

{% highlight html %}


    <ul ej-rotator [dataSource]="data" [fields]="fieldList" [showPlayButton]="autoPlay" slideWidth="600px" slideHeight="300px" >
    </ul>


{% endhighlight %}



![](Getting-Started_images/Getting-Started_img2.png)



> _Note:_ _You can find the Rotator properties from the_ [API reference](https://help.syncfusion.com/api/js/ejrotator) _document___

