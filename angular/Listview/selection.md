---
layout: post
title: selection
description: selection
platform: Angular
control: ListView
documentation: ug
---

## Selection

### MultiSelection

ListView has a checklist feature that is used to select multiple list items at the same time in the ListView. For this, set enableCheckMark property as True.

Refer the following code examples.

{% highlight html %}

<div style="width:400px;">
    <ej-listview id="defaultlistbox" showHeader="true" headerTitle="List Items" enableCheckMark="true">
        <ul>
            <li data-ej-text="Artwork"></li>
            <li data-ej-text="Abstract"></li>
            <li data-ej-text="2 Acrylic Mediums"></li>
            <li data-ej-text="Creative Acrylic"></li>
            <li data-ej-text="Modern Painting"></li>
            <li data-ej-text="Canvas Art"></li>
            <li data-ej-text="Black white"></li>
            <li data-ej-text="Children"></li>
            <li data-ej-text="Preschool Crafts"></li>
            <li data-ej-text="School-age Crafts"></li>
        </ul>
    </ej-listview>
</div>

{% endhighlight %}

Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Selection_images/multiselection_img1.png](selection_images\multiselection_img1.png)

### PreventSelection

When selecting a specific list item, it is highlighted with an active color. preventSelection property is used to prevent this behavior by setting it to True.

**NOTE**

When the click or select action is completed, the highlight is undone automatically even when the property is set to “False”.

Refer the following code examples.

{% highlight html %}

<div style="width:400px;">
    <ej-listview id="defaultlistbox" showHeader="true" headerTitle="List Items" preventSelection="true">
        <ul>
            <li data-ej-text="Artwork"></li>
            <li data-ej-text="Abstract"></li>
            <li data-ej-text="2 Acrylic Mediums"></li>
            <li data-ej-text="Creative Acrylic"></li>
            <li data-ej-text="Modern Painting"></li>
            <li data-ej-text="Canvas Art"></li>
            <li data-ej-text="Black white"></li>
            <li data-ej-text="Children"></li>
            <li data-ej-text="Preschool Crafts"></li>
            <li data-ej-text="School-age Crafts"></li>
        </ul>
    </ej-listview>
</div>

{% endhighlight %}

### PersistSelection

The persistSelection property is used to highlight the selected item in the ListView component even after touch end happens. By default, the active state is removed once the touch end happens.

Refer the following code examples.

{% highlight html %}

<div style="width:400px;">
    <ej-listview id="defaultlistbox" showHeader="true" headerTitle="List Items" persistSelection="true">
        <ul>
            <li data-ej-text="Artwork"></li>
            <li data-ej-text="Abstract"></li>
            <li data-ej-text="2 Acrylic Mediums"></li>
            <li data-ej-text="Creative Acrylic"></li>
            <li data-ej-text="Modern Painting"></li>
            <li data-ej-text="Canvas Art"></li>
            <li data-ej-text="Black white"></li>
            <li data-ej-text="Children"></li>
            <li data-ej-text="Preschool Crafts"></li>
            <li data-ej-text="School-age Crafts"></li>
        </ul>
    </ej-listview>
</div>

{% endhighlight %}

Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Selection_images/persistselection_img1.png](selection_images\persistselection_img1.png)



