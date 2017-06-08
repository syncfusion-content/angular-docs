---
layout: post
title: Represent the data to render the Diagram control
description: How to represent the data to render the Diagram control?
platform: Angular
control: Diagram
documentation: ug
---

# Model

The Diagram model represents the data to render the Diagram and to manipulate the Diagram elements. The following code illustrates how to define Diagram model.

{% highlight html %}

//Creates diagram
<div>
<ej-diagram  id="diagramCore" width="100%" height="490px" [pageSettings]="pageSettings">
</ej-diagram>
</div>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class ModelComponent {
    pageSettings: Object;
    constructor() {
        this.pageSettings = {
          pageWidth: 2000,
          pageHeight: 2000,
      };
  }
};

{% endhighlight %}

![](/angular-2/Diagram/Model_images/Model_img1.png)
