---
layout: post
title: Getting-Started | WaitingPopup | JavaScript | Syncfusion
description: getting started
platform: Angular 2
control: WaitingPopup
documentation: ug
keywords: ejwaitingpopup, waitingpopup, js waitingpopup 
---

# Getting Started

This section explains briefly about how to create a **WaitingPopup** in your application with **JavaScript**.
**Essential JavaScript WaitingPopup** provides support to display a **WaitingPopup** within your webpage. From the following guidelines, you can learn how to create a **WaitingPopup** in a real-time login page authentication scenario. 

The following screenshot illustrates the functionality of a **WaitingPopup** with login page scenario.

![](Getting-Started_images/Getting-Started_img1.png) 

You can give the Username and Password in the **login page**. When you click the **Login** button, you get the **WaitingPopup**. After loading, the alert box pops up with the message “Signed in successfully”.

## Create Username and Password

**Essential JavaScript WaitingPopup** widget basically renders built-in features like blocking the other actions until the page is loaded. You can easily create the **WaitingPopup** widget by using simple **&lt;div&gt;** element as follows.

Create an HTML file and add the following template to the HTML file.

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

Add an element to render a **WaitingPopup.**
 
{% highlight html %}

<div id="targetElement">
        <table class="loginTable">
            <tr>
                <td>Username</td>
                <td>
                    <input type="text" /></td>
            </tr>
            <tr>
                <td>Password</td>
                <td>
                    <input type="password" /></td>
            </tr>
            <tr>
                <td></td>
                <td>
                    <button id="button51" (click)="success($event)">login</button></td>
            </tr>
        </table>
        <ej-waitingpopup id="popup" ></ej-waitingpopup>  
</div>

{% endhighlight %}

Apply the following styles to show the **WaitingPopup**.

{% highlight css %}

<style type="text/css" class="cssStyles">
   #targetElement {
       width: 500px;
       height: 200px;
       margin: 50px;
       border: 1px solid #dbdcdb;
   }
   .loginTable {
       margin: 60px auto;
   }
   #popup_WaitingPopup .e-image {
       display: block;
       height: 70px;
   }
</style>

{% endhighlight %}

The following screenshot displays a **User** **login**.


![](Getting-Started_images/Getting-Started_img2.png) 

## Add WaitingPopup Widget

Initialize the WaitingPopup in script

To render the ejWaitingPopup using angular directive, we need to inject the ej angular directive with modules shown as below,


 In a real-time login page scenario, when you click the Login button, the WaitingPopup is displayed. 

{% highlight js %}

import {Component} from '@angular/core';
    
    @Component({
        selector: 'sd-home',
        templateUrl: 'app/components/waitingpopup/waitingpopup.component.html' // path for uploadbox component
        })
        export class WaitingPopupComponent { 
            constructor() {        
                }
            success(event){ 
		      var obj = jQuery("#popup").data("ejWaitingPopup");
              obj.setModel({showOnInit: true,target: "#targetElement"});
		    setTimeout(function() {
			 var obj = jQuery("#popup").data("ejWaitingPopup");
			 alert("Signed in successfully");
			 obj.hide();
		     }, 400); 
	      }
                  
       }

{% endhighlight %}


 The following screenshot shows the output of the above code example.

![](Getting-Started_images/Getting-Started_img3.png) 

