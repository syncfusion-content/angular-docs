---
title: Formula support in Spreadsheet for Syncfusion Essential Angular-2
description: How to use formulas in Spreadsheet with cell references, named ranges etc.
platform: Angular
control: Spreadsheet
documentation: Ug
---
# Formulas

Formulas are used for calculation of data in sheet. You can refer the formula cell reference in following ways,

1. Cell reference from same sheet
2. Cell reference from different sheets

You can set formula for a `cell` in following ways,

1. Initial Load
2. Method
3. User Interface

### Initial Load

You can set formula for a cell by specifying `value` property in cell data binding. The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet [sheets] = "spreadData"></ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  constructor() {
     this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      },
      {
        cells: [{
          value: "=SUM(A1,A2)"
        }]
      }]
    },
    {
      rows: [{
        cells: [{
          value: "=Sum(Sheet1!A1:A2)"
        }]
      }]
    }];  
  }
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![Formula](Formulas_images/Formula_img6.png)

Cell Reference from Same sheet
{:.caption}

![Formula](Formulas_images/Formula_img7.png)

Cell Reference from different sheets
{:.caption}

### Method

You can set formula for a cell using [`updateCellValue`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xledit-updatecellvalue "updateCellValue") method. The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet #spreadsheet [sheets] = "spreadData"></ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  constructor() {
    this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      }]
    }];
  }
  @ViewChild('spreadsheet') xlObj: EJComponents<any, any>;
  ngAfterViewInit() {
    this.xlObj.widget.XLEdit.updateCellValue({ rowIndex: 2, colIndex: 0 }, "=SUM(A1,A2)");
  }
}

{% endhighlight %}
The following output is displayed as a result of the above code example.
![Formula](Formulas_images/Formula_img1.png)

### User Interface

You can set formula for a cell by edit and save a cell through user interface using `Editing` feature. The following code example and screenshot describes the above behavior,

{% highlight html %}

<ej-spreadsheet [sheets] = "spreadData"></ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  constructor() {
    this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      }]
    }];
  }
}

{% endhighlight %}

![Formula](Formulas_images/Formula_img2.png)

The following output is displayed while saving edited cell with above code example.
![Formula](Formulas_images/Formula_img1.png)

N> 1. The list of supported formulas can be find in following [`link`](https://help.syncfusion.com/js/calculate/supported-formulas/supported-formulas "link")
N> 2. Constant values, cell references, formulas and named ranges can be passed as argument to formulas
N> 3. Selection can be used to mention cell references within formula

## User Defined Functions

The list of formulas supported in Spreadsheet is sufficient for most of your calculations. If not, you can create and use your own function using user defined function option. You can add user defined function to Spreadsheet in following ways,

1. Initial Load

2. Method


### Initial Load

You can add your own function to Spreadsheet at initial load with `customFormulas` API. The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" [sheets] = "spreadData" [customFormulas] = "formula">
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  public formula;
  constructor() {
    this.spreadData = [{
                rows: [{
                    cells: [{
                        value: 1
                    }]
                    },
                    {
                    cells: [{
                        value: 2
                    }]
                    },                    
                    {
                    cells: [{
                        value: "=CUSTOMTOTAL(A1,A2,3)"
                    }]
                }]
            }];
    this.formula=[{"formulaName":"CUSTOMTOTAL", "functionName":"customTotal"}];
  }
}

{% endhighlight %}

Place the following code in index.html,

{% highlight html %}

<script>
function customTotal(args) {
    var param1, param2, param3, value, xlObj = $('#spreadsheet').data("ejSpreadsheet"),
    argument = xlObj.getValueFromFormulaArg(args);
    param1 = argument["arg1"];
    param2 = argument["arg2"];
    param3 = argument["arg3"];
    value = param1 * param2 + param3;
    return value;
}
</script>
	
{% endhighlight %}

The following output is displayed as a result of the above code example.
![Custom Formula](Formulas_images/Formula_img5.png)

### Method

You can add your own function to Spreadsheet using [`addCustomFormula`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:addcustomformula "addCustomFormula") method. The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" [sheets] = "spreadData" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  constructor() {
    this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      }]
    }];
  }
  loadComplete(event) {
    let xlObj = $("#spreadsheet").data("ejSpreadsheet");
    xlObj.addCustomFormula("CUSTOMTOTAL", "customTotal");
    xlObj.XLEdit.updateCellValue({ rowIndex: 2, colIndex: 0 }, "=CUSTOMTOTAL(A1,A2,3)");
  }
}

{% endhighlight %}

Place the following code in index.html,

{% highlight html %}

<script>
function customTotal(args) {
    var param1, param2, param3, value, xlObj = $('#spreadsheet').data("ejSpreadsheet"),
    argument = xlObj.getValueFromFormulaArg(args);
    param1 = argument["arg1"];
    param2 = argument["arg2"];
    param3 = argument["arg3"];
    value = param1 * param2 + param3;
    return value;
}
</script>
	
{% endhighlight %}

The following output is displayed as a result of the above code example.
![Custom Formula](Formulas_images/Formula_img5.png)

To remove user defined function from Spreadsheet use [`removeCustomFormula`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:removecustomformula "removeCustomFormula") method.

## Named Ranges

To understand the purpose of cell reference or table, you can define a meaningful name using named ranges support. By using names, you can make your formula much easier to understand and maintain. You can add named ranges to Spreadsheet in following ways,

   
1. Initial load

2. Method

3. User Interface

### Initial Load

To add named ranges at initial load by using [`nameManager`](https://help.syncfusion.com/api/js/ejspreadsheet#members:namemanager "nameManager") API, and also you can specify the name and address of the range by using [`name`](https://help.syncfusion.com/api/js/ejspreadsheet#members:namemanager-name "name") and [`refersto`](https://help.syncfusion.com/api/js/ejspreadsheet#members:namemanager-refersto "refersto") API. You can find the added named range list collection in Spreadsheet by accessing [`nameManager`](https://help.syncfusion.com/api/js/ejspreadsheet#members:namemanager "nameManager") API.
The following code example describes the above behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" [sheets] = "spreadData" [nameManager] = "namemanager">
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewEncapsulation } from '@angular/core';
//import { SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  //providers: [SpreadsheetService]
})
export class AppComponent {
  public spreadData;
  public namemanager;
  constructor() {
    this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      }]
    }];
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![Named Ranges](Formulas_images/Formula_img3.png)

### Method

You can add named range to Spreadsheet with [`addNamedRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlribbon-addnamedrange "addNamedRange") method and it can be removed with [`removeNamedRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlribbon-removenamedrange "removeNamedRange") method. The following code example describes the [`addNamedRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlribbon-addnamedrange "addNamedRange") behavior,

{% highlight html %}

<ej-spreadsheet id="spreadsheet" [sheets] = "spreadData" (loadComplete)= loadComplete($event)>
</ej-spreadsheet>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
})
export class AppComponent {
  public spreadData;
  public namemanager;
  constructor() {
    this.spreadData = [{
      rows: [{
        cells: [{
          value: 1
        }]
      },
      {
        cells: [{
          value: 2
        }]
      }]
    }];
  }
  loadComplete(event) {
    let xlObj = $("#spreadsheet").data("ejSpreadsheet");
    xlObj.XLRibbon.addNamedRange("inputrange", "=Sheet1!$A$1:$A$2", "named range demo", xlObj.getActiveSheetIndex());
    xlObj.XLEdit.updateCellValue({ rowIndex: 2, colIndex: 0 }, "=SUM(inputrange)");
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.
![Named Ranges](Formulas_images/Formula_img3.png)

### User Interface

You can define name for range of cells through user interface using `Define Name` option in `OTHERS` tab. The following screenshot describes the above behavior,
![Named Ranges](Formulas_images/Formula_img4.png)

N> Defining name for cell reference or table will be accessible across all sheets.
N> Named Ranges will be displayed in Name Manger dialog box.

## Formula Bar

Formula bar is used to edit or enter cell data in much easier way. To enable formula bar set `allowFormulaBar` as `true`.

## Auto Sum

To sum a row or column of numbers, select a cell next to the numbers you want to sum, click `AutoSum` on the `HOME` tab and press enter. To enable auto sum set `allowAutoSum` API as `true`.
The auto sum options in ribbon is used to perform basic operations like sum, average, count, minimum, maximum etc.