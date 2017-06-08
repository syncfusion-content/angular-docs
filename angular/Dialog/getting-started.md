---
layout: post
title: Getting-Started
description: Getting Started
platform: Angular
control: dialog
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Dialog component with the step-by-step instructions.

# Create a Dialog

The following steps guide you to add a Dialog control.

1)	To get start with how to use the Dialog component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/gettingstarted/overview).

2)	Create a simple Dialog by adding ej-dialog attribute for initializing a Dialog component on the application. 

{% highlight javascript %}

       <ej-dialog id="basicDialog">
        
       </ej-dialog>

{% endhighlight %}

To get the following output from the above-mentioned code.

![](getting-started-images\getting-started-img1.png)

## Add dialog content

Add the below code to render dialog component with content.

{% highlight javascript %}

        <ej-dialog id="basicDialog" >
             This is a simple dialog
        </ej-dialog>
       
{% endhighlight %}

To get the following output from the above-mentioned code

![](getting-started-images\getting-started-img2.png)

## Set the title

To set the dialog component title as using the below mentioned code.

{% highlight javascript %}

       <ej-dialog id="basicDialog" title="Dialog">
            This is a simple dialog
       </ej-dialog>

{% endhighlight %}

To get the following output from the above-mentioned code.

![](getting-started-images\getting-started-img3.png)

## Open Dialog dynamically

In most cases, the Dialog components are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So, the Dialog component provides “open” and “close” methods to open/close the dialogs dynamically.
The Dialog Component can be hidden on initialize using showOnInit property which should be set to false.
The dialog will be opened on clicking the Button component. Refer to the below mentioned code.

{% highlight javascript %}

<div id="parent">
    <input id="btnOpen" style="display:block; height: 30px" type="button" class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" />
    <ej-dialog id="basicDialog" title="Dialog" (close)="onClose($event)" [showoninit]="showoninit">
        This is a simple dialog
    </ej-dialog>
</div>

{% endhighlight %}

Add the following code in the component’s constructor file.

{% highlight javascript %}

export class AppComponent {
    showoninit: boolean;
    constructor() {
        this.showoninit = false;
    }
    onClick(event) {
        $("#basicDialog").ejDialog("open");
    }
    onClose(event) {
        $("#btnOpen").show();
    }
}

{% endhighlight %}

To get the following output from the above-mentioned code.

![](getting-started-images\getting-started-img4.png)


N> You can find the Dialog component properties from the [API reference](https://help.syncfusion.com/api/js/ejdialog)              
