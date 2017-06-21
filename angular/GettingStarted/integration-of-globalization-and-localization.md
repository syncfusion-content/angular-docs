---
layout: post
title: Getting started with Globalization 
description: Overview of Syncfusion Essential Angular.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Globalization support for Angular Components

## Globalization

Syncfusion Components has been provided with the built-in globalization support, so that it will be able to adapt for the culture-specific format based on the defined locale property.

Globalization values will be automatically used when locale property is set with locale value (e.g.) en-US. The en-US locale is currently being used in all the Syncfusion components by default.

N> To translate our control content from default English to any of the culture, say for example - German language, then you need to refer the `ej.culture.de-DE.min.js` file in your application. Refer the [link](https://github.com/syncfusion/ej-global/tree/master/i18n) for Seven culture-specific script files.

## Getting started with Globalization

Syncfusion Angular Components supports culture change in application. Now, We are going to discuss about how to change the culture in Angular Application. 

Refer the below steps to create an Angular application with globalization support.

* Clone the Angular seed from [here](https://github.com/syncfusion/angular2-seeds/tree/systemjs)
* Create `textbox` folder inside `src/app` folder.
* Create `textbox.component.html` view file inside `src/app/textbox` folder and render `ejCurrencyTextbox` Angular component using the below code example.

{% highlight html %}

<input id="numeric" type="text" ej-currencytextbox [locale]='locale' format="{0:C}"/>

{% endhighlight %}

Here the `locale` property does the culture change in Angular application. To know more about locale property in textbox, refer the [link](https://help.syncfusion.com/api/js/ejtextboxes#members:locale) here.

* Create `textbox.component.ts` model file inside the folder `src/app/textbox` and create sample component using the below code example

{% highlight ts %}


import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/textbox/textbox.component.html',
})
export class TextboxComponent {
    locale: any;
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

N> If we import the culture before the `ej-angular2` package, we get the following error in our application. Because the `ej` instance will be registered into application after the installation of `ej-angular2` package. So, we should import the culture after the `ej-angular2` package.

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
