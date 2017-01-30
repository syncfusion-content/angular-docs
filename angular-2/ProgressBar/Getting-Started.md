---
layout: post
title: Getting-Started | ProgressBar | JavaScript | Syncfusion
description: getting started
platform: angular-2
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, js progressbar
---

# Getting Started

This section briefly describes how to create a **ProgressBar** control using **Javascript** and learn its features.
**Essential JavaScript** **ProgressBar** displays a **ProgressBar** within a webpage that allows you to show the progress of an event. Here, you can learn how to customize the progress and color of the **ProgressBar** in a real-time application to indicate the strength of the password, where the progress changes with respect to the change in length of the password. This helps you to validate the password is typed. 

The following screenshot shows the **ProgressBar.**

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img1.png) 

## Create a ProgressBar

**Essential JavaScript ProgressBar** widget is created using a simple **&lt;div&gt;** element. This element provides built-in features that allow you to change the progress, size and text of the control.

You can create the **ProgressBar** widget by using a simple input **&lt;div&gt;** element as follows:

 Create an **HTML** file and add the following template to the **HTML** file to create your ProgressBar. It also includes the necessary scripts and styles.

{% highlight html %}

<!DOCTYPE html>
<html>
   <head> 
    <link href="//cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script> 
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    <script src="systemjs.config.js"></script>
  </head>
  <body>
   <ej-app>Loading...</ej-app>
  </body>
</html>

{% endhighlight %}

 Add **&lt;input&gt;** element inside the **&lt;body&gt;** tag of your file to create a **ProgressBar.**

{% highlight html %}

<div class="frame" > 
    <div class="wrap_up" >
        <!-- Initializing password field* -->
        <label for="startButton" > Password</label > 
            <input type="password" id="password" (keypress)="eventHandler($event.keyCode)" >
    </div > 
    <div class="control" >
        <!-- initializing ProgressBar control-- > 
        <ej-progressbar id="progressBar" value="45" height="20" text="45%" width="200" > </ej-progressbar > 
    </div > 
</div >

{% endhighlight %}

To render the ejProgrssBar using angular directive, we need to inject the ej angular directive with modules.

It also includes a Password field and through that the progress of the **ProgressBar** can be controlled

Initialize **ProgressBar** in script.

{% highlight js %}
 
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/progressbar/progressbar.component.html'
})
export class ProgressBarComponent {  
} 

{% endhighlight %}

Here, you can initialize the properties of the **ProgressBar** such as height, value, width, text that is applied to the control by default.

The following screenshot displays a **ProgressBar** control.

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img2.png) 

Include the following code within the **&lt;head&gt;** tag to change the page layout.

{% highlight css %}

<style type="text/css" class="cssStyles">
   /*applying styles */
   .frame {
       border: 1px solid #BBBCBB;
       border-radius: 10px 10px 10px 10px;
       padding: 50px 60px;
       margin-top: 40px;
       width: 400px;
       margin-left: 400px;
   }
   .control {
       margin-bottom: 5px;
       margin-left: 230px;
   }
   .wrap_up {
       margin-left: 105px;
       font-size: 18px;
   }
   #progressBar {
       margin-top: 10px;
   }
</style>

{% endhighlight %}

## Progress Control using Length of the Password Field

In real-time scenario, the progress of **ProgressBar** is changed according to the length of text in the password field by binding the change in the properties of control and checking the length of the password field.

Add the following code example inside the **&lt;script&gt;** tag of your **HTML** file.

{% highlight js %}
 
import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',
})
export class AppComponent {
	content:string;
	i: number;
	k: number;
	progresObj: any;
	buttonObj: any;
	timer: any;
	obj: any;
	  constructor() {
			this.k=10;
			this.i=0;
			this.timer= window.clearInterval(this.timer);
		  this.content="Description: The Rich Text Editor (RTE) control is an easy to render in client side. Customer easy to edit the contents and get the HTML content from RTE";
	  }
	  
	  eventHandler(event) {
			 this.progresObj= jQuery("#progressBar").data("ejProgressBar");
   console.log(event, event.keyCode, event.keyIdentifier);
   this.i = jQuery("#password").val().length;
        if (this.i < 5) 
            this.weak();
        else if (this.i == 5 && this.i < 7) 
            this.Strong();
        else if(this.i==7 || this.i>7) {
        var pwd = jQuery("#password").val(); 
            this.very_strong();
			}
}
 Strong() {     //Change the width and text of the progress ... called when the length is greater than 5
        this.progresObj.option("text", "strong");
        this.progresObj.option("percentage", this.k + 50);
        jQuery(".e-progress").css("background-color", "#0055FF");
        jQuery(".e-progressbar").css("color", "#000000");       
    }
very_strong() {     //Change the width and text of the progress ... called when the length is greater than 7
        this.progresObj.option("text", "Very strong");
       this. progresObj.option("percentage", this.k + 90);
        jQuery(".e-progress").css("background-color", "Green");
        jQuery(".e-progressbar").css("color", "#000000");   
    }
		weak() {     //Change the width and text of the progress... called when the length is less than 5
        this.progresObj.option("text", "Weak");
        this.progresObj.option("percentage", this.k+20 );
        jQuery(".e-progress").css("background-color", "#DE0909");
        jQuery(".e-progressbar").css("border-radius", "10px");      
    }
}

{% endhighlight %}

You can calculate length of the password and call the appropriate function that changes the percentage property of **ProgressBar**.

* The **weak()** function changes the text inside the ProgressBar to **Weak** and percentage to 30, that is invoked when the length of the text is less than 5.
* The **strong()** function changes the text inside the ProgressBar to **Strong** and percentage to 60, that is invoked when the length of the text exceeds 5.
* The **very_strong()** function changes the text inside the ProgressBar to Very **Strong** and percentage to 100, that is invoked when the length of the text exceeds 7 and the text contains a symbol in it.

You can change themes or appearance of the ProgressBar as required.

The final output is displayed as follows.

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img3.png) 

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img4.png) 

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img5.png) 

You can also bind an event at the start and finish of a ProgressBar by using the start, complete and change properties of the ProgressBar.

