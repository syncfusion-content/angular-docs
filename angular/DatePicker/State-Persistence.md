---
layout: post
title: State Persistence
description: DatePicker - State persistence properties 
platform: Angular
control: DatePicker
documentation: ug
---
# State Persistence

You can sustain the entire widget model of DatePicker even after form post or browser refresh by using enablePersistence property. So the entire model values such as 

* Selected date
* Highlighted date
* Start and depth level 

are stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.


{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value" [(enablePersistence)]="persistence"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  rtl: boolean;
  persistence: boolean;
  constructor() {
    this.value = Date();
    this.persistence = true;
  }
}

{% endhighlight %}