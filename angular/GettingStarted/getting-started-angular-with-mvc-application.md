---
layout: post
title:  Getting Started Angular with MVC Application
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---
 

# Getting Started Angular with MVC Application

## Overview

To render Syncfusion Angular components in ASP .NET MVC project:

* [Prerequisites](#prerequisites)
* [Create an empty ASP DOTNET MVC Application](#create-an-empty-asp-dotnet-mvc-application)
* [Configure TypeScript configuration file](#configure-typescript-configuration-file)
* [Add NPM Configuration file for managing Angular packages](#add-npm-configuration-file-for-managing-angular-packages)
* [Gulp task Configuration](#gulp-task-configuration) (To transpile TypeScript to JavaScript). 
* [Add Syncfusion Angular seed Application](#add-syncfusion-angular-seed-application)
* [Add systemjs Configuration to load Angular core modules](#add-systemjs-configuration-to-load-angular-core-modules)
* [Add References in Layout file](#add-references-in-layout-file)
* [Run the Application](#run-the-application)

## Prerequisites

* [Node JS](https://nodejs.org/en/) ( v6.x.x or higher)
* [NPM](https://docs.npmjs.com/getting-started/installing-node#install-npm--manage-npm-versions) (v3.x.x or higher)
* Install Visual Studio 2015 Update 3
* Install TypeScript 2.2 for Visual Studio 2015

## Create an empty ASP DOTNET MVC Application

Open Visual Studio 2015 and select `ASP.NET Web Application`. Provide the name as `ESAngularMVCDemo` and select `MVC` project template.

![](/angular/GettingStarted/Images/createproject.png)

![](/angular/GettingStarted/Images/mvc.png)

## Configure TypeScript configuration file

Include TypeScript Configuration file that does the work of `transpiling TypeScript files into JavaScript files`. Create TypeScript configuration file `tsconfig.json` by right clicking `sample root folder->Add->New Item->TypeScript JSON Configuration File.`

![](/angular/GettingStarted/Images/tsconfig.png)

Copy the following code into the `tsconfig.json` file.

{% highlight javascript %}

{
  "compilerOptions": {
    "target": "es5",
    "module": "system",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false,
    "skipLibCheck": true,
    "typeRoots": [
      "node_modules/@types/"
    ],
    "types": [
      "jquery",
      "ej.web.all",
      "node",
      "es6-shim"
    ]
  },
  "exclude": [
    "node_modules",
    "deps"
  ]
}

{% endhighlight %}

## Add NPM Configuration file for managing Angular packages

Add the JSON file named as `package.json` by right clicking `sample root folder-> Add->New Item->NPM Configuration File` and copy below code into the file. The file contains Angular packages.

![](/angular/GettingStarted/Images/npmconfig.png)

{% highlight javascript %}

{
  "name": "ejangular2-systemjs-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "description": "A systemjs starter for Angular",
  "scripts": {
    "start": "concurrently \"npm run tsc:w\" \"npm run lite\" ",
    "lite": "lite-server",
    "tsc": "tsc",
    "tsc:w": "tsc -w"
  },
  "keywords": [
    "syncfusion",
    "ej",
    "essential",
    "javascript",
    "Angular",
    "Angular 2",
    "angular2"
  ],
  "author": "Syncfusion Inc",
  "license": "SEE LICENSE IN README.md",
  "bugs": {
    "url": "https://github.com/syncfusion/angular2-seeds/issues"
  },
  "homepage": "https://github.com/syncfusion/angular2-seeds#readme",
  "dependencies": {
    "@angular/common": "~5.0.0",
    "@angular/compiler": "~5.0.0",
    "@angular/core": "~5.0.0",
    "@angular/forms": "~5.0.0",
    "@angular/http": "~5.0.0",
    "@angular/platform-browser": "~5.0.0",
    "@angular/platform-browser-dynamic": "~5.0.0",
    "@angular/router": "~5.0.0",
    "@angular/upgrade": "~5.0.0",
    "core-js": "^2.4.1",
    "reflect-metadata": "^0.1.3",
    "rxjs": "5.4.2",
    "systemjs": "0.19.40",
    "zone.js": "^0.8.4",
    "angular2-in-memory-web-api": "0.0.20",
    "bootstrap": "^3.3.6",
    "jquery": "^3.1.1",
    "jsrender": "^0.9.75",
    "syncfusion-javascript": "^15.4.17",
    "ej-angular2": "^15.4.18"
  },
  "devDependencies": {
    "concurrently": "^2.0.0",
    "gulp": "^3.9.1",
    "gulp-clean": "^0.3.2",
    "gulp-typescript": "^2.13.6",
    "lite-server": "^2.1.0",
    "typescript": "~2.4.2",
    "@types/ej.web.all": "^15.4.0",
    "@types/jquery": "^3.2.12",
    "@types/es6-shim": "0.31.32",
    "@types/node": "6.0.52"
  }
}

{% endhighlight %}

Now right click the `package.json` file and choose `Restore Packages` to restore packages.

![](/angular/GettingStarted/Images/restorepackage.png) 

N> If the packages are not installed properly, open the command prompt and navigate to the location where the package.json file is defined. Run the following command to install packages.

{% highlight javascript %}
npm install
{% endhighlight %}

## Gulp task Configuration

It requires to compile TypeScript files to JavaScript file. For this process use GULP tasks that helps to compile TypeScript files to JavaScript files and then move to `Scripts` folder. 

Right Click the `ESAngularMVCDemo` project and choose `Add->New Item->Gulp Configuration File.` Name it as `gulpfile.js` in your project and copy the following code.

{% highlight javascript %}

/// <binding />
var ts = require('gulp-typescript');
var gulp = require('gulp');
var clean = require('gulp-clean');

var destPath = ['./Scripts/app/'];

// Delete the libs and app directory
gulp.task('clean', function () {
    return gulp.src(destPath)
    .pipe(clean());
});

// Transpiling TypeScript files into JavaScript.
tsProject = ts.createProject('./tsconfig.json', {
    typescript: require('typescript')
});

gulp.task('ts', function (done) {
    var tsResult = gulp.src([
            "src/**/*.ts"
    ])
        .pipe(ts(tsProject), undefined, ts.reporter.fullReporter());
    return tsResult.js.pipe(gulp.dest('./Scripts/app')); // Copying ts files to Scripts/app folder from src
});

// Watching for ts file changes
gulp.task('watch', ['watch.ts']);

gulp.task('watch.ts', ['ts'], function () {
    return gulp.watch('src/**/*.ts', ['ts']);
});


gulp.task('default', ['watch']);

{% endhighlight %}

## Add Syncfusion Angular seed Application

Copy the folder `src` from Syncfusion Angular seed application in our [GitHub repository](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and paste it in the root folder of the application. The cloned Angular seed consists of files in the following structure. 

* Grid
    * grid.component.html
    * grid.component.ts
* Home
    * home.component.html
    * home.component.ts
* app.component.html	
* app.component.ts	
* app.module.ts	
* app.routes.ts	
* main.ts

|              Files            |               Purpose                |                                       
|:------------------------------|:-------------------------------------|
|src/app.component.ts           |It is a top-level component that contains all functionalities.|
|src/app.module.ts              |It tells the angular how to construct and bootstrap the app in the root module. In our application, it bootstraps the `AppComponent` to launch the application.|
|src/main.ts              	    |The main entry point of the application, in that our application is kicked off by importing the `AppComponent` and bootstrapping it.| 
|src/app.routes.ts              |Contains routes of Angular seed application. We have two routes, home and ejGrid in our seed application.|
|src/grid/grid.component.html   |Contains template for Syncfusion Angular component (ejGrid).|
|src/grid/grid.component.ts     |Component file to render grid component. It will have data of grid.|   

## Add systemjs Configuration to load Angular core modules

The file `systemjs.config.js` is used for loading Angular files into the browser. In the existing `Scripts` folder, create `systemjs.config.js` file and copy the following code.

{% highlight javascript %}

/**
* System configuration for Angular  samples
* Adjust as necessary for your application needs.
*/
(function (global) {
    System.config({
        paths: {
            // paths serve as alias
            'npm:': 'node_modules/'
        },
        // map tells the System loader where to look for things
        map: {
            // our app is within the app folder
            app: '/Scripts',
            // angular bundles
            '@angular/core': 'npm:@angular/core/bundles/core.umd.js',
            '@angular/common': 'npm:@angular/common/bundles/common.umd.js',
            '@angular/compiler': 'npm:@angular/compiler/bundles/compiler.umd.js',
            '@angular/platform-browser': 'npm:@angular/platform-browser/bundles/platform-browser.umd.js',
            '@angular/platform-browser-dynamic': 'npm:@angular/platform-browser-dynamic/bundles/platform-browser-dynamic.umd.js',
            '@angular/http': 'npm:@angular/http/bundles/http.umd.js',
            '@angular/router': 'npm:@angular/router/bundles/router.umd.js',
            '@angular/forms': 'npm:@angular/forms/bundles/forms.umd.js',
            // other libraries
            'rxjs': 'npm:rxjs',
            'angular2-in-memory-web-api': 'npm:angular2-in-memory-web-api',
            'jquery': 'npm:jquery/dist/jquery.min.js',
            'jsrender': 'npm:jsrender/jsrender.min.js',
            'jquery-validation': 'npm:jquery-validation/dist/jquery.validate.min.js',
            'syncfusion-javascript': 'npm:syncfusion-javascript',
            'ej-angular2': 'npm:ej-angular2'
        },
        // packages tells the System loader how to load when no filename and/or no extension
        packages: {
            app: {
                main: './main.js',
                defaultExtension: 'js'
            },
            rxjs: {
                defaultExtension: 'js'
            },
            'angular2-in-memory-web-api': {
                main: './index.js',
                defaultExtension: 'js'
            },
            'ej-angular2': {
                main: './src/index.js'
            },
            'syncfusion-javascript': {
                defaultExtension: 'js'
            }
        }
    });
})(this);

{% endhighlight %}

## Add References in Layout file

To load Angular in ASP.NET MVC, include the script references of Angular core modules and Syncfusion JavaScript asset files in `_Layout file`, and load the component in `index.cshtml` like the following code snippets.

{% highlight html %}

<!-- Refer to the code for _Layout.cshtml-->
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@ViewBag.Title - My ASP.NET Application</title>
    @Styles.Render("~/Content/css")
    @Scripts.Render("~/bundles/modernizr")


    <title>Essential JavaScript for Angular | SystemJS seed</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="shortcut icon" type="image/png" href="deps/images/favicon.ico">

    <link href="node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css" rel="stylesheet" />
    <link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css">

    <!-- Polyfill(s) for older browsers -->
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>


    <!-- 2. Configure SystemJS -->
    <script src="~/Scripts/systemjs.config.js"></script>

    <!-- 2. Configure SystemJS -->
    <script>

            System.import('../Scripts/app/main')
            .then(null, console.error.bind(console));
    </script>



</head>
<body>

    <div class="container body-content">
        @RenderBody()
        <hr />
        <footer>
            <p>&copy; @DateTime.Now.Year - My ASP.NET Application</p>
        </footer>
    </div>

    @Scripts.Render("~/bundles/jquery")
    @Scripts.Render("~/bundles/bootstrap")
    @RenderSection("scripts", required: false)
</body>
</html>

{% endhighlight %}

{% highlight html %}

<!-- Refer to the code for index.cshtml-->

@{
    ViewBag.Title = "Home Page";
}
<ej-app>Loading...</ej-app>


{% endhighlight %}

## Run the Application

Run the GULP tasks, so that the Angular TypeScript files are compiled and moved to the appropriate folder (Scripts). Open the `Task Runner Explorer (View->Other Windows->Task Runner)` in Visual Studio 2015. 

![](/angular/GettingStarted/Images/taskrunner.png)

Run the default task as shown in the following screenshot.

![](/angular/GettingStarted/Images/mvcgulptask.png)

Run the task runner to compile then build and run the application to view the Syncfusion JavaScript Angular components in ASP.NET MVC application.

![](/angular/GettingStarted/Images/grid.png)
