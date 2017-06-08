---
layout: post
title: Clipboard with Spreadsheet widget for Syncfusion Essential JS
description: How to use the Spreadsheet Clipboard
platform: Angular-2
control: Spreadsheet
documentation: ug
---

# Clipboard

The Spreadsheet provides support for the clipboard operations (cut, copy, and paste). Clipboard operations can be enabled or disabled by setting `allowClipboard` property in Spreadsheet.
By default `allowClipboard` property is `true`.  

## Cut

This function cuts the selected range values and make it available in clipboard.

You can do this by one of the following ways. 

* Using "Ctrl + X" key.
* Using Cut button of HOME tab in ribbon to perform cut operation.
* Using Cut option in Context Menu.
* Using [`cut`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-cut "cut") method.

## Copy

This function copies the selected range values and make it available in clipboard.

You can do this by one of the following ways. 

* Using "Ctrl + C" key.
* Using Copy button of HOME tab in ribbon to perform copy operation.
* Using Copy option in Context Menu.
* Using [`copy`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-copy "copy") method.

## Paste

This function pastes the clipboard content to newly selected range. If you perform cut paste, clipboard contents are cleared whereas in copy paste the clipboard contents are maintained. 

You have following options in Paste.

* Paste Special - You can paste the values with formatting.
* Paste - You can paste only the values.

N> The default paste option is Paste Special. This is working only within the current Spreadsheet. If you copy the content from other sources, it will paste only the values in the Spreadsheet.

You can do this by one of the following ways,

* Using "Ctrl + V" key.
* Using Paste button of HOME tab in ribbon to perform paste operation.
* Using Paste option in Context Menu.
* Using [`paste`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlclipboard-paste "paste") method.

The following code example describes the above behavior.

{% highlight html %}
<ej-spreadsheet id="spreadsheet" [allowClipboard]= true (loadComplete)= loadComplete($event) >
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
    var xlClip = xlObj.XLClipboard;
    xlObj.performSelection("G1:H3");
    xlClip.cut(); // Cut the selected cells
    //xlClip.copy();//Copy the selected cells.
    xlObj.performSelection("J4");
    xlClip.paste();
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Clipboard_images/Clipboard_img1.png)

N> Similarly you can perform clipboard operations for shapes (Chart and Image).