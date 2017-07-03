---
layout: post
title: Getting started with Globalization 
description: Overview of Syncfusion Essential Angular.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Globalization and Localization support for Angular Components

## Globalization

Syncfusion Components has been provided with the built-in globalization support, so that it will be able to adapt for the culture-specific format based on the defined locale property.

Globalization values will be automatically used when locale property is set with locale value (e.g.) en-US. The en-US locale is currently being used in all the Syncfusion components by default.

N> To translate our control content from default English to any of the culture, say for example - German language, then you need to refer the `ej.culture.de-DE.min.js` file in your application. Refer the [link](https://github.com/syncfusion/ej-global/tree/master/i18n) for Seven culture-specific script files.

## Getting started with Globalization

Syncfusion Angular Components supports culture change in application. Now, We are going to discuss about how to change the culture in Angular Application. 

Refer the below steps to create an Angular application with globalization support.

* Clone the Angular seed from [here](https://github.com/syncfusion/angular2-seeds/tree/systemjs)
* Create `textbox` folder inside `src/app` folder.
* Create `textbox.component.html` view file inside `src/app/textbox` folder and render `ejCurrencyTextbox` Angular component using `locale` property which does the culture change in Angular application.

{% highlight html %}

<input id="numeric" type="text" ej-currencytextbox [locale]='locale' format="{0:C}"/>

{% endhighlight %}

N> To know more about `locale` property in textbox, refer the [link](https://help.syncfusion.com/api/js/ejtextboxes#members:locale) here.

* Create `textbox.component.ts` model file inside the folder `src/app/textbox` and create sample component using the below code example

{% highlight ts %}


import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/textbox/textbox.component.html',
})
export class TextboxComponent {
    locale: string;
   constructor(){
       this.locale = 'fr-FR';
    }
}

{% endhighlight %}

* To support the globalization, import the needed culture in `app.module.ts` file 

{% highlight ts %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouterModule } from '@angular/router';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { EJAngular2Module } from 'ej-angular2';
import 'syncfusion-ej-global/i18n/ej.culture.fr-FR.min.js'; // Here we supported the french culture
import { AppComponent } from './app.component';
import { TextboxComponent } from './textbox/textbox.component';
...
...

{% endhighlight %}

N> If we import the culture before the `EJAngular2Module`, we get the following error in our application. So, we should import the culture after the `ej-angular2` package.

![](/angular/GettingStarted/Images/cultureerror.png)

## Run the Application

Run the application with below command

{% highlight javascript %}

npm start

{% endhighlight %}

Before adding the culture to Angular Component

![](/angular/GettingStarted/Images/textbox.png)

After added the `French culture` to Angular Component

![](/angular/GettingStarted/Images/locale.png)

## Localization

Syncfusion Angular components has also been provided with the built-in localization support, so that it will be able to adapt based on the defined locale value. The en-US locale is currently being used in all the Syncfusion Angular components by default.

* To localize the Syncfusion Angular Components into a specific culture, it is necessary to import the culture-specific JavaScript files which contains localized texts.

## Getting Started with Localization

To getting started with Localization support for Angular Components follow the below steps.

* Clone the Angular seed from [here](https://github.com/syncfusion/angular2-seeds/tree/systemjs)
* To support the localization, import the appropriate culture in `app.module.ts` file 

{% highlight ts %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . .
. . .
import { EJAngular2Module } from 'ej-angular2';
import 'syncfusion-ej-global/i18n/ej.culture.de-DE.min.js';
import 'syncfusion-ej-global/l10n/ej.localetexts.de-DE.min.js';
import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { GridComponent } from './grid/grid.component';

import { rootRouterConfig } from './app.routes';

. . . 
. . .

{% endhighlight %}

N> If we import the culture before the `EJAngular2Module`, we get the following error in our application.  So, we should import the culture after the `ej-angular2` package.

![](/angular/GettingStarted/Images/cultureerror.png)

* Add the `locale` property to modify the needed culture in `grid` component.

{% highlight html %}

<ej-grid [allowPaging]="true" [allowSorting]="true" [dataSource]="gridData" [locale]='locale'>
    <e-columns>
        <e-column field="OrderID" headerText="Order ID" width="75" textAlign="right"></e-column>
        <e-column field="CustomerID" headerText="Customer ID" width="80"></e-column>
        <e-column field="EmployeeID" headerText="Employee ID" width="75" textAlign="right"></e-column>
        <e-column field="Freight" width="75" format="{0:C}" textAlign="right"></e-column>
        <e-column field="OrderDate" headerText="Order Date" width="80" format="{0:MM/dd/yyyy}" textAlign="right"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

* Refer the needed culture in `grid.component.ts` file

{% highlight ts %}


import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    locale: string;
    constructor() {
        this.locale= 'de-DE'; // Here we referred the German Culture
    }      
}

{% endhighlight %}

## Run the Application

Run the application with below command

{% highlight javascript %}

npm start

{% endhighlight %}

Before adding the culture to Angular Component

![](/angular/GettingStarted/Images/gridwithoutculture.png)

After added the `German culture` to Angular Component

![](/angular/GettingStarted/Images/culturegrid.png)

	
## FAQ

Query: How to install syncfusion-ej-global package?

Answer: you need not to install `npm:syncfusion-ej-global` package separately. Installation of syncfusion-javascript package will automatically install syncfusion-ej-global package. 

Query: My native culture is not included in syncfusion-ej-global?

Answer: `syncfusion-ej-global package` will have only 13 culture files. If your culture is not included in syncfusion-ej-global then you need to install `npm:syncfusion-ej-global-all` package separately.
Install `syncfusion-ej-global-all` via npm package manager by executing the below command

{% highlight javascript %}

npm install syncfusion-ej-global-all --save

{% endhighlight %}

And refer the `syncfusion-ej-global-all` path instead of `syncfusion-ej-global` like the below one in `app.module.ts` file

{% highlight javascript %}

import 'syncfusion-ej-global-all/i18n/ej.culture.de-DE.min.js';
import 'syncfusion-ej-global-all/l10n/ej.localetexts.de-DE.min.js';

{% endhighlight %}
