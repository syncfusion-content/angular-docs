---
layout: post
title: Getting-Started
description: getting started
platform: Angular
control: Autocomplete 
documentation: ug
---

# Getting Started

The Angular2 AutoComplete control is a textbox control that provides a list of suggestions based on your query. When you enter text into the text box, the control performs a search operation and provides a list of results. There are several filter types available to perform the search.

This section helps to understand the getting started of the Angular2 AutoComplete with the step-by-step instructions.

## Create an Angular2 AutoComplete

Create a new HTML file and include the below code:

{% highlight html %}

<!DOCTYPE html>
<html>
   <head> 
    <link href="//cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js">
    </script>
    <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.angular2.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src="systemjs.config.js"></script>
  </head>
  <body>
   <ej-app>Loading...</ej-app>
  </body>
</html>

{% endhighlight %}

Create input element and add in the body tag as below.


{% highlight html %}
        
     <div class="container" style="padding-top:100px">
        <div style="padding-left:100px;font-weight: 700;">Car Details</div><br/><br/>
            <div class="row">
                <div class="col-md-1">
                    <p style="font-weight: 700;">Car:</p>
                </div>
            <div class="col-md-8">
                <input type="text" id="auto" ej-autocomplete />
            </div>
        </div>
        <div class="row">
            <div class="col-md-1">
                <p style="font-weight: 700;">Price:</p>
            </div>
            <div class="col-md-8">
                <input type="text" ej-autocomplete  /> 
            </div>
        </div>
{% endhighlight %}

To render the Angular2 AutoComplete using below code.

{% highlight javascript %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
   selector: 'ej-app',    
  templateUrl: 'app/app.component.html',
})

export class AppComponent {
   constructor() {}
}

{% endhighlight %}


![](Getting_started_images/autocomplete.png)

## Model binding

The Angular2 AutoComplete supports the data binding feature. When a widget’s model attribute is bound to ngModel variable, it will be reflected the changes both ways.

Add in the ngModel value as below.

{% highlight html %}

    <div class="container" style="padding-top:100px">
		<div style="padding-left:100px;font-weight: 700;">Car Details</div><br/><br/>
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Car:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{value}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" id="auto" ej-autocomplete [(ngModel)]="value" />
			</div>
        </div>
	<br/>	
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Price:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{valueText}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" ej-autocomplete [(ngModel)]="valueText"  /> 
			</div>
        </div>
{% endhighlight %}
{% highlight javascript %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
   selector: 'ej-app',    
  templateUrl: 'app/app.component.html',
})

export class AppComponent {
  value: string;
  valueText:Number;
   constructor() {
    this.value = "Jaguar XJS";
    this.valueText=29908.18;
   }
}

{% endhighlight %}

![](Getting_started_images/modelbinding.png)


## Data binding

The data for the suggestion list can be populated using the dataSource property. 
{% tabs %}
{% highlight html %}

 <div class="container" style="padding-top:100px">
		<div style="padding-left:100px;font-weight: 700;">Car Details</div><br/><br/>
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Car:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{value}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" id="auto" ej-autocomplete  [dataSource]="dataList" [fields]="nameField" [(ngModel)]="value" />
			</div>
        </div>
	<br/>	
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Price:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{valueText}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" ej-autocomplete  [dataSource]="dataList" [fields]="priceField" [filterType]="greaterthanorequal" [(ngModel)]="valueText"  /> 
			</div>
        </div>


{% endhighlight %}
{% highlight javascript %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
   selector: 'ej-app',    
  templateUrl: 'app/app.component.html',
})

export class AppComponent {
  value: string;
  priceField:any;
  valueText:Number;
  nameField:any;
  dataList:Array<{Price:Number,Mileage:Number,Cylinder:Number,Doors:Number,Name:string}>;
   constructor() {
    this.value = "Jaguar XJS";
	this.dataList = [{Price:22661.05,Mileage:20105,Cylinder:6,Doors:4,Name:"Acura"},
				   {Price:21725.01,Mileage:13457,Cylinder:6,Doors:2,Name:"Alfa Romeo"},
				   {Price:29142.71,Mileage:31655,Cylinder:4,Doors:2,Name:"Aston Martin"},
				   {Price:30731.94,Mileage:22479,Cylinder:4,Doors:2,Name:"Audi S6"},
				   {Price:33358.77,Mileage:17590,Cylinder:4,Doors:2,Name:"BMW 7"},
				   {Price:30315.17,Mileage:23635,Cylinder:4,Doors:2,Name:"Bentley Mulsanne"},
				   {Price:33381.82,Mileage:17381,Cylinder:4,Doors:2,Name:"Bugatti Veyron"},
				   {Price:30251.02,Mileage:27558,Cylinder:4,Doors:2,Name:"Chevrolet Camaro"},
				   {Price:30166.85,Mileage:25049,Cylinder:4,Doors:2,Name:"Cadillac"},
				   {Price:27060.14,Mileage:17319,Cylinder:4,Doors:4,Name:"Duesenberg J"},
				   {Price:26841.08,Mileage:10003,Cylinder:4,Doors:4,Name:"Dodge Sprinter"},
				   {Price:25790.51,Mileage:21160,Cylinder:4,Doors:4,Name:"Elantra"},
				   {Price:25148.38,Mileage:22272,Cylinder:4,Doors:4,Name:"Excavator"},
				   {Price:24173.53,Mileage:27015,Cylinder:4,Doors:4,Name:"Ford Boss 302"},
				   {Price:24852.5,Mileage:22814,Cylinder:4,Doors:4,Name:"Ferrari 360"},
				   {Price:27825.95,Mileage:10014,Cylinder:4,Doors:4,Name:"Ford Thunderbird"},
				   {Price:26698.08,Mileage:23055,Cylinder:4,Doors:4,Name:"GAZ Siber"},
				   {Price:28185.78,Mileage:19854,Cylinder:4,Doors:4,Name:"Jaguar XJS"},
				   {Price:27241.44,Mileage:23204,Cylinder:4,Doors:4,Name:"Maruti Alto 800"},
				   {Price:30800.66,Mileage:8017,Cylinder:4,Doors:4,Name:"Porsche 356"},
				   {Price:28416.46,Mileage:14613,Cylinder:4,Doors:4,Name:"Scion SRS/SC/SD"},
				   {Price:26653.24,Mileage:22590,Cylinder:4,Doors:4,Name:"Saab Sportcombi"},
				   {Price:27610.86,Mileage:22881,Cylinder:4,Doors:4,Name:"Subaru Sambar"},
				   {Price:27788.81,Mileage:26786,Cylinder:4,Doors:4,Name:"Suzuki Swift"},
				   {Price:29986.79,Mileage:18464,Cylinder:4,Doors:4,Name:"Triumph Spitfire"},
				   {Price:29197.79,Mileage:20907,Cylinder:4,Doors:4,Name:"Toyota 2000GT"},
				   {Price:29908.18,Mileage:19830,Cylinder:4,Doors:4,Name:"Lamborghini Diablo"},
				   {Price:29481.53,Mileage:21822,Cylinder:4,Doors:4,Name:"Volvo P1800"},
				   {Price:26792.3,Mileage:25357,Cylinder:4,Doors:4,Name:"Volkswagen Shirako"}
		];
	this.priceField = {text:"Price"};
	this.nameField = {text:"Name"};
    this.valueText=29908.18;
   }
}
 
{% endhighlight %}

{% endtabs %}


![](Getting_started_images/datasource.png)

## Enable Popup Button

This button helps you to show all the available suggestions on clicking it.

{% highlight html %}
<div class="container" style="padding-top:100px">
		<div style="padding-left:100px;font-weight: 700;">Car Details</div><br/><br/>
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Car:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{value}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" id="auto" ej-autocomplete  [dataSource]="dataList" [fields]="nameField" [showPopupButton]="true" [(ngModel)]="value" />
			</div>
        </div>
	<br/>	
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Price:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{valueText}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" ej-autocomplete  [dataSource]="dataList" [fields]="priceField" [showPopupButton]="true" [filterType]="greaterthanorequal" [(ngModel)]="valueText"  /> 
			</div>
        </div>

{% endhighlight %}

![](Getting_started_images/showpopupbutton.png)

## Two Way Binding

The Angular2 AutoComplete have supports a two-way data binding when a model variable is bound to an element that changed in both and display the value of the variable. 

{% tabs %}
{% highlight html %}

        <div class="container" style="padding-top:100px">
		<div style="padding-left:100px;font-weight: 700;">Car Details</div><br/><br/>
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Car:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{value}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" id="auto" ej-autocomplete  [dataSource]="dataList" [fields]="nameField" [showPopupButton]="true" (select)="onAutoselect($event)" [(ngModel)]="value" />
			</div>
        </div>
	<br/>	
		<div class="row">
			<div class="col-md-1">
				<p style="font-weight: 700;">Price:</p>
			</div>
			<div class="col-md-1">
				<p style="font-weight: 700;">{{valueText}}</p>
			</div>
			<div class="col-md-8">
				<input type="text" ej-autocomplete  [dataSource]="dataList" [fields]="priceField" [showPopupButton]="true" [filterType]="greaterthanorequal" (select)="onAutoselect($event)" [(ngModel)]="valueText"  /> 
			</div>
        </div>
    {% endhighlight %}
{% highlight javascript %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
   selector: 'ej-app',    
  templateUrl: 'app/app.component.html',
})

export class AppComponent {
  value: string;
  priceField:any;
  valueText:Number;
  nameField:any;
  dataList:Array<{Price:Number,Mileage:Number,Cylinder:Number,Doors:Number,Name:string}>;
   constructor() {
    this.value = "Jaguar XJS";
	this.dataList = [{Price:22661.05,Mileage:20105,Cylinder:6,Doors:4,Name:"Acura"},
				   {Price:21725.01,Mileage:13457,Cylinder:6,Doors:2,Name:"Alfa Romeo"},
				   {Price:29142.71,Mileage:31655,Cylinder:4,Doors:2,Name:"Aston Martin"},
				   {Price:30731.94,Mileage:22479,Cylinder:4,Doors:2,Name:"Audi S6"},
				   {Price:33358.77,Mileage:17590,Cylinder:4,Doors:2,Name:"BMW 7"},
				   {Price:30315.17,Mileage:23635,Cylinder:4,Doors:2,Name:"Bentley Mulsanne"},
				   {Price:33381.82,Mileage:17381,Cylinder:4,Doors:2,Name:"Bugatti Veyron"},
				   {Price:30251.02,Mileage:27558,Cylinder:4,Doors:2,Name:"Chevrolet Camaro"},
				   {Price:30166.85,Mileage:25049,Cylinder:4,Doors:2,Name:"Cadillac"},
				   {Price:27060.14,Mileage:17319,Cylinder:4,Doors:4,Name:"Duesenberg J"},
				   {Price:26841.08,Mileage:10003,Cylinder:4,Doors:4,Name:"Dodge Sprinter"},
				   {Price:25790.51,Mileage:21160,Cylinder:4,Doors:4,Name:"Elantra"},
				   {Price:25148.38,Mileage:22272,Cylinder:4,Doors:4,Name:"Excavator"},
				   {Price:24173.53,Mileage:27015,Cylinder:4,Doors:4,Name:"Ford Boss 302"},
				   {Price:24852.5,Mileage:22814,Cylinder:4,Doors:4,Name:"Ferrari 360"},
				   {Price:27825.95,Mileage:10014,Cylinder:4,Doors:4,Name:"Ford Thunderbird"},
				   {Price:26698.08,Mileage:23055,Cylinder:4,Doors:4,Name:"GAZ Siber"},
				   {Price:28185.78,Mileage:19854,Cylinder:4,Doors:4,Name:"Jaguar XJS"},
				   {Price:27241.44,Mileage:23204,Cylinder:4,Doors:4,Name:"Maruti Alto 800"},
				   {Price:30800.66,Mileage:8017,Cylinder:4,Doors:4,Name:"Porsche 356"},
				   {Price:28416.46,Mileage:14613,Cylinder:4,Doors:4,Name:"Scion SRS/SC/SD"},
				   {Price:26653.24,Mileage:22590,Cylinder:4,Doors:4,Name:"Saab Sportcombi"},
				   {Price:27610.86,Mileage:22881,Cylinder:4,Doors:4,Name:"Subaru Sambar"},
				   {Price:27788.81,Mileage:26786,Cylinder:4,Doors:4,Name:"Suzuki Swift"},
				   {Price:29986.79,Mileage:18464,Cylinder:4,Doors:4,Name:"Triumph Spitfire"},
				   {Price:29197.79,Mileage:20907,Cylinder:4,Doors:4,Name:"Toyota 2000GT"},
				   {Price:29908.18,Mileage:19830,Cylinder:4,Doors:4,Name:"Lamborghini Diablo"},
				   {Price:29481.53,Mileage:21822,Cylinder:4,Doors:4,Name:"Volvo P1800"},
				   {Price:26792.3,Mileage:25357,Cylinder:4,Doors:4,Name:"Volkswagen Shirako"}
		];
	this.priceField = {text:"Price"};
	this.nameField = {text:"Name"};
    this.valueText=29908.18;
   }
    onAutoselect(event) { 
        if(event.item) {
       this.valueText = event.item.Price;
       this.value = event.item.Name;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![](Getting_started_images/twowaybinding.png)
