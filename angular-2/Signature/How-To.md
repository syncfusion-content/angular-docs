---
layout: post
title: How To
description: How To
platform: Angular-2
control: Signature
documentation: ug
---

##How To?

### Save signature image with user defined format

By default the downloaded image form the signature canvas will be of **png** format. We can define our own format to download the image with **saveImageFormat** property. And we can also save the image along with the background by using the **saveWithBackground** property.

The following code example is used to download drawn image on the Signature control.

{% highlight html %}
<ej-signature id="mysign" [backgroundImage]="image" [saveWithBackground]="true" [saveImageFormat]="format" > </ej-signature>

<input id="btnOpen" style="height: 30px" type="button" class="ejinputtext" value="Save" (click)="onClick($event)"/>


{% endhighlight %}



Add the following script to define the download format for the canvas.

{% highlight js %}

export class SignatureComponent {
    image: any;
    format: any;
    constructor() {
     this.image = "image.png";
     this.format="jpeg";
    }
onClick(event) {
    let obj = $('#mysign').ejSignature('instance');
    obj.save("mysignature");
  }
 }

{% endhighlight %}


The following screenshot illustrates the Signature with saving (downloading) the drawn image.

![https://help.syncfusion.com/js/signature/How_To_images/savesignatureimagewithuserdefinedformat_img1.png](How_To_images\savesignatureimagewithuserdefinedformat_img1.png)

### Make signature as responsive

When the signature component is resized or even the window is resized the strokes drawn in the signature will be disappeared. To make the strokes visible even after resizing the window, we must set the **isResponsive** property as true.

The following code example is used to render the Signature component with responsive support.

{% highlight html %}

<ej-signature id="mysign" [isResponsive ]="true" > </ej-signature>


{% endhighlight %}


The following screenshot illustrates the Signature with responsiveness.

Before Responsiveness:

![https://help.syncfusion.com/js/signature/How_To_images/makesignatureasresponsive_img1.png](How_To_images\makesignatureasresponsive_img1.png)

After giving the Responsiveness:

![https://help.syncfusion.com/js/signature/How_To_images/makesignatureasresponsive_img2.png](How_To_images\makesignatureasresponsive_img2.png)



