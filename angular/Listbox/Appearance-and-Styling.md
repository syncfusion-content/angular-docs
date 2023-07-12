---
layout: post
title: Appearance-And-Styling | ListBox | Angular | Syncfusion
description: Learn here about Appearance And Styling in Syncfusion Essential Angular ListBox Control, its elements, and more.
platform: Angular
control: ListBox
documentation: ug
---

# Appearance And Styling in Angular ListBox 

## Theme

**ListBox** control support rich appearance. This control consist of six flat themes and six gradient themes. To use these twelve themes, refer the themes files in HTML file. 

You need two style sheets to apply styles to **ListBox** control; one **ej.widgets.core.min.css** and one **ej.theme.min.css**. If you use **ej.web.all.min.css** then you don’t need to use **ej.widgets.core.min.css** and **ej.theme.min.css** because **ej.web.all.min.css** is a combination of these two.

The core style sheet applies styles related to positioning and size, but are not related to the color scheme and always require the control to look correct and function properly. The theme styles sheet applies theme-specific styles like colors and backgrounds.

The following list is of themes supported by **ListBox**:

* default-theme
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* Material
* office-365
* Bootstrap
* High-Contrast-01
* High-contrast-02

Add the following code in your **HTML** page.

{% highlight html %}

<!DOCTYPE html>
<html lang="en">
   <head>
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/gradient-lime/ej.web.all.min.css" rel="stylesheet" />
      <script src="node_modules/core-js/client/shim.min.js"></script>
      <script src="node_modules/zone.js/dist/zone.js"></script>
      <script src="node_modules/reflect-metadata/Reflect.js"></script>
      <script src="node_modules/systemjs/dist/system.src.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
      <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
      <script src="systemjs.config.js"></script>
   </head>
 <body>
    <ej-app>Loading...</ej-app>
 </body>
</html>

{% endhighlight %}

Create input element and add in the body tag as below.

{% highlight html %}

<div><b>Select a car</b></div>

<ej-listbox [dataSource]="data" [fields]="fieldList" > </ej-listbox>

{% endhighlight %}

To render the Angular ListBox use the below code.

{% highlight ts %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
  selector: 'home',
  templateUrl: 'app/app.component.html',
  encapsulation: ViewEncapsulation.None,
})
export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    constructor() {
    this.data=[
        { employeeId: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { employeeId: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { employeeId: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { employeeId: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { employeeId: "cr5", text: "Dazzler", value: "Dazzler" },
        { employeeId: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { employeeId: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { employeeId: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { employeeId: "cr9", text: "Honda Cross tour", value: "Honda Cross tour" },
        { employeeId: "cr10", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { employeeId: "cr11", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    }
}

{% endhighlight %}

![Appearance and Styling in Angular ListBox](appearance-and-styling_images/angular-listbox-appearance-and-styling.png)

## Css Class

**ListBox** control also allows you to customize its appearance using user-defined CSS and custom skin options such as colors and backgrounds. To apply custom themes you have a property called **cssClass**. **cssClass** property sets the root class for **ListBox** theme.

Using this **cssClass** you can override the existing styles under the theme style sheet. The theme style sheet applies theme-specific styles like colors and backgrounds. In the following example, the value of **cssClass** property is set as **customClass**. **customClass** is added as root class to **ListBox** control at the runtime. From this root class you can customize the **ListBox** control theme.

Add the following code in your **HTML** page to render the ListBox.

{% highlight html %}

<!DOCTYPE html>
<html lang="en">
   <head>
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/gradient-lime/ej.web.all.min.css" rel="stylesheet" />
      <script src="node_modules/core-js/client/shim.min.js"></script>
      <script src="node_modules/zone.js/dist/zone.js"></script>
      <script src="node_modules/reflect-metadata/Reflect.js"></script>
      <script src="node_modules/systemjs/dist/system.src.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
      <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
      <script src="systemjs.config.js"></script>
   </head>
 <body>
    <ej-app>Loading...</ej-app>
 </body>
</html>

{% endhighlight %}

Create input element and add in the body tag as below.

{% highlight html %}

 <div><b>Select a car</b></div>

 <ej-listbox [dataSource]="data" [fields]="fieldList" [cssClass]="cssClass"> </ej-listbox>

{% endhighlight %}

To render the Angular ListBox use the below code.

{% highlight ts %}

import {Component,NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';
import {BrowserModule} from '@angular/platform-browser';

@Component({
  selector: 'home',
  templateUrl: 'app/app.component.html',
  encapsulation: ViewEncapsulation.None,
})
export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    cssClass: string;
    constructor() {
    this.data=[
        { employeeId: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { employeeId: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { employeeId: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { employeeId: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { employeeId: "cr5", text: "Dazzler", value: "Dazzler" },
        { employeeId: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { employeeId: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { employeeId: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { employeeId: "cr9", text: "Honda Cross tour", value: "Honda Cross tour" },
        { employeeId: "cr10", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { employeeId: "cr11", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    this.cssClass = "customClass";
    }
}

{% endhighlight %}

In the following style sheet the existing theme style sheet file has been over-ridden using root class **customClass**. 

Add the following code in your style section.

{% highlight css %}

<style>
    .customClass .e-listbox .e-select {
        background: #FF1975;
    }
</style>

{% endhighlight %}

![CSS Class in Angular ListBox](appearance-and-styling_images/angular-listbox-css-class.png)

