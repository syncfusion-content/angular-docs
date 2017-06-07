---
layout: post
title: Behavior-settings
description: behavior settings
platform: Angular
control: Toolbar
documentation: ug
---

# Behavior settings

The following are some miscellaneous properties that enables you to change the behavior of **Toolbar** control.

## Enabling Toolbar

The **Toolbar** property [enabled](https://help.syncfusion.com/api/js/ejtoolbar#members:enabled) is used to enable or disable the **Toolbar**. Set the value to this property as **Boolean** type.

{% highlight html %}

<ej-toolbar id="toolbar" [dataSource]="data" [fields]="fieldsvalues" [width]="250" [enabled]="true"></ej-toolbar>

{% endhighlight %}

{% highlight html %}

    import {Component,ViewEncapsulation} from '@angular/core';
    import {encapsulation} from '@angular/core'; 
    @Component({
    selector: 'sd-home',
    templateUrl: 'app/components/toolbar/toolbar.component.html',
    styleUrls: ['app/components/toolbar/toolbar.component.css'],
    encapsulation: ViewEncapsulation.None
    })
    export class ToolBarComponent {
    fieldsvalues: Object;
    data: Array<Object>;
    constructor() {
        this.data = [
        {
        iconid: "1",
        spriteCss: "mailtools movetofolder",

        }, {
        iconid: "2",
        spriteCss: "mailtools categorize",

        }, {
        iconid: "3",
        spriteCss: "mailtools flag",

        }, {
        iconid: "4",
        spriteCss: "mailtools forward",

        }, {
        iconid: "5",
        spriteCss: "mailtools newmail",

        },
        {
        iconid: "6",
        spriteCss: "mailtools reply",

        },
        {
        iconid: "7",
        spriteCss: "mailtools done",

        }
        ];
        this.fieldsvalues = { id: "iconid", spriteCssClass: "spriteCss" };
    }
    }

{% endhighlight %}

Add the below css in toolbar.component.css file.

{% highlight css %}

    .e-tooltxt .mailtools {
        background-image: url('../../content/images/maild.png');
    }
    .e-tooltxt .mailtools {
        display: block;
        background-image: url('../../content/images/maill.png');
        height: 24px;
        width: 24px;
        background-repeat: no-repeat;
    }
    .e-tooltxt:hover .mailtools, .darktheme .cols-sample-area .e-tooltxt:hover .mailtools {
        background-image: url('../../content/images/mailh.png');
    }
    .mailtools.done {
        background-position: -11px -140px;
    }
    .mailtools.movetofolder {
        background-position: -12px -40px;
    }
    .mailtools.categorize {
        background-position: -14px -248px;
    }
    .mailtools.flag {
        background-position: -13px -282px;
    }
    .mailtools.forward {
        background-position: -14px -314px;
    }
    .mailtools.newmail {
        background-position: -14px -348px;
    }
    .mailtools.reply {
        background-position: -14px -388px;
    } 
    .frame {
        height: 280px;
        width: 695px;
        border-radius: none;
        margin-left: 0;
        margin-top: 40px;
        padding: 0;
    }
    .control {
        margin: 120px 200px 0;
    }

{% endhighlight %}

## Hiding Toolbar 

The **Toolbar** property [hide](https://help.syncfusion.com/api/js/ejtoolbar#members:hide) is used to show or hide the **Toolbar**. Set the value to this property as **Boolean** type.

{% highlight html %}
    
<ej-toolbar id="toolbar" [dataSource]="data" [fields]="fieldsvalues" [width]="250" [hide]="true"></ej-toolbar>

{% endhighlight %}