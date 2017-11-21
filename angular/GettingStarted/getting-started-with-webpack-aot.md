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

N> We already implemented the below Ahead-of-Time Compiler configuration in our Angular Seed. To quick start with AOT,clone the seed [here](https://github.com/syncfusion/angular2-seeds/tree/webpack-aot) to render the Syncfusion Angular Components.

## Ahead-of-Time Compilation

The Angular [Ahead-of-Time (AOT) compiler](https://angular.io/guide/aot-compiler) converts your Angular HTML and TypeScript code into efficient JavaScript code during the build phase before the browser downloads and runs that code.


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

N> If you get an error like `TypeError:this.compiler.analyzeModulesAsync is not a function`, then the problem is with the mismatched versions of `@angular/compiler-cli` and `other angular packages`. So we suggest you to install `@angular/compiler-cli` package in the same version of other angular packages.

The [`@ngtools/webpack`](https://www.npmjs.com/package/@ngtools/webpack) provides AOTPlugin and loader for Webpack which shares the context with other loaders/plugins. Run the below command to install NPM package `@ngtools/webpack`.

{% highlight javascript %}
npm install @ngtools/webpack --save-dev
{% endhighlight %}

## Configure @ngtools/webpack

The below steps depicts the configuration of `` in Angular application.

* Instead of using `awesome-typescript-loader` configure `@ngtools/webpack` to compile the typescript files of the application, under rules section in `config/webpack.common.js` file.

* Add instance of `AngularCompilerPlugin`, which has an apply property. This apply property is called by the webpack compiler, giving access to the entire compilation lifecycle. Add options `tsConfigPath` and `entryModule` with `AngularCompilerPlugin` instance.

  * `tsConfigPath` - The path to the `tsconfig.json` file. In your `tsconfig.json`, you can pass options to the Angular Compiler with `angularCompilerOptions`.

  * `entryModule` - Optional if specified in `angularCompilerOptions`. The path and classname of the main application module. This follows the format `path/to/file#ClassName`.

Refer to the below configuration of `webpack.common.js` file. 

{% highlight javascript %}

var webpack = require('webpack');
. . . . .
var AngularCompilerPlugin = require('@ngtools/webpack').AngularCompilerPlugin;

module.exports = {
 

  module: {
    rules: [
      {
        test: /(?:\.ngfactory\.js|\.ngstyle\.js|\.ts)$/,
        loader: '@ngtools/webpack',
      },
      . . . . .
    ]
  },

  plugins: [
    . . . . . .

    new AngularCompilerPlugin({
      tsConfigPath: 'src/tsconfig.json',
      entryModule: 'src/app/app.module#AppModule'
    })
    . . . .
  ]
};

{% endhighlight %}


## Build the application

* To build the webpack application with Ahead-of-Time compiler, run the below command. It will create `dist` folder for production build.

{% highlight javascript %}
npm run build
{% endhighlight %}

Refer the below codes to create an application.
{% tabs %}

{% highlight ts %}

// Refer the code for app.component.ts file(src/app/app.component.ts) 

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './app.component.html',
})
export class AppComponent {
}

{% endhighlight %}

{% highlight ts %}

// Refer the code for app.module.ts file(src/app/app.module.ts) 

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouterModule } from '@angular/router';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { EJAngular2Module } from 'ej-angular2';

import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { GridComponent } from './grid/grid.component';

import { rootRouterConfig } from './app.routes';

enableProdMode();

class CustomErrorHandler implements ErrorHandler {
  call(error, stackTrace = null, reason = null) {
    console.log(error + "\n" + stackTrace);
  }
  handleError(error: any): void {
    console.log(error);
  }
}

@NgModule({
  imports: [
    BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true }), EJAngular2Module.forRoot()
  ],
  declarations: [
    AppComponent, HomeComponent, GridComponent
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight ts %}

// Refer the code for main.ts file(src/main.ts) 

import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { enableProdMode } from '@angular/core';
import { AppModule } from './app/app.module';
if (process.env.ENV === 'production') {
  enableProdMode();
}
platformBrowserDynamic().bootstrapModule(AppModule);


{% endhighlight %}

{% highlight html %}

<!-- Refer the code for app.component.html file (src/app/app.component.html)-->

<nav class="navbar navbar-default navbar-fixed-top" role="navigation">
	<div style="padding-left:0px;" class="collapse navbar-collapse" id="skeleton-navigation-navbar-collapse">
		<ul class="nav navbar-nav">
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#">Syncfusion Angular Seed</a></li>
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#home">Home</a></li>
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#grid">Grid</a></li>
		</ul>
	</div>
</nav>
<main>
	<router-outlet></router-outlet>
</main>

{% endhighlight %}

{% highlight json %}

// Refer the code for package.json file 

{
  "name": "ejangular-webpack-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "description": "A webpack starter for Angular",
  "scripts": {
    "build": "rimraf dist && webpack --config config/webpack.prod.js --progress --profile --bail",
    "ngc": "ngc -p src/tsconfig.json",
    "start": "webpack-dev-server --inline --progress --port 3000",
    "test": "karma start"
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
    "@angular/compiler-cli": "^5.0.0",
    "@angular/core": "~5.0.0",
    "@angular/forms": "~5.0.0",
    "@angular/http": "~5.0.0",
    "@angular/platform-browser": "~5.0.0",
    "@angular/platform-browser-dynamic": "~5.0.0",
    "@angular/router": "~5.0.0",
    "core-js": "^2.4.1",
    "rxjs": "^5.4.3",
    "zone.js": "^0.7.4"
  },
  "devDependencies": {
    "@ngtools/webpack": "^1.8.2",
    "css-loader": "^0.26.1",
    "extract-text-webpack-plugin": "~2.1.0",
    "file-loader": "~0.11.1",
    "html-loader": "~0.4.5",
    "html-webpack-plugin": "^2.16.1",
    "jasmine-core": "^2.4.1",
    "karma": "^1.2.0",
    "karma-jasmine": "^1.0.2",
    "karma-phantomjs-launcher": "^1.0.2",
    "karma-sourcemap-loader": "^0.3.7",
    "karma-webpack": "^1.8.0",
    "null-loader": "^0.1.1",
    "phantomjs-prebuilt": "^2.1.7",
    "protractor": "~4.0.14",
    "raw-loader": "^0.5.1",
    "rimraf": "^2.5.4",
    "style-loader": "^0.13.1",
    "typescript": "^2.4.2",
    "url-loader": "^0.5.8",
    "webpack": "~2.6.1",
    "webpack-dev-server": "~2.4.5",
    "webpack-merge": "~4.1.0",
    "bootstrap": "^3.3.6",
    "jquery": "~3.2.1",
    "jsrender": "~0.9.84",
    "syncfusion-javascript": "^15.3.29",
    "ej-angular2": "^15.3.29",
    "@types/ej.web.all": "^15.3.3",
    "@types/jquery": "^3.2.12",
    "@types/node": "^6.0.46"
  }
}

{% endhighlight %}

{% highlight ts %}

// Refer the code for app.routes.ts file(src/app/app.routes.ts)

import { Routes } from '@angular/router';
import { GridComponent } from './grid/grid.component';
import { HomeComponent } from './home/home.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    { path: 'home', component: HomeComponent },
    { path: 'grid', component: GridComponent }
];

{% endhighlight %}

{% highlight json %}

// Refer the below code for tsconfig.json(src/tsconfig.json)
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false,
    "suppressImplicitAnyIndexErrors": true,
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
  }
}
{% endhighlight %}

{% endtabs %}

## Running the application

* Now run the application with below command and navigate to [http://localhost:3000/](http://localhost:3000/) to see the output window.

{% highlight javascript %}
npm start
{% endhighlight %}

N> If you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js.`

![](/angular/GettingStarted/Images/aotoutput.png)