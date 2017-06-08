---
layout: post
title: Create custom connection points to draw connections with any specific point of node
description: How to draw connections with specific points of node?
platform: Angular-2
control: Diagram
documentation: ug
---

# Port

Essential Diagram for JS provides support to define custom ports for making connections.

![](/angular-2/Diagram/Port_images/Port_img3.png)

When a connector is connected between two nodes, its end points are automatically docked to node's nearest boundary as shown in the following image. 

![](/angular-2/Diagram/Port_images/Port_img4.png)

Ports act as the connection points of node and allows to create connections with only those specific points as shown in the following image.

![](/angular-2/Diagram/Port_images/Port_img5.png)

## Create Port

### Add ports when initializing nodes

To add a connection port, you need to define the port object and add it to node's `ports` collection. The `offset` property of port accepts an object of fractions and used to determine the position of ports. The following code illustrates how to add ports when initializing the node.

{% highlight html %}

<div>
 <ej-diagram id="diagram" width="100%" height="600">
    <e-nodes>	
        <e-node name="node1" [width]="60" [height]="60" [offsetX]="100" [offsetY]="100">
            <e-ports>
                <e-port name="port1" visibility="visible" shape="square" fillColor="red"></e-port>
            </e-ports>
        </e-node>
    </e-nodes>
</ej-diagram>
</div>

{% endhighlight %} 

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class DefaultComponent {
  }

{% endhighlight %} 

### Add ports at runtime

You can add ports at runtime by using the client side method `addPorts`. The following code illustrates how to add ports to node at runtime.

{% highlight javascript %}

// Defines a collection of ports that have to be added at runtime
var ports = [{
        name: "port1",
        // Specifies the port offset – fraction value relative
        to node bounds– determines the position of port on node
        offset: {
            x: 0,
            y: 0.5
        }
    },
    {
        name: "port2",
        offset: {
            x: 1,
            y: 0.5
        }
    },
    {
        name: "port3",
        offset: {
            x: 0.5,
            y: 0
        }
    },
    {
        name: "port4",
        offset: {
            x: 0.5,
            y: 1
        }
    }
];

// Gets the instance for the Diagram
var diagram = $("#diagram").ejDiagram("instance");
// Adds the ports to the node of name "node"
diagram.addPorts("node", ports)

{% endhighlight %}

![]((/angular-2/Diagram/Port_images/Port_img1.png)

To explore the set of properties for defining a port, refer to [Port Properties](/api/js/ejDiagram#members:nodes-ports "Port Properties")

### Update Port at runtime

The client side API `updatePort` is used to update the ports at run time. The following code example illustrates how to change the port properties.

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");
var selectedObject = diagram.model.selectedItems.children[0];
var visibility = ej.datavisualization.Diagram.PortVisibility.Visible;
diagram.updatePort(selectedObject.name, selectedObject.ports[0], {
    fillColor: "red",
    visibility: visibility
});

{% endhighlight %}

## Connect with ports

Connector’s `sourcePort` and `targetPort` properties allow to create connections between some specific points of source/target nodes. 
For more information about creating connections with port, refer to [Connections with ports](/angular-2/Diagram/Connector#connections-with-ports "Connections with ports")

## Appearance 

You can change the shape of port by using its `shape` property. To explore the different types of port shapes, refer to [Port Shapes](/api/js/global#portshapes "Port Shapes").
The appearance of ports can be customized with a set of style specific properties. 

The following code illustrates how to change the appearance of port.

{% highlight javascript %}

<div>
 <ej-diagram id="diagram" width="100%" height="600">
    <e-nodes>	
        <e-node name="node1" [width]="60" [height]="60" [offsetX]="100" [offsetY]="100">
            <e-ports>
                <e-port name="port1" visibility="visible" shape="circle" fillColor="yellow" size="12" borderColor="black" borderWidth="2" ></e-port>
            </e-ports>
        </e-node>
    </e-nodes>
</ej-diagram>
</div>
{% endhighlight %}

![]((/angular-2/Diagram/Port_images/Port_img2.png)

## Constraints

The `constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/angular-2/Diagram/Constraints#portconstraints)