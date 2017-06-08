---
layout: post
title: multiple columns
description: multiple columns
platform: Angular
control: Autocomplete 
documentation: ug
---

## Multiple Columns

The Autocomplete allows list of data to be displayed in several columns and column collection can be defined and customized through the [multiColumnSettings ](http://help.syncfusion.com/api/js/ejautocomplete)property.

In AutoComplete Multiple Column search is based on [stringFormat ](http://help.syncfusion.com/api/js/ejautocomplete)property which specifies column indices.

NOTE : [stringFormat ](http://help.syncfusion.com/api/js/ejautocomplete)as “{0} ({1}) ({2})” means search based on 0, 1 and 2 columns data.

<table>
<tr>
<td>
Name</td><td>
Description</td></tr>
<tr>
<td>
multiColumnSettings.enable</td><td>
Allow list of data to be displayed in several columns.</td></tr>
<tr>
<td>
multiColumnSettings.showHeader</td><td>
Allow header text to be displayed in corresponding columns.</td></tr>
<tr>
<td>
multiColumnSettings.stringFormat</td><td>
Displayed selected value and autocomplete search is based on mentioned column value specified in that format.</td></tr>
<tr>
<td>
multiColumnSettings.columns</td><td>
Field and Header Text collections can be defined and customized through this field.</td></tr>
<tr>
<td>
multiColumnSettings.columns.field</td><td>
Get or set a value that indicates to display the columns in the autocomplete mapping with column name of the dataSource.</td></tr>
<tr>
<td>
multiColumnSettings.columns.headerText</td><td>
Get or set a value that indicates to display the title of that particular column.</td></tr>
<tr>
<td>
multiColumnSettings.columns.cssClass</td><td>
Used to set the user defined cssClass for the particular column</td></tr>
<tr>
<td>
multiColumnSettings.columns.type</td><td>
Used to define the data type for a particular column</td></tr>
<tr>
<td>
multiColumnSettings.columns.filterType</td><td>
Used to set the search filter type for the column</td></tr>
<tr>
<td>
multiColumnSettings.columns.headerTextAlign</td><td>
Used to align or position the header value in the column</td></tr>
<tr>
<td>
multiColumnSettings.columns.textAlign</td><td>
Used to align or position all the values in a column</td></tr>
</table>


{% highlight html %}


                  <input type="text" id="automulticolumn" ej-autocomplete [dataSource]="multicolumndataList" fields="multicolumnfields" watermarkText="Select a Order"
                            [highlightSearch]="true" [showPopupButton]="true" [multiColumnSettings]="multicolumncolset" width="500"/>



{% endhighlight %}





{% highlight js %}

export class AppComponent {
     multicolumndataList: Array<any>;
    multicolumncolset: Object;
    multicolumnfields: Object;
    value: string;
    constructor() {
        this.multicolumndataList = [{ 'EmployeeID': 1, 'FirstName': 'Nancy', 'City': 'Seattle' },
        { 'EmployeeID': 2, 'FirstName': 'Andrew', 'City': 'Tacoma' },
        { 'EmployeeID': 3, 'FirstName': 'Janet', 'City': 'Kirkland' },
        { 'EmployeeID': 4, 'FirstName': 'Margaret', 'City': 'Redmond' },
        { 'EmployeeID': 5, 'FirstName': 'Steven', 'City': 'London' },
        { 'EmployeeID': 6, 'FirstName': 'Michael', 'City': 'London' },
        { 'EmployeeID': 7, 'FirstName': 'Robert', 'City': 'London' },
        { 'EmployeeID': 8, 'FirstName': 'Laura', 'City': 'Seattle' },
        { 'EmployeeID': 9, 'FirstName': 'Anne', 'City': 'London' },
        { 'EmployeeID': 10, 'FirstName': 'Laura', 'City': 'Seattle' },
        { 'EmployeeID': 11, 'FirstName': 'Janet', 'City': 'Kirkland' },
        { 'EmployeeID': 12, 'FirstName': 'Michael', 'City': 'London' },
        { 'EmployeeID': 13, 'FirstName': 'Steven', 'City': 'London' },
        { 'EmployeeID': 14, 'FirstName': 'Andrew', 'City': 'Tacoma' },
        { 'EmployeeID': 15, 'FirstName': 'Robert', 'City': 'London' },
        { 'EmployeeID': 16, 'FirstName': 'Margaret', 'City': 'Redmond' },
        { 'EmployeeID': 17, 'FirstName': 'Steven', 'City': 'London' },
        { 'EmployeeID': 18, 'FirstName': 'Michael', 'City': 'London' },
        { 'EmployeeID': 19, 'FirstName': 'Robert', 'City': 'London' },
        { 'EmployeeID': 20, 'FirstName': 'Laura', 'City': 'Seattle' },
        { 'EmployeeID': 21, 'FirstName': 'Anne', 'City': 'London' },
        { 'EmployeeID': 22, 'FirstName': 'Margaret', 'City': 'London' },
        { 'EmployeeID': 23, 'FirstName': 'Andrew', 'City': 'Tacoma' },
        { 'EmployeeID': 24, 'FirstName': 'Janet', 'City': 'Kirkland' },
        { 'EmployeeID': 25, 'FirstName': 'Margaret', 'City': 'Redmond' },
        { 'EmployeeID': 26, 'FirstName': 'Steven', 'City': 'London' },
        { 'EmployeeID': 27, 'FirstName': 'Michael', 'City': 'London' },
        { 'EmployeeID': 28, 'FirstName': 'Robert', 'City': 'London' },
        { 'EmployeeID': 29, 'FirstName': 'Laura', 'City': 'Seattle' },
        { 'EmployeeID': 30, 'FirstName': 'Anne', 'City': 'London' },
        { 'EmployeeID': 31, 'FirstName': 'Margaret', 'City': 'Redmond' },
        { 'EmployeeID': 32, 'FirstName': 'Steven', 'City': 'London' }];
        this.multicolumncolset = {
            stringFormat: '{0}  ({2}) ({1})',
            enable: true,
            showHeader: true,
            columns: [
                {
                    field: 'FirstName',
                    headerText: 'FirstName'
                },
                {
                    field: 'EmployeeID',
                    headerText: 'EmployeeID'
                },
                {
                    field: 'City',
                    headerText: 'City'
                }
            ]
        };
        this.multicolumnfields = { key: 'EmployeeID', text: 'FirstName' };

    }
}

{% endhighlight %}


Run the above code to render the following output.

![](multiplecolumns_images\multiplecolumns_img1.png)

