---
layout: post
title: Miscellaneous
description: miscellaneous
platform: Angular
control: ColorPicker
documentation: Ug
---

# Miscellaneous

## getValue

The **getValue**() method in **ColorPicker** returns the hexadecimal value.

In the **HTML** page, add a **&lt;input&gt;** element to render **ColorPicker** widget

{% highlight html %}

    <div align="center">
    <input id="picker" ej-colorpicker (open)="onOpen($event)"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
  value: string;
  onOpen(args) {
      $('#picker').ejColorPicker({ value: "#278787" });
      alert($("#picker").ejColorPicker("getValue"));
  }
}

{% endhighlight %}

## setValue

The **setValue**() method in **ColorPicker** is used to set the color value. The given value is in hexadecimal form.

In the **HTML** page, add a **&lt;input&gt;** element to render **ColorPicker** widget

{% highlight html %}

    <div align="center">
    <input id="picker" ej-colorpicker (open)="onOpen($event)"/>
    </div> 

{% endhighlight %}

{% highlight html %}
 
import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
  value: string;
  onOpen(args) {
      var colorObj = $("#picker").data("ejColorPicker");
      var color = colorObj.setValue("#278787");
      alert("color");
  }
}

{% endhighlight %}

## getColor

The **getColor**() method in **ColorPicker** control returns the color value in r,g,b,a form.

In the **HTML** page, add a **&lt;input&gt;** element to render **ColorPicker** widget

{% highlight html %}

    <div align="center">
    <input id="picker" ej-colorpicker (open)="onOpen($event)"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
  value: string;
  onOpen(args) {
      var colorObj = $("#picker").data("ejColorPicker");
      var color = colorObj.getColor();
      alert("Red=" + color.r + ", Green=" + color.g + ", Blue=" + color.b);
  }
}

{% endhighlight %}
