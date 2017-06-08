---
layout: post
title: Getting started for Angular Tooltip
description: How to create the Tooltip in Angular
platform: Angular
control: Tooltip
documentation: ug
keywords : ejTooltip, Tooltip, js Tooltip, Tooltip widget
---
# Getting started

## Preparing HTML document

The Tooltip control has the following list of external JavaScript dependencies. 

* [jQuery](http://jquery.com/) 1.7.1 and later versions

* [jQuery.easing](http://gsgd.co.uk/sandbox/jquery/easing/) - to support animation effects in the components

Refer to the internal dependencies in the following table.

<table>
<tr>
<th>
File                                </th><th>
Description/Usage</th></tr>
<tr>
<td>
ej.core.min.js</td><td>
It is referred always before using all the JS controls.</td></tr>
<tr>
<td>
ej.tooltip.min.js</td><td>
The Tooltip's main file.</td></tr>
</table>

To get started, you can use the `ej.web.all.min.js` file that encapsulates all the `ej` controls and frameworks in one single file. So the complete boilerplate code is

Create an HTML page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}
    
	<!DOCTYPE html>
     <html>
     <head> 
     <link href="//cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
     <script src="node_modules/core-js/client/shim.min.js"></script>
     <script src="node_modules/zone.js/dist/zone.js"></script>
     <script src="node_modules/reflect-metadata/Reflect.js"></script>
     <script src="node_modules/systemjs/dist/system.src.js"></script>
     <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
	 <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
     <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
     <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.Angular.min.js"></script>
     <script src="systemjs.config.js"></script>
     </head>
     <body>
     <ej-app>Loading...</ej-app>
     </body>
     </html>

{% endhighlight %}

N> In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets)  to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.

For themes, you can use the `ej.web.all.min.css` CDN link from the code example given. To add the themes in your application, please refer to [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Create a Tooltip

The Tooltip can be created from any HTML element with the HTML `id` attribute and pre-defined options set to it. To create the Tooltip, you should call the `ejTooltip` jQuery plug-in function with the options as parameter. Refer to the following code example.

{% highlight html %}
 
       <div class="img" id="sample">
          <ej-tooltip [content]="content" [width]="width"><a>
               <img src="http://js.syncfusion.com/demos/web/images/tooltip/template-05.png" alt="Delphi">
                </a>
		</ej-tooltip>
        <div class="desc">Delphi Succinctly</div>
      </div>

{% endhighlight %}

{% highlight html %}

     import {Component} from '@angular/core';
     @Component({
     selector: 'sd-home',
      templateUrl: 'app/components/tooltip/tooltip.component.html' //path for tooltip component.
      })
     export class ToolTipComponent {
	             content : string;
				 width : string;
				 constructor() {
                 this.content = "Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms";
				 this.width = "270px";
				 }
			   
	 }
	 
{% endhighlight %}

Apply the following style sheet

{% highlight html %}

    <style>
       div.img {
        border: 1px solid #ccc;
        width: 159px;
        height: 213px;
        left: 35%;
        position: relative;
        top: 20%;
      }
     div.img img {
        width: 159px;
        height: 179px;
       }
     div.desc {
        padding: 8px;
        text-align: center;
       }
    </style>
    
{% endhighlight %}

![](Getteing-Started_images/Getteing-Started_img1.jpeg)

## Setting Dimensions

Tooltip dimensions can be set using [width](http://help.syncfusion.com/js/api/ejtooltip#members:width) and [height](http://help.syncfusion.com/js/api/ejtooltip#members:height) API.

{% highlight html %}
 
     <div class="control">
           TypeScript lets you write <a><ej-tooltip [content]="content" [width]="width" [height]="height"><u>JavaScript</u></ej-tooltip></a>the way you really want to.
    </div>
     
	 // Creates the Tooltip

{% endhighlight %}

{% highlight html %}

    import {Component} from '@angular/core';
     @Component({
     selector: 'sd-home',
      templateUrl: 'app/components/tooltip/tooltip.component.html' //path for tooltip component.
      })
     export class ToolTipComponent {
	              content : string;
				  width : string;
				  height:string;
				  constructor() {
                    this.content="JavaScript is the programming language of HTML and the Web";
				    this.width = "100px";
                    this.height="100px";
				   }
	 }
	 
{% endhighlight %}

## Tooltip Appearance 

You can configure the appearance of the Tooltip with the title, close button and call out as your application requires.

{% highlight html %}
 
     <div class="img" id="sample">
       <ej-tooltip [content]="content" [width]="width" [height]="height" closeMode="sticky" [isBalloon]="false" title="Delphi Succintly"><a>
        <img src="http://js.syncfusion.com/demos/web/images/tooltip/template-05.png" alt="Delphi">
        </a>
		</ej-tooltip>
        <div class="desc">Delphi Succinctly</div>
    </div>

// Creates the Tooltip
    
{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight html %}

    <style>
       div.img {
        border: 1px solid #ccc;
        float: left;
        box-sizing: border-box;
        height: 200px;
        width: 146px;
         }
        div.img img{
        width: 100%;
        height: 166px;
        }
       div.desc {
        padding: 6px;
        text-align: center;
         }
    </style>
    
{% endhighlight %}

![](Getteing-Started_images/Getteing-Started_img2.jpeg)

