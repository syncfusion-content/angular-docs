---
layout: post
title: getting started
description: getting started
platform: angular-2
control: ListBox
documentation: ug
---

# Getting Started

The Angular2 ListBox widget that contains a list of selectable items. It performs exceptionally well with thousands of items and supports checkboxes, template, single and multiple selection, keyboard navigation and virtual scrolling.

 This section explains briefly about how to create a web ListBox in your application with Angular 2 by step-by-step instructions

## Create an ListBox widget in Angular2

Create a new HTML file and include the below code:

{% highlight html %}

<!DOCTYPE html>
<html>
   <head> 
    <link href="//cdn.syncfusion.com/{{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js">
    </script>
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/{{site.releaseversion}}/js/common/ej.angular2.min.js"></script>

    <script src="systemjs.config.js"></script>
  </head>
  <body>
   <ej-app>Loading...</ej-app>
  </body>

{% endhighlight %}


Create **input** element and add in the body tag as below.

{% highlight html %}

<div class="container" style="padding-top:100px">

<div class="row">
<div class="ctrllabel" style="padding-bottom: 12px"><b>Select a car</b></div>

<ej-listbox [dataSource]="data" [fields]="fieldList" > </ej-listbox>
        </div>
</div>


{% endhighlight %}


To render the Angular2 ListBox use the below code.

{% highlight js %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/app.component.html',
 styles: [
     ".e-listbox.e-ul li { height: 25px; padding-top: 6px;  }"
  ],
  encapsulation: ViewEncapsulation.None,
})
export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    constructor() {
    this.data=[
        { empid: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { empid: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { empid: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { empid: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { empid: "cr5", text: "Dazzler", value: "Dazzler" },
        { empid: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { empid: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { empid: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { empid: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
        { empid: "cr10", text: "Acura RL", value: "Acura RL" },
        { empid: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { empid: "cr12", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    }
}


{% endhighlight %}


Run the above code to render the following output. 


![](Getting_Started_images\createanlistboxwidgetinangular2_img1.png)


## Model binding

The Angular2 **ListBox** supports the data binding feature. When a widget’s model attribute is bound to ngModel variable, it will be reflected the changes.

The below table depicts the properties of **ListBox** widget that supports model binding:

<table>
<tr>
<td>
<b>control</b></td><td>
<b>Supported properties</b></td></tr>
<tr>
<td>
ejListbox</td><td>
valuedataSource</td></tr>
</table>


Add in the ngModel value as below.

{% highlight html %}

<div class="container" style="padding-top:100px">
<div class="row">
<div class="ctrllabel" style="padding-bottom: 12px"><b>Select a car</b></div>
<ej-listbox [dataSource]="data" [fields]="fieldList" [value]="value" > </ej-listbox>
               <br/>
<div id="binding">
                  <input type="text" id="listValue" class="input ejinputtext" [(ngModel)]="value" />
             </div>
        </div>
</div>


{% endhighlight %}


{% highlight js %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
   selector: 'ej-app',    
  templateUrl: 'app/app.component.html',
})

export class AppComponent {
   data:array;
    fieldList:object;
    value:string;
    constructor() {
    this.data=[
        { empid: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { empid: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { empid: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { empid: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { empid: "cr5", text: "Dazzler", value: "Dazzler" },
        { empid: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { empid: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { empid: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { empid: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
        { empid: "cr10", text: "Acura RL", value: "Acura RL" },
        { empid: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { empid: "cr12", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={text:"text"};
    this.value="Mazda3";
    }
}


{% endhighlight %}

Run the above code to render the following output. 

![](Getting_Started_images\modelbinding_img1.png)


## Enable Selection

The selection property is used to render the ListBox list item by Selection.

{% highlight html %}

       <div class="container" style="padding-top:100px">

<div class="row">
<div class="ctrllabel" style="padding-bottom: 12px"><b>Select a car</b></div>

<ej-listbox [dataSource]="data" [fields]="fieldList" [selectedIndex]="4" > </ej-listbox>

        </div>
</div>

{% endhighlight %}

Run the above code to render the following output. 

![](Getting_Started_images\enableselection_img1.png)



