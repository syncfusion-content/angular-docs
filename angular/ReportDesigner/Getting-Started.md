---
title: Getting Started for Angular ReportDesigner
description: ReportDesigner
platform: Angular
control: ReportDesigner
documentation: ug
keywords: ejReportDesigner, ReportDesigner, js ReportDesigner
---

# Getting Started

This section explains briefly about how to integrate a **Report Designer** control in your application with **Angular**.

## Getting started with SystemJS

Run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and install required dependency packages.

{% highlight javascript %}

    > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

    > cd angular2-seeds

    > npm install

{% endhighlight %}

The following steps describe how to add report designer control with above cloned seed application:

## Report Designer control source configuration and sample creation

* Create `reportdesigner` folder inside `src` folder.

* Create `reportdesigner.component.html` view file inside `src/reportdesigner` folder and render ejReportDesigner Angular component using the below code snippet.

{% highlight html %}

<ej-reportdesigner></ej-reportdesigner>

{% endhighlight %}

* Create `reportdesigner.component.css` file inside `src/reportdesigner` folder and you can add required styles in the reportdesigner.component.css file.

{% highlight html %}

ej-reportdesigner {
    height: 550px;
    display: block;
}

{% endhighlight %}

* Create `reportdesigner.component.ts` model file inside the folder `src/reportdesigner` and create sample component using the below code snippet.

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/reportdesigner/reportdesigner.component.html',
    styleUrls: ['src/reportdesigner/reportdesigner.component.css']
})

export class ReportDesignerComponent {
        //..
}

{% endhighlight %}

## Configuring the routes for the router

* Now, we are going to configure the route navigation link for created ReportDesigner sample in `src/app.component.html` file.

{% highlight html %}

<div>
    <ul class="nav navbar-nav">
        . . . .
        <li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#reportdesigner" [routerLink]="['/reportdesigner']">ReportDesigner </a></li>
    </ul>
</div>
<main>
    <router-outlet></router-outlet>
</main>

{% endhighlight %}

* Import the ejReportDesigner sample component and define the route in `src/app.routes.ts` file.

    {% highlight javascript %}

    import { Routes } from '@angular/router';
    . . . .
    import { ReportDesignerComponent } from './reportdesigner/reportdesigner.component';

    export const rootRouterConfig: Routes = [
        { path: '', redirectTo: 'home', pathMatch: 'full' },
        . . . .
        { path: 'reportdesigner', component: ReportDesignerComponent }
    ];

    {% endhighlight %}

* Import and declare the Syncfusion source component and ejReportDesigner sample component into `app.module.ts` as shown in the below code snippet.

    {% highlight javascript %}

        import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
        . . . . . 
        import { EJAngular2Module } from 'ej-angular2';
        import { AppComponent } from './app.component';
        . . . . .
        import { ReportDesignerComponent } from './reportdesigner/reportdesigner.component';

        import { rootRouterConfig } from './app.routes';
        . . . . 
        @NgModule({
        imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
        declarations: [. . . . , ReportDesignerComponent],
        bootstrap: [AppComponent]
        })
        export class AppModule { }

    {% endhighlight %}

## Add Scripts, Styles and Control in HTML Page

Open the **index.html** file from the root path `angular2-seeds/index.html` and add the scripts and CSS references mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html>
<head> 
	<link href="node_modules/syncfusion-javascript/Content/ej/web/material/ej.reportdesigner.min.css" rel="stylesheet" />	
     <!--  code miror theme  -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.css" rel="stylesheet" />
    <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.css" rel="stylesheet" />
    <!-- Angular related script references -->
    <!-- 1. Load libraries -->
         <!-- Polyfill(s) for older browsers -->
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <!--  code miror script  -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>
    <script src="systemjs.config.js"></script>
</head>
<body>
<ej-app>
		<div class="splash">
			<div class="message">Angular Syncfusion Components App</div>
			<div class="spinner"></div>
		</div>
	</ej-app>
</body>
</html>

{% endhighlight %}

N> In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use it during deployment, as it contains all the widgets, which results in deploying large script file. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize and configure the control

1.Add the below code snippet in **reportdesigner.component.html** page.

    {% highlight html %}

    <ej-reportdesigner id="reportdesigner_Control" [serviceUrl] = "serviceUrl">
    </ej-reportdesigner>

    {% endhighlight %}

2.Open a typescript file **reportdesigner.component.ts** and add the below code snippet.

    {% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/reportdesigner/reportdesigner.component.html',
        styleUrls: ['src/reportdesigner/reportdesigner.component.css']
    })

    export class ReportDesignerComponent {
        public serviceUrl: string;  

        constructor() {
            this.serviceUrl = 'https://js.syncfusion.com/demos/ejServices/api/ReportDesigner/';        
        }
    }

    {% endhighlight %}

> In the report designer service url, need to mention the controller name of the reporting service. To create reporting service for report designer follow the steps explained in the following link [Reporting Service ](https://help.syncfusion.com/js/reportdesigner/getting-started#add-webapi-controller-for-report-designer).

## Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportDesigner** tab to view the ReportDesigner output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started-img1.png) 
