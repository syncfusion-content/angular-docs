---
layout: post
title: Freeze Pane with Spreadsheet widget for Syncfusion Essential Angular-2
description: How to use the Spreadsheet Freeze Pane
platform: Angular
control: Spreadsheet
documentation: ug
keywords: Freeze, unfreeze, freezePanes, freezeleftcolumn, freezetoprow
--- 

# Freeze Pane 
Freeze pane allows you to keep a portion of the sheet visible, while scrolling through the rest of the worksheet. 

The freeze pane can be applied in a following ways,

1. User Interface
2. Initial Load
3. Method

### User Interface
Select any cell and on OTHERS tab click Freeze Panes in Freeze Panes dropdown list.

![Freeze-Pane](Freeze-Pane_images/Freeze-Pane_img1.png)

### Initial Load
You can use `allowFreezing` property to enable or disable freeze pane in Spreadsheet.
To specify number of rows and columns to be frozen, use `frozenRows` and `frozenColumns` property in sheets.

The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData" [frozenRows]="5" [frozenColumns]="2"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

Create datasource for `Person List`  in `app/services/spreadsheet.service.js` file. Refer the below code snippet to create datasource,

{% highlight javascript %}

export class SpreadsheetService {
    getPersonList(): Array<any> {
        return [{ "SupplierID": 1, "CompanyName": "Exotic Liquids", "ContactName": "Charlotte Cooper", "ContactTitle": "Purchasing Manager", "City": "London", "PostalCode": "EC1 4SD", "Country": "UK" }, { "SupplierID": 2, "CompanyName": "New Orleans Cajun Delights", "ContactName": "Shelley Burke", "ContactTitle": "Order Administrator", "City": "New Orleans", "PostalCode": "70117", "Country": "USA" }, { "SupplierID": 3, "CompanyName": "Grandma Kelly's Homestead", "ContactName": "Regina Murphy", "ContactTitle": "Sales Representative", "City": "Ann Arbor", "PostalCode": "48104", "Country": "USA" }, { "SupplierID": 4, "CompanyName": "Tokyo Traders", "ContactName": "Yoshi Nagase", "ContactTitle": "Marketing Manager", "City": "Tokyo", "PostalCode": "100", "Country": "Japan" }, { "SupplierID": 5, "CompanyName": "Cooperativa de Quesos 'Las Cabras'", "ContactName": "Antonio del Valle Saavedra", "ContactTitle": "Export Administrator", "City": "Oviedo", "PostalCode": "33007", "Country": "Spain" }, { "SupplierID": 6, "CompanyName": "Mayumi's", "ContactName": "Mayumi Ohno", "ContactTitle": "Marketing Representative", "City": "Osaka", "PostalCode": "545", "Country": "Japan" }, { "SupplierID": 7, "CompanyName": "Pavlova, Ltd.", "ContactName": "Ian Devling", "ContactTitle": "Marketing Manager", "City": "Melbourne", "PostalCode": "3058", "Country": "Australia" }, { "SupplierID": 8, "CompanyName": "Specialty Biscuits, Ltd.", "ContactName": "Peter Wilson", "ContactTitle": "Sales Representative", "City": "Manchester", "PostalCode": "M14 GSD", "Country": "UK" }, { "SupplierID": 9, "CompanyName": "PB Knäckebröd AB", "ContactName": "Lars Peterson", "ContactTitle": "Sales Agent", "City": "Göteborg", "PostalCode": "S-345 67", "Country": "Sweden" }];
    }
}

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList(); //Person List
  }
}

{% endhighlight %}

N> The default value of `allowFreezing` property is true.

### Method
You can freeze rows or columns using [`freezePanes`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-freezepanes "freezePanes") method. 

The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet #spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList();  //Person list
  }
  @ViewChild('spreadsheet') xlObj: EJComponents<any, any>;
  ngAfterViewInit() {
    this.xlObj.widget.XLFreeze.freezePanes(5, 2);
  }
}

{% endhighlight %}

The following output is displayed as a result of the above behavior.
![FreezePanes](Freeze-Pane_images/Freeze-Pane_img2.png)

N> When we apply freeze pane by selecting cell “A1”, rows and columns are frozen based on the middle cell in the worksheet.

## Freeze Rows
It allows you to keep the certain number of rows visible while scrolling through the rest of the worksheet.

The freeze rows can be applied in a following ways,

1. Initial Load
2. Method

### Initial Load
You can freeze rows using `frozenRows` property in sheets. 

The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData" [frozenRows]="3"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList(); //Person List
  }
}

{% endhighlight %}

### Method
You can freeze rows using [`freezeRows`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-freezerows "freezeRows") method. 

The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet #spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList();  //Person list
  }
  @ViewChild('spreadsheet') xlObj: EJComponents<any, any>;
  ngAfterViewInit() {
    this.xlObj.widget.XLFreeze.freezeRows(3);
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![FreezeRows](Freeze-Pane_images/Freeze-Pane_img3.png)

N> On OTHERS tab click Freeze Top Row in FreezePanes dropdown list, to freeze top row. You can also freeze top row using [`freezeTopRow`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-freezetoprow "freezeTopRow") method. 

## Freeze Columns
It allows you to keep the certain number of column visible while scrolling through the rest of the work sheet.

The freeze columns can be applied in a following ways,

1. Initial Load
2. Method

### Initial Load
You can apply freeze columns using `frozenColumns` property in sheets.
The following code example describes the above behavior

{% highlight html %}

<ej-spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData" [frozenColumns]="3"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList();  //Person List
  }
}

{% endhighlight %}

### Method
You can apply freeze columns using [`freezeColumns`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-freezecolumns "freezeColumns") method. 
The following code example describes the above behavior

{% highlight html %}

<ej-spreadsheet #spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList();  //Person list
  }
  @ViewChild('spreadsheet') xlObj: EJComponents<any, any>;
  ngAfterViewInit() {
    this.xlObj.widget.XLFreeze.freezeColumns(3);
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![FreezeColumns](Freeze-Pane_images/Freeze-Pane_img4.png)

N> On OTHERS tab click Freeze First Column in FreezePanes dropdown list, to freeze left Column. You can also apply freeze first column using [`freezeLeftColumn`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-freezeleftcolumn "freezeLeftColumn") method. 

## Unfreeze Pane
Unfreeze all the rows and columns to scroll through entire sheet.

The unfreeze pane can be applied in a following ways,

1. User Interface
2. Method

### User Interface
On OTHERS tab click Unfreeze Panes in Freeze Panes dropdown list.
![UnfreezePanes](Freeze-Pane_images/Freeze-Pane_img5.png)

### Method
You can unfreeze rows or columns using [`unfreezePanes`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfreeze-unfreezepanes "unfreezePanes") method. 

The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet #spreadsheet id="Spreadsheet">
    <e-sheets>
        <e-sheet [dataSource]= "spreadData"></e-sheet>
    </e-sheets>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';
import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  constructor(public SpreadsheetService: SpreadsheetService) {
    this.spreadData = SpreadsheetService.getPersonList();  //Person list
  }
  @ViewChild('spreadsheet') xlObj: EJComponents<any, any>;
  ngAfterViewInit() {
    this.xlObj.widget.XLFreeze.freezePanes(5, 2);
    this.xlObj.widget.XLFreeze.unfreezePanes();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![UnfreezePanes](Freeze-Pane_images/Freeze-Pane_img6.png)


