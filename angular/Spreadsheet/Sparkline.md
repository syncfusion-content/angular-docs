---
layout: post
title: Sparkline with Spreadsheet widget for Syncfusion Essential Angular-2
description: How to Create sparkline chart in Spreadsheet 
platform: Angular
control: Spreadsheet
documentation: ug
---

# Sparkline

Sparkline are easy to interpret and it conveys much more information to the user by visualizing the data in a small amount of space. Here sparkline were placed inside the cell. It creates the Sparkline based on the selected cell range’s data. You can use `allowSparkline` property to enable/disable Sparkline.


## Types of Sparkline 

The Following Types of Sparkline are available in Spreadsheet.

*	Column
*	Line
*	Win/loss 

You can create the Sparkline by one of the following ways,

*	Using the `Sparkline Type` button to select the type of Sparkline under Sparkline groups of INSERT Tab in ribbon.
*	Using `createSparkline` method to create the Sparkline.


## Sparkline Customization

You can perform the following customizations for Sparkline. These options are available in SPARKLINE DESIGN Tab which is enabled, while clicking the Sparkline element.


<table>
    <colgroup><col width="180px" /></colgroup>
    <tr><th>Feature</br></th><th>API</br></th><th>Description</br></th></tr>
    <tr><td>Edit Data & Location Range</br></td><td>createSparkline</br></td><td>You can modify the data range, location range of Sparkline </br></td></tr>
    <tr><td>Sparkline Type</br></td><td>changeType</br></td><td>You can change the type of sparkline by using sparkline type button.</br></td></tr>
    <tr><td>High Point, First Point, Last Point, Low Point, Negative Point, Sparkline Color and Marker Color</br></td><td>changePointColor</br></td><td>You can high light the high point, low point, first point, last point, negative point and Marker Color of sparkline .</br></td></tr>
</table>

The following code example describes the above behavior,

{% highlight html %}

 <ej-spreadsheet id="Spreadsheet" [allowSparkline]= true (loadComplete)= loadComplete($event)  >
     <e-sheets>
            <e-sheet>
                 <e-rangesettings>
                    <e-rangesetting [dataSource]="spreadData" startCell="A1"></e-rangesetting>
                 </e-rangesettings>
            </e-sheet>
    </e-sheets>
</ej-spreadsheet>


{% endhighlight %}

{% highlight ts %}

import {Component, ViewEncapsulation,ViewChild} from '@angular/core';
 import {SpreadsheetService } from './services/spreadsheet.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
  providers:[SpreadsheetService ]
})

export class AppComponent {
  public spreadData;
  constructor() {
    this.spreadData = [
                 { Discount: 1,  Quantity: 90, Profit: 10, Loss: -10 },
                 { Discount: 5,  Quantity: 83, Profit: 50, Loss: -54 },
                 { Discount: 7,  Quantity: 80, Profit: 27, Loss: -32 },
                 { Discount: 11, Quantity: 93, Profit: 67, Loss: -43 },
                 { Discount: 10, Quantity: 60, Profit: 70, Loss: -50 },
                 { Discount: 13, Quantity: 71, Profit: 66, Loss: -47 },
                 { Discount: 3,  Quantity: 88, Profit: 14, Loss: -30 },
                 { Discount: 6,  Quantity: 95, Profit: 29, Loss: -70 },
                 { Discount: 12, Quantity: 69, Profit: 16, Loss: -56 },
                 { Discount: 9,  Quantity: 77, Profit: 55, Loss: -67 }
             ];
  }

loadComplete(event) {  

       var  xlSparkline = this.XLSparkline;
        if(!this.isImport) {
           this.sheetRename("Sparkline Chart");
           this.mergeCells("F3:G4", true);
           xlSparkline.createSparkline("A5:D5", "F3", "Column", {highPointColor: "red", negativePointColor: "black", startPointColor: "green"} );
           this.mergeCells("F8:G8", true);
           xlSparkline.createSparkline("B2:B4", "F8", "Winloss");
           this.mergeCells("F10:G11", true);
           xlSparkline.createSparkline("C3:C5", "F10",  "Line", {markerSettings:{visible:true},highPointColor: "red", negativePointColor: "black", startPointColor: "green"} );
             }       
        }
    }

    
{% endhighlight %}

The following output is displayed as a result of the above code example.
![](Sparkline_images/Sparkline.png)
