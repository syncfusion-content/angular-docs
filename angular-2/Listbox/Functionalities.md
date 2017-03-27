---
layout: post
title: Functionalities in the ListBox component
description: Functionalities in the ListBox component
platform: angular-2
control: ListBox
documentation: ug
---
# Behavior settings

## Drag and Drop

To move the list item from one Listbox component to another ListBox by using the drag and drop support through “allowDragAndDrop” property.

{% highlight html %}

   <div class="frame">
            <div class="contents">
                <ej-listbox id="selectskills" [dataSource]="skillset" [fields]="fields" [allowDragAndDrop]="true" width="180px" height="220px"></ej-listbox>
            </div>
            <div class="contents">
                <ej-listbox id="selected" [allowDragAndDrop]="true" width="180px" height="220px"></ej-listbox>
            </div>
    </div>

{% endhighlight %}

{% highlight ts %}

export class DragAndDropComponent {
    skillset: Array<any>;
    fields: Object;
    constructor() {
        this.fields = { text: 'skill' };
        this.skillset = [
            { skill: 'ASP.NET' }, { skill: 'ActionScript' }, { skill: 'Basic' },
            { skill: 'C++' }, { skill: 'C#' }, { skill: 'dBase' }, { skill: 'Delphi' },
            { skill: 'ESPOL' }, { skill: 'F#' }, { skill: 'FoxPro' }, { skill: 'Java' },
            { skill: 'J#' }, { skill: 'Lisp' }, { skill: 'Logo' }, { skill: 'PHP' }
        ];
    }
}

{% endhighlight %}

![](Drag-and-drop_images\Drag-and-drop_img1.png)

![](Drag-and-drop_images\Drag-and-drop_img2.png)

## Reordering

To reorder the list item within the ListBox component by using “allowDragAndDrop” property.

{% highlight html %}
  
     <div id="control">
        <ej-listbox id="selectskills" [dataSource]="skillset" [fields]="fields" [allowDragAndDrop]="true" width="180px" height="220px"></ej-listbox>
    </div>	

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    skillset: Array<any>;
    fields: Object;
    constructor() {
        this.fields = { text: 'skill' };
        this.skillset = [
            { skill: 'ASP.NET' }, { skill: 'ActionScript' }, { skill: 'Basic' },
            { skill: 'C++' }, { skill: 'C#' }, { skill: 'dBase' }, { skill: 'Delphi' },
            { skill: 'ESPOL' }, { skill: 'F#' }, { skill: 'FoxPro' }, { skill: 'Java' },
            { skill: 'J#' }, { skill: 'Lisp' }, { skill: 'Logo' }, { skill: 'PHP' }
        ];
    }
}
{% endhighlight %}

![](Drag-and-drop_images\Drag-and-drop_img3.png)

![](Drag-and-drop_images\Drag-and-drop_img4.png)

N> _The item reordering can be done dynamically without mouse interaction. For that we have provided two methods “[moveUp](http://help.syncfusion.com/js/api/ejlistbox#methods:moveup)” and “[moveDown](http://help.syncfusion.com/js/api/ejlistbox#methods:movedown)”._

## Incremental Search

The [Incremental search](https://en.wikipedia.org/wiki/Incremental_search) helps to finding the specific item in the ListBox. The user types any character in ListBox component for that matched list box item will be selected by enabling the “enableIncrementalSearch”property in the ListBox component. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use [caseSensitiveSearch](https://help.syncfusion.com/api/js/ejlistbox#members:casesensitivesearch) property. 

{% highlight html %}

    <div id="control">
       <ej-listbox id="selectskills" [dataSource]="skillset" [fields]="fields" [enableIncrementalSearch]="true" width="180px" height="220px"></ej-listbox>
    </div> 

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    skillset: Array<any>;
    fields: Object;
    constructor() {
        this.fields = { text: 'fonts' };
        this.skillset = [
            { fonts: "Algerian" },
            { fonts: "ARIAL" }, { fonts: "Bimini" }, { fonts: "Courier" },
            { fonts: "Cursive" }, { fonts: "Fantasy" }, { fonts: "Georgia" }, { fonts: "Impact" },
            { fonts: "New york" }, { fonts: "Sans-Serif" }, { fonts: "Scripts" }, { fonts: "Times" },
            { fonts: "Times New Roman" }, { fonts: "Verdana" }, { fonts: "Western" }, { fonts: "Zapfellipt bt" }
        ];
        ];
    }
}

{% endhighlight %}

![](Keyboard-interaction_images\Keyboard-interaction_img1.png)

Press <kbd> tab </kbd> key to get ListBox focus and press <kbd>"C"</kbd> to get the following output.

![](Keyboard-interaction_images\Keyboard-interaction_img2.png)





