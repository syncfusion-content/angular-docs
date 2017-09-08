---
layout: post
title: Content Loading in Dialog component
description: How to load content to dialog component either using the Ajax, iframe, and Image.
platform: Angular
control: dialog
documentation: ug
---

# Load content

BY default, the content inside the Dialog element is considered as the content for the Dialog component. 

Also, we can render the Dialog component's content through the following ways.

1. request through AJAX

2. request iframe content

3. request image content

This settings can be specified through `contentType` property. 

{% highlight javascript %}

    <ej-dialog id="basicDialog" title="Dialog" contentUrl="app\components\dialog\test.html" contentType="ajax" 
    [(allowKeyboardNavigation)]="keyboard" containment="#parent">
    </ej-dialog>

{% endhighlight %}



Here below the content of that HTML file.

{% highlight html %}

    <div id="content">
        This content is loaded via AJAX request.
    </div>


{% endhighlight %}



![Load content](load-content_images\load-content_img1.png)

We can handle the AJAX request’s success and failures through the events “ajaxSuccess” and “ajaxError” events respectively. See also ajaxSuccess and ajaxError

The previous example is modified as below to handle the success and failure events.

{% highlight javascript %}

    <ej-dialog id="basicDialog" title="Dialog" contentUrl="app\components\dialog\test.html" contentType="ajax" 
    containment="#parent" (ajaxSuccess)="onSuccess($event)" (ajaxError)="onError($event)">
    </ej-dialog>

{% endhighlight %}

Add the following code in typescript file.

{% highlight javascript %}

    onSuccess(event) {
            //handle success event
                    }

	onError(event) {
            //handle Error event
                   }

{% endhighlight %}



N>The same way we can render the iframe and image content for the Dialog component by specifying the `contentType` as “iframe” and “image” respectively and also by specifying the proper location in the `contentUrl` property.

