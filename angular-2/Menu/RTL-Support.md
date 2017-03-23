---
layout: post
title: RTL-Support
description: rtl support
platform: Angular2
control: Menu
documentation: ug
---

# RTL Support

The [enableRTL](https://help.syncfusion.com/api/js/ejmenu#members:enablertl) property allows the **Menu** control to display it in the right to left direction. By default, this property is set to "false" in the **Menu** control.

The following code depicts you on how to enable the **rtl** property of the **Menu** control.

{% highlight html %}

<ej-menu id="menu" [enableRTL]="true" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

{% endhighlight %}

{% highlight html %}

    import {Component} from '@angular/core';
    @Component({
            selector: 'sd-home',
            templateUrl: 'app/components/menu/menu.component.html'
            })
    export class MenuComponent {
            data: Array<Object>;
            fieldsvalues: Object;
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

Following screenshot displays the output for the above code.

![](RTL-Support_images/RTL-Support_img1.png)