---
layout: post
title: Welcome to Syncfusion Essential Angular 2
description: Overview of Syncfusion Essential Angular 2
platform: Angular
control: Introduction
documentation: ug
--- 
# Angular 2

Essential JavaScript provides support for [Angular 2](https://angular.io/docs/ts/latest/quickstart.html) Framework through wrappers. Each Syncfusion widgets are created as Angular 2 components with built in support for data binding and child directives to make complex property definition easier.

The Syncfusion Angular 2 components are named with prefix `ej` to avoid conflicting with other library component and offers the following features.

* Properties
* Two-way binding
* Event binding

<blockquote class="notes angular-version">
<p>The Essential JavaScript for Syncfusion Angular 2 components supports Angular 2 release version <a href="http://angularjs.blogspot.in/2017/03/angular-400-now-available.html" title="Release Version">4.X.X</a>.</p>
</blockquote>

N> To getting started with Syncfusion Angular 2 seed application navigate to [here](/angular-2/GettingStarted "Getting started").

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

Two-way binding of Angular 2 synchronizes the value in both view and component model using attribute `[(ngModel)]`. The same conversion is used for Syncfusion widgets which reflect the changes both ways. In general, we could have more than one property bound to the same variable.

Two-way binding for ejAutocomplete has been demonstrated in the below code.

{% highlight javascript %}

@Component({
    selector: 'my-app',
    template: `<h2>Two-Way Binding</h2>
    <input type="text" ej-autocomplete [dataSource]="states" (open)="onOpen($event)" [(ngModel)]="value"/>
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
value</td></tr>
<tr>
<td>
ejBarcode</td><td>
-</td></tr>
<tr>
<td>
ejBulletGraph</td><td>
-</td></tr>
<tr>
<td>
ejButton</td><td>
-</td></tr>
<tr>
<td>
ejChart</td><td>
-</td></tr>
<tr>
<td>
ejCheckBox</td><td>
-</td></tr>
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
value</td></tr>
<tr>
<td>
ejDateTimePicker</td><td>
value</td></tr>
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
dataSource<br/>selectedItem<br/>splitterSettings.position</td></tr>
<tr>
<td>
ejGrid</td><td>
dataSource<br/>pageSettings.currentPage</td></tr>
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
ejMaps</td><td>
baseMapIndex<br/>enablePan<br/>enableResize<br/>enableAnimation<br/>zoomSettings.level<br/>zoomSettings.minValue<br/>zoomSettings.maxValue<br/>zoomSettings.factor<br/>zoomSettings.enableZoom<br/>zoomSettings.enableZoomOnSelection<br/>navigationControl.enableNavigation<br/>navigationControl.orientation<br/>navigationControl.absolutePosition<br/>navigationControl.dockPosition</td></tr>
<tr>
<td>
ejMaskEdit</td><td>
value</td></tr>
<tr>
<td>
ejMenu</td><td>
-</td></tr>
<tr>
<td>
ejPivotGrid</td><td>
-</td></tr>
<tr>
<td>
ejRadioButton</td><td>
-</td></tr>
<tr>
<td>
ejRangeNavigator</td><td>
-</td></tr>
<tr>
<td>
ejRating</td><td>
value</td></tr>
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
ejScroller</td><td>
-</td></tr>
<tr>
<td>
ejSlider</td><td>
value</td></tr>
<tr>
<td>
ejSplitButton</td><td>
-</td></tr>
<tr>
<td>
ejSplitter</td><td>
-</td></tr>
<tr>
<td>
ejTab</td><td>
-</td></tr>
<tr>
<td>
ejTagCloud</td><td>
-</td></tr>
<tr>
<td>
ejNumericTextbox</td><td>
value</td></tr>
<tr>
<td>
ejPercentageTextbox</td><td>
value</td></tr>
<tr>
<td>
ejCurrencyTextbox</td><td>
value</td></tr>
<tr>
<td>
ejTimePicker</td><td>
value</td></tr>
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
-</td></tr>
<tr>
<td>
ejUploadbox</td><td>
-</td></tr>
<tr>
<td>
ejWaitingPopup</td><td>
-</td></tr>
</table>



N> For complete understanding of Angular 2 inputs and outputs binding syntaxes, refer [this](https://angular.io/docs/ts/latest/guide/template-syntax.html#!#binding-syntax-an-overview) Angular 2 help document.

## Invoking EJ widget methods from component instance

You can invoke the ej widget's public methods using Angular 2 component instance reference like the below syntax.

{% highlight javascript %}

<componentInstance>.widget.<methodName>(<params_if_any>)

{% endhighlight %}

For example, to invoke `clearText` method of ejAutocomplete widget, you can use like `myApp.widget.clearText()`. So the complete code structure of `app.component.ts` will be as follows.

{% highlight javascript %}

import {Component} from '@angular/core';
import {EJ_AUTOCOMPLETE_COMPONENTS} from 'ej/autocomplete.component';

@Component({
    selector: 'my-app',
    template: ` <h2>Two-Way Binding</h2>
    <button id="clearTxt" (click)="myApp.widget.clearText()">clearText</button>
    <input #myApp type="text" ej-autocomplete [dataSource]="states" (open)="onOpen($event)" [(ngModel)]="value"/>
    <input type="text" name="AutoComplete" class="input ej-inputtext" [(ngModel)]="value" />
    `,
    directives: [EJ_AUTOCOMPLETE_COMPONENTS],
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

<style>
.angular-version {
	box-shadow: 0 4px 4px rgba(0,0,0,0.24), 0 0 4px rgba(0,0,0,0.12);
}
</style>
