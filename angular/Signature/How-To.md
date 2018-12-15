---
layout: post
title: How To
description: How To
platform: Angular
control: Signature
documentation: ug
---

##How To?

### Save signature image with user defined format

By default the downloaded image from the signature canvas will be of **png** format. We can define our own format to download the image with **saveImageFormat** property. And we can also save the image along with the background by using the **saveWithBackground** property.

The following code example is used to download drawn image on the Signature component.

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


### To clear the Signature

To clear the signature, you can simply use the **clear()** method. This method will clear all the drawn strokes in the signature canvas and leaves it empty.

{% highlight html %}
<ej-signature id="mysign" [height]="height" > </ej-signature>

<input id="btnOpen" style="height: 30px" type="button" class="ejinputtext" value="Save" (click)="onClick($event)"/>


{% endhighlight %}

Add the following script to clear the Signature.

{% highlight js %}

export class SignatureComponent {

    constructor() {
      this.height = 300;
    }
onClick(event) {
    let obj = $('#mysign').ejSignature('instance');
    obj.clear();
  }
 }

{% endhighlight %}

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


### To check whether any input to the signature control since render

We can detect whether not there has been any input to the signature control since it has rendered. To detect we can use the storeSnap public variable, which is an array that stores all the canvas inputs. At initial rendering this array is empty and we can use this variable to check for the drawn strokes.


{% highlight js %}

export class SignatureComponent {

      let obj  = $("#signature").ejSignature("instance");

            if (ej.isNullOrUndefined(sign.storeSnap)) {
               
                //Something

            }

}

{% endhighlight %}
