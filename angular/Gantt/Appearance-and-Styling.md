---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Appearance and Styling

You can customize the look and feel of the Gantt control by applying themes and formatting the schedule header.

## Schedule Header Customization

You can customize the week header format and day header format in the Schedule part of the Gantt control by using the following code example.

{% highlight html %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings" >
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public scheduleHeaderSettings: any;
  constructor() {
      this.scheduleHeaderSettings = {
          weekHeaderFormat: "MMM yyyy",
          dayHeaderFormat: "d",
          weekendBackground: '#F2F2F2'
      }
  }
}

{% endhighlight %}

The following screenshot shows the customized format schedule header in Gantt control.

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## Taskbar Customization

You can customize the Taskbar based on the task information in Gantt control to highlight the task. The following code example shows how to customize the Taskbar in Gantt control.

{% highlight html %}

<ej-gantt #events id="GanttControl" (queryTaskbarInfo)="onganttqueryTaskbarInfo($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
  constructor() {      
   }
  onganttqueryTaskbarInfo(sender) {
        if (sender.data.level === 0) {
            sender.parentTaskbarBackground = "pink";
            sender.parentProgressbarBackground = "cyan";
        } else {
            if (sender.data.status == "60") {
                sender.progressbarBackground = "red";
            } else if (sender.data.status == "70") {
                sender.progressbarBackground = "yellow";
            } else if (sender.data.status == "80") {
                sender.progressbarBackground = "green";
            }
        }
    }

}

{% endhighlight %}

The following screenshot shows the customized taskbar in Gantt control.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

## Themes

 The following are the types of themes available in Gantt control.

1.Flat Azure                           
2.Flat Azure Dark                  
3.Flat Lime                             
4.Flat Lime Dark                   
5.Flat Saffron                        
6.Flat Saffron Dark
7.Gradient Azure
8.Gradient Azure Dark
9.Gradient Lime
10.Gradient Lime Dark
11.Gradient Saffron
12.Gradient Saffron Dark
13.Bootstrap
14.High Contrast
15.Material
16.Office 365

You can apply the theme (Gradient lime) to the Gantt control by using the style sheet from the online link as follows.

{% highlight html %}

    <!DOCTYPE??html>

    <html xmlns="http://www.w3.org/1999/xhtml">
        <head>
        <title>Getting Started with Gantt Control for JavaScript</title>
        <!-- style sheet for default theme(gradient lime) -->
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />??
        //...
    </html>

{% endhighlight %}

The following screenshot shows the Gantt control with `Gradient-lime` theme.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

