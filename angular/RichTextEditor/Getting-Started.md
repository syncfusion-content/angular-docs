---
title: Getting Started with Angular RichTextEditor | Syncfusion
description: Learn here all about getting started with Syncfusion Essentia Angular RichTextEditor control, it's elements and more details.
platform: Angular
control: RTE
documentation: Ug
keywords: ejrte, rte, js rte
---

# Getting started with Angular RichTextEditor

This section helps to understand the getting started of RTE control with the step-by-step instruction.

## Create RTE Control

Create an HTML page and add the scripts references in the order mentioned in the following code example.

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

## Initialize RTE

In the `rte` component HTML file.

{% highlight html %}

<textarea ej-rte width="600px" height="300px"></textarea>

{% endhighlight %} 
 
{% highlight js %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',
})
export class AppComponent {  
}

{% endhighlight %}

Now, the RTE is rendered.

![Angular RTE.](Getting-Started_images/angular-rich-text-editor-getting-started.png)

## Toolbar–Configuration

You can configure a toolbar with the tools as your application requires.

{% highlight html %}
 
 <textarea ej-rte width="600px" height="300px" [(toolsList)]="tools"></textarea>

{% endhighlight %}

{% highlight js %}

import {Component} from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: 'app/components/rating/rating.component.html'
})
export class RatingComponent {
    tools: any; 
    constructor() {
        this.tools = ["formatStyle", "font", "style", "effects", "alignment", "lists", "indenting", "clipboard", "doAction", "clear", "casing", "customTools", "print"];  
    }
}

{% endhighlight %}

The above code example displays the following output.

![Angular RichTextEditor tools.](Getting-Started_images/angular-rich-text-editor-tool.png)

You can set the content of the editor as follows.

{% highlight html %} 

 <textarea ej-rte width="600px" height="300px" [(value)]="content"></textarea>

{% endhighlight %}

{% highlight js %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',
})
export class AppComponent {
	content:string;
	  constructor() {
		  this.content="Description: The Rich Text Editor (RTE) control is an easy to render in client side. Customer easy to edit the contents and get the HTML content from RTE";
	  }
}

{% endhighlight %}

The following screenshot displays a RTE widget.

![Angular RichTextEditor value.](Getting-Started_images/angular-rich-text-editor-value.png)