---
layout: post
title: Enable/Disable the optional features
description: How to enable/disable the optional features?
platform: Angular
control: Diagram
documentation: ug
---

# Constraints
Constraints are used to enable/disable certain behaviors of the diagram, node and connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (`&`, `|`, `~`, `<<`, etc.).
To know more about bitwise operators, refer to [Bitwise Operations](#bitwise-operations) 

## DiagramConstraints
Diagram constraints allow to enable or disable the following behaviors.

* Page Editing
* Line Bridging
* Zoom and Pan
* Undo Redo
* Crisp Edges
* Resizing

For more information about Diagram constraints, refer to [Diagram Constraints](/api/js/global#diagramconstraints "Diagram Constraints").

**Example**

The following example illustrates how to disable page editing.

{% highlight html %}

<div>
<ej-diagram  id="diagram" width="100%" height="600px" [constraints]="constraints">
</ej-diagram>
</div>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class ModelComponent {
    constraints: Object;
    constructor() {
        //Disables PageEditing
        this.constraints = ej.datavisualization.Diagram.DiagramConstraints.Default & ~ej.datavisualization.Diagram.DiagramConstraints.PageEditable
  }
};

{% endhighlight %}

## NodeConstraints

NodeConstraints allows to enable or disable the following behaviors of node.

* Selection
* Deletion
* Drag
* Resize
* Rotate
* Connect
* Drop shadow
* Drag label
* Define tooltip
* Crisp Edges
* Interaction

For more information about node constraints, refer to [Node Constraints](/api/js/global#nodeconstraints "Node Constraints")

**Example**

The following code illustrates how to disable rotation.

{% highlight javascript %}

export class ModelComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "Node",
                offsetX: 100,
                offsetY: 100,
                width: 50,
                height: 50,
                //Disables rotation
                constraints: ej.datavisualization.Diagram.NodeConstraints.Default & ~ej.datavisualization.Diagram.NodeConstraints.Rotate
            }
        ];
    }
}

{% endhighlight %}

## ConnectorConstraints

ConnectorConstraints allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection
* Deletion
* Drag
* Segment editing
* Define tooltip
* Bridging
* Label dragging
* Crisp Edges
* Interaction

For more information about connector constraints, refer to [Connector Constraints](/api/js/global#connectorconstraints "Connector Constraints")

**Example**

The following code illustrates how to disable selection.

{% highlight javascript %}

export class ModelComponent {
    connectors: Array<any>;
    constructor() {
        this.connectors = [
            {
                name: "connector",
                //Disables selection
                constraints: ej.datavisualization.Diagram.ConnectorConstraints.Default & ~ej.datavisualization.Diagram.ConnectorConstraints.Select
            }
        ];
    }
}

{% endhighlight %}

## PortConstraints

You can enable or disable certain behaviors of Port. They are as follows.

* Connect
* ConnectOnDrag

For more information about port constraints, refer to [Port Constraints](/api/js/global#portconstraints "Port Constraints")

**Example**

The following code illustrates how to disable creating connections with a port.

{% highlight javascript %}

export class ModelComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "Node",
                ports: [{
                //Sets the port as not connectable
                constraints: ej.datavisualization.Diagram.PortConstraints.None
                    }]
            }
        ];
    }
}

{% endhighlight %}

## SelectorConstraints
Selector visually represents the selected elements with certain editable thumbs. The visibility of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer
* Rotator
* User handles

For more information about Selector constraints, refer to [Selector Constraints](/api/js/global#selectorconstraints "Selector Constraints")

**Example**

The following code illustrates how to hide rotator.

{% highlight javascript %}

export class ModelComponent {
    selectedItems: Object;
    constructor() {
        this.selectedItems = [
            {
                //Hides rotator for selectedItems
                constraints: ej.datavisualization.Diagram.SelectorConstraints.All & ~ej.datavisualization.Diagram.SelectorConstraints.Rotator
            }
        ];
    }
}

{% endhighlight %}

## SnapConstraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only horizontal or vertical gridlines
* Show both horizontal and vertical gridlines
* Snap to either horizontal or vertical gridlines
* Snap to both horizontal and vertical gridlines

For more information about snap constraints, refer to [Snap Constraints](/api/js/global#snapconstraints "Snap Constraints")

**Example**

The following code illustrates how to show only horizontal gridlines.

{% highlight javascript %}

export class ModelComponent {
    snapSettings: Object;
    constructor() {
        this.snapSettings = [
            {
                //Shows horizontal gridlines
                snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowHorizontalLines
            }
        ];
    }
}

{% endhighlight %}

## Inherit behaviors

Some of the behaviors can be defined through both the specific object(node/connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram model.

{% highlight javascript %}

export class ModelComponent {
    connectors: Array<any>;
    constructor() {
        this.connectors = [
            {
            name: "connector",
            sourcePoint: {
                x: 100,
                y: 100
            },
            targetPoint: {
                x: 200,
                y: 200
            },

            //Sets to inherit bridging from model
            constraints: ej.datavisualization.Diagram.ConnectorConstraints.Default | ej.datavisualization.Diagram.DiagramConstraints.InheritBridging
            }
        ];
    }
}

{% endhighlight %}

## Bitwise Operations

**Bitwise Operations** are used to manipulate the flagged enumerations [enum]. In this section, Bitwise Operations are illustrated by using node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

### Add Operation

You can **add** or **enable** multiple values at a time by using **Bitwise** ‘\|’ (OR) **operator**.

{% highlight javascript %}

node.constraints = ej.datavisualization.Diagram.NodeConstraints.Select | ej.datavisualization.Diagram.NodeConstraints.Rotate;

{% endhighlight %}

In the above example, you can do both the selection and rotation.

### Remove Operation

You can **remove** or **disable** values by using **Bitwise** ‘&~’ (XOR) **operator**.

{% highlight javascript %}

var NodeConstraints = ej.datavisualization.Diagram.NodeConstraints;
node.constraints = node.constraints & ~(NodeConstraints.Rotate);

{% endhighlight %}

In the above example, **Rotation** is disabled but other constraints are enabled.

### Check Operation

You can check any value by using **Bitwise** ‘&’ (AND) **operator**.

{% highlight javascript %}

if ((node.constraints & (ej.datavisualization.Diagram.NodeConstraints.Rotate)) == (ej.datavisualization.Diagram.NodeConstraints.Rotate));

{% endhighlight %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.
