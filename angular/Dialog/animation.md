---
layout: post
title: animation
description: animation
platform: Angular
control: Angular- Dialog
documentation: ug
---

## Animation

The Dialog component can be animated while opening and closing the dialog.

We can specify the effect and the duration for the animation. The two types of effects of Dialog are slide and fade. We can configure these settings separately for open and close dialog actions.

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [actionButtons]="Icons" [animation]="animation">
        This is a dialog
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        Icons:any;
        animation:object;
        constructor() {
            this.Icons=["close", "maximize", "minimize"];
            this.animation={show: {effect: "slide",duration: 500},hide: {effect: "fade",duration: 500}};
    }

{% endhighlight %}

![Animation](animation_images\animation_img1.png)


### Loading Dialog content

By default, the content inside the Dialog element is simply the user given content. But also, we can render the Dialog’s component content through the following ways.

1. AJAX

2. Using iframe

3. iImage

This settings can be specified through **contentType** property.


#### AJAX

We can load the content through AJAX by setting the **contentType** property as ajax.

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [contentUrl]="contenturl" [contentType]="contenttype">
    </ej-dialog>

{% endhighlight %}


The content of that `dialogcontent.html` file is below:

**&lt;div id="content"&gt;** This content is loaded via AJAX request. **&lt;/div&gt;**

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        contenturl:any;
        contenttype:any;
        constructor() {
            this.contenturl="dialogcontent.html";
            this.contenttype="ajax";
    }

{% endhighlight %}

![Load content](animation_images\ajax_img1.png)

We can handle the AJAX request’s success and failures through the events “ajaxSuccess” and “ajaxError” events respectively. See also ajaxSuccess and ajaxError

The previous example is modified as below to handle the success and failure events.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [contentUrl]="contenturl" [contentType]="contenttype" (ajaxSuccess)="onSuccess($event)" (ajaxError)="onError($event)">
    </ej-dialog>

{% endhighlight %}






#### Iframe



We can also load the content in iframe by setting the **contentType** property as iframe.


Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [contentUrl]="contenturl" [contentType]="contenttype">
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        contenturl:any;
        contenttype:any;
        constructor() {
            this.contenturl="dialogcontent.html";
            this.contenttype="iframe";
    }

{% endhighlight %}

![](animation_images\iiframe_img1.png)


#### Image 

We can also load an image as the content by setting the **contentType** property as image

Add the following code in HTML page.

{% highlight html %}

    <ej-dialog id="dialog" title="Dialog" [contentUrl]="contenturl" [contentType]="contenttype">
    </ej-dialog>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        contenturl:any;
        contenttype:any;
        constructor() {
            this.contenturl=" http://js.syncfusion.com/demos/web/content/images/twitter.jpg";
            this.contenttype="image";
    }

{% endhighlight %}


![](animation_images\iimage-_img1.png)



