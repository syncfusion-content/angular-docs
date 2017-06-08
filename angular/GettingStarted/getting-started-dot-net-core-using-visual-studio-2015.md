---
layout: post
title:  Getting Started with Angular on ASP.Net Core using Visual Studio 2015
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---
 

# Getting Started with Angular on ASP.Net Core using Visual Studio 2015

ASP.Net Core is a cross-platform framework for building applications such as web apps. Now, we are going to discuss about how to create a angular application in ASP.NET Core Environment in detailed.

## Synopsis

* [Prerequisites](#prerequisites)
* [Create Empty Application](#create-empty-application)
* [Configuration of Angular application](#configuration-of-angular-application)
* [Serve Static Files](#serve-static-files)
* [Transpile typescript files using Gulp Tasks](#transpile-typescript-files-using-gulp-tasks)
* [Configure the routes for the Router](#configure-the-routes-for-the-router)
* [Run the application](#run-the-application)

## Prerequisites

* Node.js ( v6.x.x or higher)
* Npm (v3.x.x or higher)
* Install Visual Studio 2015 Update 3
* Configure external web tools
* Install TypeScript 2.2 for Visual Studio 2015

## Create Empty Application

* Create a new ASP.NET Core project in VS2015 and select Empty as template.

![](/angular-2/GettingStarted/Images/createapp.png)

## Configuration of Angular application

* Add NPM Configuration file in Solution Explorer and restore the packages and ensure that the packages are installed properly.

Refer the below code snippet for packages used in our application.

{% highlight javascript %}

{
  "name": "ejAngular-systemjs-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/Angular-seeds.git"
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
    "Angular"
  ],
  "author": "Syncfusion Inc",
  "license": "SEE LICENSE IN README.md",
  "bugs": {
    "url": "https://github.com/syncfusion/Angular-seeds/issues"
  },
  "homepage": "https://github.com/syncfusion/Angular-seeds#readme",
  "dependencies": {
    "@angular/common": "~2.4.0",
    "@angular/compiler": "~2.4.0",
    "@angular/core": "~2.4.0",
    "@angular/forms": "~2.4.0",
    "@angular/http": "~2.4.0",
    "@angular/platform-browser": "~2.4.0",
    "@angular/platform-browser-dynamic": "~2.4.0",
    "@angular/router": "~3.4.0",
    "@angular/upgrade": "2.0.0",
    "core-js": "^2.4.1",
    "reflect-metadata": "^0.1.3",
    "rxjs": "5.0.1",
    "systemjs": "0.19.40",
    "zone.js": "^0.7.4",
    "Angular-in-memory-web-api": "0.0.20",
    "bootstrap": "^3.3.6",
    "jquery": "^3.1.1",
    "jsrender": "^0.9.75",
    "syncfusion-javascript": "^15.1.33",
    "ej-Angular": "^15.1.33",
    "@types/ej.web.all": "^14.4.1",
    "@types/jquery": "2.0.34",
    "@types/es6-shim": "0.31.32",
    "@types/node": "6.0.52"
  },
  "devDependencies": {
    "concurrently": "^2.0.0",
    "lite-server": "^2.1.0",
    "typescript": "^2.1.4",
    "gulp": "3.9.1",
    "rimraf": "^2.5.4",
    "gulp-typescript": "^3.1.2",
    "gulp-tsc": "^1.2.5",
    "@types/node": "6.0.40"
  }
}

{% endhighlight %}

![](/angular-2/GettingStarted/Images/restore.png)


![](/angular-2/GettingStarted/Images/npmpackage.png)

* Copy the `src` folder in solution from the cloned seed application. The cloned Angular-seed consists of following files.

    * app.component.ts
    * app.module.ts
    * main.ts 
    * tsconfig.json 
    * systemjs.config.js 

* Add index.html file in `wwwroot` folder

## Serve Static Files

* Add the below package in the dependencies section of project.json file.
            
            {% highlight javascript %}
            `"Microsoft.AspNetCore.StaticFiles":"1.0.0"`
            {% endhighlight %}
            
* Add the below required middleware in configure() method in startup.cs

    * app.UseDefaultFiles()
    * app.UseStaticFiles()

## Transpile typescript files using Gulp Tasks

* Add Gulp configuration file in solution

    The below table depicts the purpose of tasks in this gulpfile.js

|              Tasks            |               Purpose                |                                       
|:------------------------------|:-------------------------------------|
|default                        |The default task is used in gulp to run any number of dependent sub tasks defined in a sequential order automatically.|
|copy:lib                       |It is used to copy all libraries from node_modules to `wwwroot/lib` folder. These libraries are used to run the Angular application in ASP.Net Core environment             |
|copy:systemjs           	    |This task copy the systemjs.config.js file from `src` folder to `wwwroot` folder|  
|clean                          |A task that uses the rimraf Node deletion module to remove the library files from `wwwroot/lib` folder.|
|ts                             |It is used to transpile the typescript files into `wwwroot` folder.|
|watch.ts                       |It is used to monitor our typescript files changes. Whenever we made change on our typescript files and it will automatically transpile the changed typescript file into wwwroot.|       

The below code snippet explains the functionalities of tasks in gulp file.

{% highlight javascript %}

var ts = require('gulp-typescript');

var gulp = require('gulp'),
 rimraf = require('rimraf');

gulp.task('clean', function (cb) {
    return rimraf('./wwwroot/lib/', cb);
});

gulp.task('copy:lib', function () {
    return gulp.src('node_modules/**/*')
        .pipe(gulp.dest('./wwwroot/lib/'));
});
gulp.task('copy:systemjs', function () {
    return gulp.src('src/systemjs.config.js')
        .pipe(gulp.dest('./wwwroot/'));
});
var tsProject = ts.createProject('src/tsconfig.json', {
    typescript: require('typescript')
});
gulp.task('ts', function () {
    var tsResult = gulp.src("src/**/*.ts")
        .pipe(tsProject());

    return tsResult.js.pipe(gulp.dest('./wwwroot'));
});

gulp.task('watch', ['watch.ts']);
gulp.task('watch.ts', ['ts'], function () {
    return gulp.watch('src/**/*.ts', ['ts']);
});

gulp.task('default', ['watch']);
{% endhighlight %}
Once, you are finished with adding all Angular application files, you need to run the every gulp tasks via View->Other Windows->Task Runner Explorer.

![](/angular-2/GettingStarted/Images/gulptask.png)


N> If we run our application, we will get a following typescript error while building the application. Because the Gulp task `ts` will do the same work of typescript compiler.

![](/angular-2/GettingStarted/Images/tscerror.png)

So, we should disable the typescript compiler in our Angular environment.

* Add the following property in Property Group of `Applicationname.xproj`
        {% highlight html %}
        <TypeScriptCompileBlocked>true<\TypeScriptCompileBlocked>
        {% endhighlight %}

After adding this property, we can run our application without errors.

{% tabs %}

{% highlight ts %}
import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    template: `<div id="parent">
<ej-dialog title="Facebook" containment="#parent">
Facebook is an online social networking service headquartered in Menlo Park, California.
Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo Saverin, Andrew McCollum, Dustin Moskovitz and Chris Hughes.
The founders had initially limited the website's membership to Harvard students, but later expanded it to colleges in the Boston area, the Ivy League, and Stanford University.
It gradually added support for students at various other universities and later to high-school students.
</ej-dialog>
</div>`
})
export class AppComponent { }

{% endhighlight %}

{% highlight ts %}
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    HttpModule, EJAngularModule.forRoot()

  ],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}
{% highlight ts %}
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app.module';

platformBrowserDynamic().bootstrapModule(AppModule);
{% endhighlight %}

{% highlight javascript %}
/**
 * System configuration for Angular samples
 * Adjust as necessary for your application needs.
 */
(function (global) {
    System.config({
        paths: {
            // paths serve as alias
            'npm:': '../../lib/'
        },
        // map tells the System loader where to look for things
        map: {
            // our app is within the app folder
            app: '../../app',
            // angular bundles
            '@angular/core': 'npm:@angular/core/bundles/core.umd.js',
            '@angular/common': 'npm:@angular/common/bundles/common.umd.js',
            '@angular/compiler':
            'npm:@angular/compiler/bundles/compiler.umd.js',
            '@angular/platform-browser':
            'npm:@angular/platform-browser/bundles/platform-browser.umd.js',
            '@angular/platform-browser-dynamic':
            'npm:@angular/platform-browser-dynamic/bundles/platform-browser-dynamic.umd.js',
            '@angular/http': 'npm:@angular/http/bundles/http.umd.js',
            '@angular/router': 'npm:@angular/router/bundles/router.umd.js',
            '@angular/forms': 'npm:@angular/forms/bundles/forms.umd.js',
            '@angular/upgrade': 'npm:@angular/upgrade/bundles/upgrade.umd.js',
            // other libraries
            'rxjs': 'npm:rxjs',
            'Angular-in-memory-web-api': 'npm:Angular-in-memory-web-api',
            'ej-Angular': 'npm:ej-Angular/src'
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
            'Angular-in-memory-web-api': {
                main: './index.js',
                defaultExtension: 'js'
            },
            'ej-Angular': {
                main: './index.js'
            }
        }
    });
})(this);
{% endhighlight %}

{% highlight html %}
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
    <base href="/" />
    <title>Essential JavaScript for Angular</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="shortcut icon" type="image/png" href="deps/css/images/browser-logo.png">
    <link href="./lib/syncfusion-javascript/Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
    <link href="./lib/bootstrap/dist/css/bootstrap.min.css" rel="stylesheet">
  
    <script src="./lib/core-js/client/shim.min.js"></script>
    <script src="./lib/zone.js/dist/zone.js"></script>
    <script src="./lib/reflect-metadata/Reflect.js"></script>
    <script src="./lib/systemjs/dist/system.src.js"></script>

    <script src="./lib/jquery/dist/jquery.min.js"></script>
    <script src="./lib/jsrender/jsrender.min.js"></script>
    <script src="./lib/bootstrap/dist/js/bootstrap.min.js"></script>
    <script src="./lib/syncfusion-javascript/Scripts/ej/web/ej.web.all.min.js"></script>

    <!-- 2. Configure SystemJS -->
    <script src="./systemjs.config.js"></script>
    <script>
        System.import('app/main').catch(function (err)
        {
            console.error(err);
        });
    </script>

</head>

<!-- 3. Display the application -->

<body>
    <ej-app>Loading...</ej-app>
</body>
</html>

{% endhighlight %}

{% highlight json %}
{
  "version": "1.0.0",
  "name": "Angulardemoinasp.net",
  "dependencies": {
    "@angular/common": "~2.1.1",
    "@angular/compiler": "~2.1.1",
    "@angular/core": "~2.1.1",
    "@angular/forms": "~2.1.1",
    "@angular/http": "~2.1.1",
    "@angular/platform-browser": "~2.1.1",
    "@angular/platform-browser-dynamic": "~2.1.1",
    "@angular/router": "~3.1.1",
    "@angular/upgrade": "~2.1.1",
    "bootstrap": "3.3.7",
    "core-js": "^2.4.1",
    "reflect-metadata": "^0.1.8",
    "rxjs": "5.0.0-beta.12",
    "systemjs": "0.19.39",
    "zone.js": "^0.6.25",
    "Angular-in-memory-web-api": "0.0.21",
    "jquery": "^3.1.1",
    "jsrender": "^0.9.75",
    "syncfusion-javascript": "^14.3.49",
    "ej-Angular": "15.1.33",
    "@types/ej.web.all": "0.0.2",
    "@types/jquery": "2.0.34",
    "@types/es6-shim": "0.31.32"
  },
  "devDependencies": {
    "gulp": "3.9.1",
    "rimraf": "^2.5.4",
    "gulp-typescript": "^3.1.2",
    "typescript": "^2.0.7",
    "gulp-tsc": "^1.2.5",
    "@types/node": "6.0.40"
  }
}
{% endhighlight %}

{% highlight json %}

{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": true,
    "outDir": "../wwwroot/app",
    "types": []
  },
  "exclude": [
    "node_modules",
    "node_modues/typings",
    "typings",
    "wwwroot/lib",
    "wwwroot"
  ]
}

{% endhighlight %}

{% highlight javascript %}

var ts = require('gulp-typescript');

var gulp = require('gulp'),
 rimraf = require('rimraf');

gulp.task('clean', function (cb) {
    return rimraf('./wwwroot/lib/', cb)
});

gulp.task('copy:lib', function () {
    return gulp.src('node_modules/**/*')
        .pipe(gulp.dest('./wwwroot/lib/'));
});
gulp.task('copy:systemjs', function () {
    return gulp.src('src/systemjs.config.js')
        .pipe(gulp.dest('./wwwroot/'));
});
var tsProject = ts.createProject('src/tsconfig.json', {
    typescript: require('typescript')
});
gulp.task('ts', function () {
    var tsResult = gulp.src("src/**/*.ts")
        .pipe(tsProject());

    return tsResult.js.pipe(gulp.dest('./wwwroot'));
});

gulp.task('watch', ['watch.ts']);
gulp.task('watch.ts', ['ts'], function () {
    return gulp.watch('src/**/*.ts', ['ts']);
});

gulp.task('default', ['watch']);

{% endhighlight %}

{% endtabs %}


## Configure the routes for the Router

Before adding router configuration for above created ejDialog component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing.

* Now, we are going to configure the route navigation link for created Dialog sample in `src/app.component.html` file.

{% highlight html %}

<nav>
. . . .
<a routerLink="/dialog">Dialog</a>
</nav>
<router-outlet></router-outlet>

{% endhighlight %}
* Add below package in dependencies section of project.json file

        {% highlight javascript %}
        "Microsoft.AspNetCore.Mvc":"1.0.1"
        {% endhighlight %}

* Add below Service and middleware for routing in startup.cs
    * services.AddMvc() in ConfigureServices()
    * app.UseMvc() in Configure()

* Import the ejDialog sample component and define the route in `src/app.routes.ts` file.

{% highlight ts %}

import { Routes } from '@angular/router'; 
. . . . 
import { DialogComponent } from './dialog/dialog.component'; 
export const routes: Routes = [ 
{path: '', redirectTo: 'home', pathMatch: 'full'}, 
. . . . 
{path: 'dialog', component: DialogComponent} 
];

{% endhighlight %}

* Import and declare the ejDialog sample component into `app.module.ts` like the below code snippet.

{% highlight ts %}

import { NgModule } from '@angular/core'; 
. . . . . 
import { EJAngularModule } from 'ej-Angular'; 
import { AppComponent } from './app.component'; 
. . . . . 
import { DialogComponent } from './dialog/dialog.component'; 
import { AppRoutingModule } from './app.routes'; 
. . . . 
@NgModule({ 
imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), 
RouterModule, AppRoutingModule ], 
declarations: [. . . . , DialogComponent], 
bootstrap: [AppComponent] }) 
export class AppModule { }

{% endhighlight %}

## Run the application

* To run the application, press `Ctrl+F5`

![](/angular-2/GettingStarted/Images/output.png)
