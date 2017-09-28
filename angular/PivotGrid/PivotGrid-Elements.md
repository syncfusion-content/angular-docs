---
title: PivotGrid-Elements
description: pivotGrid elements
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# PivotGrid: Elements

## Hyperlink
The PivotGrid control supports hyperlink option to link data for each individual cell. Hyperlink can be enabled separately for row header, column header, value and summary cells. Following are the respective properties:

* [`enableColumnHeaderHyperlink`](/api/angular/ejpivotgrid#members:hyperlinksettings-enablerowheaderhyperlink) - Enables hyperlink for column headers.
* [`enableRowHeaderHyperlink`](/api/angular/ejpivotgrid#members:hyperlinksettings-enablerowheaderhyperlink) - Enables hyperlink for row headers.
* [`enableSummaryCellHyperlink`](/api/angular/ejpivotgrid#members:hyperlinksettings-enablesummarycellhyperlink) - Enables hyperlink for summary cell.
* [`enableValueCellHyperlink`](/api/angular/ejpivotgrid#members:hyperlinksettings-enablevaluecellhyperlink) - Enables hyperlink for value cell.

Also hyperlink option provides separate events for row header, column header, value and summary cells as mentioned below.
 
* [`columnHeaderHyperlinkClick`](/api/angular/ejpivotgrid#events:columnheaderhyperlinkclick) - Returns column header information through event on hyperlink click.
* [`rowHeaderHyperlinkClick`](/api/angular/ejpivotgrid#events:rowheaderhyperlinkclick) - Returns row header information through event on hyperlink click.
* [`summaryCellHyperlinkClick`](/api/angular/ejpivotgrid#events:summarycellhyperlinkclick) - Returns summary cell information through event on hyperlink click.
* [`valueCellHyperlinkClick`](/api/angular/ejpivotgrid#events:valuecellhyperlinkclick) - Returns value cell information through event on hyperlink click.

{% tabs %}

{% highlight html %}

<ej-pivotgrid [hyperlinkSettings]="hyperlinkSettings" (rowHeaderHyperlinkClick)="CellClickEvent($event)" (summaryCellHyperlinkClick)="CellClickEvent($event)"
    (valueCellHyperlinkClick)="CellClickEvent($event)" (columnHeaderHyperlinkClick)="CellClickEvent($event)">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}
    //..
    export class PivotGridComponent {
        public hyperlinkSettings;
        constructor() {
          this.hyperlinkSettings = hyperlinkSettings= {
            enableValueCellHyperlink: true,
            enableRowHeaderHyperlink: true,
            enableColumnHeaderHyperlink: true,
            enableSummaryCellHyperlink: true
            };
        }
        CellClickEvent() {
            alert("Cell click event is fired.");
        }
    }

{% endhighlight %}

{% endtabs %}

![](PivotGrid-Elements_images/hyperlink.png)

## Selection
You can select a particular range of value cells from PivotGrid and manipulate/display them. Cell selection is applicable only for value cells and you can enable this functionality by setting [`enableCellSelection`](/api/angular/ejpivotgrid#members:enablecellselection) property to true.

The [`cellSelection`](/api/angular/ejpivotgrid#events:cellselection) event would be triggered as soon as the selection process is over, that is, when the mouse left click is released. The event argument contains a collection of JSON records and header values, which contains information about the selected cells.

{% tabs %}

{% highlight html %}

<ej-pivotgrid [enableCellSelection]="true" (cellSelection)="valueCellClick($event)">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    valueCellClick() {
       //This event lets you to perform required operation with the selected range of cells.
        let cellvalue = evt.JSONRecords;
        let rowheaders = evt.rowHeader;
        let colheaders = evt.columnHeader;
    }
}

{% endhighlight %}

{% endtabs %}

![](PivotGrid-Elements_images/cellselection.png)

## Cell Context
Cell context allows user to perform any custom operation on cell right-click. For example, you can create and display context menu on cell right-click.

Cell context is enabled by setting the [`enableCellContext`](/api/angular/ejpivotgrid#members:enablecellcontext) property to true. The [`cellContext`](/api/angular/ejpivotgrid#events:cellcontext) event would be raised as soon as right-click is done providing cell information through event argument.

{% tabs %}

{% highlight html %}

<ej-pivotgrid [enableCellContext]="true" (cellContext)="cell_RightClick($event)">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    cell_RightClick() {
       //You can write your code here
    }
}

{% endhighlight %}

{% endtabs %}

## Conditional Formatting
Conditional formatting in PivotGrid allows user to highlight particular cells with certain color, font-style, font-family etc. based on the condition they have met.  Also the condition can be applied for certain Measure alone.
  
Conditional formatting is enabled by setting [`enableConditionalFormatting`](/api/angular/ejpivotgrid#members:enableConditionalFormatting) property to true and the formatting dialog is launched when **"createConditionalDialog"** method is invoked.

{% tabs %}

{% highlight html %}

<ej-pivotgrid [enableConditionalFormatting]="true">
</ej-pivotgrid>
<input id="conFormat" ej-button size="normal" (click)="onConFormat($event)" value="Apply" text="Apply" />

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    onConFormat(args) {
      let pivotGrid = $('.e-pivotgrid').data('ejPivotGrid');
      if (pivotGrid.model.enableConditionalFormatting) {
        pivotGrid.openConditionalFormattingDialog();
      }
  }
}

{% endhighlight %}

{% endtabs %}

![](PivotGrid-Elements_images/FormatDialog.png)

![](PivotGrid-Elements_images/FormattedGrid.png)

### Export

We can export the PivotGrid with highlighted particular cells along with its formatting styles. 

LIMITATIONS FOR WORD:

The following border styles are not supported

* Solid
* Groove
* Ridge

LIMITATIONS FOR PDF:

Border styles are not applicable.

LIMITATIONS FOR EXCEL:

The following border styles are alone supported

* Dashed
* Dotted
* Double

Also border size is not supported.

![](PivotGrid-Elements_images/conditional_export.png)