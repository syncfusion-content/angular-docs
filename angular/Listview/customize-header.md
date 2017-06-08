---
layout: post
title: customize header
description: customize header
platform: Angular
control: ListView
documentation: ug
---

## Customize Header

In ListView component, you can enable the built-in Header support. To show or hide the Header in ListView by using showHeader property. By default, ListView is rendered with the Header. To set the title for the Header by using the headerTitle property.

In some cases, for the purpose of navigation, you may want to show the Back button text in ListView Header. To achieve this, showHeaderBackButton property is used. By default, ListView is not rendered with the header back button in parent page. To customize the text shown in ListView Header Back button, the property headerBackButtonText is used.

Refer the following code example.

{% highlight html %}

<div style="width:400px;">
    <ej-listview id="defaultlistbox" showHeader="true" headerTitle="List Items" headerBackButtonText="Menu" showHeaderBackButton="true">
        <ul>
            <li data-ej-text="Artwork">
                <ul>
                    <li data-ej-text="Canvas Art"></li>
                    <li data-ej-text="Black white"></li>
                </ul>
            </li>
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

Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Customize-Header_images/Customize-Header_img1.png](customizeheader_images\customizeheader_img1.png)

