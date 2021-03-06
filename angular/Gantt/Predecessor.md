---
layout: post
title: Predecessor
description: Predecessor
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Predecessor

## Predecessor offset with duration units

In Gantt, predecessor offset can be defined with the following duration units, 

* Day
* Hour
* Minute

We can define offset with various offset duration units for predecessors by using below code example

{% highlight javascript %}

<ej-gantt
    //...
    predecessorMapping= "Predecessor">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public data: any;
    constructor() {

        this.data = [
            //...
            Predecessor: "3FS+2d" {
                //...
                Predecessor: "3FS+16h"
            },
            {
                //...
                Predecessor: "3FS+960m"
            }
        ];
    }
}

{% endhighlight %}

The following screen shot depicts the duration unit support in the predecessor offset.

![](Predecessor_images/Predecessor_img1.png)

## Validate predecessor links on editing

In Gantt, it is possible to validate the taskbar editing based on the predecessor connections. Below are the following ways to validate the taskbar editing

* Using actionBegin event 
* Using validation dialog

### Using actionBegin event


actionBegin event with requestType argument as **validateLinkedTask** will be triggered when editing a task with predecessor links.

And it is possible to validate the editing within the actionBegin event using the **validateMode** event argument. The validateMode event argument has the following properties,

<table>
<tr>
<td>
Argument<br/><br/></td><td>
Default value<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
args.validateMode.respectLink<br/><br/></td><td>
False<br/><br/></td><td>
In this validation mode, the predecessor links will be considered as high priority. With this mode enabled, when the successor task is moved before predecessor task???s end date, the editing will be reverted and dates will be validated based on the dependency links.<br/><br/><br/><br/></td></tr>
<tr>
<td>
args.validateMode.removeLink<br/><br/></td><td>
False<br/><br/></td><td>
In this validation mode, the taskbar editing will be considered as high priority, where in the case of inappropriate task dates the dependency links will be removed and tasks will be moved to the edited date.<br/><br/><br/><br/></td></tr>
<tr>
<td>
args.validateMode.preserveLinkWithEditing<br/><br/></td><td>
True<br/><br/></td><td>
In this validation mode, taskbar editing will be considered along with the dependency links. There will be no validations in task editing.<br/><br/><br/><br/></td></tr>
</table>

By default, the **preserveLinkWithEditing** validation mode will be enabled, thus the validations will not occur when editing the linked tasks. 

The below code snippet explains enabling the **respectLink** validation mode while editing the linked tasks in the actionBegin event.

{% highlight javascript %}

<ej-gantt
    //...
    (actionBegin)= "actionBegin($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public data: any;
    constructor() {

    }
    actionBegin(sender) {
        if (sender.requestType == "validateLinkedTask") {
            sender.validateMode.respectLink = true;
        }
    }
}

{% endhighlight %}

### Using validation dialog:

When disabling all the validation modes in the actionBegin event, a validation popup will be displayed prompting the user to select the validation mode to validate taskbar editing.

This validation popup will display different options based on the successor task???s start date after editing.

If the user moved the successor task, that starts after predecessor task???s end date then the dialog will be rendered with below options,

* Cancel, Keep the existing link
* Remove the link and move the task to start on edited date.
* Move the task to start on edited date and keep the link.

If the user moved the successor task, that starts before the predecessor task???s end date then the dialog will be rendered with below options.

* Cancel, Keep the existing link
* Remove the link and move the task to start on edited date.

The following code example explains this.

{% highlight javascript %}

<ej-gantt
    //...
    (actionBegin)= "actionBegin($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public data: any;
    constructor() {

    }
    actionBegin(sender) {
        if (sender.requestType == "validateLinkedTask") {
            sender.validateMode.preserveLinkWithEditing = false;
        }
    }
}

{% endhighlight %}

In this case, if the user dragging action violated the predecessor type then the following dialog will be rendered to perform operation.

![](Predecessor_images/Predecessor_img2.png)




