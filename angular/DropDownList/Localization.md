---
layout: post
title: Localization in DropDownList widget
description: Localization in DropDownList widget
platform: Angular
control: DropDownList
documentation: ug
---
# Localization

The DropDownList provides option to localize its strings, it is used to adapting the DropDownList to a particular local language. By default, the DropDownList will use the US English (en-US) as its language.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the dropdownlist’s strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the DropDownList in German language (“de-DE”).

{% highlight html %}

ej.DropDownList.Locale["de-DE"] = {
    emptyResultText: "Keine Vorschläge" //replace with your text  
};
    
{% endhighlight %}

Set the locale property of the DropDownList to the new language.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="items" [fields]="fieldsvalues" [showCheckbox]="true" [locale]="locale" [enableFilterSearch]="true" [enablePopupResize]="true"/>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	items: Array<Object>;
    fieldsvalues: Object;
    locale: string;
    constructor() {
        this.items = [{
            text: "Adams",
            value: "emp1"
        }, {
            text: "James",
            value: "emp2"
        }, {
            text: "Maria",
            value: "emp3"
        }, {
            text: "Jessica",
            value: "emp4"
        }, {
            text: "jenneth",
            value: "emp5"
        }];
        this.fieldsvalues = { dataSource: this.items, text: "text", value: "value" };
        this.locale = "de-DE";
        ej.DropDownList.Locale["de-DE"] = {
            emptyResultText: "Keine Vorschlage" //replace with your text  
        };
    }
}

{% endhighlight %}