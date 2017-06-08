---
layout: post
title: Zoom and Print support in RichTextEditor widget
description: Zoom and Print support for RichTextEditor widget
platform: Angular
control: RichTextEditor
documentation: ug
---
# Zoom

The editor provides zoom tools which enlarges the view of an editor's object enabling you to see more detail. You can continuous zoomIn and zoomOut either using zoom tools or keyboard.

You can assign Increases and decreases of zooming range using [zoomStep](http://help.syncfusion.com/api/js/ejrte#members:zoomStep) property

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [(toolsList)]="toolslist" [(tools)]="tools" [zoomStep]="zoomstep"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    toolslist: any;
    tools: Object;
    zoomstep: any;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.toolslist = ["view"];
        this.tools = { view: ["zoomIn", "zoomOut"] };
        this.zoomstep = 0.1;
    }
}

{% endhighlight %}

![](ZoomandPrint_images/zoom.png)

# Print

The editor provides print tools which use to print the contents of the editor.

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [(toolsList)]="toolslist" [(tools)]="tools"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    toolslist: any;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.toolslist = ["print"];
        this.tools = { print: ["print"] };
    }
}

{% endhighlight %}

![](ZoomandPrint_images/print.png)