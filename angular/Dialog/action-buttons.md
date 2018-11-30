---
layout: post
title: action-buttons
description: action buttons
platform: Angular
control: Angular- Dialog
documentation: ug
---

## Action Buttons

The Dialog component provides the following action buttons.

1. Close

2. Maximize

3. Minimize

4. Pin/Unpin

5. Collapse/Expand

You can display only the necessary buttons in the Dialog component by configuring the **actionButtons** property.

Add the following code in HTML page to render Dialog component.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [actionButtons]="actionbuttons">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        actionbuttons: any;
        constructor() {
            this.actionbuttons = ["close", "maximize", "minimize"];
        }
    }

{% endhighlight %}

![Action Buttons](action-buttons_images\action-buttons_img1.png)

### Customizing Action Buttons

We can customize the action buttons in dialog component.

You can add new action button in the dialog component by configuring the **actionButtonClick** event.

Add the following code in HTML page to define actionButtonClick event of Dialog component.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [actionButtons]="actionbuttons" (actionButtonClick)="playMedia($event)">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        actionbuttons: any;
        constructor() {
            this.actionbuttons = ["close", "maximize", "minimize", "pin", "mediaplay", "search"];
        }
        playMedia(event){
            console.log(event.buttonID);
        }
    }

{% endhighlight %}


![Action Buttons](action-buttons_images\customizing-action-buttons_img1.png)

### Giving Modal dialog

The Dialog component’s [`modal dialog`](https://en.wikipedia.org/wiki/Modal_window) acts like a child window that is displayed on top of the main window/screen and disables the main window interaction until it is closed. We can enable or disable this modal dialog in our dialog component by using the property **enableModal**.

You can refer the following code example to set this property.



{% highlight html %}

    <ej-dialog id="lognForm" title="Modal dialog" [enableModal]="enablemodal" [enableResize]="resize" [isResponsive]="responsive">
        This is a simple model dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        enablemodal: boolean;
        resize:boolean;
        responsive:boolean;
        constructor() {
            this.enablemodal = true;
            this.resize=true;
            this.responsive=true;
        }
    }

{% endhighlight %}

![](action-buttons_images\giving-modael-dialog_img1.png)


### Containment

If the property **containment** is set, then dialog will append to the selected element and it is restricted to move only within the specified container element (i.e.) it is the selector for the container element. It is more useful for the modal dialog the place in a container. 

You can refer the following code example to set this property.

{% highlight html %}

    <div class="cols-sample-area">
        <ej-dialog id="lognForm" title="Modal dialog" [enableModal]="enablemodal" [containment]="containment" [enableResize]="resize" [isResponsive]="responsive">
            This is a simple model dialog
        </ej-dialog>
    </div>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        enablemodal: boolean;
        resize:boolean;
        responsive:boolean;
        containment:any;
        constructor() {
            this.enablemodal = true;
            this.resize=true;
            this.responsive=true;
            this.containment=".cols-sample-area";
        }
    }

{% endhighlight %}

In the above code we have restricted to move the dialog component with the given containment (i.e.) with the cols-sample-area 

![](action-buttons_images\containment_img1.png)

Note: This **containment** property is mostly used for the Modal dialog to restrict to specific container. And this property is similar to the “[target](https://help.syncfusion.com/api/js/ejdialog)” property but this additionally sets the drag area for dialog. Also this property overrides target property if both are set.

