---
layout: post
title: Selection
description: Selection
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Selection

## Row selection

You can enable or disable the row selection in Gantt, by using [allowSelection](/api/js/ejgantt#members:allowselection) property. And you can able to get the selected row object using selectedItem property from the Gantt model. The following code example shows how to disable the row selection in Gantt.


{% highlight javascript %}

<ej-gantt id="GanttControl" [allowSelection]="false"
    //...>
</ej-gantt>

{% endhighlight %}

### Selecting a row on initial load

You can select a row on load time by setting the index of the row to [selectedRowIndex](/api/js/ejgantt#members:selectedrowindex) property. Find the following code example for details.

{% highlight javascript %}

<ej-gantt id="GanttControl" [selectedRowIndex]="selectedRowIndex"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
  public selectedRowIndex:any;
  constructor() {
   //...
   this.selectedRowIndex=3;
  }
}

{% endhighlight %}

![](Selection_images/Selection_img1.png)

### Selecting a row programmatically 

You can also select a row programmatically by setting index of the row value to [selectedRowIndex](/api/js/ejgantt#members:selectedrowindex) property. The following code shows to select a row programmatically with a custom button click action,

{% highlight javascript %}

<button id="selectRow" (click)="selectRow($event)">SelectRow</button>

<ej-gantt id="GanttControl"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
  constructor() {
   //...
  }
   public selectRow(event) {
         $("#GanttControl ").ejGantt("option", "selectedRowIndex", 4);
    }
}

{% endhighlight %}

### Multiple row selection

It is also possible to select multiple rows by setting `selectionType` as `multiple`. You can select more than one row by holding down `CTRL` key while selecting multiple rows.
The following code example explains how to enable multiple selection in Gantt.

{% highlight javascript %}

<ej-gantt id="GanttControl" selectionMode="row" selectionType= "multiple"
    //...>
</ej-gantt>

{% endhighlight %}

The output of??the Gantt??with??multiple row selection??is as follows.

![](Selection_images/Selection_img5.png)

To enable multiple selection, you can set `selectionType` property either as `multiple` or enumeration value `ej.Gantt.SelectionType.Multiple`.

### Selecting multiple rows programmatically 

You can also select multiple rows programmatically  by using `selectMultipleRows` public method. The following code example explains how to enable multiple selection in Gantt.

{% highlight javascript %}

<button id="selectMultipleRows" (click)="selectMultipleRows($event)">selectMultipleRows</button>

<ej-gantt id="GanttControl"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    constructor() {
        //...
    }
    public selectMultipleRows(event) {
        //create Gantt object
        var ganttObj = $("#GanttControl").data("ejGantt"),
        multipleRowIndex = [1,0,5,7];   
        ganttObj.selectMultipleRows(multipleRowIndex);
    }
}

{% endhighlight %}

## Cell selection

You can select a cell in Gantt by setting [selectionMode](/api/js/ejgantt#members:selectionmode) property as ???cell???. And you can able to get the selected cell information using selectedCellIndexes property from the Gantt object. selectedCellIndexes is an object collection, which has the cell index and row index information of the selected cells.

Find the code example below to enable the cell selection in Gantt. 

{% highlight javascript %}

<ej-gantt id="GanttControl" selectionMode="cell"
    //...>
</ej-gantt>

{% endhighlight %}

The following screen shots shows you cell selection.

![](Selection_images/Selection_img2.png)

### Selecting multiple cells

You can also select multiple cells by setting [selectionType](/api/js/ejgantt#members:selectiontype) property as ???multiple??? while [selectionMode](/api/js/ejgantt#members:selectionmode) property is set to ???cell???. Multiple cells can be selected by holding the ctrl key and to click on the cells. The following code example shows you to select multiple cells.

{% highlight javascript %}

<ej-gantt id="GanttControl" selectionMode="cell" selectionType= "multiple"
    //...>
</ej-gantt>

{% endhighlight %}

![](Selection_images/Selection_img3.png)

### Select cells programmatically 

You can select the cells programmatically using [selectCells](/api/js/ejgantt#methods:selectcells) public method. Find the code example below for details.

{% highlight javascript %}

<button id="SelectMultipleCell" (click)="SelectMultipleCell($event)">SelectMultipleCells</button>

<ej-gantt id="GanttControl"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    constructor() {
        //...
    }
    public SelectMultipleCell(event) {
        //create Gantt object
        var ganttObj = $("#GanttControl").data("ejGantt");
        cellIndex = [{
            rowIndex: 2,
            cellIndex: 1
        }, {
            rowIndex: 3,
            cellIndex: 1
        }];
        ganttObj.selectCells(cellIndex);
    }
}

{% endhighlight %}


![](Selection_images/Selection_img4.png)

## MultiSelection ??? Touch Option

It is possible to select rows using touch action in Gantt. Gantt provides support for both single selection and multiple row selection using touch action. For multiple row selection, when we tap on a cell, a helper icon will be displayed using which we can select multiple rows.

The following code example describes how to enable multiple selection in Gantt.

{% highlight javascript %}

<ej-gantt id="GanttControl" selectionMode="row" selectionType= "multiple"
    //...>
</ej-gantt>

{% endhighlight %}

The following output is displayed the result of multiple selection in touch device environment.

![](Selection_images/Selection_img6.png)