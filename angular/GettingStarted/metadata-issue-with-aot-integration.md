---
layout: post
title: How to - Resolving issue with AOT integration?
description: FAQ.
platform: Angular
control: Introduction
documentation: ug
---
 
# Metadata version mismatch issue with AOT integration
 
To resolve issue `Metadata version mismatch for module ***/node_modules/ej-angular2/src/ej/core.d.ts, found version 4, expected 3` we recommended to upgrade NPM package [ej-angular2](https://www.npmjs.com/package/ej-angular2) to the latest version `15.4.18`. Run the below command to install latest `ej-angular2` package.
 
{% highlight javascript %}
npm install ej-angular2 --save
{% endhighlight %} 
