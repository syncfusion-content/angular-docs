---
layout: post
title: Overview of Angular GroupButton
description: How to get started with Angular GroupButton?
platform: Angular
control: GroupButton
documentation: ug
---

# Getting Started

This section will explain the rendering procedure for the Angular GroupButton with the step-by-step instructions.

You can create the Angular project with the **required script and themes files** with the help of the below link:

[https://help.syncfusion.com/angular-2/overview](https://help.syncfusion.com/angular-2/overview)


## Creating a GroupButton in Angular environment

Create the GroupButton using GroupButton tag inside the body tag as like below

{% highlight html %}

    <ej-groupbutton></ej-groupbutton>

{% endhighlight %}


Create the component TS file like below to render the component.

{% highlight html %}

    import { Component, ViewEncapsulation} from '@angular/core';



    @Component({

        selector: 'ej-app',

        templateUrl: 'app/app.component.html',

    })

    export class AppComponent {



        constructor() {}

    }

{% endhighlight %}


## Model biding

DataSource for GroupButton can be set to component via model binding like below code example.
Here we have added the all required fields for GroupButton DataSource with data (inside the constructor of component)


{% highlight javascript %}

    export class AppComponent { 

    constructor() { 

    this.data = [
                { text: "Day", contentType: "textonly" },
            { text: "Week", contentType: "textonly" },
            { text: "Month", contentType: "textonly", selected: "selected" },
            { text: "Year", contentType: "textonly" }];
    }
    }


{% endhighlight %}

This dataSource need to be bounded with the GroupButton component like below




{% highlight html %}

    <ej-groupbutton [(dataSource)]="data"></ej-groupbutton>



{% endhighlight %}


## Configuring the APIs of Angular GroupButton 

All APIs of GroupButton can be configured and values can be updated from constructor. Please check with the below code example

{% highlight html %}

    <div class="content-container-fluid">
        <div class="row">

                GroupButton
                        <ej-groupbutton [(dataSource)]="data" [groupButtonMode] = "radioButton"></ej-groupbutton>

        </div>
        
    </div>



{% endhighlight %}



{% highlight html %}


        import { Component, ViewEncapsulation} from '@angular/core';

        @Component({

            selector: 'ej-app',

            templateUrl: 'app/app.component.html',

        })

        export class AppComponent {



            radioButton:string;

            constructor() {

                    this.radioButton ="radioButton";   
                    this.data = [
                { text: "Day", contentType: "textonly" },
            { text: "Week", contentType: "textonly" },
            { text: "Month", contentType: "textonly", selected: "selected" },
            { text: "Year", contentType: "textonly" }];
    
            }

        }

{% endhighlight %}




