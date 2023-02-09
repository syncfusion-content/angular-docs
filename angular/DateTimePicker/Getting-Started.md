---
layout: post
title: Getting Started | DateTimePicker | Angular | Syncfusion
description: Learn here more about Getting Started with Syncfusion Essential Angular DateTimePicker Control, its elements, and more.
platform: Angular
control: DateTimePicker
documentation: ug
---

# Getting Started with Angular DateTimePicker

This section discloses the details on how to render and configure a **DateTimePicker** component in an Angular-2 application.

To get started with **DateTimePicker** component, you need to refer the basic prerequisites and system configuration to be done form the given [getting started](https://help.syncfusion.com/Angular/overview) document.

Once you have cloned the sample Angular-2 application as mentioned in getting started document, you will have an angular application named **angular2-seeds** and the application is now ready integrate our EJ components in it. 

## Copying DateTimePicker source file

Copy the required Angular-2 source components file from the installed location and move it to **app/src/ej** folder available in the angular2-seeds folder.

{Installed Location}\Syncfusion\Essential Studio\{installed version}\JavaScript\assets-src\angular2\ 

> _Note:_ _core.ts file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49._

## Adding DateTimePicker component

1.Create a folder named "DateTimepicker" inside app folder.

2.Create a View file and name it as "DateTimepicker.component" with "html" extension and add the Datetimepicker component in it as given below. 

{% highlight html %}

<input type="text" ej-datetimepicker id="datetimepick" value="new Date()" />

{% endhighlight %} 

3.Create a Model file named "DateTimepicker.component" with "ts" extension inside "DateTimepicker" folder created in step 1.

4.Now, define the **ej-app** component and **DateTimepicker** Model class inside the Model file created in the above step.

{% highlight JS %}

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
}

{% endhighlight %}

5.To Run the application, execute the below commands in the command prompt window. 

{% highlight JS %}

npm install
npm start 

{% endhighlight %}

6.Browse the port where your application is hosted and navigate to **DateTimepicker** tab to see the output. 

![Adding DateTimePicker component](Getting-Started_images/datetime.png)

### Data Binding

To bind the model values to the **DateTimePicker** component, define the model values in the **AppComponent** class available in DateTimepicker.component.ts file as given below.

{% highlight HTML %}

<input type="text" ej-datetimepicker id="datepick" [{value}]=startDate />

{% endhighlight %}

{% highlight JS %}

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    startDate: Date;
    constructor() {
       this.startDate = new Date();
    }
}

{% endhighlight %}

## Configuring DateTimePicker

### Set minDateTime and maxDateTime

EJ **DateTimePicker** provides API through which you can set the maximum and minimum allowed date and time values.You can bind the model values to this API as shown in the below code snippet.

{% highlight HTML %}

<input type="text" ej-datetimepicker id="datepick" [minDateTime]="minDateTime" [maxDateTime]="maxDateTime" />

{% endhighlight %}

{% highlight JS %}

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    minDateTime: Date;
    maxDateTime: Date;
    constructor() {
        this.minDateTime = new Date("11/1/2016 10:00 AM");
        this.maxDateTime = new Date("11/27/2016 10:00 PM");
    }
}

{% endhighlight %}

The following screenshot illustrates the output of above code.

![Configuring DateTimePicker](getting-started_images/minmax.png) 


