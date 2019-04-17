---
layout: post
title: Welcome to Syncfusion Essential JS 1 Angular
description: Learn the prerequisite and features of Essential JS 1 for Angular components
platform: Angular
control: Introduction
documentation: ug
--- 

# Angular 

Essential JavaScript provides support for [Angular](https://angular.io/docs/ts/latest/quickstart.html) Framework through wrappers. Each Syncfusion widgets are created as Angular components with built in support for data binding to make complex property definition easier.

The Syncfusion Angular components are named with prefix `ej` to avoid conflicting with other library component and offers the following features.

* Properties
* Two-way binding
* Event binding

<blockquote class="notes angular-version">
<p>The Essential JavaScript for Syncfusion Angular components supports Angular release version <a href="https://blog.angular.io/version-6-of-angular-now-available-cc56b0efa7a4" title="Release Version">6.0.0</a>.</p>
</blockquote>

N> To getting started with Syncfusion Angular seed application navigate to [here](/angular/gettingstarted/overview "Getting started").

## Property Binding

Properties of Syncfusion controls can be initialized with the exact casing of original property names. Bind property to the controls within square bracket(`[]`).

For example, create ejAutocomplete component with prefixing of `ej-` and control name then the properties `dataSource` and `value` can be defined as follows.

{% highlight html %}

<input type="text" ej-autocomplete [value]= "Austin-Healey" [dataSource]="states" />

{% endhighlight %}

N> The dataSource `states` will be defined in component.ts file.

## Event Binding

Events can be bound to the controls using the event name within bracket [`()`]. For example, the `open` event of ejAutocomplete control can be defined as follows.

{% highlight html %}

<input type="text" ej-autocomplete (open)="onOpen($event)" />

{% endhighlight %}

Define event definition at component model as like the below code example.

{% highlight javascript %}

export class AppComponent { 
    onOpen(e){
        console.log("Triggers after the suggestion list is opened.");        
    }
}

{% endhighlight %}

N> Get event argument values as e.data1,e.data2,e.data3.. (For ex,. for ejAutoComplete get type of event as `e.type`).

## Two-way Binding

Two-way binding of Angular synchronizes the value in both view and component model using attribute `[(ngModel)]`. The same conversion is used for Syncfusion widgets which reflect the changes both ways. In general, we could have more than one property bound to the same variable.

Two-way binding for ejAutocomplete has been demonstrated in the below code.

{% highlight javascript %}
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h2>Two-Way Binding</h2>
    <input type="text" ej-autocomplete [dataSource]="states" [(ngModel)]="value"/>
    <input type="text" name="AutoComplete" class="input ej-inputtext" [(ngModel)]="value" />
    `
})
export class AppComponent {
    states: Array<string>;
    value:string; 
    constructor() {
        this.states = [
         "Audi S6", "Austin-Healey", "Alfa Romeo", "Aston Martin",
                    "BMW 7 ", "Bentley Mulsanne", "Bugatti Veyron",
                    "Chevrolet Camaro", "Cadillac ",
                    "Duesenberg J ", "Dodge Sprinter",
                    "Elantra", "Excavator",
                    "Ford Boss 302", "Ferrari 360", "Ford Thunderbird ",
                    "GAZ Siber",
                    "Honda S2000", "Hyundai Santro",
                    "Isuzu Swift", "Infiniti Skyline",
                    "Jaguar XJS",
                    "Kia Sedona EX", "Koenigsegg Agera",
                    "Lotus Esprit", "Lamborghini Diablo ",
                    "Mercedes-Benz ", "Mercury Coupe", "Maruti Alto 800",
                    "Nissan Qashqai",
                    "Oldsmobile S98", "Opel Superboss",
                    "Porsche 356 ", "Pontiac Sunbird",
                    "Scion SRS/SC/SD", "Saab Sportcombi", "Subaru Sambar", "Suzuki Swift",
                    "Triumph Spitfire ", "Toyota 2000GT",
                    "Volvo P1800", "Volkswagen Shirako"
        ];
        this.value="Jaguar XJS";
   }
}


{% endhighlight %}



The below table depicts the properties of all the Syncfusion widgets that supports model binding.


<table>
<tr>
<th>
Control</th><th>
Supported properties</th></tr>
<tr>
<td>
ejAccordion</td><td>
-</td></tr>
<tr>
<td>
ejAutoComplete</td><td>
-</td></tr>
<tr>
<td>
ejBarcode</td><td>
-</td></tr>
<tr>
<td>
ejBulletGraph</td><td>
featureMeasures-value<br/>featureMeasures-comparativeMeasureValue</td></tr>
<tr>
<td>
ejButton</td><td>
-</td></tr>
<tr>
<td>
ejChart</td><td>
xZoomFactor<br/>yZoomFactor<br/>xZoomPosition<br/>yZoomPosition<br/>legend.visibility</td></tr>
<tr>
<td>
ejCheckBox</td><td>
checked<br/>checkState</td></tr>
<tr>
<td>
ejCircularGauge</td><td>
value<br/>minimum<br/>maximum</td></tr>
<tr>
<td>
ejColorPicker</td><td>
value<br/>opacityValue</td></tr>
<tr>
<td>
ejDatePicker</td><td>
-</td></tr>
<tr>
<td>
ejDateTimePicker</td><td>
-</td></tr>
<tr>
<td>
ejDiagram</td><td>
-</td></tr>
<tr>
<td>
ejDialog</td><td>
-</td></tr>
<tr>
<td>
ejDigitalGauge</td><td>
value</td></tr>
<tr>
<td>
ejDropDownList</td><td>
value</td></tr>
<tr>
<td>
ejGantt</td><td>
dataSource<br/>selectedRowIndex<br/>splitterSettings.position</td></tr>
<tr>
<td>
ejGrid</td><td>
dataSource<br/>pageSettings.currentPage<br/>selectedRowIndices<br/>selectedRowIndex</td></tr>
<tr>
<td>
ejGroupButton</td><td>
-</td></tr>
<tr>
<td>
ejFileExplorer</td><td>
-</td></tr>
<tr>
<td>
ejHeatMap</td><td>
-</td></tr>
<tr>
<td>
ejHeatMapLegend</td><td>
-</td></tr>
<tr>
<td>
ejKanban</td><td>
dataSource</td></tr>
<tr>
<td>
ejLinearGauge</td><td>
value<br/>minimum<br/>maximum</td></tr>
<tr>
<td>
ejListBox</td><td>
value</td></tr>
<tr>
<td>
ejListView</td><td>
dataSource</td></tr>
<tr>
<td>
ejMap</td><td>
baseMapIndex<br/>enablePan<br/>enableResize<br/>enableAnimation<br/>zoomSettings.level<br/>zoomSettings.minValue<br/>zoomSettings.maxValue<br/>zoomSettings.factor<br/>zoomSettings.enableZoom<br/>zoomSettings.enableZoomOnSelection<br/>navigationControl.enableNavigation<br/>navigationControl.orientation<br/>navigationControl.absolutePosition<br/>navigationControl.dockPosition</td></tr>
<tr>
<td>
ejMaskEdit</td><td>
-</td></tr>
<tr>
<td>
ejMenu</td><td>
-</td></tr>
<tr>
<td>
ejNavigationDrawer</td><td>
-</td></tr>
<tr>
<td>
ejOverview</td><td>
-</td></tr>
<tr>
<td>
ejPivotGrid</td><td>
-</td></tr>
<tr>
<td>
ejPivotChart</td><td>
-</td></tr>
<tr>
<td>
ejPivotSchemaDesigner</td><td>
-</td></tr>
<tr>
<td>
ejPivotTreeMap</td><td>
-</td></tr>
<tr>
<td>
ejPivotGauge</td><td>
-</td></tr>
<tr>
<td>
ejProgressBar</td><td>
-</td></tr>
<tr>
<td>
ejRadialMenu</td><td>
-</td></tr>
<tr>
<td>
ejRadialSlider</td><td>
value</td></tr>
<tr>
<td>
ejRadioButton</td><td>
-</td></tr>
<tr>
<td>
ejRangeNavigator</td><td>
selectedRangeStart<br/>selectedRangeEnd<br/></td></tr>
<tr>
<td>
ejRating</td><td>
value</td></tr>
<tr>
<td>
ejReportViewer</td><td>
-</td></tr>
<tr>
<td>
ejRibbon</td><td>
-</td></tr>
<tr>
<td>
ejRTE</td><td>
value</td></tr>
<tr>
<td>
ejRotator</td><td>
-</td></tr>
<tr>
<td>
ejSchedule</td><td>
appointmentSettings.dataSource<br/>currentView<br/>currentDate</td></tr>
<tr>
<td>
ejSignature</td><td>
-</td></tr>
<tr>
<td>
ejScroller</td><td>
-</td></tr>
<tr>
<td>
ejSlider</td><td>
value</td></tr>
<tr>
<td>
ejSparkline</td><td>
-</td></tr>
<tr>
<td>
ejSpellCheck</td><td>
-</td></tr>
<tr>
<td>
ejSplitter</td><td>
-</td></tr>
<tr>
<td>
ejSpreadsheet</td><td>
-</td></tr>
<tr>
<td>
ejSunburstChart</td><td>
-</td></tr>
<tr>
<td>
ejSymbolPalette</td><td>
-</td></tr>
<tr>
<td>
ejTab</td><td>
selectedItemIndex</td></tr>
<tr>
<td>
ejTagCloud</td><td>
-</td></tr>
<tr>
<td>
ejTooltip</td><td>
-</td></tr>
<tr>
<td>
ejTreeGrid</td><td>
dataSource<br/>selectedRowIndex</td></tr>
<tr>
<td>
ejNumericTextbox</td><td>
-</td></tr>
<tr>
<td>
ejPercentageTextbox</td><td>
-</td></tr>
<tr>
<td>
ejCurrencyTextbox</td><td>
-</td></tr>
<tr>
<td>
ejTile</td><td>
badge.value<br/>badge.enabled<br/>badge.text<br/>badge.position<br/>text<br/>caption.text</td></tr>
<tr>
<td>
ejTimePicker</td><td>
-</td></tr>
<tr>
<td>
ejToggleButton</td><td>
-</td></tr>
<tr>
<td>
ejToolbar</td><td>
-</td></tr>
<tr>
<td>
ejTreemap</td><td>
dataSource<br/>weightValuePath</td></tr>
<tr>
<td>
ejTreeView</td><td>
dataSource</td></tr>
<tr>
<td>
ejUploadbox</td><td>
-</td></tr>
<tr>
<td>
ejWaitingPopup</td><td>
-</td></tr>
</table>



N> For complete understanding of Angular inputs and outputs binding syntaxes, refer [this](https://angular.io/guide/template-syntax#binding-syntax-an-overview) Angular help document.

## Setting complex properties dynamically

Complex properties don't have two-way binding support in Angular. To set these complex properties dynamically, use setModel option. For example, `editSettings` in Grid is a complex property and you can change this dynamically as done in the following code

{% highlight ts %}

import {Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
    selector: 'my-app',
    template: `<button (click)="set()">Click</button>
     <ej-grid #grid  [allowPaging]="true" [allowScrolling]="true" [toolbarSettings]="toolbarItems" [dataSource]="gridData">
       <e-columns>
        <e-column field="OrderID" headerText="Order ID"  width="85" textAlign="right"></e-column>
        <e-column field="CustomerID" headerText="Customer ID" textAlign="left"  width="100"></e-column>
        <e-column field="EmployeeID" headerText="Employee ID " width="120" textAlign="left"></e-column> 
        <e-column field="Freight" headerText="Freight" width="120" textAlign="left"></e-column> 
        <e-column field="ShipCity" headerText="Ship City " width="120" textAlign="left"></e-column>   
      </e-columns>
    </ej-grid>`
})
export class AppComponent {
     @ViewChild('grid') grid: EJComponents<any, any>; 
        public gridData; 
        public toolbarItems; 
        public Edit; 
       
        constructor() 
        { 
           this.gridData = window.gridData; 
           this.toolbarItems = { showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]}; 
           this.Edit = true; 
        } 
      
       set(e: any){  
           if(this.Edit) 
              //update the editSettings based on value in button click event 
              this.grid.widget.option({editSettings: {allowEditing:true,allowAdding: true,allowDeleting: true,showAddNewRow:true,rowposition: ej.Grid.RowPosition.Bottom }}) 
        else 
             this.grid.widget.option({editSettings: {allowEditing:false,allowAdding: false,allowDeleting: false,showAddNewRow:false,rowposition: ej.Grid.RowPosition.Bottom }}) 
      } 
}

{% endhighlight %}

## Invoking EJ widget methods from component instance

You can invoke the ej widget's public methods using Angular component instance reference like the below syntax.

{% highlight javascript %}

<componentInstance>.widget.<methodName>(<params_if_any>)

{% endhighlight %}

For example, to invoke `clearText` method of ejAutocomplete widget, you can use like `myApp.widget.clearText()`. So the complete code structure of `app.component.ts` will be as follows.

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'my-app',
    template: ` <h2>Two-Way Binding</h2>
    <button id="clearTxt" (click)="myApp.widget.clearText()">clearText</button>
    <input #myApp type="text" ej-autocomplete [dataSource]="states" (open)="onOpen($event)" [(ngModel)]="value"/>
    <input type="text" name="AutoComplete" class="input ej-inputtext" [(ngModel)]="value" />
    `
})
export class AppComponent {
    states: Array<string>;
    value:string; 
    constructor() {
        this.states = [
         "Audi S6", "Austin-Healey", "Alfa Romeo", "Aston Martin",
                    "BMW 7 ", "Bentley Mulsanne", "Bugatti Veyron",
                    "Chevrolet Camaro", "Cadillac ",
                    "Duesenberg J ", "Dodge Sprinter",
                    "Elantra", "Excavator",
                    "Ford Boss 302", "Ferrari 360", "Ford Thunderbird ",
                    "GAZ Siber",
                    "Honda S2000", "Hyundai Santro",
                    "Isuzu Swift", "Infiniti Skyline",
                    "Jaguar XJS",
                    "Kia Sedona EX", "Koenigsegg Agera",
                    "Lotus Esprit", "Lamborghini Diablo ",
                    "Mercedes-Benz ", "Mercury Coupe", "Maruti Alto 800",
                    "Nissan Qashqai",
                    "Oldsmobile S98", "Opel Superboss",
                    "Porsche 356 ", "Pontiac Sunbird",
                    "Scion SRS/SC/SD", "Saab Sportcombi", "Subaru Sambar", "Suzuki Swift",
                    "Triumph Spitfire ", "Toyota 2000GT",
                    "Volvo P1800", "Volkswagen Shirako"
        ];
        this.value="Jaguar XJS";
   }
   onOpen(e){
        console.log("Triggers after the suggestion list is opened.");        
    }
}

{% endhighlight %}

N> Here, We don't need to import the specific component file. Because all component files are import in `EJAngular2Module` from `ej-angular2` package in `app.module.ts` file

* We can invoke the `clearText` method of `ejAutocomplete` widget using `ViewChild` in model file. Refer the below code snippet 

{% highlight ts %}

import {Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
    selector: 'my-app',
    template: ` <h2>Two-Way Binding</h2>
    <button id="clearTxt" #autocomplete (click)="buttonclick($event)">clearText</button>
    <input #myApp type="text" ej-autocomplete [dataSource]="states" (open)="onOpen($event)" [(ngModel)]="value"/>
    <input type="text" name="AutoComplete" class="input ej-inputtext" [(ngModel)]="value" />
    `
})
export class AppComponent {
    states: Array<string>;
    value:string; 
    @ViewChild('myApp') autocomplete: EJComponents<any, any>;
    constructor() {
        this.states = [
         "Audi S6", "Austin-Healey", "Alfa Romeo", "Aston Martin",
                    "BMW 7 ", "Bentley Mulsanne", "Bugatti Veyron",
                    "Chevrolet Camaro", "Cadillac ",
                    "Duesenberg J ", "Dodge Sprinter",
                    "Elantra", "Excavator",
                    "Ford Boss 302", "Ferrari 360", "Ford Thunderbird ",
                    "GAZ Siber",
                    "Honda S2000", "Hyundai Santro",
                    "Isuzu Swift", "Infiniti Skyline",
                    "Jaguar XJS",
                    "Kia Sedona EX", "Koenigsegg Agera",
                    "Lotus Esprit", "Lamborghini Diablo ",
                    "Mercedes-Benz ", "Mercury Coupe", "Maruti Alto 800",
                    "Nissan Qashqai",
                    "Oldsmobile S98", "Opel Superboss",
                    "Porsche 356 ", "Pontiac Sunbird",
                    "Scion SRS/SC/SD", "Saab Sportcombi", "Subaru Sambar", "Suzuki Swift",
                    "Triumph Spitfire ", "Toyota 2000GT",
                    "Volvo P1800", "Volkswagen Shirako"
        ];
        this.value="Jaguar XJS";
   }
   buttonclick(e){
       this.autocomplete.widget.clearText();
   }
   onOpen(e){
        console.log("Triggers after the suggestion list is opened.");        
    }
}

{% endhighlight %}

<style>
.angular-version {
	box-shadow: 0 4px 4px rgba(0,0,0,0.24), 0 0 4px rgba(0,0,0,0.12);
}
</style>
