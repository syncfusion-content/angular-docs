---
layout: post
title: Separators
description: separators
platform: Angular2
control: Menu
documentation: ug
---

# Separators

Menu can also contain separators that are horizontal bars between menu items. You cannot select a separator. Separators are somewhat similar to [borders](http://docs.oracle.com/javase/tutorial/uiswing/components/border.html), except that they are genuine components and, as such, are drawn inside a control, rather than around the edges of the **Menu** control. [enableSeparator](https://help.syncfusion.com/api/js/ejmenu#members:enableseparator) is the property that is used to display the separators in the **Menu** control. It accepts the Boolean type value. Its default value is true. 

Add the following the code sample to display the **Menu** control without separator by setting **enableSeparator** as **false**.

{% highlight html %}
    
<ej-menu id="menu" [enableSeparator]="false" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

{% endhighlight %}

{% highlight html %}

    import {Component} from '@angular/core';
    @Component({
            selector: 'sd-home',
            templateUrl: 'app/components/menu/menu.component.html'
            })
    export class MenuComponent {
            data: array;
            fieldsvalues: object;
            constructor() {
                this.data = [
                    { id: 1, text: "Home", parentId: null },
                    { id: 2, text: "Services", parentId: null },
                    { id: 3, text: "About", parentId: null },
                    { id: 4, text: "Contact us", parentId: null },
                    { id: 5, text: "Careers", parentId: null },
                    { id: 11, parentId: 1, text: "Foundation" },
                    { id: 12, parentId: 1, text: "Launch" },
                    { id: 13, parentId: 1, text: "About" },
                    { id: 14, parentId: 2, text: "Consulting" },
                    { id: 15, parentId: 2, text: "Outsourcing" },
                    { id: 16, parentId: 4, text: "Contact number" },
                    { id: 17, parentId: 4, text: "E-mail" },
                    { id: 18, parentId: 5, text: "Position" },
                    { id: 19, parentId: 5, text: "Apply online" },
                    { id: 20, parentId: 13, text: "Company" },
                    { id: 21, parentId: 13, text: "Location" },
                ];
                this.fieldsvalues = { parentId: "parentId", id: "id", text: "text" };
            }
    }

{% endhighlight %}

The following screenshot displays the output for the above code. 

![](Separators_images/Separators_img1.png)