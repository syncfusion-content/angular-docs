---
layout: post
title: Data source given to HeatMap is configured using ItemsMapping
description: How to populate data for heatmap?
platform: Angular
control: HeatMap
documentation: ug
---

#Items Mapping

External data source can be mapped with HeatMap using `itemsMapping` property. It supports 2 kind of data source.

* In `TableMapping` rows represents an objects in collection, columns represents numerical properties of that object.
* In `CellMapping` each cell represent an object in collection, this collection is grouped based on specific property to form as rows and columns.

{% highlight javascript %}
<div style="margin: 0 auto; text-align: center;width:69%;">
    <ej-heatmap id="heatmap1" width="100%" [itemsMapping]="itemsMapping" [itemsSource]="itemsSource">
        <e-colormappingcollection>
            <e-colormapping [value]="0" color="#8ec8f8" [label]="label">
            </e-colormapping>
            <e-colormapping [value]="100" color="#0d47a1" [label]="label">
            </e-colormapping>
        </e-colormappingcollection>
    </ej-heatmap>

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/components/heatmap/celldatabinding.component.html'
})
export class DefaultComponent {
    margin: Object;
    itemsSource: Array<Object>;
    itemsMapping: Object;
    label: Object;
    constructor() {
        this.margin = { 'left': 25, 'right': 25 };
        let itemsSource = [
            { ProductName: "Vegie-spread", Y2010: 10, Y2011: 15, Y2012: 56, Y2013: 75 },
            { ProductName: "Tofuaa", Y2010: 56, Y2011: 34, Y2012: 93, Y2013: 26 },
            { ProductName: "Alice Mutton", Y2010: 73, Y2011: 12, Y2012: 67, Y2013: 47 },
            { ProductName: "Konbu", Y2010: 24, Y2011: 39, Y2012: 36, Y2013: 67 }];
        this.itemsSource = itemsSource;
        this.itemsMapping = {
            headerMapping:
            {
                "propertyName": "ProductName",
                "displayName": "Product Name",
                columnStyle: { width: 140 }
            },
            columnMapping: [
                {
                    "propertyName": "Y2010",
                    "displayName": "Y2010",
                    columnStyle: { width: 100 }
                },
                {
                    "propertyName": "Y2011",
                    "displayName": "Y2011",
                    columnStyle: { width: 100 }
                },
                {
                    "propertyName": "Y2012",
                    "displayName": "Y2012",
                    columnStyle: { width: 100 }
                },
                {
                    "propertyName": "Y2013",
                    "displayName": "Y2013",
                    columnStyle: { width: 100 }
                }]
        };
    }
}
{% endhighlight %}
![](Items-Mapping_images/ItemsMapping_img1.png)
