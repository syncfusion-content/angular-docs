---
layout: post
title: Getting-Started for Angular TagCloud
description: getting started for Angular TagCloud
platform: Angular
control: TagCloud
documentation: ug
keywords: TagCloud,js tagcloud,ejtagcloud
---

# Getting Started

This section explains briefly about how to create a **TagCloud** in your application with **Angular**. The **TagCloud** can be easily configured to the div element in which the tags are placed. The following screenshot illustrates the functionality of a **TagCloud** widget with a list of the topmost search engines. 

![](Getting-Started_images/Getting-Started1.jpg)

## Create TagCloud widget

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
     <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
     <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.Angular.min.js"></script>
     <script src="systemjs.config.js"></script>
     </head>
     <body>
     <ej-app>Loading...</ej-app>
     </body>
     </html>

{% endhighlight %}

Add necessary **HTML** elements to render TagCloud

{% highlight html %}

    <ej-tagcloud id="tag" titleText="Popular Sites" [dataSource]="list"></ej-tagcloud>

{% endhighlight %}

Add the following code example to add list of items to the **TagCloud** and initialize the **TagCloud** widget.

{% highlight html %}

        import {Component} from '@angular/core';
        @Component({
           selector: 'sd-home',
            templateUrl: 'app/components/tagcloud/tagcloud.component.html'
         })
        export class TagCloudComponent {
          list: array;
          constructor() {
      
          this.list = [
            { text: "Google", url: "http://www.google.co.in", frequency: 12 },
            { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
            { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
            { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
            { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
            { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
            { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
            { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
            { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
            { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
            { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
            { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
            { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
            { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
            { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
            { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
            { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
            { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

                ];
            }
       }
{% endhighlight %}

The following screenshot displays the output of the above code example.

![](Getting-Started_images/Getting-Started1.jpg) 

## Set Min and Max Font Size

In the above code example, the **frequency** properties are used to set the min and max font size to the **TagCloud** list item.

{% highlight javascript %}
   
    import {Component} from '@angular/core';

        @Component({
             selector: 'sd-home',
             templateUrl: 'app/components/tagcloud/tagcloud.component.html'
             })
              export class TagCloudComponent {
                    list: array;
                    constructor() {
                    this.list = [
            { text: "Google", url: "http://www.google.co.in", frequency: 12 },
            { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
            { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
            { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
            { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
            { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
            { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
            { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
            { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
            { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
            { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
            { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
            { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
            { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
            { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
            { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
            { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
            { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

                    ];
                }
           }

{% endhighlight %}

In the above code, the min font size is 0 and max font size is 12.

## Set event to perform an operation

Here, you can set the **TagCloud** events such as create, mouseover, mouseout, click.

{% highlight html %}

    <ej-tagcloud id="tag" titleText="Popular Sites" [dataSource]="list" (create)="onCreate($event)" (click)="onClick($event)" (mouseover)="onmouseover($event)" (mouseout)="onmouseout($event)"></ej-tagcloud>

{% endhighlight %}

{% highlight html %}

     import {Component,ViewEncapsulation} from '@angular/core';
 
        @Component({
           selector: 'ej-app',
           templateUrl: 'app/app.component.html',
            
             })
        export class AppComponent {
                list: array;
                 constructor() {
      
            this.list = [
            { text: "Google", url: "http://www.google.co.in", frequency: 12 },
            { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
            { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
            { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
            { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
            { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
            { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
            { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
            { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
            { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
            { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
            { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
            { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
            { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
            { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
            { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
            { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
            { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

        ];
    }
	
	onCreate($event)
	{
	alert();
	}
    
	onClick($event)
	{
	alert();
	}
      
    onmouseover($event)
	{
	alert();
	}
	
	onmouseout($event)
	{
	alert();
	}
	 
	 }

{% endhighlight %}

In the above code example, the **alert()** function is used  to show the events that happened.

