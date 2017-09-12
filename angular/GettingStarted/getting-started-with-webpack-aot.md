---
layout: post
title: Getting started with Webpack Ahead-of-Time Configuration
description: Overview of Syncfusion Essential Angular.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Webpack Ahead-of-Time Configuration

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}

N> The cloned application is fully configured to work with Essential Studio for JavaScript Angular components, in which we configured our [ej-angular2](https://github.com/syncfusion/ej-angular2) library and necessary changes to consume our Angular components. 

## Ahead-of-Time Compilation

The [Ahead-of-Time (AOT) compiler](https://angular.io/guide/aot-compiler) can catch template errors early and improve performance by compiling at build time.

|              AOT Compiler            |               JIT Compiler           |                                       
|:-------------------------------------|:-------------------------------------|
|The compiler runs once at build time using one set of libraries  | It runs every time for every user at runtime using a different set of libraries. |
|Speed in process                     | Late in process |

## Why do Ahead-of-Time Compilation

* Faster Rendering
* Fewer asynchronous requests
* Smaller Angular framework download size
* Detect template errors earlier
* Better security

## Configuration of Ahead-of-Time compiler in Webpack Seed

To start with the Ahead-of-Time Compiler, we need [@angular/compiler-cli](https://www.npmjs.com/package/@angular/compiler-cli) npm dependency. To install the dependency, run the below command in your application's root directory.

{% highlight javascript %}
npm install @angular/compiler-cli --save
{% endhighlight %}

It will install the ngc compiler to support the Ahead-of-Time Compilation.

N> If you get an error like `TypeError:this.compiler.analyzeModulesAsync is not a function`, then the problem is with the mismatched versions of `@angular/compiler-cli` and `other angular packages`. So we suggest you to install `@angular/compiler-cli` package in the same version of other angular packaes.

## tsconfig.json

The ngc compiler needs its own `tsconfig.json` with Ahead-of-Time compilation oriented settings. Modify the tsconfig.json file as below code snippet.

{% highlight javascript %}
{
  "compilerOptions": {
    "target": "es5",
    "module": "es2015",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false,
    "suppressImplicitAnyIndexErrors": true,
    "outDir": "./build",
    "skipLibCheck": true,
    "lib": [
      "es2015",
      "dom"
    ],
    "typeRoots": [
      "./../node_modules/@types/"
    ],
    "types": [
      "jquery",
      "ej.web.all",
      "node"
    ]
  },
  "compileOnSave": false,
  "buildOnSave": false,
  "exclude": [
    "node_modules",
    "dist",
    "src/main*.ts",
    "src/polyfills.ts",
    "src/vendor.ts"
  ],
   "awesomeTypescriptLoaderOptions": {
    "forkChecker": true,
    "useWebpackText": true
  },
  "angularCompilerOptions": {
    "genDir": ".",
    "entryModule": "src/app/app.module#AppModule"
  }
}
{% endhighlight %}

The below table depicts the purpose of `tsconfig.json` file with Ahead-of-Time compilation oriented settings.

|              Properties       |               Purpose                |                                       
|:------------------------------|:-------------------------------------|
|entryModule                    |It tells the entry point for angular-compiler.|
|gendir                         |It tells the angular-compiler to store the compiled output files in that folder.|
|skipLibCheck         	        |It skips type checking of all declaration files (*.d.ts).|

## Compiling the Application

To initiate Ahead-of-Time compilation by using the previously installed ngc compiler, run the below command in your application's root directory. Before that we need to add the NPM command `ngc` in script section of `package.json` file as below code snippet.

{% highlight javascript %}
{
  "name": "EJAngular2-webpack-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "description": "A webpack starter for Angular",
  "scripts": {
    "start": "webpack-dev-server --inline --progress --port 3000",
    "test": "karma start",
    "build:aot": "rimraf dist && webpack --config config/webpack.prod.js --progress --profile --bail",
    "ngc": "ngc -p src/tsconfig.json"
  },
  
. . .
. . .

{% endhighlight %}

Now run the below command. 

{% highlight javascript %}

npm run ngc
{% endhighlight %}

* After ngc completes, it has the collection of NgFactory files in the src folder, those factory files are essential to the compiled application. Each component factory creates an instance of the component at runtime by combining the original class file and a JavaScript representation of the component's template.

## Bootstrap the Application

* The application with Ahead-of-Time compiler will be bootstraped with the generated `AppModuleNgFactory`. To bootstrap the application, modify the `main.ts` file as below code snippet.

{% highlight javascript %}

import { platformBrowser }    from '@angular/platform-browser';
import { AppModuleNgFactory } from './app/app.module.ngfactory';
import { enableProdMode } from '@angular/core';
if (process.env.ENV === 'production') {
  enableProdMode();
}
platformBrowser().bootstrapModuleFactory(AppModuleNgFactory);

{% endhighlight %}

## Build the application

* To build the webpack application with Ahead-of-Time compiler, run the below command. It will create `dist` folder for production build.

{% highlight javascript %}
npm run build:aot
{% endhighlight %}

## Running the application

* Now run the application with below command and navigate to [http://localhost:3000/](http://localhost:3000/) to see the output window.

{% highlight javascript %}
npm start
{% endhighlight %}

N> If you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js.`

![](/angular/GettingStarted/Images/aotoutput.png)