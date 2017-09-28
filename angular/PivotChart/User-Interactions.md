---
layout: post
title: User-Interactions
description: user interactions
platform: Angular
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# User Interactions

## Tooltip

### Enable Tooltip for Data Points

Tooltip for the data points can be enabled using the **"Visible"** option of the `e-chart-tooltip` property under **"e-common-series-options"** of the PivotChart.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { 
            //..
            //Enabling tooltip for data points
            tooltip:
            {
                visible: true
            }
       };
    }
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/tooltip.png) 

### Tooltip Template

HTML elements can be displayed inside the tooltip by using the `template` option. The template option takes the value of the "id" attribute from the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the X and Y values of the corresponding data points.

{% tabs %}

{% highlight html %}

<div id="Tooltip" style="display: none;">
    <div id="icon">
        <div id="ccicon"> </div>
    </div>
    <div id="value">
        <div>
            <label id="ccvalue">&nbsp;#point.y# </label>
            <label id="cc">Customer Count </label>
        </div>
    </div>
</div>
<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { 
            //..
            //Enabling tooltip of data points
            tooltip:
            {
                visible: true,
                template: 'Tooltip'
            }
       };
    }
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/tooltiptemplate.png) 

### Tooltip Customization

By using `Fill` and `Border` properties of tooltip, you can customize its background color, border color and border width.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { 
            //..
            //Enabling tooltip of data points
            tooltip:
            {
                visible: true,
                //Customize tooltip background color and border
                fill: '#FF9933',
                border:
                {
                    width: 1,
                    color: "#993300"
                }
            }
       };
    }
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/tooltipcustomization.png) 

### Tooltip with Rounded Corners

The tooltip properties, `Rx` and `Ry` are used to customize its corner radius.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { 
            //..
            //Enabling tooltip of data points
            tooltip:
            {
                visible: true,
                //Customize the corner radius of the tooltip rectangle
                rx: "20",
                ry: "20"
            }
       };
    }
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/tooltiprouded.png) 

## Zooming and Panning

### Enable Zooming

There are two ways to zoom the Chart:

* When [`zooming.enable`](/api/angular/ejchart#members:zooming-enable) option is set to true, you can zoom the Chart by using rubber band selection.
* When [`zooming.enableMouseWheel`](/api/angular/ejchart#members:zooming-enablemousewheel) option is set to true, you can zoom the Chart on mouse wheel scrolling.

{% tabs %}

{% highlight html %}

<ej-pivotchart [zooming]="zooming">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public zooming; 
    constructor() {
      //..
      //Enable zooming in Chart
      this.zooming = { enable: true };
    }
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/zooming.png) 

After zooming the Chart, a zooming toolbar will appear with options to *zoom, pan and reset*. Selecting the **“Pan”** option will allow to view the Chart and selecting the **“Reset”** option will reset the zoomed Chart.

![](User-Interactions_images/pan.png) 

### Types of Zooming
You can zoom the particular axis like horizontal axis or vertical axis or both axis using [`type`](/api/angular/ejchart#members:zooming-type) option in zooming. 

N> By default, the value for the `type` option in zooming is “x,y” (indicating both axis) in PivotChart.

{% tabs %}

{% highlight html %}

<ej-pivotchart [zooming]="zooming">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public zooming; 
    constructor() {
      //..
      //Enable zooming in Chart
      this.zooming = { 
            enable: true,
            //Enable horizontal zooming
            type: 'x'
       };
    }
}

{% endhighlight %}

{% endtabs %}

### Enable Scrollbar

* When [`zooming.enableScrollbar`](/api/angular/ejpivotchart#members:zooming-enablescrollbar) option is set to true, the PivotChart is rendered along with the scroll bars for precise view of data. The data can be viewed by using scroll bar or by using mouse wheel scrolling.

{% highlight html %}

<ej-pivotchart [zooming.enableScrollbar]="true">
</ej-pivotchart>

{% endhighlight %}

![](User-Interactions_images/scrollbar.png)

## Marker and Crosshair

### Marker Shape Customization

In PivotChart, you can customize the marker `Shape` with following symbols.

* Rectangle
* Circle
* Cross
* Diamond 
* Pentagon
* Hexagon
* Star
* Ellipse
* Triangle etc.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Line };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) 
                this.model.series[seriescount].marker.shape = "Triangle";
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/marker.png) 

## Highlight

PivotChart provides highlighting support for the series and data points on mouse hover. To enable highlighting, set the **“enable”** property to true in the `highlightSettings` option of the series.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)
                {
                    this.model.series[seriescount].highlightSettings.enable = true;
                    this.model.series[seriescount].highlightSettings.mode = "series";
                }
        };
    };
}

{% endhighlight %}

{% endtabs %}

### Highlight Mode

You can set three different modes for highlighting data points and series by using the `mode` property of the `highlightSettings`.
 
* series
* points
* cluster

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.mode = "series";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/highlightmode.png) 

### Customize the Highlight Styles

To customize the highlighted series, use `border.color`, `border.width` and `opacity`
 options in the `highlightSettings` property.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.opacity = "0.5";
                this.model.series[seriescount].highlightSettings.border.width = "1.5";
                this.model.series[seriescount].highlightSettings.border.color = "red";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/customizehighlight.png) 

### Patterns to Highlight

PivotChart provides pattern support for highlighting the data by setting an appropriate value to the `pattern` property of the `highlightSettings`. The different types of highlight patterns are as follows.

* chessboard
* crosshatch
* dots
* pacman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.pattern = "chessboard";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/patternhighlight.png) 

## Selection

PivotChart provides selection support for the series and data points on mouse click. To enable selection, set the **“enable”** property to true in the `selectionSettings` option of the series.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

### Selection Mode

You can set three different selection mode for highlighting the data points and series by using the `mode` property of the `selectionSettings`.

* series
* points
* cluster

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
                this.model.series[seriescount].selectionSettings.mode = "series";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/selectionmode.png) 

### Customize the Selection Styles

To customize the selection styles, use the `border.color`, `border.width` and `opacity` options in the `selectionSettings`.

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
                this.model.series[seriescount].selectionSettings.border.width = "1.5";
                this.model.series[seriescount].selectionSettings.border.color = "red";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/customizeselection.png) 

### Patterns for Selection

PivotChart provides pattern support for the selecting the data by setting an appropriate value to the `pattern` property of the `selectionSettings` option. The different types of selection patterns are as follows.

* chessboard
* crosshatch
* dots
* pacman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward

{% tabs %}

{% highlight html %}

<ej-pivotchart [commonSeriesOptions]="commonSeriesOptions" [size]="size" (load)="onLoad($event)">
</ej-pivotchart>

{% endhighlight %}

{% highlight ts %}

//..

export class PivotChartComponent {
    public size; commonSeriesOptions; 
    constructor() {
      //..
      this.size = { height: "460px", width: "950px" };
      this.commonSeriesOptions = { type: ej.PivotChart.ChartTypes.Column };
    }
    onLoad(args) {
        args.model.seriesRendering = function (evt) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true
                this.model.series[seriescount].selectionSettings.pattern = "chessboard";
            }
        };
    };
}

{% endhighlight %}

{% endtabs %}

![](User-Interactions_images/patternselecion.png) 
