---
layout: post
title: Start-and-Depth-level
description: start and depth level
platform: Angular
control: DateTimePicker
documentation: ug
---

# Start and Depth level

## Start Level

**DateTimePicker** allows you to change the starting level view of Calendar inside the **DateTimePicker** popup. Consider you are creating a login form for your blog. If the “Birth date” field in the form starts from year, it is easy to select date from year, month and date. By default, the Start Level of **DateTimePicker** is “Month” level view. Refer the following table to know the different types of start level.

Start Level

<table>
   <tr>
      <th>
         Start Level 
      </th>
      <th>
         Syntax
      </th>
      <th>
         Description
      </th>
   </tr>
   <tr>
      <td>
         month
      </td>
      <td>
         startLevel: “month”
      </td>
      <td>
         Starts from month level view.
      </td>
   </tr>
   <tr>
      <td>
         year
      </td>
      <td>
         startLevel: “year”
      </td>
      <td>
         Starts from year level view.
      </td>
   </tr>
   <tr>
      <td>
         decade
      </td>
      <td>
         startLevel: “decade”
      </td>
      <td>
         Starts from year decade level view.
      </td>
   </tr>
   <tr>
      <td>
         century
      </td>
      <td>
         startLevel: “century”
      </td>
      <td>
         Starts from century level view.
      </td>
   </tr>
</table>


In the following example **DateTimePicker** popup start level view is set to “century level” when you drop down the **DateTimePicker** popup.

Add the following code in your **HTML** page.

{% highlight html %}
  
    <div align="center">
    <input type="text" id="dateTime" ej-datetimepicker width='200' startLevel="century" [(ngModel)]="value">
    </div>

{% endhighlight %}


{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html'
})
export class DefaultComponent {
    value: any;
    constructor() {
        this.value = Date();
    }
}

{% endhighlight %}

![](/DateTimePicker/Start-and-Depth-level_images/Start-and-Depth-level_img1.png)


## Depth Level

**DateTimePicker** enables you to set the drill down level of **DateTimePicker**. Consider, you are going to take the monthly report of sales in your company. In that case, there is no need for selecting date from month view. You can restrict the drill-down of **DateTimePicker** popup to month view.

In the following example, start level is set from century and drill down is set to year view. So drill-down to month is restricted. So you can avoid selecting the day of the month. By default, the current day of the month is maintained in the day number field. Refer the following code to set drill down value to year view.

The following code snippet is set to depth level in **DateTimePicker.**


{% highlight html %}

    <div align="center">
    <input type="text" id="dateTime" ej-datetimepicker width='200' startLevel="century" depthLevel="year" [(ngModel)]="value">
    </div>
                   

{% endhighlight %}

{% highlight html %}

    import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html'
})
export class DefaultComponent {
    value: any;
    constructor() {
        this.value = Date();
    }
}

                   

{% endhighlight %}

![](/DateTimePicker/Start-and-Depth-level_images/Start-and-Depth-level_img2.png)


