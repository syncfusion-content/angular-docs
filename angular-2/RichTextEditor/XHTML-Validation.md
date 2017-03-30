---
layout: post
title: XHTML Validation in RichTextEditor widget
description: XHTML Validation to format the RichTextEditor widget's content
platform: Angular2
control: RichTextEditor
documentation: ug
---

# XHTML Validation

The editor provides option to validate its content through the [enableXHTML](http://help.syncfusion.com/api/js/ejrte#members:enablexhtml) property. When you set or modify the content into the editor, it continuously checks whether the HTML source of the content that you are creating is valid. The editor examines the HTML markup and then removes the elements or attributes that are not valid. 

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [enableXHTML]="true"></textarea>
 
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images, it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
}

{% endhighlight %}

The editor checks the following settings on validation:

* **Attributes** 
  * Must be specified in lowercase 
  * Proper use of quotation marks around the attributes
  * Must be valid attributes for corresponding HTML element
  * All the required attributes must be included in the HTML element
  * Accepts the allowed values alone such as true or false.
* **HTML** **Elements** 
  * Must be in lowercase 
  * All opening tags must be closed
  * Allows only the valid HTML elements