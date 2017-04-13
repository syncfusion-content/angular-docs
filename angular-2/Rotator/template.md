---
layout: post
title: template
description: template
platform: angular-2
control: rotator
documentation: ug
---

## Template

The Rotator component provided the template support for having a customized appearance. Instead of having the same look for the rotator we can use our desired templates by using the **template** property.

You can refer the following code example to give the template for the rotator.

{% highlight html %}

<ul id="sliderContent" ej-rotator [dataSource]="dataList" slideWidth="600px" slideHeight="223px" [enableAutoPlay]="true" [animationSpeed]="1200" [showPlayButton]="true" [template]="mytemplate">
                           </ul>



{% endhighlight %}



{% highlight js %}

export class AppComponent {
    mytemplate: any;
    dataList: Array<any>;
    constructor() {
        this.dataList = [
            { text: "Louis", color: "#43BDC2", eimg: "03", desig: "Representative", country: "England" },
            { text: "Silivia", color: "#80C344", eimg: "04", desig: "Representative", country: "Norway" },
            { text: "Linden", color: "#F68A3F", eimg: "05", desig: "Representative", country: "Australia" },
            { text: "Lawrence", color: "#E4BF21", eimg: "06", desig: "Representative", country: "India" }
        ];
        this.mytemplate = '<div style="background-color:${color}; height:300px"> <div style="padding: 32px 10px 20px 40px"> <img class="eimgs" src="../images/rotator/${eimg}.png" alt="employee" height="159px" width="159px"/> </div>' + '<div style="padding: 0 100px 0 250px"><div class="ename"> ${text} </div> <div class="desig"> ${desig} </div><div class="cont"> ${country} </div></div></div>';
    }
}




{% endhighlight %}



{% highlight css %}


<style type="text/css" class="cssStyles">

        .eimgs {
            border-radius: 50%;
            background-color: #DDDDDD;
            float: left;
        }

        .ename {
            font-family: segoe UI;
            font-weight: bold;
            font-size: 20px;
            padding-top: 10px;
            color: white;
        }

        .desig {
            font-family: segoe UI;
            font-size: 14px;
            opacity: 0.8;
            color: white;
            padding-bottom: 3px;
        }

        .cont {
            font-family: segoe UI;
            font-size: 14px;
            padding-top: 3px;
            border-top: 1px solid white;
        }
    </style>



{% endhighlight %}



![](template_images\template_img1.png)

### Providing template for each slide

The property **templateId** enables to bind multiple customized template items in Rotator. Hence we set the different template for each slide of rotator.



{% highlight html %}

<ul id="sliderContent" ej-rotator slideWidth="600px" slideHeight="223px" [showPager]="true" [templateId]="mytemplateid">
                           </ul>




{% endhighlight %}



{% highlight js %}


<script id="tt1" type="text/x-jsrender">
        <div id="t1">
            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="Snowfall" />
        </div>
    </script>
    <script id="tt2" type="text/x-jsrender">
        <div id="t2">
            <video width="472" height="350" controls style="margin-left: -2px;">
                <source src="video.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </script>
    <script id="tt3" type="text/x-jsrender">
        <div id="t3" style="height:400px">
            <audio style="width:468px;margin-top:120px;" controls>
                <source src="audio.mp3" type="audio/mp3">
                Your browser does not support the audio tag.
            </audio>
        </div>
    </script>
    <script id="tt4" type="text/x-jsrender">
        <div id='text4' style="background-color:lightgray; margin-top:-20px; height:370px">
            <div id="t4" class="text">
                <p><h2> World best mobile phones </h2></p>
            </div>
            <ul class="text1">
                <li><h4> Apple iPhone 6S  </h4></li>
                <li><h4> Samsung Galaxy S7Edge </h4></li>
                <li><h4> Oneplus 3 </h4></li>
                <li><h4> HTC 10 </h4></li>
                <li><h4> LG G5  </h4></li>
                <li><h4> Google Nexus 6P  </h4></li>
                <li><h4> Apple iPhone SE  </h4></li>
                <li><h4> Sony Z5 Premium </h4></li>
                <li><h4> Motorola Moto X Force </h4></li>
            </ul>
        </div>
    </script>
    <script id="tt5" type="text/x-jsrender">
        <div id="t5">
            <div class="leftPanel">
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="nature" />
            </div>
            <div class="rightPanel rightSide">
                <div class="contentPanel" style="color:yellow"><b>Tablet</b> </div>
                <ul>
                    <li>A tablet computer, or simply tablet, is a mobile computer with display, circuitry and battery in a single unit.</li>
                    <li>
                        Tablets are equipped with sensors, including cameras, microphone, accelerometer and touchscreen.
                    </li>
                </ul>
            </div>
        </div>
    </script>
   
{% endhighlight %}

{% highlight js %}

export class AppComponent {
    mytemplateid: any;
    constructor() {    
        this.mytemplateid = ['tt1', 'tt2', 'tt3', 'tt4', 'tt5'];
    }
}
{% endhighlight %}



![](template_images\providingtemplateforeachslide_img1.png)



