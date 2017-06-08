---
layout: post
title: Customization
description: Customization
platform: angular-2
control: ListBox
documentation: ug
---

# Customization

## Applying Rounded Corner

To use [showRoundedCorner](https://help.syncfusion.com/api/js/ejlistbox#members:showroundedcorner) property to add the rounded borders for the ListBox component. By default, showRoundedCorner property is disabled in ListBox.

{% highlight html %}

    <div id="control">
       <ej-listbox [dataSource]="data" [fields]="fieldList" [showRoundedCorner]="showroundedcorner"> </ej-listbox>
    </div>
     
{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    showroundedcorner: boolean;
    constructor() {
    this.data=[
        { empid: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { empid: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { empid: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { empid: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { empid: "cr5", text: "Dazzler", value: "Dazzler" },
        { empid: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { empid: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { empid: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { empid: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
        { empid: "cr10", text: "Acura RL", value: "Acura RL" },
        { empid: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { empid: "cr12", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    this.showroundedcorner = true;
    }
}
	
{% endhighlight %}

![](Customization_Images/rounded_corner.png)

I> The browser support details for rounded corner is given [here](http://www.w3schools.com/cssref/css3_pr_border-radius.asp).

## Enable/Disable the ListBox component

The [enabled](https://help.syncfusion.com/api/js/ejlistbox#members:enabled) property is used to indicate whether the component can respond to the user interaction or not. You can disable it by setting as false to this property. When the component as disabled state, you cannot interact with the component.

N> you can also use [enable()](https://help.syncfusion.com/api/js/ejlistbox#methods:enable)  or [disable()](https://help.syncfusion.com/api/js/ejlistbox#methods:disable) methods.

{% highlight html %}

   <div id="control">
       <ej-listbox [dataSource]="data" [fields]="fieldList" [enabled]="enabled"> </ej-listbox>
    </div>
     
{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    enabled: boolean;
    constructor() {
    this.data=[
        { empid: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { empid: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { empid: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { empid: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { empid: "cr5", text: "Dazzler", value: "Dazzler" },
        { empid: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { empid: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { empid: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { empid: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
        { empid: "cr10", text: "Acura RL", value: "Acura RL" },
        { empid: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { empid: "cr12", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    this.enabled = false;
    }
}
	
{% endhighlight %}

![](Customization_Images/disabled.png)

N> you can disable/enable the single or multiple list items by using [disableItemsByIndices](https://help.syncfusion.com/api/js/ejlistbox#methods:disableitemsbyindices) and [enableItemsByIndices](https://help.syncfusion.com/api/js/ejlistbox#methods:enableitemsbyindices) method.

