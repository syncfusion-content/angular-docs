---
layout: post
title: Visually represent a business process with its functional blocks/departments
description: How to visually represent a business process and the relationships among its functional blocks?
platform: Angular
control: Control Name undefined
documentation: ug
---

# Swim lane

Swim-lane Diagrams are typically used to visualize the relationship between a business process and the department responsible for it by focusing on the logical relationships between activities. Swimlanes may be arranged either horizontally or vertically.

## Initialize Diagram

Add a placeholder `div` element that can be used to initialize the diagram widget as shown below.

{% highlight html %}

<div>
    <ej-diagram id="diagramCore" width="100%" height="100%">
    </ej-diagram>
</div>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/swimlane.component.html',
})

export class SwimlaneComponent {
    constructor() {}}

{% endhighlight %}

## Create a swimlane

To create a swimlane, you need to define an object with `isSwimlane` property that helps identify the object as a swimlane. By default, the swimlanes are arranged vertically. You can change that with the `orientation` property of swimlane.

The following code example illustrates how to define a swimlane object.

{% highlight javascript %}

export class SwimlaneComponent {
    nodes: Array<any>;
        constructor() {
            this.nodes = [{
                type: "swimlane",
                name: "swimlaneNode",
                //Changes the orientation
                orientation: "horizontal",
                //Sets the position and size
                offsetX: 400,
                offsetY: 200,
                height: 100,
                width: 700
            }]
        }
    }

{% endhighlight %}

## Add swimlane into diagram

Adding a swimlane to the Diagram is same as adding a node. You can add either through the `nodes` collection or through the client side method `add`. You can also drag and drop a swimlane from symbol palette.
For more information about adding a node/swimlane to the Diagram, refer to [Add Nodes](/angular/Diagram/Node#create-node "Add Nodes").

The following code example illustrates how to add a swimlane to the Diagram through `nodes` collection.

{% highlight html %}

<div>
    <ej-diagram id="diagramCore" width="100%" height="100%" [nodes]="nodes">
    </ej-diagram>
</div>

{% endhighlight %}

![](/angular/Diagram/Swim-lane_images/Swim-lane_img2.png)

## Headers

Swimlane allows to define a header to textually describe it. The `header` property of swimlane allows you to define its textual description(`text`) and to customize its appearance. The following code example illustrates how to define swimlane header.

{% highlight javascript %}

export class SwimlaneComponent {
    nodes: Array<any>;
        constructor() {
            this.nodes = [{
                type: "swimlane",
                name: "swimlane",
                //Defines the header and format its text
                header: {
                    'text': 'Swimlane', 
                    'height': 50, 
                    'fillColor': '#C7D4DF', 
                    'fontSize': 11,
                    'fontFamily': "Arial",
                    'bold': true,
                    'italic': true,
                    'textDecoration': "underline" },
                orientation: "horizontal",
                offsetX: 400,
                offsetY: 200,
                height: 100,
                width: 700
            }]
        }
    }

{% endhighlight %}

![](/angular/Diagram/Swim-lane_images/Swim-lane_img3.png)

### Disable headers

You can hide the swimlane headers. The following code example illustrates how to hide headers.

{% highlight javascript %}

var header = {
    text: "Swimlane",
    //Sets "0" to hide header
    height: 0
};

{% endhighlight %}

## Lane

Lane is a functional unit or a responsible department of a business process that helps to map a process within the functional unit or in between other functional units.
You can add any number of lanes to a swimlane and the lanes are automatically stacked inside a swimlane based in the order they are added.

### Create an empty lane

To create an empty lane, you need to define an object with `isLane` property that helps identify the object as a lane. The following example illustrates how to define a swimlane with a lane.

{% highlight javascript %}

export class SwimlaneComponent {
    nodes: Array<any>;
        constructor() {
        this.nodes = [
            {
                'type': 'swimlane', 'name': 'swimlane',
                //Defines an empty lane
                'lanes': [
                    {
                        'name': 'lane1', 
                        'fillColor': '#f5f5f5',
                        'height': 120,
                        //Sets the object as Lane
                        'isLane': "true"
                    }],
                'orientation': "horizontal",
                'offsetX': 400,
                'offsetY': 200,
                'height': 100,
                'width': 700
                }
            ]
        }
}

{% endhighlight %}

### Create a lane with header

The `header` property of the lane allows you to textually describe the lane(`text`) and to customize the appearance of the description. The following code example illustrates how to define a lane header.
You can limit the size of a lane with its `minWidth`, `minHeight`, `maxWidth`, and `maxHeight` properties.

{% highlight javascript %}

export class SwimlaneComponent {
    nodes: Array<any>;
        constructor() {
        this.nodes = [
            {
                'type': 'swimlane',
                'name': 'swimlane',
                //Defines the lane
                'lanes': [
                    {
                        'name': 'lane1', 
                        'fillColor': '#f5f5f5',
                        'height': 120,
                        //Sets the object as Lane
                        'isLane': "true",
                        //Defines the lane header
                        'header':{
                            text: "swimlane label",
                            fillColor: "#C7D4DF",
                            fontColor: "black",
                            fontSize: 15,
                            fontFamily: "Arial",
                            bold: false,
                            italic: false,
                            textDecoration: "none"
                        }, 
                        //Specifies the minimum and maximum size of the lane
                        'minWidth': 500,
                        'maxWidth': 700,
                        'minHeight': 120,
                        'maxHeight': 200,
                    }],
                'orientation': "horizontal",
                'offsetX': 400,
                'offsetY': 200,
                'height': 100,
                'width': 700
                }
            ]
        }
    }

{% endhighlight %}

### Add nodes to a lane

To add nodes to a lane, You need to add them to the `children` collection of lane. The following code example illustrates how to add nodes to a lane.

{% highlight javascript %}

export class SwimlaneComponent {
        nodes: Array<any>;
        constructor() {
        this.nodes = [
                {
                'type': 'swimlane',
                'name': 'swimlane',
                //Defines the lane
                'lanes': [
                    {
                        'name': 'lane1', 
                        'fillColor': '#f5f5f5',
                        'height': 120,
                        //Sets the object as Lane
                        'isLane': "true",
                        //Defines children of lane
                        children:{
                            name: "node",
                            width: 70,
                            height: 30,
                            labels: [{
                                text: "Node",
                            }],
                            // Specifies the margin values of the child
                            marginLeft: 70,
                            marginTop: 1
                        }
                        //Defines the lane header
                        'header':{
                            text: "swimlane label",
                            fillColor: "#C7D4DF",
                            fontColor: "black",
                            fontSize: 15,
                            fontFamily: "Arial",
                            bold: false,
                            italic: false,
                            textDecoration: "none"
                        }, 
                        //Specifies the minimum and maximum size of the lane
                        'minWidth': 500,
                        'maxWidth': 700,
                        'minHeight': 120,
                        'maxHeight': 200,
                    }],
                'orientation': "horizontal",
                'offsetX': 400,
                'offsetY': 200,
                'height': 100,
                'width': 700
                }
            ]
        }
    }

{% endhighlight %}

![](/angular/Diagram/Swim-lane_images/Swim-lane_img4.png)

## Phase

Phases are the sub-processes that are used to break the swimlane into multiple smaller regions.

### Add phase

To define a phase, you have to set the length of the region to the `offset` property of phase. Every region can be textually described with the `label` property of phase.

The following code example illustrates how to add a phase on initializing swimlane.

{% highlight javascript %}

export class SwimlaneComponent {
        nodes: Array<any>;
        constructor() {
        this.nodes = [
            {
                'type': 'swimlane', 'name': 'swimlane',
                'header': {'text': 'ONLINE PURCHASE STATUS', 'height': 50, 'fillColor': '#C7D4DF', 'fontSize': 11 },
                'fillColor': '#f5f5f5', 'orientation': 'horizontal', 'offsetX': 350, 'offsetY': 290, 'height': 100, 'width': 650,
                //Creates a phase
                'phases': [
                    { 'name': 'phase1',
                    //Length of the first region
                    'offset': 300, 
                    //Initializes labels for phases
                    'label': {
                        'text': "Phase1"
                    },
                    //Specifies the appearance of separator
                    'lineWidth': 1, 'lineDashArray': '3,3', 'lineColor': '#606060',
                    },
                    {
                        'name': 'phase2',
                        'label': { 'text': 'Phase' }
                    }
                    ],
                    'phaseSize': 20,
                //Adds lanes and header as mentioned in header and lane section
                }
            ];
        }
}

{% endhighlight %}

![](/angular/Diagram/Swim-lane_images/Swim-lane_img5.png)

## Limitations

* You cannot add connectors as the children of lanes.