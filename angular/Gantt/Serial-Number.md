---
layout: post
title: Serial Number
description: Serial Number
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Serial Number

The Serial number support in Gantt control provides the sequential order structure for all the available collections of tasks in Gantt chart. The Serial number column can be enabled in Gantt control, with the help of enableSerialNumber property by assigning the “true” value to it. While enabling this property Serial number column will be included and Task Id column will be hidden as well as the default behavior of “Predecessor” column will be changed. In general Predecessor column will be rendered and updated with the value of “Task Id”. But on enabling Serial number support, it will be rendered and updated with the value of “Serial number” of corresponding tasks.

Code snippets for enabling Serial number:

{% highlight javascript %}

<ej-gantt id="GanttControl" [enableSerialNumber]="true"
    //...>
</ej-gantt>

{% endhighlight %}


The following screenshot displays the Serial number column in Gantt control.

![](Serial_Number_images/Serial_img1.png)

