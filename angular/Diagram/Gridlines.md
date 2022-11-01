---
layout: post
title: Gridlines in Angular Diagram Control | Syncfusion
description: Learn here all about gridlines support in Syncfusion Essential Angular Diagram control, its elements, and more.
platform: Angular
control: Diagram
documentation: ug
---

# Gridlines in Essential Angular Diagram

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

## Customize the gridlines visibility

The `snapSettings.snapConstraints` enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

{% highlight html %}

<div>
<ej-diagram  id="diagramCore" width="700px" height="500px" [snapSettings]="snapSettings">
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
    snapSettings: Object;
    constructor() {
        //Shows both horizontal and vertical gridlines
        this.snapSettings = {
              snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines
        };
    }
};

{% endhighlight %}

![Angular Diagram Customize the gridlines visibility](Gridlines_images/Gridlines_img1.png)

To show only horizontal/vertical gridlines or to hide gridlines, refer to [Constraints](/angular/Diagram/Constraints#snapconstraints "Constraints")

## Appearance

You can customize the appearance of the gridlines by using a set of predefined properties. To explore those properties, refer to [Gridlines](/api/js/ejDiagram#snapsettings:horizontalgridlines "Gridlines")
The `horizontalGridLines` and `verticalGridLines` properties allow to customize the appearance of the gridlines. The following code example illustrates how to customize the appearance of gridlines.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class ModelComponent {
    snapSettings: Object;
    constructor() {
        //Shows both horizontal and vertical gridlines
        this.snapSettings = {
            snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines,
            // Customizes the line color and line style to the gridlines.
            horizontalGridLines: {
                lineColor: "blue",
                lineDashArray: "2 2"
            },
            verticalGridLines: {
                lineColor: "blue",
                lineDashArray: "2 2"
            }
        };
    }
};

{% endhighlight %}

![Angular Diagram Appearance](Gridlines_images/Gridlines_img4.png)

### Line Intervals

Thickness and the space between gridlines can be customized by using `linesInterval` property. In the linesInterval collections, values at the odd places are referred as the thickness of lines and the values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class ModelComponent {
    snapSettings: Object;
    constructor() {
        //Shows both horizontal and vertical gridlines
        this.snapSettings = {
            snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines,
            horizontalGridLines: {
                // Defines the thickness and intervals for a pattern of lines
                linesInterval: [1.25, 14, 0.25, 15, 0.25, 15, 0.25, 15, 0.25, 15],
                lineColor: "blue",
                lineDashArray: "2 2"
            },
            verticalGridLines: {
                linesInterval: [1.25, 14, 0.25, 15, 0.25, 15, 0.25, 15, 0.25, 15],
                lineColor: "blue",
                lineDashArray: "2 2"
            }
        };
    }
};

{% endhighlight %}

![Angular Diagram Line Intervals](Gridlines_images/Gridlines_img2.png)

## Snapping

## Snap To Lines

This feature allows the Diagram objects to snap to the nearest intersection of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the `snapSettings.snapConstraints`. The following code example illustrates how to enable/disable the snapping to gridlines.

{% highlight javascript %}

export class ModelComponent {
    snapSettings: Object;
    constructor() {
        //Enables snapping to both the horizontal and vertical lines.
        this.snapSettings = {
            snapConstraints: ej.datavisualization.Diagram.SnapConstraints.SnapToLines
        };
    }
};

{% endhighlight %}

To enable/disable snapping to horizontal/vertical lines, refer to [Constraints] (/angular/Diagram/Constraints#SnapConstraints "Constraints")

## Customization of Snap Intervals

By default, the objects are snapped towards the nearest gridline. The gridline or position towards where the diagram object snaps can be customized with the property, `snapInterval`. The following code example illustrates how to customize the snap intervals.

{% highlight javascript %}

export class ModelComponent {
    snapSettings: Object;
    constructor() {
        //Enables snapping to both the horizontal and vertical lines.
        this.snapSettings = {
            horizontalGridLines: {
                //Defines a set of intervals where the object is snapped.
                //In this example, the object is snapped to every 10px.
                snapInterval: [10]
            },
            verticalGridLines: {
                //The object is snapped to every 10px.
                snapInterval: [10]
            },
            snapConstraints: ej.datavisualization.Diagram.SnapConstraints.All        };
    }
};

{% endhighlight %}

## Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram elements. A node can be snapped with its neighboring objects based on certain alignments. Such alignments are visually represented as smart guides.

The `enableSnapToObject` property allows you to enable/disable smart guides. The following code example illustrates how to enable/disable the smart guides.

{% highlight javascript %}

export class ModelComponent {
    snapSettings: Object;
    constructor() {
        //Enables snapping to both the horizontal and vertical lines.
        this.snapSettings = {
            enableSnapToObject: true,
        };
    }
};

{% endhighlight %}

![Angular Diagram Snapping](Gridlines_images/Gridlines_img4.png)