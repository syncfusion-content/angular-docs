---
layout: post
title: Cell Range with Spreadsheet widget for Syncfusion Essential JS
description: How to use the Spreadsheet Cell Range
platform: Angular
control: Spreadsheet
documentation: ug
--- 

# Cell Range

A Cell Range is a collection of cells in a sheet. It represents single cell or selection of cells. When cells have been selected, they are surrounded by border. 

You have following features in Cell Range,

* Comment
* Cell Navigation
* Data Validation
* Drag and Drop
* Auto Fill
* Hyperlink
* Merge Cell

## Comment

Comment is used to give additional information for an individual cell about the data it contains. When a cell has a comment, a red indicator appears in the corner of the cell. When mouse hover on the cell, the comment will appear. You can use `allowComments` property to enable/disable comments. 

### To insert a Comment

You can insert a comment by using one of the following ways,

* Using "New" button under Comments group of REVIEW Tab in ribbon.
* Using context menu to select "Insert Comment" option in "Comment".
* Using [`setComment`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcomment-setcomment "setComment") method.

### To remove a Comment

You can remove a comment by using one of the following ways,

* Using "Delete" button under Comments group of REVIEW Tab in ribbon.
* Using context menu to select "Delete Comment" option in "Comment".
* Using [`deleteComment`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcomment-deletecomment "deleteComment") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowComments]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLComment.setComment("A2", " Casual Foot wears with wide variety of colors.", false);
        xlObj.XLComment.setComment("A4", " Formal Foot wears with wide variety of sizes.", true); // If true comment is in Editing mode.
        //To Remove a Comment
        xlObj.XLComment.deleteComment ("A2");
    }
  }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img1.png)

## Cell Navigation

Cell navigation is used to navigate through the cells using keyboard. You can use `allowKeyboardNavigation` property to enable/disable cell navigation. The following list of keys used for cell navigation are,

<table>
<colgroup><col width="180px" /></colgroup>
<tr><th>Keys<br/></th><th>Description<br/></th></tr>
<tr><td>Ctrl + Home<br/></td><td>Go to first cell in the first row.<br/></td></tr>
<tr><td>Ctrl + End<br/></td><td>Go to last cell in the last row.<br/></td></tr>
<tr><td>Up Arrow<br/></td><td>Go to previous cell in the same column<br/></td></tr>
<tr><td>Down Arrow<br/></td><td>Go to next cell in the same column<br/></td></tr>
<tr><td>Right Arrow<br/></td><td>Go to next cell in the same row<br/></td></tr>
<tr><td>Left Arrow<br/></td><td>Go to previous cell in the same row<br/></td></tr>
<tr><td>Page Down<br/></td><td>Go to next block<br/></td></tr>
<tr><td>Page Up<br/></td><td>Go to previous block<br/></td></tr>
<tr><td>Home<br/></td><td>Go to first cell of the same row<br/></td></tr>
<tr><td>End<br/></td><td>Go to last cell of the same row<br/></td></tr>
<tr><td>Enter<br/></td><td>Save the current cell changes and navigate to the next row.<br/></td></tr>
<tr><td>Tab<br/></td><td>Go to next cell<br/></td></tr>
<tr><td>Shift + Tab<br/></td><td>Go to previous cell<br/></td></tr>
<tr><td>Shift + Up Arrow<br/></td><td>Go to previous row or previous row cell with selection<br/></td></tr>
<tr><td>Shift+ Down Arrow<br/></td><td>Go to next row or next row cell with selection<br/></td></tr>
<tr><td>Shift + Right Arrow<br/></td><td>Go to next cell within the same row with selection<br/></td></tr>
<tr><td>Shift + Left Arrow<br/></td><td>Go to previous cell within the same row with selection<br/></td></tr>
<tr><td>Ctrl + Up Arrow<br/></td><td>Go to next cell from the first empty cell in upwards.<br/></td></tr>
<tr><td>Ctrl + Down Arrow<br/></td><td>Go to previous cell from the first empty cell in downwards.<br/></td></tr>
<tr><td>Ctrl + Left Arrow<br/></td><td>Go to next cell from the first empty cell in leftwards.<br/></td></tr>
<tr><td>Ctrl+ Right Arrow<br/></td><td>Go to previous cell from the first empty cell in rightwards.<br/></td></tr>
</table>

N> In the above table, "Ctrl + Home" and "Ctrl + End" is based on the used range.

## Data Validation

Data Validation is used to restrict the user to enter the invalid data. You can use `allowDataValidation` property to enable/disable data validation. 

N> The below validation script files are needed for validation.
N> * jquery.validate.min.js
N> * jquery.validate.unobtrusive.min.js

#### To apply validation.

You can apply data validation by using one of the following ways,

* Using "Data Validation" option in Data Validation button under Data Tools group of DATA Tab in ribbon, Data Validation dialog will be opened in that you can perform Validation.
* Using [`applyDVRules`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-applydvrules "applyDVRules") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowDataValidation]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
      }
   }
}
{% endhighlight %}

#### To clear validation

You can clear data validation rule by one of the following ways,

* Using "Clear Validation" option in Data Validation button under Data Tools group of DATA Tab in ribbon.
* Using [`clearDV`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-cleardv "clearDV") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowDataValidation]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
        xlObj.XLValidate.clearDV("G2:G12");
      }
   }
}
{% endhighlight %}

#### To format invalid data

You can highlight the invalid data by using following ways,

* Using "Format Invalid Data" option in Data Validation button under Data Tools group of DATA Tab in ribbon.
* Using [`highlightInvalidData`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-highlightinvaliddata "highlightInvalidData") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowDataValidation]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

   loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
       xlObj.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
        xlObj.XLValidate.highlightInvalidData ("G2:G12");
      }
   }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img2.png)

## Drag and Drop

Drag and drop is used to pick a selected cells and drop it into a new place on the worksheet. You can use `allowDragAndDrop` property to enable/disable drag and drop. 

You can do this by one of the following ways,

* Using mouse drag and drop.
* Using [`moveRangeTo`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragdrop-moverangeto "moveRangeTo") Method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowDragAndDrop]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLDragDrop.moveRangeTo([1, 6, 4, 7], [1, 9, 4, 10]);
      }
   }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img3.png)

## Auto Fill

Auto Fill is used to fill the cells with data based on adjacent cells. It also follows a pattern from adjacent cells if available. There is no need to enter the repeated data manually. You can use `allowAutoFill` property to enable/disable the auto fill support. You can also use `showFillOptions` property to enable/disable the fill option and `fillType` property to change the default auto fill option which is available in `autoFillSettings`. 

You can do this by one of the following ways,

* Using ???AutoFillOptions??? menu which is open, while drag and drop the cell using fill handle element.
* Using [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method.

In Auto Fill we have following options, 

* Copy Cells
* Fill Series
* Fill Formatting Only
* Fill Without Formatting
* Flash Fill

N> The default auto fill option is "fillSeries" which can be referred from `fillType` property.

#### Copy Cells

To copy the selected cell content to the adjacent cells. You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Copy Cells" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "copyCells" as fill type in [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Series

To fill the series of numbers, characters, or dates based on selected cell content to the adjacent cells with their formats.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Series" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "fillSeries" as fill type in [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Formatting Only

To fill the cell style and number formatting based on the selected cell content to the adjacent cells without their content.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Formatting Only" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "fillFormattingOnly" as fill type in [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Without Formatting

To fill series of numbers, characters, or dates based on the selected cells to the adjacent cells without their formats.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Without Formatting" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "fillWithoutFormatting" as fill type in [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Flash Fill 

To fill the column when it senses a pattern from adjacent column data based on what you type.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Flash Fill" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "flashFill" as fill type in [`autoFill`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

The following code example describes the above behavior.

{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowAutoFill]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
                <e-rangesetting [dataSource]="[{i : 1, j: 1, k : 1, l : 1}, {i : 2, j: 2, k : 2, l : 2}, {i : 3, j: 3, k : 3, l : 3}, {i : 4, j: 4, k : 4, l : 4}]" startCell="I2"></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLEdit.updateValue("N2", "Name");
        xlObj.XLEdit.updateValue("N3", "Casual Shoes");
        xlObj.XLEdit.updateValue("N4", "Formal Shoes");
        xlObj.XLEdit.updateValue("N5", "Sports Shoes");
        xlObj.XLEdit.updateValue("O2", "FirstName");
        xlObj.XLEdit.updateValue("O3", "Casual");
        xlObj.XLFormat.format({ "style": { "background-color": "yellow" } }, "K2:L2");
        xlObj.XLFormat.format({ "style": { "background-color": "red" } }, "K4:L4");
        xlObj.XLFormat.format({ "style": { "background-color": "blue" } }, "K5:L5");
        xlObj.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 8, 4, 8], fillRange: "I6:I10", fillType: "copycells", direction:"down"}); //copy Cells
        xlObj.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 9, 4, 9], fillRange: "J6:J10", fillType: "fillseries", direction:"down"}); //fill series
        xlObj.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 10, 4, 10], fillRange: "K6:K10", fillType: "fillformattingonly", direction:"down"}); //fill formatting only
        xlObj.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 11, 4, 11], fillRange: "L6:L10", fillType: "fillwithoutformatting", direction:"down"}); //fill without formatting
        xlObj.XLDragFill.autoFill({sheetIdx: 1, dataRange:[2, 14, 2, 14], fillRange: "O4:O6", fillType: "flashfill", direction:"down"}); //flash fill
      }
   }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img5.png)

## Hyperlink

Hyperlink is used to navigate to web links or cell reference within the sheet or to other sheets in Spreadsheet. You can use `allowHyperlink` property to enable/disable Hyperlink.

### To insert a Hyperlink

You can insert a hyperlink by one of the following ways,

* Using "Hyperlink" button under Links group of INSERT Tab in ribbon.
* Using context menu to select "Insert Hyperlink" option in "Hyperlink".
* Using [`setHyperlink`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:sethyperlink "setHyperlink") method.

### To remove a Hyperlink

You can remove a hyperlink by one of the following ways,

* Using context menu to select "Remove Hyperlink" option in Hyperlink.
* Using [`removeHyperlink`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:removehyperlink "removeHyperlink") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowHyperlink]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.XLEdit.updateValue("I2", "amazon");
        xlObj.XLEdit.updateValue("J2", "flipkart");
        xlObj.setHyperlink("E3:E3", { "cellAddr": "A1:D2" }, 2);
        xlObj.setHyperlink("I2:I2", { "webAddr": "http://www.amazon.com" }, 1);
        xlObj.setHyperlink("J2:J2", { "webAddr": "http://www.flipkart.com" }, 1);
        //To Remove a Hyperlink
        xlObj.removeHyperlink("J2:J2");
      }
   }
}
{% endhighlight %}


The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img6.png)

## Merge Cell

Merge cell is a single cell created by combining two or more individual cells together. You can use `allowMerging` property to enable/disable merge cells. The cell reference for a merged cell is the cell in the upper left corner of the original selected range or group of cells. 

You have following options in Merge Cell,

* Merge Cells
* Merge & Center
* Merge Across
 
### Merge Cells

You can combine two or more cells located in the same row or column into a single cell. When cells with multiple values are merged, upper-left most cell's data will be the data of merged cell. 

You can do this by one of the following ways,

* Using "Merge Cells" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeCells`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:mergecells "mergeCells") method.

### Merge & Center

You can combine two or more cells located in the same row or column into a single cell with center text align. When cells with multiple values are merged, upper-left most cell's data will be the data of the merged cell. You can do this by one of the following ways,

* Using Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using "Merge & Center" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeCells`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:mergecells "mergeCells") method with `mergeCenter` property as `true` to enable the center alignment.

### Merge Across

You can combine two or more cells located in the same row into a single cell. When cells with multiple values are merged, left most cell's data will be the data of the merged cell.

You can do this by one of the following ways,

* Using "Merge Across" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeAcrossCells`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:mergeacrosscells "mergeAcrossCells") method.

The following code example describes the behavior of merge Cells, merge & center and merge Across.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowMerging]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

    loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.mergeCells("A2:B4", true);
        xlObj.mergeCenter = true;
        xlObj.mergeCells("D2:E4", true); // true is to prevent the alert message.
        xlObj.mergeAcrossCells("G2:H4", true); // true is to prevent the alert message.
      }
   }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img7.png)

### Unmerge Cells

You can split the merged cell into multiple cells. You can do this by one of the following ways,

* Using "Unmerge cells" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`unMergeCells`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:unmergecells "unMergeCells") method.

The following code example describes the above behavior.
{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowMerging]= true (loadComplete)= loadComplete($event)>
    <e-sheets>
        <e-sheet>
            <e-rangesettings>
                <e-rangesetting [dataSource]= "spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}

{% highlight ts %}
import {Component, ViewEncapsulation} from '@angular/core';
import { SpreadsheetService } from '../services/spreadsheet.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[SpreadsheetService]
    })

    export class AppComponent {
        public spreadData;
        constructor(public SpreadsheetService: SpreadsheetService) {
            this.spreadData = SpreadsheetService.getDefaultData();
     }

   loadComplete(event) {
     let xlObj = $("#spreadsheet").data("ejSpreadsheet");
      if(!xlObj.isImport) {
        xlObj.mergeCells("B2:C4", true); // true is to prevent the alert message.
        xlObj.unmergeCells("B2:C4");
      }
   }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Cell-Ranges_images/Cell-Ranges_img8.png)