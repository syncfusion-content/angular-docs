---
title: Selection with Spreadsheet widget for Syncfusion Essential Angular-2
description: How to perform Selection and configure its properties like selection type, selection mode etc.
platform: angular-2
control: Spreadsheet
documentation: ug
---
# Selection

Selection provides an interactive support to highlight cell, row, or column that you select. Selection can be done through Mouse, Touch or Keyboard interaction. To enable selection, set [`allowSelection`](https://help.syncfusion.com/api/js/ejspreadsheet#members:allowselection "allowSelection") as `true`.

## Selection Modes

The mode of selection can be single or range selection. The default selection mode can be set using `selectionUnit` in `selectionSettings`.
The two types of selection mode are as follows,

* Single - `ej.Spreadsheet.SelectionUnit.Single`
* Range - `ej.Spreadsheet.SelectionUnit.Range`

## Selection Type

There are four types of selection in Spreadsheet,

1. Cell Selection
2. Row Selection
3. Column Selection
4. Sheet Selection

You can set default `selectionType` in `selectionSettings`.

### Cell Selection 

Cell selection is used to select a single or multiple cells. It can be performed using [`selectRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlselection-selectrange "selectRange") method. 
The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
    loadComplete(event) {
      let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      xlObj.XLSelection.selectRange("A1:C3");
      xlObj.XLDragFill.positionAutoFillElement();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Selection_images/Selection_img1.png)

### Row Selection 

Row selection is used to select a single or multiple rows. It can be performed using [`selectRows`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlselection-selectrows "selectRows") method.
The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
    loadComplete(event) {
      let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      xlObj.XLSelection.selectRows(0,2);
      xlObj.XLDragFill.positionAutoFillElement();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Selection_images/Selection_img2.png)

N> This type can be set as default by setting `selectionType` property in `selectionSettings` as `ej.Spreadsheet.SelectionType.Row`

### Column Selection

Column selection is used to select a single or multiple columns. It can be performed using [`selectColumns`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlselection-selectcolumns "selectColumns") method.
The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
    loadComplete(event) {
      let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      xlObj.XLSelection.selectColumns(0,2);
      xlObj.XLDragFill.positionAutoFillElement();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Selection_images/Selection_img3.png)

N> This type can be set as default by setting `selectionType` property in `selectionSettings` as `ej.Spreadsheet.SelectionType.Column`

### Sheet Selection

Sheet selection is used to select all cells in a worksheet.  It can be performed using [`selectSheet`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlselection-selectsheet "selectSheet") method.
The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
    loadComplete(event) {
      let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      xlObj.XLSelection.selectSheet();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example. 
![](Selection_images/Selection_img4.png)