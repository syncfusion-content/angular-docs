---
layout: post
title: Miscellaneous
description: miscellaneous
platform: Angular2
control: Menu
documentation: ug
---

# Miscellaneous

## Height

Specifies the height of the root menu. You can customize the height of the **Menu** control by using [height](https://help.syncfusion.com/api/js/ejmenu#members:height) property. 

You can specify the height of the **Menu** control as shown below.

{% highlight html %}

    <ej-menu id="menu" [height]="50"></ej-menu>

{% endhighlight %}

## Width

Specifies the width of the main menu. You can customize the width of the **Menu** control by using [width](https://help.syncfusion.com/api/js/ejmenu#members:width) property.

You can specify the width of the **Menu** control as shown below.

{% highlight html %}

    <ej-menu id="menu" [width]="700"></ej-menu>

{% endhighlight %}

## Open on click

Specifies the sub menu items to be show or open only on click. It accepts the Boolean value. Its default value is false. If we set [openOnClick](https://help.syncfusion.com/api/js/ejmenu#members:openonclick) property to true then the submenu items will open only on click. By default the submenu will open when we hover on menu items.

Add the following code in order to show the menu items only on click. 

{% highlight html %}

    <ej-menu id="menu" [fields.dataSource]="data" [fields]="fieldsvalues" [width]="612" [openOnClick]="true"></ej-menu>

{% endhighlight %}

Output screenshot for the above code example is as follows.

![](Miscellaneous_images/Miscellaneous_img1.png)


## Animation

[**AnimationType**](https://help.syncfusion.com/api/js/ejmenu#members:animationtype) is used to enable or disable the Animation when hover or click on menu items. Its value type is string. It accepts two values such as "none" and "default". Support to disable the **AnimationType** when hover or click on menu items is none. Support to enable the Animation Type when hover or click on menu items is default. 

Add the following code to render menu using animation type. 

{% highlight html %}

  <ej-menu id="menu" [animationType]="type" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

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
            type: any;
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
                this.type = ej.AnimationType.Default;
            }
    }

{% endhighlight %}

Output screenshot for the above code sample is as follows.

![](Miscellaneous_images/Miscellaneous_img2.png)


## Title text

Specifies the title to the responsive menu. You can provide title to the **Menu** control by using [titleText](https://help.syncfusion.com/api/js/ejmenu#members:titletext) property. 

You can specify the title of the **Menu** control as follows.

{% highlight html %}

    <ej-menu id="menu" titleText="title" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

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
            title: string;
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
                this.title = "Title of the Menu";
            }
    }

{% endhighlight %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img3.png)


## Show root level arrows

Specifies the main menu item arrows to display only when it contains child menu items. You can use “**showRootLevelArrows**” property to display the arrows of main menu items only when it contains child menu items. This property accepts Boolean value. Its default value is true. 

Refer to the below code example.

{% highlight html %}

    <ej-menu id="menu" [showRootLevelArrows]="false" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

{% endhighlight %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img4.png)


## Show sub level arrows

Specifies the sub menu items arrows to display only when it contains child menu items. You can use [showSubLevelArrows](https://help.syncfusion.com/api/js/ejmenu#members:showsublevelarrows) property to show the arrows of sub menu items only when it contains child menu items. This property accepts Boolean value. Its default value is true. 

Refer to the below code example.

{% highlight html %}

    <ej-menu id="menu" [showSubLevelArrows]="false" [fields.dataSource]="data" [fields]="fieldsvalues"></ej-menu>

{% endhighlight %}

The following screenshot displays the output of the above code.

![](Miscellaneous_images/Miscellaneous_img5.png)