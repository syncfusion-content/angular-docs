---
layout: post
title: Draw shapes, selection rectangles, or Pan Diagram, when you click and drag over the Digram surface
description: How to draw shapes or pan Diagram by clicking and dragging over the Diagram surface?
platform: Angular
control: Diagram
documentation: ug
---

# Tools

## Drawing Tools

Drawing tool allows you to draw any kind of node/connector during runtime by clicking and dragging on the Diagram page. 

### Shapes

To draw a shape, you need to set the JSON of that shape to the `drawType` property of the Diagram model and you have to activate the drawing tool by using the `tool` property. The following code example illustrates how to draw a rectangle at run time. 

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");

//JSON to create a rectangle
diagram.model.drawType = {
    type: ej.datavisualization.Diagram.Shapes.Basic,
    shape: "rectangle",
    //customize the appearance of the shape
    fillColor: "#fcbc7c",
    borderColor: "#f89b4c",
    labels: [{
        "text": "Rectangle"
    }]
};

//To draw an object once, activate draw once
diagram.update({
    tool: ej.datavisualization.Diagram.Tool.DrawOnce,
});

//To draw an object multiple times, activate continuous draw tool
diagram.update({
    tool: ej.datavisualization.Diagram.Tool.ContinousDraw,
});
{% endhighlight %}

![](/angular/Diagram/Tools_images/Tools_img1.png)

The following code example illustrates how to draw a path.

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");
diagram.model.drawType = {
    name: "Path",
    fillColor: "#fbe172",
    labels: [{
        text: "Path"
    }],
    shape: "path",
    pathData: "M13.560 67.524 L 21.941 41.731 L 0.000 25.790 L 27.120 25.790 L 35.501 0.000 L 43.882 25.790 L 71.000 25.790 L 49.061 41.731 L 57.441 67.524 L 35.501 51.583 z"
};

//To draw an object once, activate draw once
diagram.update({
    tool: ej.datavisualization.Diagram.Tool.DrawOnce,
});

{% endhighlight %}

![](/angular/Diagram/Tools_images/Tools_img3.png)

### Connectors

To draw connectors, you have to set the JSON of the connector to `drawType` property. The drawing tool can be activated by using the `tool` property as shown. The following code example illustrates how to draw a straight line connector. 

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");
//JSON to create a straight line connector
diagram.model.drawType = {
    type: "connector",
    segments: [{
        type: "straight"
    }]
};
//To draw an object once, activate draw once
diagram.update({
    tool: ej.datavisualization.Diagram.Tool.DrawOnce
});

{% endhighlight %}

![](/angular/Diagram/Tools_images/Tools_img2.png)

### Text 

Diagram??allows you to create a textNode as soon as you click on the Diagram page. The following code illustrates how to draw a text.

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");

//JSON to draw a text 
diagram.model.drawType = {
    type: "text"
};

diagram.update({
    tool: ej.datavisualization.Diagram.Tool.DrawOnce
});

{% endhighlight %}

Once you activate the TextTool, you can also able to perform label editing of a node/connector.

## Tool Selection

There are some functionalities that can be achieved by clicking and dragging on the Diagram surface. They are as follows.

* Draw selection rectangle - MultipleSelect tool
* Pan the Diagram - Zoom pan
* Draw nodes/connectors - ContinuousDraw / DrawOnce

As all the three behaviors are completely different, You can achieve only one behavior at a time based on the tool that you choose.
When more than one of those tools are applied, a tool is activated based on the precedence given in the following table. 

| Precedence | Tools | Description |
|---|---|---|
| 1st | ContinuesDraw | Allows you to draw the nodes or connectors continuously. Once it is activated, you cannot perform any other interaction in the Diagram. |
| 2nd | DrawOnce | Allows you to draw single node or connector. Once you complete the drawOnce action, SingleSelect and MultipleSelect tools are automatically enabled. |
| 3rd | ZoomPan | Allows you to pan the Diagram. When you enable both the SingleSelect and ZoomPan tools, you can perform the basic interaction as the cursor hovers node/connector. Panning is enabled when cursor hovers the Diagram. |
| 4th | MultipleSelect | Allows you to select multiple nodes and connectors. When you enable both the MultipleSelect and ZoomPan tools, cursor hovers the Diagram. When panning is enabled, you cannot select multiple nodes. |
| 5th | SingleSelect | Allows you to select individual nodes or connectors. |
| 6th | None | Disables all tools |

You can set the desired tool to the `tool` property of the Diagram model. The following code illustrates how to enable single/multiple tools.

{% highlight html %}

<ej-diagram id="diagram" width="100%" height="450" [tool]="tool">
</ej-diagram>

{% endhighlight %}

{% highlight javascript %}

// To Enable Single Tool 

export class OrganizationalChartComponent {
    tool: Object;
    constructor() {
        this.tool = ej.datavisualization.Diagram.Tool.SingleSelect;
        }
    }
{% endhighlight %}

{% highlight javascript %}

// Enables multiple tools

export class OrganizationalChartComponent {
    tool: Object;
    constructor() {
        this.tool = ej.datavisualization.Diagram.Tool.SingleSelect | ej.datavisualization.Diagram.Tool.ZoomPan;
        }
    }

{% endhighlight %}