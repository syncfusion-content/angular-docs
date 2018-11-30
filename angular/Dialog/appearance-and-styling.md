---
layout: post
title: appearance-and-styling
description: appearance and styling
platform: Angular
control: Angular- Dialog
documentation: ug
---

## Appearance and styling

### Showing header

In order to display any title for our dialog, we can use the **showHeader** property to display the header of the Dialog. By default, showHeader property is true in Dialog.	

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [showHeader]="showheader">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        showheader:boolean;
        constructor() {
            this.showheader=false;
    }

{% endhighlight %}

### Display dialog on initialization

Using **showOnInit** property to true or false, we can either display our dialog on the page load or on any actions. By default, showOnInit property is true in Dialog.

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [showOnInit]="showoninit">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        showoninit:boolean;
        constructor() {
            this.showoninit=false;
    }

{% endhighlight %}

### Applying Rounded Corner

You can use **showRoundedCorner** property to add rounded borders to the dialog popup elements. By default, rounded corner property is disabled in Dialog.

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [showRoundedCorner]="showroundedcorner">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        showroundedcorner:boolean;
        constructor() {
            this.showroundedcorner=true;
    }

{% endhighlight %}


![](appearance-and-styling_images\applying-rounded-corner_img1.png)

### Responsive Dialog:

To set the Dialog the dialog to be responsive set the **isResponsive** property as true. By default, isResponsive property is disabled in Dialog. This will override the height and width set for Dialog on resizing the widow and in device view.

### Using Adding HTML attributes

Using the **htmlAttributes** property we can directly set our own html attributes to the wrapper of the Dialog component.

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [htmlAttributes]="htmlattributes">
        This is a simple dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        htmlattributes:object;
        constructor() {
            this.htmlattributes={
                    class: "my-class", style: "border:1px solid red"
                }
    }
    }

{% endhighlight %}

![](appearance-and-styling_images\using-adding-html-attributes_img1.png)

