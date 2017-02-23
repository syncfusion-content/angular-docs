---
layout: post
title: getting started
description: getting started
platform: js
control: Control Name undefined
documentation: ug
---

# Getting Started

The Angular2 Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature using mouse or touch.

This section explains briefly about how to create a **Signature** component in your application with Angular2 by the following step-by-step instructions. The following screenshot demonstrates the functionality of Signature component.

![https://help.syncfusion.com/js/signature/Getting_Started_images/gettingstarted_img1.png](Getting_Started_images\gettingstarted_img1.png)

## Create an Signature component in Angular2

Create a new HTML file and include the below code:

{% highlight html %}

  <!DOCTYPE html>
    <html>
    <head>
        <link href="//cdn.syncfusion.com/{{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="node_modules/core-js/client/shim.min.js"></script>
        <script src="node_modules/zone.js/dist/zone.js"></script>
        <script src="node_modules/reflect-metadata/Reflect.js"></script>
        <script src="node_modules/systemjs/dist/system.src.js"></script>
        <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.web.all.min.js" type="text/javascript"></script>
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/common/ej.angular2.min.js"></script>
        <script src="systemjs.config.js">
        </script>
    </head>
    <body>
        <ej-app>Loading...</ej-app>
    </body>



{% endhighlight %}



Create **div** element and add in the body tag as below.

{% highlight html %}

  <div style="width:300px;height:600px;">

<ej-signature > </ej-signature>
        </div>



{% endhighlight %}



To render the Angular2 Signature use the below code.

{% highlight js %}


import { Component } from '@angular/core';

@Component({
    selector: 'sd-home',
    templateUrl: 'app/signature.component.html'
})
export class SignatureComponent {

    constructor() {
    }
}


{% endhighlight %}



Run the above code to render the following output.

![https://help.syncfusion.com/js/signature/Getting_Started_images/createsignaturecontrol_img1.png](Getting_Started_images\createansignaturecomponentinangular2_img1.png)



## Adjusting Signature Size

You can customize the width and height of the Signature by width and height properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature component with customized width and height.

Add the following HTML to render signature with customized width and height.

{% highlight html %}


 <ej-signature [height]="height" [width]=”width">
    </ej-signature>


{% endhighlight %}



Add the following script to render signature with customized width and height.

{% highlight js %}

import { Component } from '@angular/core';

@Component({
    selector: 'sd-home',
    templateUrl: 'app/signature.component.html'
})
export class SignatureComponent {
    constructor() {
        this.width = 200;
        this.height = 300;

    }
}


{% endhighlight %}





 The following screenshot illustrates signature with customized width and height.

![https://help.syncfusion.com/js/signature/Getting_Started_images/adjustingsignaturesize_img1.png](Getting_Started_images\adjustingsignaturesize_img1.png)





