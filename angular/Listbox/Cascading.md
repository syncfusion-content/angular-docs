---
layout: post
title: Cascading
description: Cascading
platform: Angular
control: ListBox
documentation: ug
---

# Cascading

To dynamically populate list items to another list box while selecting the list item in list box. i.e. rendering the child list box based on the item selection in parent list box. This can be achieved by using “cascadeTo” property.

Create an ul elements to render the both parent and child ListBox components as like below.

{% highlight html %}

 <div class="frame">
     <div class="contents">
         <ej-listbox id="groupsList" [dataSource]="groups" [fields]="fields" cascadeTo="countryList"></ej-listbox>
     </div>
     <div class="contents">
        <ej-listbox id="countryList" [loadDataOnInit]="false" [dataSource]="countries"></ej-listbox>
     </div>
 </div>
        
{% endhighlight %}

The child ListBox component id should mapping to the “cascadeTo” property of the parent ListBox component. To show the empty data of the child ListBox on component initializion by setting the “loadDataOnInit” property as false.

{% highlight ts %}
            
export class CascadeComponent {
    countries: Array<any>;
    fields: Object;
    groups: Array<any>;
    constructor() {
        this.fields = { value: 'parentId' };
        this.groups = [
            { parentId: 'a', text: 'Group A' },
            { parentId: 'b', text: 'Group B' },
            { parentId: 'c', text: 'Group C' },
            { parentId: 'd', text: 'Group D' },
            { parentId: 'e', text: 'Group E' },
            { parentId: 'f', text: 'Group F' },
            { parentId: 'g', text: 'Group G' },
            { parentId: 'h', text: 'Group H' },
            { parentId: 'i', text: 'Group I' },
            { parentId: 'j', text: 'Group J' }];
        this.countries = [{ value: 11, parentId: 'a', text: 'Algeria', sprite: 'flag-dz' },
        { value: 12, parentId: 'a', text: 'Armenia', sprite: 'flag-am' },
        { value: 13, parentId: 'a', text: 'Bangladesh', sprite: 'flag-bd' },
        { value: 14, parentId: 'a', text: 'Cuba', sprite: 'flag-cu' },
        { value: 15, parentId: 'b', text: 'Denmark', sprite: 'flag-dk' },
        { value: 16, parentId: 'b', text: 'Egypt', sprite: 'flag-eg' },
        { value: 17, parentId: 'c', text: 'Finland', sprite: 'flag-fi' },
        { value: 18, parentId: 'c', text: 'India', sprite: 'flag-in' },
        { value: 19, parentId: 'c', text: 'Malaysia', sprite: 'flag-my' },
        { value: 20, parentId: 'd', text: 'New Zealand', sprite: 'flag-nz' },
        { value: 21, parentId: 'd', text: 'Norway', sprite: 'flag-no' },
        { value: 22, parentId: 'd', text: 'Poland', sprite: 'flag-pl' },
        { value: 23, parentId: 'e', text: 'Romania', sprite: 'flag-ro' },
        { value: 24, parentId: 'e', text: 'Singapore', sprite: 'flag-sg' },
        { value: 25, parentId: 'e', text: 'Thailand', sprite: 'flag-th' },
        { value: 26, parentId: 'e', text: 'Ukraine', sprite: 'flag-ua' },
        { value: 27, parentId: 'f', text: 'Falkland Islands', sprite: 'flag-ua' },
        { value: 28, parentId: 'f', text: 'Faroe Islands', sprite: 'flag-ua' },
        { value: 29, parentId: 'f', text: 'Fiji', sprite: 'flag-ua' },
        { value: 30, parentId: 'g', text: 'Germany', sprite: 'flag-ua' },
        { value: 31, parentId: 'g', text: 'Greece', sprite: 'flag-ua' },
        { value: 32, parentId: 'g', text: 'Greenland', sprite: 'flag-ua' },
        { value: 33, parentId: 'g', text: 'Ghana', sprite: 'flag-ua' },
        { value: 34, parentId: 'h', text: 'Hong Kong', sprite: 'flag-ua' },
        { value: 35, parentId: 'h', text: 'Haiti', sprite: 'flag-ua' },
        { value: 36, parentId: 'i', text: 'Iceland', sprite: 'flag-ua' },
        { value: 37, parentId: 'i', text: 'Indonesia', sprite: 'flag-ua' },
        { value: 38, parentId: 'i', text: 'Ireland', sprite: 'flag-ua' },
        { value: 39, parentId: 'j', text: 'Jamaica', sprite: 'flag-ua' },
        { value: 40, parentId: 'j', text: 'Japan', sprite: 'flag-ua' },
        { value: 41, parentId: 'j', text: 'Jordan', sprite: 'flag-ua' }];
    }
}
{% endhighlight %}

![](Cascading_images\Cascading_img1.png)

## Multilevel cascading

Refer to the following code example which is expanded from the above example, to achieve multi-level (three level here) cascading of the ListBox component.

Create an ul elements to render the parent and the child ListBox component as below.

{% highlight html %}

<div class="frame">
     <div class="contents">
        <ej-listbox id="groupsList" [dataSource]="data" [fields]="fields" cascadeTo="countryList"></ej-listbox>
     </div>
     <div class="contents">
        <ej-listbox id="countryList" [loadDataOnInit]="false" [dataSource]="firstLevelChildData" [fields]="firstchildfields" cascadeTo="productList"></ej-listbox>
     </div>
     <div class="contents">
        <ej-listbox id="productList" [loadDataOnInit]="false" [dataSource]="secondLevelChildData" [fields]="secondchildfields" cascadeTo="subproductList"></ej-listbox>
     </div>
     <div class="contents">
        <ej-listbox id="subproductList" [loadDataOnInit]="false" [dataSource]="thirdLevelChildData"></ej-listbox>
     </div>
 </div>

{% endhighlight %}

The child ListBox component id should mapping to the “cascadeTo” property of the parent ListBox component. To show the empty data of the child ListBox on component initializion by setting the “loadDataOnInit” property as false.

{% highlight ts %}

export class appComponent {
    data: Array<any>;
    firstLevelChildData: Array<any>;
    secondLevelChildData: Array<any>;
    thirdLevelChildData: Array<any>;
    fields: Object;
    firstchildfields: Object;
    secondchildfields: Object;
    groups: Array<any>;
    constructor() {
        this.data = [
            { categoryId: 'a', text: "Clothing" },
            { categoryId: 'b', text: "Furniture" }];
        this.firstLevelChildData = [{ subCategoryId: 11, categoryId: 'a', text: "Men" },
            { subCategoryId: 12, categoryId: 'a', text: "Women" },
            { subCategoryId: 13, categoryId: 'b', text: "Home furniture" },
            { subCategoryId: 14, categoryId: 'b', text: "Bedding" }];
        this.secondLevelChildData = [{ productid: 101, subCategoryId: 11, text: "men shirts" },
            { productid: 102, subCategoryId: 11, text: "men pants" },
            { productid: 103, subCategoryId: 12, text: "Women shirts" },
            { productid: 104, subCategoryId: 12, text: "Women pants" },
            { productid: 105, subCategoryId: 13, text: "sofa" },
            { productid: 106, subCategoryId: 13, text: "chairs" },
            { productid: 107, subCategoryId: 14, text: "bedsheets" },
            { productid: 108, subCategoryId: 14, text: "pillows" }];
        this.thirdLevelChildData = [{ productid: 101, text: "red men shirts" },
            { productid: 101, text: "blue men shirts" },
            { productid: 102, text: "red men pants" },
            { productid: 102, text: "blue men pants" },
            { productid: 103, text: "blueWomen shirts" },
            { productid: 103, text: "red Women shirts" },
            { productid: 104, text: "red women pants" },
            { productid: 104, text: "blue women pants" },
            { productid: 105, text: "red sofa" },
            { productid: 105, text: "blue sofa" },
            { productid: 106, text: "red chairs" },
            { productid: 106, text: "blue chairs" },
            { productid: 107, text: "red bedsheets" },
            { productid: 107, text: "blue bedsheets" },
            { productid: 108, text: "red pillows" },
            { productid: 108, text: "blue pillows" }];
        this.fields = { value: 'categoryId' };
        this.firstchildfields = { value: 'subCategoryId' };
        this.secondchildfields = { value: 'productid' };
    }
}

{% endhighlight %}

![](Cascading_images\Cascading_img2.png)