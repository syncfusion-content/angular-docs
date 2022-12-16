---
layout: post
title: Getting started with Webpack in Angular Application | Syncfusion
description: Learn here all about Getting started with Webpack Ahead-of-Time Configuration in Syncfusion  Essential Angular Chart control, its elements, and more.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Webpack in Angular Application

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

N> If you get an error like `TypeError:this.compiler.analyzeModulesAsync is not a function`, then the problem is with the mismatched versions of `@angular/compiler-cli` and `other angular packages`. So we suggest you to install `@angular/compiler-cli` package in the same version of other angular packages in your application.

## Configure @ngtools/webpack package in webpack configuration

The [`@ngtools/webpack`](https://www.npmjs.com/package/@ngtools/webpack) provides AOT Plugin and loader for Webpack which shares the context with other loaders/plugins. Run the below command to install NPM package `@ngtools/webpack`.

{% highlight javascript %}
npm install @ngtools/webpack --save-dev
{% endhighlight %}

The below steps depicts the configuration of `@ngtools/webpack` in Angular application.

* `@ngtools/webpack` compiles the typescript files in application. It replaces other typescript loader like `ts-loader` or `awesome-typescript-loader.` It works with `AngularCompilerPlugin` together to enable AOT compilation.

### Options for AngularCompilerPlugin

* Add instance of [AngularCompilerPlugin](https://github.com/angular/angular-cli/tree/master/packages/%40ngtools/webpack), which has an apply property. This apply property is called by the webpack compiler, giving access to the entire compilation life cycle. Add options `tsConfigPath` and `entryModule` with `AngularCompilerPlugin` instance.

  * `tsConfigPath` - The path to the `tsconfig.json` file. In your `tsconfig.json`, you can pass options to the Angular Compiler with `angularCompilerOptions`.

  * `entryModule` - Optional if specified in `angularCompilerOptions`. The path and classname of the main application module. This follows the format `path/to/file#ClassName`.

N> To know more about Options in AOT refer [here](https://github.com/angular/angular-cli/tree/master/packages/%40ngtools/webpack)

Refer to the below AOT configuration code snippet for `config/webpack.dev.js` file. 

{% highlight javascript %}

var helpers = require('./helpers');
const fs = require('fs');
const path = require('path');
const ProgressPlugin = require('webpack/lib/ProgressPlugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const rxPaths = require('rxjs/_esm5/path-mapping');
var webpack = require('webpack');
const { NoEmitOnErrorsPlugin, SourceMapDevToolPlugin, NamedModulesPlugin } = require('webpack');
const { CommonsChunkPlugin } = require('webpack').optimize;
var ExtractTextPlugin = require('extract-text-webpack-plugin');
const nodeModules = path.join(process.cwd(), 'node_modules');
const realNodeModules = fs.realpathSync(nodeModules);
const genDirNodeModules = path.join(process.cwd(), 'src', '$$_gendir', 'node_modules');
const entryPoints = ["inline", "polyfills", "sw-register", "styles", "vendor", "main"];
const { AngularCompilerPlugin } = require('@ngtools/webpack');
module.exports = {
    // devtool: 'source-map',
    "resolve": {
        "extensions": [
            ".ts",
            ".js"
        ],
        alias: {
            jquery: "jquery/src/jquery"
        },
        "modules": [
            "./node_modules",
            "./node_modules"
        ],
        "symlinks": true,
        "mainFields": [
            "browser",
            "module",
            "main"
        ]
    },
    "resolveLoader": {
        "modules": [
            "./node_modules",
            "./node_modules"
        ],
        "alias": rxPaths()
    },
    "entry": {
        "main": [
            "./src\\main.ts"
        ],
        "polyfills": [
            "./src\\polyfills.ts"
        ],
        "vendor": [
            "./src\\vendor.ts"
        ]
    },
    "output": {
        "path": path.join(process.cwd(), "dist"),
        "filename": "[name].bundle.js",
        "chunkFilename": "[id].chunk.js",
        "crossOriginLoading": false
    },
    "module": { 
        "rules": [
            {
                "test": /\.ts$/,
                "loader": "@ngtools/webpack"
            },
            {
                "test": /\.html$/,
                "loader": "raw-loader"
            },
            {
                "test": /\.(eot|svg|cur)$/,
                "loader": "file-loader",
                "options": {
                    "name": "[name].[hash:20].[ext]",
                    "limit": 10000
                }
            },
            {
                "test": /\.(jpg|png|webp|gif|otf|ttf|woff|woff2|ani)$/,
                "loader": "url-loader",
                "options": {
                    "name": "[name].[hash:20].[ext]",
                    "limit": 10000
                }
            },
            {
                test: /\.css$/,
                exclude: helpers.root('src', 'app'),
                loader: ExtractTextPlugin.extract({ fallback: 'style-loader', loader: 'css-loader?sourceMap' })
            },
            {
                test: /\.css$/,
                include: helpers.root('src', 'app'),
                loader: 'raw-loader'
            }
        ]
    },
    "plugins": [
        new NoEmitOnErrorsPlugin(),
        new ExtractTextPlugin('[name].css'),
        new HtmlWebpackPlugin({
            "template": "./src\\index.html",
            "filename": "./index.html",
            "hash": false,
            "inject": true,
            "compile": true,
            "favicon": false,
            "minify": false,
            "cache": true,
            "showErrors": true,
            "chunks": "all",
            "excludeChunks": [],
            "title": "Webpack App",
            "xhtml": true,
            "chunksSortMode": function sort(left, right) {
                let leftIndex = entryPoints.indexOf(left.names[0]);
                let rightindex = entryPoints.indexOf(right.names[0]);
                if (leftIndex > rightindex) {
                    return 1;
                }
                else if (leftIndex < rightindex) {
                    return -1;
                }
                else {
                    return 0;
                }
            }
        }),
        new CommonsChunkPlugin({
            "name": [
                "inline"
            ],
            "minChunks": null
        }),
        new CommonsChunkPlugin({
            "name": [
                "vendor"
            ],
            "minChunks": (module) => {
                return module.resource
                    && (module.resource.startsWith(nodeModules)
                        || module.resource.startsWith(genDirNodeModules)
                        || module.resource.startsWith(realNodeModules));
            },
            "chunks": [
                "main"
            ]
        }),
        new SourceMapDevToolPlugin({
            "filename": "[file].map[query]",
            "moduleFilenameTemplate": "[resource-path]",
            "fallbackModuleFilenameTemplate": "[resource-path]?[hash]",
            "sourceRoot": "webpack:///"
        }),
        new CommonsChunkPlugin({
            "name": [
                "main"
            ],
            "minChunks": 2,
            "async": "common"
        }),
        new NamedModulesPlugin({}),
        new webpack.HotModuleReplacementPlugin(),
        new AngularCompilerPlugin({
            "mainPath": "main.ts",
            "platform": 0,
            "sourceMap": true,
            "tsConfigPath": "src\\tsconfig.json",
            "skipCodeGeneration": true,
            "compilerOptions": {}
          })
    ],
    "node": {
        "fs": "empty",
        "global": true,
        "crypto": "empty",
        "tls": "empty",
        "net": "empty",
        "process": true,
        "module": false,
        "clearImmediate": false,
        "setImmediate": false
    },
    "devServer": {
        "historyApiFallback": true
    }
};

{% endhighlight %}

* Refer to the below AOT Production build configuration in `config/webpack.prod.js`.

{% highlight javascript %}
var webpack = require('webpack');
var ExtractTextPlugin = require('extract-text-webpack-plugin');
var helpers = require('./helpers');
var HtmlWebpackPlugin = require('html-webpack-plugin');
var path = require('path');
const { AngularCompilerPlugin } = require('@ngtools/webpack');
const ENV = process.env.NODE_ENV = process.env.ENV = 'production';

module.exports =  {
  devtool: 'source-map',
  entry: {
    'polyfills': './src/polyfills.ts',
    'vendor': './src/vendor.ts',
    'app': './src/main.ts'
  },

  resolve: {
    extensions: ['.ts', '.js'],
     alias: {
            jquery: "jquery/src/jquery"
        }
  },
  output: {
    path: helpers.root('dist'),
    publicPath: '',
    filename: '[name].[hash].js',
    chunkFilename: '[id].[hash].chunk.js'
  },
  module: {
    rules: [
      {
        "test": /\.ts$/,
        "loader": "@ngtools/webpack"
      },
      {
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        test: /\.(png|jpe?g|gif|cur|svg|woff|woff2|ttf|eot|ico)$/,
        loader: 'file-loader?name=assets/[name].[hash].[ext]'
      },
      {
        test: /\.css$/,
        exclude: helpers.root('src', 'app'),
        loader: ExtractTextPlugin.extract({ fallback: 'style-loader', loader: 'css-loader?sourceMap' })
      },
      {
        test: /\.css$/,
        include: helpers.root('src', 'app'),
        loader: 'raw-loader'
      }
    ]
  },
  plugins: [
    // Workaround for angular/angular#11580
    new webpack.ContextReplacementPlugin(
      /angular(\\|\/)core(\\|\/)@angular/,
      path.resolve(__dirname, '../src')
    ),

    new webpack.optimize.CommonsChunkPlugin({
      name: ['app', 'vendor', 'polyfills']
    }),

    new HtmlWebpackPlugin({
      template: 'src/index.html'
    }),
    new webpack.NoEmitOnErrorsPlugin(),
    new webpack.optimize.UglifyJsPlugin({ // https://github.com/angular/angular/issues/10618
      mangle: {
        keep_fnames: true
      }
    }),
    new ExtractTextPlugin('[name].[hash].css'),
    new webpack.DefinePlugin({
      'process.env': {
        'ENV': JSON.stringify(ENV)
      }
    }),
    new webpack.LoaderOptionsPlugin({
      htmlLoader: {
        minimize: false // workaround for ng2
      }
    }),
    new AngularCompilerPlugin({
      "mainPath": "main.ts",
      "platform": 0,
      "sourceMap": true,
      "tsConfigPath": "src\\tsconfig.json",
      "skipCodeGeneration": true,
      "compilerOptions": {}
    })
  ]
};

{% endhighlight %}

## Import Require Component in Root Module

* To render Syncfusion Angular Components, import required components in `app.module.ts` file. Refer to the below code snippet for root module file.

{% highlight ts %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouterModule } from '@angular/router';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { EJ_GRID_COMPONENTS } from 'ej-angular2/src/ej/grid.component';

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
    BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })
  ],
  declarations: [
    AppComponent, HomeComponent, GridComponent, EJ_GRID_COMPONENTS
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }

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

import { EJ_GRID_COMPONENTS } from 'ej-angular2/src/ej/grid.component';

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
    BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })
  ],
  declarations: [
    AppComponent, HomeComponent, GridComponent, EJ_GRID_COMPONENTS
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
    "start": "webpack-dev-server --inline --progress --port 3000",
    "test": "karma start",
    "build": "rimraf dist && webpack --config config/webpack.prod.js --progress --profile --bail"
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
    "@angular/common": "~5.1.2",
    "@angular/compiler": "~5.1.2",
    "@angular/compiler-cli": "~5.1.2",
    "@angular/core": "~5.1.2",
    "@angular/forms": "~5.1.2",
    "@angular/http": "~5.1.2",
    "@angular/platform-browser": "~5.1.2",
    "@angular/platform-browser-dynamic": "~5.1.2",
    "@angular/router": "~5.1.2",
    "core-js": "^2.4.1",
    "rxjs": "^5.4.3",
    "zone.js": "^0.7.4",
    "bootstrap": "^3.3.6",
    "jquery": "~3.2.1",
    "jsrender": "~0.9.84",
    "syncfusion-javascript": "^15.4.17",
    "ej-angular2": "^15.4.18"
  },
  "devDependencies": {
    "@ngtools/webpack": "^1.9.3",
    "angular2-template-loader": "~0.6.2",
    "awesome-typescript-loader": "~3.1.3",
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
    "typescript": "~2.4.2",
    "url-loader": "^0.5.8",
    "webpack": "~2.6.1",
    "webpack-dev-server": "~2.4.5",
    "@types/ej.web.all": "^15.4.0",
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

![Running the Application in Angular Chart ](GettingStarted/Images/aotoutput.png)