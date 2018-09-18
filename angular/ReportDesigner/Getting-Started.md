---
title: Getting Started for Angular ReportDesigner
description: ReportDesigner
platform: Angular
control: ReportDesigner
documentation: ug
keywords: ejReportDesigner, ReportDesigner, js ReportDesigner
---

# Getting Started

Before we start with the ReportDesigner, please refer [this page](https://help.syncfusion.com/angular-2/overview) for general information regarding integrating Syncfusion widget’s.

# Getting started with Webpack

Run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and install required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install

{% endhighlight %}

The following steps describe how to add report designer control with above cloned seed application:

## Report Designer control source configuration and sample creation

* Create a folder named `ej` inside the `angular2-seeds/src` folder.

* Copy the report designer **reportdesigner.component.ts**  and `core.ts` file from the build location specified below and paste it in `src/ej` folder.

    {% highlight javascript %}

    (Installed Location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\

    {% endhighlight %}

    N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components

* Create `ReportDesigner` folder inside `src` folder.

* Create `ReportDesigner.component.html` view file inside `src/ReportDesigner` folder and render ejReportDesigner Angular component using the below code snippet.

    {% highlight html %}

    <ej-reportdesigner></ej-reportdesigner>

    {% endhighlight %}

* Create `ReportDesigner.component.ts` model file inside the folder `src/ReportDesigner` and create sample component using the below code snippet.

    {% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/ReportDesigner/ReportDesigner.component.html',
        styleUrls: ['src/ReportDesigner/ReportDesigner.component.css']
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
                <li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#ReportDesigner" [routerLink]="['/ReportDesigner']">ReportDesigner </a></li>
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
    import { ReportDesignerComponent } from './ReportDesigner/ReportDesigner.component';

    export const rootRouterConfig: Routes = [
        { path: '', redirectTo: 'home', pathMatch: 'full' },
        . . . .
        { path: 'ReportDesigner', component: ReportDesignerComponent }
    ];

    {% endhighlight %}

* Import and declare the Syncfusion source component and ejReportDesigner sample component into `app.module.ts` as shown in the below code snippet.

    {% highlight javascript %}

    import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
    . . . . .
    import { ReportDesignerComponent } from './ReportDesigner/ReportDesigner.component';

    import { rootRouterConfig } from './app.routes';
    . . . .
    @NgModule({
    imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
    declarations: [. . . . , EJ_REPORTDESIGNER_COMPONENTS,ReportDesignerComponent],
    bootstrap: [AppComponent]
    })
    export class AppModule { }

    {% endhighlight %}

## Add Scripts, Styles and Control in HTML Page

Open the **ReportDesigner.component.html** page and add the scripts and CSS references mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html>
<head> 
    <!-- theme reference -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.reportdesigner.min.css" rel="stylesheet" />
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
    <!--  jquery script  -->
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
    <!--  code miror script  -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>
    <!-- Essential JS UI widget -->
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.reportdesigner.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    <script src="systemjs.config.js"></script>
</head>
<body>
<ej-app>Loading...</ej-app>
</body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use it during deployment, as it contains all the widgets, which results in deploying large script file. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize and configure the control

1. Add the below code snippet in body tag of **ReportDesigner.component.html** page.

    {% highlight html %}

    <body>
    <ej-reportdesigner id="reportdesigner_Control" [serviceUrl] = "serviceUrl">
    </ej-reportdesigner>

    <style>
    ej-reportdesigner {
        display: block;
        height: 550px;
    }
    </style>
    </body>

    {% endhighlight %}

2. Open a typescript file **ReportDesigner.component.ts** and add the below code snippet.

    {% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/ReportDesigner/ReportDesigner.component.html',
        styleUrls: ['src/ReportDesigner/ReportDesigner.component.css']
    })

    export class ReportDesignerComponent {
        public serviceUrl: string;  

        constructor() {
            this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/ReportDesigner';        
        }
    }

    {% endhighlight %}

## Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportDesigner** tab to view the ReportDesigner output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started-img1.png) 
