---
layout: post
title: Stacked Header in Angular TreeGrid Control | Syncfusion
description: Learn here about stacked header in Syncfusion Essential Angular TreeGrid Control, its elements, and more.
platform: Angular
control: TreeGrid
documentation: ug
api: /api/js/ejtreegrid

---
# Stacked Headers in Angular TreeGrid

The stacked headers helps you to group the logical columns in TreeGrid. It can be shown by setting `showStackedHeader` as `true` and by defining `stackedHeaderRows`.

## Adding Stacked header columns

To stack columns in stacked header, you need to define `column` property in `stackedHeaderColumns` with field names of visible columns.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" showStackedHeader="true" [stackedHeaderRows]="stackedHeaderRows"
     // >
    <e-treegrid-columns>
        <e-treegrid-column field="taskID" headerText="Task ID"></e-treegrid-column>
        <e-treegrid-column field="taskName" headerText="TaskName"></e-treegrid-column>
        <e-treegrid-column field="startDate" headerText="Start Date"></e-treegrid-column>
        <e-treegrid-column field="endDate" headerText="End Date"></e-treegrid-column>
        <e-treegrid-column field="duration" headerText="Duration"></e-treegrid-column>
        <e-treegrid-column field="progress" headerText="Progress"></e-treegrid-column>
    </e-treegrid-columns> 
</ej-treegrid>
{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    stackedHeaderRows: any;
  
    constructor() {
        //...
         this.stackedHeaderRows = [{
          stackedHeaderColumns: [{ column: "taskID,taskName,startDate", headerText: "Shipment details", textAlign: ej.TextAlign.Center },
              { column: "endDate,duration,progress", headerText: "Price details", textAlign: ej.TextAlign.Center}
          ]
      }]
    }
}

{% endhighlight %}

![Angular TreeGrid column customization](Stacked-header_images/Stacked-Header-img1.png)

## Stacked header column customization

we can customize the stacked header cells with more options as described below.

### CSS Class

You can provide external CSS styles to the stacked header with the help of `cssClass` property.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" showStackedHeader="true" [stackedHeaderRows]="stackedHeaderRows"
     // >
</ej-treegrid>
{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
	styleUrls: ['app/app.component.css']
})
export class AppComponent {
    stackedHeaderRows: any;  
    constructor() {
        //...
         this.stackedHeaderRows = [{
          stackedHeaderColumns: [{ column: "taskID,taskName,startDate", headerText: "Shipment details",cssClass: "stack" },
              { column: "endDate,duration,progress", headerText: "Price details"}
          ]
      }]
    }
}

{% endhighlight %}

write the below code in app.component.css file.

{% highlight html %}
.stack {
            background-color: #ffb3b3; 
        }
{% endhighlight %}

![Angular TreeGrid Text Align](Stacked-header_images/Stacked-Header-img2.png)

### Text Align

There is an option to align the stacked header text inside the header cell using `textAlign` property in `stackedHeaderColumns` as follows.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" showStackedHeader="true" [stackedHeaderRows]="stackedHeaderRows"
     // >
</ej-treegrid>
{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    stackedHeaderRows: any;  
    constructor() {
        //...
         this.stackedHeaderRows = [{
          stackedHeaderColumns: [{ column: "taskID,taskName,startDate", headerText: "Shipment details",textAlign:ej.TextAlign.Left  },
              { column: "endDate,duration,progress", headerText: "Price details",textAlign: ej.TextAlign.Right}
          ]
      }]
    }
}
{% endhighlight %}

![Angular TreeGrid Tooltip](Stacked-header_images/Stacked-Header-img4.png)

### Tooltip

We can have the customized tooltip for the stacked header text with the help of `tooltip` property in `stackedHeaderColumns`. JsRender template script id can be assigned to this property to get tooltip.

{% highlight html %}
    <script id="tooltip" type="text/x-jsrender">
      <div>Custom Tooltip</div>
    </script>
{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" showStackedHeader="true" [stackedHeaderRows]="stackedHeaderRows"
     showGridCellTooltip="true" >
</ej-treegrid>
{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    stackedHeaderRows: any;  
    constructor() {
        //...
         this.stackedHeaderRows = [{
          stackedHeaderColumns: [{ column: "taskID,taskName,startDate", headerText: "Shipment details" },
              { column: "endDate,duration,progress", headerText: "Price details",tooltip:"#tooltip"}
          ]
      }]
    }
}
{% endhighlight %}

![Angular TreeGrid stacked header](Stacked-header_images/Stacked-Header-img3.png)

N>
To enable stacked header tooltip we need to set `showGridCellTooltip` as `true`.

