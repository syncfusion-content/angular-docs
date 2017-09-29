---
layout: post
title: Keyboard-Interaction
description: keyboard interaction
platform: Angular
control: NumericTextbox
documentation: ug
---

# Keyboard Interaction

With the keyboard navigation enabled in the **NumericTextBox** control, it is possible to control the actions of the **NumericTextBox** with the provided shortcut keys. Almost all the **NumericTextBox** actions that are done through mouse can be controlled with shortcut keys.

The various keyboard shortcuts available within the **NumericTextBox** control are discussed in the following table. 

Keyboard Shortcuts

<table>
<tr>
<th>Shortcut Key</th><th>Description</th></tr>
<tr>
<td>
<a href="http://en.wikipedia.org/wiki/Access_key">Access key</a><b> + j</b></td><td>
Focuses the control</td></tr>
<tr>
<td>
Up</td><td>
Increments the value</td></tr>
<tr>
<td>
Down</td><td>
Decrements the value</td></tr>
<tr>
<td>
Tab</td><td>
Focus the next element</td></tr>
</table>

## Configuring Keyboard Navigation

The following steps explain the implementation of keyboard interaction in **NumericTextBox** .

In the HTML page set the corresponding &lt;input&gt; elements for rendering NumericTextBox controls. Set the access key property to the NumericTextBox control for focusing the control while key is pressed.

{% highlight html %}

<input id="numeric" type="text" ej-numerictextbox [value]="value"/>
	
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/numerictextbox/numerictextbox.component.html'
})
export class NumericTextboxComponent { 
    public value: number;
    constructor() {
        this.value = 11;
    }
}

{% endhighlight %}

Run the above example and press [Access key](http://en.wikipedia.org/wiki/Access_key) **+ j** key to focus the **NumericTextBox** widget. Perform provided functionality by using keyboard shortcuts.

![](/angular/NumericTextbox/Keyboard-Interaction_images/Keyboard-Interaction_img1.png) 