---
layout: post
title: BPMN shapes in Syncfusion Diagram control.
description: How to graphically notate the internal business procedure?
platform:  Angular
control: Diagram
documentation: ug
---

### BPMN Shapes

BPMN shapes are used to represent the internal business procedure in a graphical notation and enables you to communicate the procedures in a standard manner. To create a BPMN shape, the `type` of the node should be set as "bpmn" and its `shape` should be set as any one of the built-in shape. [BPMN Shapes](/api/js/global#bpmnshapes "BPMN Shapes"). The following code example illustrates how to create a simple business process. 

{% highlight html %}
<ej-diagram width="100%" height="600" width="700">
<e-nodes>
    <e-node name ="node" type = "bpmn" [width]="100" [height]="100" [offsetX]="100" [offsetY]="100" borderWidth="2" borderColor="black" 
                 shape="event" event="end">
                <e-nodelabels>
                    <e-nodelabel text="End Event"></e-nodelabel>
                </e-nodelabels>
    </e-node>
</e-nodes>
</ej-diagram>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class DefaultComponent {}
}

{% endhighlight %}
![BPMN diagram](../Diagram/Shapes_images/Shapes_img5.png)

N> The default value for the property `shape` is "event".

The list of BPMN shapes are as follows.

| Shape | Image |
|---|---|
| Event | ![Event](../Diagram/Shapes_images/Shapes_img6.png) |
| Gateway | ![Gateway](../Diagram/Shapes_images/Shapes_img7.png) |
| Task | ![Task](../Diagram/Shapes_images/Shapes_img8.png) |
| Message | ![Message](../Diagram/Shapes_images/Shapes_img9.png) |
| DataSource | ![DataSource](../Diagram/Shapes_images/Shapes_img10.png) |
| DataObject | ![DataObject](../Diagram/Shapes_images/Shapes_img11.png) |
| Group | ![Group](../Diagram/Shapes_images/Shapes_img12.png) |

The BPMN shapes and its types are explained as follows.

### Event 

An event is notated with a circle and it represents an event in a business process. The type of events are as follows.

* Start
* End
* Intermediate

The `event` property of the node allows you to define the type of the event. The default value of the `event` is "start". The following code example illustrates how to create a BPMN Event.

{% highlight html %}
<div>
    <ej-diagram width="100%" height="600" width="700" [nodes]="nodes">
    </ej-diagram>
</div>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "node",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                //Sets the type as BPMN
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the shape as BPMN Event
                shape: ej.datavisualization.Diagram.BPMNShapes.Event,
                //Sets type of the Event
                event: ej.datavisualization.Diagram.BPMNEvents.End,
                //Sets sub-type of the Event
                trigger: ej.datavisualization.Diagram.BPMNTriggers.None
            }
        ];
    }
}

{% endhighlight %}

![BPMN event](../Diagram/Shapes_images/Shapes_img13.png)

Event triggers are notated as icons inside the circle and they represent the specific details of the process. The `triggers` property of node allows you to set the type of trigger and by default, it is set as "none". The following table illustrates the type of event triggers.

| Triggers | Start | Non-Interrupting Start | Intermediate | Non-Interrupting Intermediate | Throwing Intermediate | End |
| --- | --- | --- | --- | --- | --- | --- |
| None | ![None](../Diagram/Shapes_images/Shapes_img63.png) | ![None](../Diagram/Shapes_images/Shapes_img64.png) | ![None](../Diagram/Shapes_images/Shapes_img65.png) | ![None](../Diagram/Shapes_images/Shapes_img66.png) |   | ![None](../Diagram/Shapes_images/Shapes_img67.png) |
| Message | ![Message](../Diagram/Shapes_images/Shapes_img68.png) | ![Message](../Diagram/Shapes_images/Shapes_img69.png) | ![Message](../Diagram/Shapes_images/Shapes_img70.png) | ![Message](../Diagram/Shapes_images/Shapes_img71.png) | ![Message](../Diagram/Shapes_images/Shapes_img72.png) | ![Message](../Diagram/Shapes_images/Shapes_img73.png) |
| Timer | ![Timer](../Diagram/Shapes_images/Shapes_img74.png) | ![Timer](../Diagram/Shapes_images/Shapes_img75.png) | ![Timer](../Diagram/Shapes_images/Shapes_img76.png) | ![Timer](../Diagram/Shapes_images/Shapes_img77.png) |   |   |
| Conditional | ![Conditional](../Diagram/Shapes_images/Shapes_img78.png) | ![Conditional](../Diagram/Shapes_images/Shapes_img79.png) | ![Conditional](../Diagram/Shapes_images/Shapes_img80.png) | ![Conditional](../Diagram/Shapes_images/Shapes_img81.png) |   |   |
| Link |   |   | ![Link](../Diagram/Shapes_images/Shapes_img82.png) |   | ![Link](../Diagram/Shapes_images/Shapes_img83.png) |   |
| Signal | ![Signal](../Diagram/Shapes_images/Shapes_img84.png) | ![Signal](../Diagram/Shapes_images/Shapes_img85.png) | ![Signal](../Diagram/Shapes_images/Shapes_img86.png) | ![Signal](../Diagram/Shapes_images/Shapes_img87.png) | ![Signal](../Diagram/Shapes_images/Shapes_img88.png) | ![Signal](../Diagram/Shapes_images/Shapes_img89.png) |
| Error | ![Error](../Diagram/Shapes_images/Shapes_img90.png) |   | ![Error](../Diagram/Shapes_images/Shapes_img91.png) |   |   | ![Error](../Diagram/Shapes_images/Shapes_img92.png) |
| Escalation | ![Escalation](../Diagram/Shapes_images/Shapes_img93.png) | ![Escalation](../Diagram/Shapes_images/Shapes_img94.png) | ![Escalation](../Diagram/Shapes_images/Shapes_img95.png) | ![Escalation](../Diagram/Shapes_images/Shapes_img96.png) | ![Escalation](../Diagram/Shapes_images/Shapes_img97.png) | ![Escalation](../Diagram/Shapes_images/Shapes_img98.png) |
| Termination |   |   |   |   |   | ![Termination](../Diagram/Shapes_images/Shapes_img99.png) |
| Compensation | ![Compensation](../Diagram/Shapes_images/Shapes_img100.png) |   | ![Compensation](../Diagram/Shapes_images/Shapes_img101.png) |   | ![Compensation](../Diagram/Shapes_images/Shapes_img102.png) | ![Compensation](../Diagram/Shapes_images/Shapes_img103.png) |
| Cancel |   |   | ![Cancel](../Diagram/Shapes_images/Shapes_img104.png) |   |   | ![Cancel](../Diagram/Shapes_images/Shapes_img105.png) |
| Multiple | ![Multiple](../Diagram/Shapes_images/Shapes_img106.png) | ![Multiple](../Diagram/Shapes_images/Shapes_img107.png) | ![Multiple](../Diagram/Shapes_images/Shapes_img108.png) | ![Multiple](../Diagram/Shapes_images/Shapes_img109.png) | ![Multiple](../Diagram/Shapes_images/Shapes_img110.png) | ![Multiple](../Diagram/Shapes_images/Shapes_img111.png) |
| Parallel | ![Parallel](../Diagram/Shapes_images/Shapes_img112.png) | ![Parallel](../Diagram/Shapes_images/Shapes_img113.png) | ![Parallel](../Diagram/Shapes_images/Shapes_img114.png) | ![Parallel](../Diagram/Shapes_images/Shapes_img115.png) |   |   |

### Gateway

Gateway is used to control the flow of a process. It is represented as a diamond shape. To create a gateway, the `shape` property of node should be set as "gateway" and the `gateway` property can be set with any of the appropriate [Gateways](/api/js/global#bpmngateways "Gateways"). The following code example illustrates how to create a BPMN Gateway.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "node",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the shape as Gateway
                shape: ej.datavisualization.Diagram.BPMNShapes.Gateway,
                //Sets the type of BPMN Gateway
                gateway: ej.datavisualization.Diagram.BPMNGateways.None,
            }
        ];
    }
}

{% endhighlight %}

![Gateway](../Diagram/Shapes_images/Shapes_img25.png)

N> By default, the `gateway` will be set as "none".

There are several types of gateways as tabulated

| Gateways | Image |
|---|---|
| Exclusive | ![Exclusive](../Diagram/Shapes_images/Shapes_img26.png) |
| Parallel | ![Parallel](../Diagram/Shapes_images/Shapes_img27.png) |
| Inclusive | ![Inclusive](../Diagram/Shapes_images/Shapes_img28.png) |
| Complex | ![Complex](../Diagram/Shapes_images/Shapes_img29.png) |
| EventBased | ![EventBased](../Diagram/Shapes_images/Shapes_img30.png) |
| ExclusiveEventBased | ![ExclusiveEventBased](../Diagram/Shapes_images/Shapes_img31.png) |
| ParallelEventBased | ![ParallelEventBased](../Diagram/Shapes_images/Shapes_img32.png) |

### Activity

The activity is the task that is performed in a business process. It is represented by a rounded rectangle.

There are two types of activities .They are listed as follows.

* Task – Occurs within a process and it is not broken down to finer level of detail.
* Subprocess – Occurs within a process and it is broken down to finer level of detail.

To create a BPMN activity, you need to set the `shape` as "activity". You also need to set the type of the [BPMN Activity](/api/js/global#bpmnactivity "BPMN Activity") by using the `activity` property of node. By default, the type of the `activity` is set as "task". The following code example illustrates how to create an activity.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "node",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the bpmn shape as activity
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
            }
        ];
    }
}

{% endhighlight %}
![Activity](../Diagram/Shapes_images/Shapes_img33.png)

The different activities of BPMN process are listed as follows.

#### Tasks

The `task` property of node allows you to define the `type` of task such as sending, receiving, user based task etc… By default, the `type` property of task is set as "none". The following code illustrates how to create different types of BPMN tasks. 

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of bpmn shape
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
                //Sets the type of BPMN Task Activity
                task: {
                    type: ej.datavisualization.Diagram.BPMNTasks.Send
                }
            }
        ];
    }
}

{% endhighlight %}

![Task](../Diagram/Shapes_images/Shapes_img34.png)

The various types of BPMN tasks are tabulated as follows.

| Task Type | Image |
|---|---|
| Service | ![Service](../Diagram/Shapes_images/Shapes_img35.png) |
| Send | ![Send](../Diagram/Shapes_images/Shapes_img34.png) |
| Receive | ![Receive](../Diagram/Shapes_images/Shapes_img37.png) |
| Instantiating Receive | ![Instantiating Receive](../Diagram/Shapes_images/Shapes_img38.png) |
| Manual | ![Manual](../Diagram/Shapes_images/Shapes_img39.png) |
| Business Rule | ![Business Rule](../Diagram/Shapes_images/Shapes_img40.png) |
| User | ![User](../Diagram/Shapes_images/Shapes_img41.png) |
| Script | ![Script](../Diagram/Shapes_images/Shapes_img42.png) |

#### Subprocess

A sub-process is a group of tasks which is used to hide or reveal details of additional levels which can be done using `collapsed` property .

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "node",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of bpmn shape
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Sets the state of BPMN Subprocess
                subProcess: {
                    collapsed: true,
                }
            }
        ];
    }
}

{% endhighlight %}

![subprocess](../Diagram/Shapes_images/Shapes_img116.png)

The different types of subprocess are as follows.

* Event Subprocess
* Transaction 

##### Event Subprocess

A Sub-process is defined as an Event Sub-process when it is triggered by an event. An event-subprocess is placed within another subprocess which is not part of the normal flow of its parent process . You can set event to a sub-process with the `event` and `trigger` property of subprocess. 

 {% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "node",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the bpmn shape as activity
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Creates event subprocess
                subProcess: {
                    type: ej.datavisualization.Diagram.BPMNSubProcessTypes.Event,
                    event: ej.datavisualization.Diagram.BPMNEvents.Start,
                    trigger: ej.datavisualization.Diagram.BPMNTriggers.Message
                }
            }
        ];
    }
}

{% endhighlight %}

![Event subprocess](../Diagram/Shapes_images/Shapes_img117.png)

##### Transaction Subprocess

An transaction is a set of activities that logically belong together, in which all contained activities must complete their parts of the transaction; otherwise the process is undone. The execution result of a transaction is one of Successful Completion, Unsuccessful Completion (Cancel), and Hazard (Exception). The `events` property of subprocess allows to represent these results as an event attached to the subprocess. 

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "transactionSubProcess",
                width: 130,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Creates transaction subprocess
                subProcess: {
                    type: ej.datavisualization.Diagram.BPMNSubProcessTypes.Transaction,
                    // Defines a collection of events to be attached 
                    events: [
                        //Defines type of the event and the position relative to the subprocess. 
                        {
                            event: "intermediate",
                            trigger: "cancel",
                            offset: { x: 0.25, y: 1 }
                        },
                        {
                            event: "intermediate",
                            trigger: "error",
                            offset: { x: 0.75, y: 1 }
                        }
                    ]
                }
            }
        ]
    }
}

{% endhighlight %}

![Transaction subprocess](../Diagram/Shapes_images/Shapes_img118.png)

#### Processes 

Processes is a array collection that defines the children values for BPMN subprocess.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    connectors: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "group",
                offsetX: 500,
                offsetY: 300,
                width: 300,
                height: 200,
                type: "bpmn",
                shape: ej.datavisualization.Diagram.BPMNShapes.Group,
                children: [{
                    name: "node",
                    marginLeft: 15,
                    marginTop: 15,
                    width: 250,
                    height: 150,
                    type: "bpmn",
                    shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                    activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                    subProcess: {
                        collapsed: false,
                        Processes: [{
                                name: "subnode01",
                                marginLeft: 20,
                                marginTop: 50,
                                width: 30,
                                height: 30,
                                type: "bpmn",
                                shape: ej.datavisualization.Diagram.BPMNShapes.Event
                            },
                            {
                                name: "subnode02",
                                marginLeft: 90,
                                marginTop: 25,
                                width: 100,
                                height: 80,
                                type: "bpmn",
                                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
                                task: { type: "user" },
                                annotation: {
                                    text: "Review Customer Rating",
                                    length: 125,
                                    angle: 24,
                                    width: 100,
                                    height: 30
                                }
                        }]
                    }
                }]
            }]
        }
    }
        this.connectors = [{
                name: "connector1",
                sourceNode: "subnode01",
                targetNode: "subnode02"
            }];
{% endhighlight %}

![process](../Diagram/Shapes_images/Shapes_img151.png)

#### Loop

Loop is a task that is internally being looped. The `loop` property of task allows you to define the type of loop. The default value for `loop` is "none". 

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of BPMN shape
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
                //Sets the type of bpmn loops.
                task: {
                    loop: ej.datavisualization.Diagram.BPMNLoops.Standard
                }
            },{
                name: "subprocess",
                width: 100,
                height: 100,
                offsetX: 300,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN activity
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Sets the type of bpmn loops.
                subProcess: {
                    loop: ej.datavisualization.Diagram.BPMNLoops.Standard
                }
            }
        ];
    }
}

{% endhighlight %}

![Loop](../Diagram/Shapes_images/Shapes_img43.png)

The following table contains various types of BPMN loops.

| Loops | Task | SubProcess |
|---|---|---|
| Standard | ![Standard](../Diagram/Shapes_images/Shapes_img44.png) | ![Standard](../Diagram/Shapes_images/Shapes_img45.png) |
| SequenceMultiInstance | ![SequenceMultiInstance](../Diagram/Shapes_images/Shapes_img46.png) | ![SequenceMultiInstance](../Diagram/Shapes_images/Shapes_img47.png) |
| ParallelMultiInstance | ![ParallelMultiInstance](../Diagram/Shapes_images/Shapes_img48.png) | ![ParallelMultiInstance](../Diagram/Shapes_images/Shapes_img49.png) |

#### Compensation

Compensation is triggered when operation is partially failed and you can enable it with the `compensation` property of task.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
                //Creates compensation task
                task: {
                    compensation: true
                }
            },{
                name: "subprocess",
                width: 100,
                height: 100,
                offsetX: 300,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Creates compensation subprocess 
                subProcess: {
                    compensation: true
                }
            }
        ];
    }
}

{% endhighlight %}

![Compensation](../Diagram/Shapes_images/Shapes_img50.png)

#### Call

A call activity is a global sub-process that is reused at various points of the business flow and you can set it with the `call` property of task.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                //Sets the type of BPMN Activity
                activity: ej.datavisualization.Diagram.BPMNActivity.Task,
                //Creates a call task
                task: {
                    call: true
                }
            }
        ];
    }
}

{% endhighlight %}

![Call](../Diagram/Shapes_images/Shapes_img51.png)

#### Ad-Hoc

An ad hoc subprocess is a group of tasks that are executed in any order or skipped in order to fulfill the end condition and you can set it with the `adhoc` property of subprocess. 

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Creates ad hoc subprocess
                subProcess: {
                    adhoc: true
                }
            }
        ];
    }
}

{% endhighlight %}

![Ad-Hoc](../Diagram/Shapes_images/Shapes_img52.png)

#### Boundary

Boundary represents the type of task that is being processed. The `boundary` property of sub process allows you to define the type of boundary. By default, it is set as "default".

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "task",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                shape: ej.datavisualization.Diagram.BPMNShapes.Activity,
                activity: ej.datavisualization.Diagram.BPMNActivity.SubProcess,
                //Adds boundary to a subprocess 
                subProcess: {
                    boundary: ej.datavisualization.Diagram.BPMNBoundary.Call
                }
            }
        ];
    }
}

{% endhighlight %}

The following table contains various types of BPMN boundaries.

| Boundary | Image |
|---|---|
| Call | ![Call](../Diagram/Shapes_images/Shapes_img53.png) |
| Event | ![Event](../Diagram/Shapes_images/Shapes_img54.png) |
| Default | ![Default](../Diagram/Shapes_images/Shapes_img55.png) |

### Data

A data object represents information flowing through the process, such as data placed into the process, data resulting from the process, data that needs to be collected, or data that must be stored. To define a data object, set the `shape` as `ej.datavisualization.Diagram.BPMNShapes.DataObject` and `type` property defines whether data is an input or a output. You can create multiple instances of data object with the `collection` property of data.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "dataObject",
                width: 75,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                //Sets the type of the shape
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of BPMN Shape
                shape: ej.datavisualization.Diagram.BPMNShapes.DataObject,
                //Sets collection as true when Data object is not a Single instance
                data: {
                    type: ej.datavisualization.Diagram.BPMNDataObjects.Input,
                    collection: true
                }
            }
        ];
    }
}

{% endhighlight %}

![Data](../Diagram/Shapes_images/Shapes_img56.png)

The following table contains various representation of BPMN Data Object.

| Boundary | Image |
|---|---|
| Collection Data Object | ![Collection Data Object](../Diagram/Shapes_images/Shapes_img119.png) |
| Data Input | ![Data Input](../Diagram/Shapes_images/Shapes_img120.png) |
| Data Ouptput | ![Data Ouptput](../Diagram/Shapes_images/Shapes_img121.png) |

### Datasource

DataSource is used to store or access data associated with a business process. To create a data source, set the `shape` as "datasource". The following code example illustrate how to create data source.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "dataSource",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                //Sets type of the shape
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of bpmn shape
                shape: ej.datavisualization.Diagram.BPMNShapes.DataSource,
            }
        ];
    }
}

{% endhighlight %}

![Datasource](../Diagram/Shapes_images/Shapes_img57.png)

### Artifact

Artifact is used to show additional information about a Process in order to make it easier to understand. There are 2 types of artifacts in BPMN.

* Text Annotation
* Group

#### Text Annoatation

A BPMN object can be associated with a text annotation which does not affect the flow but gives details about objects within a flow. The `annotation` property of the node is used to connect an annotation element to the BPNN node.

{% highlight javascript %}
export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "data",
                width: 75,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                //Sets type of the shape
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of bpmn shape
                shape: ej.datavisualization.Diagram.BPMNShapes.DataObject,
                //Sets collection as true when Dataobject is not a Single instance
                data: {
                    collection: true
                },
                annotation: {
                    //Sets the text to annotate the bpmn shape
                    text: "Data Collection",
                    //Sets the angle between the bpmn shape and the annotation
                    angle: 45,
                    //Sets the dimensions of the text
                    width: 100,
                    height: 40,
                    //Sets the distance between the bpmn shape and the annotation 
                    length: 150
                }
            }
        ];
    }
}

{% endhighlight %}

![Text Annotation](../Diagram/Shapes_images/Shapes_img122.png)

#### Group

A group is used to frame a part of the diagram, shows that elements included in it are logically belong together and don't have any other semantics other than organizing elements. To create a Group, the `shape` property of node should be set as "group". The following code example illustrates how to create a BPMN Group.

{% highlight javascript %}

export class NodesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "group",
                width: 100,
                height: 100,
                offsetX: 100,
                offsetY: 100,
                borderWidth: 2,
                borderColor: "black",
                //Sets type of the shape
                type: ej.datavisualization.Diagram.Shapes.BPMN,
                //Sets the type of bpmn shape
                shape: ej.datavisualization.Diagram.BPMNShapes.Group
            }
        ];
    }
}

{% endhighlight %}

![Group](../Diagram/Shapes_images/Shapes_img123.png)

#### BPMN Flows

BPMN Flows are lines that connects BPMN flow objects.

### Association

BPMN Association flow is used to link flow objects with its corresponding text or artifact. An association is represented as a dotted graphical line with opened arrow. The type of association are as follows.

* Directional
* BiDirectional
* Default

The `association` property allows you to define the type of association.The following code example illustrates how to create an association.

{% highlight javascript %}

export class NodesComponent {
    connectors: Array<any>;
    constructor() {
        this.connectors = [
            {
                name: "connect1",
                sourcePoint: {
                    x: 100,
                    y: 200
                },
                targetPoint: {
                    x: 300,
                    y: 200
                },
                segments: [{
                    type: "straight"
                }],
                shape: {
                    type: "bpmn",
                    //Sets the type of the flow as association
                    flow: "association",
                    //Sets the type of association
                    association: "bidirectional"
                }
            }
        ];
    }
}

{% endhighlight %}

![Association](../Diagram/Shapes_images/Shapes_img134.png)

The following table demonstrates the visual representation of assosiation flows.

| Association | Image |
|---|---|
| Default | ![Default](../Diagram/Shapes_images/Shapes_img133.png) |
| Directional | ![Directional](../Diagram/Shapes_images/Shapes_img134.png) |
| BiDirectional | ![BiDirectional](../Diagram/Shapes_images/Shapes_img132.png) |

N> The default value for the property `association` is "default".

### Sequence

A Sequence flow shows the order in which the activities are performed in a BPMN Process and is represented with a solid graphical line.The type of sequence are as follows.

* Normal
* Conditional
* Default

The `sequence` property allows you to define the type of sequence.The following code example illustrates how to create a sequence flow.

{% highlight javascript %}

export class NodesComponent {
    connectors: Array<any>;
    constructor() {
        this.connectors = [
            {
                name: "connect1",
                sourcePoint: {
                    x: 100,
                    y: 200
                },
                targetPoint: {
                    x: 300,
                    y: 200
                },
                segments: [{
                    type: "straight"
                }],
                shape: {
                    type: "bpmn",
                    flow: "sequence",
                    //Sets the type of sequence flow
                    sequence: "conditional"
                }
            }
        ];
    }
}

{% endhighlight %}

![Sequence](../Diagram/Shapes_images/Shapes_img135.png)

The following table contains various representation of sequence flows.

| Sequence | Image |
|---|---|
| Default | ![Default](../Diagram/Shapes_images/Shapes_img136.png) |
| Conditional | ![Conditional](../Diagram/Shapes_images/Shapes_img135.png) |
| Normal | ![Normal](../Diagram/Shapes_images/Shapes_img137.png) |

N> The default value for the property `sequence` is "normal".

### Message

A Message flow shows the flow of messages between two Participents.A message flow is represented by dashed line.The type of message are as follows.

* InitiatingMessage
* NonInitiatingMessage
* Default

The `message` property allows you to define the type of message.The following code example illustrates how to define a message flow.

{% highlight javascript %}

export class NodesComponent {
    connectors: Array<any>;
    constructor() {
        this.connectors = [
            {
                name: "connect1",
                sourcePoint: {
                    x: 100,
                    y: 200
                },
                targetPoint: {
                    x: 300,
                    y: 200
                },
                segments: [{
                    type: "straight"
                }],
                shape: {
                    type: "bpmn",
                    flow: "message",
                    //Sets the type of message flow
                    message: "initiatingmessage"
                }
            }
        ];
    }
}

{% endhighlight %}

![Message](../Diagram/Shapes_images/Shapes_img138.png)

The following table contains various representation of message flows.

| Message | Image |
|---|---|
| Default | ![Default](../Diagram/Shapes_images/Shapes_img139.png) |
| InitiatingMessage | ![InitiatingMessage](../Diagram/Shapes_images/Shapes_img138.png) |
| NonInitiatingMessage | ![NonInitiatingMessage](../Diagram/Shapes_images/Shapes_img140.png) |

N> The default value for the property `message` is "default".