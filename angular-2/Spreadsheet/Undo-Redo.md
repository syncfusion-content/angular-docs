---
layout: post
title: Undo Redo with Spreadsheet widget for Syncfusion Essential JS
description: How to enable Undo Redo and its functionalities
platform: Angular-2
control: Spreadsheet
documentation: ug
--- 

# Undo and Redo

Spreadsheet provides the support to perform undo and redo operations. You can set `allowUndoRedo` as true to enable undo redo feature. You can also use `undoRedoStep` property to limit the undo redo action.

N> Default value of `undoRedoStep` is 20. You can perform 20 undo or redo actions.

The following code example describes the above behavior.

{% highlight html %}
<ej-spreadsheet id="spreadsheet" scrollSettings.height="550" scrollSettings.width="750" (loadComplete)= loadComplete($event)  [allowUndoRedo]= "false" >
    <e-sheets>
        <e-sheet >
            <e-rangesettings>
                <e-rangesetting [dataSource]="spreadData" ></e-rangesetting>
            </e-rangesettings>
        </e-sheet>
    </e-sheets>
</ej-spreadsheet>
{% endhighlight %}


## Undo the last action

Undo reverses the last action you performed with spreadsheet. You can do this by following ways.

* Use Undo button of HOME tab in ribbon.
* Use "Ctrl + Z" key.

## Redo the action

Redo reverses the last undo action you performed with spreadsheet. You can do this by following ways.

* Use Redo button of HOME tab in ribbon.
* Use "Ctrl + Y" key.