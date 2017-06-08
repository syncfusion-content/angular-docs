---
layout: post
title: Editing with Grid widget for Syncfusion Essential Angular-2
description: How to perform editing and configure edit time functionalities like edit type, edit time controls etc
platform: angular-2
control: Grid
documentation: ug
api: /api/angular2/grid
--- 
# Editing

The grid control has support for dynamic insertion, updation and deletion of records. You can start the edit action either by double clicking the particular row or by selecting the required row and clicking on Edit icon in toolbar. Similarly, you can add new record to grid either by clicking on insert icon in toolbar or on an external button which is bound to call `addRecord` method of grid. `Save` and `Cancel` while on edit mode is possible using respective toolbar icon in grid.

Deletion of the record is possible by selecting the required row and clicking on Delete icon in toolbar. 

The primary key for the data source should be defined in `e-column` definition, for editing to work properly. In `e-column` definition, particular primary column's `isPrimaryKey` property should be set to `true`. Refer the Knowledge base [link](http://www.syncfusion.com/kb/2675/cant-edit-any-row-except-the-first-row-in-grid# "link") for more information.

N> 1. In grid, the primary key column will be automatically set to read only while editing the row, but you can specify primary key column value while adding a new record.
N> 2. The column which is specified as `isIdentity` will be in readonly mode both while editing and adding a record. Also, auto incremented value is assigned to that `isIdentity` column.

## Toolbar with edit option

Using toolbar which is rendered at the top of the grid header, you can show all the CRUD related action. To enable toolbar and toolbar items, set `showToolbar` property as true and `toolbarItems`. The default toolbar items are `Add`, `Edit`, `Delete`, `Update` and `Cancel`.

N> For `toolbarItems` property you can assign either `string` value ("add") or `enum` value (`ej.Grid.ToolBarItems.Add`).

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
    </e-columns>
 </ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true};
	       this.toolbarItems = { showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img1.png)


## Cell edit type and its params

The edit type of bound column can be customized using `editType` property of `columns`. The following Essential Javascript controls are supported built-in by `editType`. You can set the `editType` based on specific data type of the column. 

* `CheckBox` control for boolean data type.
* `NumericTextBox`control for integers, double, and decimal data types.
* `InputTextBox` control for string data type.
* `DatePicker` control for date data type.
* `DateTimePicker`control for date-time data type.
* `DropDownList`control for list of data type.


And also you can define the model for all the editTypes controls while editing through `editParams` property of `columns`.

The following table describes `editType`and their corresponding `editParams` of the specific data type of the column.

<table>
<tr>
<th>
EditType</th><th>
EditParams</th><th>
Example</th></tr>
<tr>
<td>
CheckBox</td><td>
{{ '[ejCheckBox]' | markdownify }} </td><td>
editParams: { checked: true }</td></tr>
<tr>
<td>
NumericTextBox </td><td>
{{ '[ejTextBoxes]' | markdownify }} </td><td>
editParams: { decimalPlaces: 2, value:5  }</td></tr>
<tr>
<td>
InputTextBox </td><td>
-</td><td>
-</td></tr>
<tr>
<td>
DatePicker </td><td>
{{ '[ejDatePicker]' | markdownify }} </td><td>
editParams: {  buttonText : "Now" }</td></tr>
<tr>
<td>
DateTimePicker</td><td>
{{ '[ejDateTimePicker]' | markdownify }} </td><td>
editParams: {  enabled: true }</td></tr>
<tr>
<td>
DropDownList</td><td>
{{ '[ejDropDownList]' | markdownify }} </td><td>
editParams: {  allowGrouping: true }</td></tr>

</table>

N> 1. If `editType` is not set, then by default it will display the input element ("stringedit") while editing a column.
N> 2. For `editType` property you can assign either `string` value ("numericedit") or `enum` value (`ej.Grid.EditingType.Numeric`).

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"  headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit" [editParams]="{ decimalPlaces: 2}"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit" [editParams] ="{enableAnimation: true}"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
        <e-column field="Verified" headerText="Verified" editType="booleanedit" [editParams] ="{showRoundedCorner: true}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img4.png)


## Cell Edit Template

On editing the column values, custom editor can be created by using `editTemplate` property of `columns`. It has three functions, they are

1. `create` - It is used to create the control at time of initialize.
2. `read` - It is used to read the input value at time of save.
3. `write` - It is used to assign the value to control at time of editing.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCity" headerText="ShipCity" editType="dropdownedit" ></e-column>
        <e-column field="ShipPostalCode" headerText="ShipPostalCode" [editTemplate]="editTemp"></e-column>
	</e-columns>
 </ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      providers:[NorthwindService]
    })
    export class AppComponent {
        public gridData;
        public editTemp;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
           this.editTemp = {
					create : function () {
							return "<input>";
					},
					read : function (args) {
						return args.ejMaskEdit("get_UnstrippedValue");
					},
					write : function (args) {
						args.element.ejMaskEdit({
						maskFormat : "99-99-9999",
						value : args.rowdata["ShipPostalCode"]
						});
					}
				}
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img3.png)


## Edit Modes

### Inline 

Set `editMode` as `normal`, then the row itself is changed as edited row.

N> For `editMode` property you can assign either `string` value ("normal") or `enum` value (`ej.Grid.EditMode.Normal`).

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "normal" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img4.png)


### Inline Form

Set `editMode` as `inlineform`, then edit form will be inserted next to the row which is to be edited.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
 </ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "inlineform" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img4.png)


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img5.png)


### Inline Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using Inline template form, set `editMode`as `inlineformtemplate` and specify the template ID to `inlineFormTemplateID` of `editSettings`property.

While using template form, you can change the HTML elements to appropriate JS controls based on the column type. This can be achieved by using `actionComplete` event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while saving the edited record.
N> 3.  It's a standard way to enclose the `template` within the `script` tag with `type` as "text/ng-template".
N> 4.  For `editMode` property you can assign either `string` value ("inlineformtemplate") or `enum` value (`ej.Grid.EditMode.InlineTemplateForm`) 


The following code example describes the above behavior.

Place the ng-template in the "index.html" page.

{% highlight html %}

<script id="template" type="text/ng-template">
        <table cellspacing="10">
            <tr>
                <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>

{% endhighlight %}

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" (actionComplete)="onActionComplete($event)" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"  headerText="OrderID" ></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="ShipCity" headerText="ShipCity" ></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "inlineformtemplate", inlineFormTemplateID: "#template"};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
		   onActionComplete(e: any){ 
                $("#OrderDate").ejNumericTextbox();
                $("#Freight").ejNumericTextbox();
                $("#ShipCity").ejDropDownList();
            }
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img6.png)

{:caption}
Before the template elements are converted to JS controls


![](Editing_images/Editing_img7.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event 


### Dialog

Set `editMode` as `dialog` to edit data using a dialog box, which displays the fields associated with the data record being edited.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "dialog" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img8.png)


### Dialog Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using Inline template form, set `editMode` as dialogtemplate and specify the template id to `dialogEditorTemplateID` property of `editSettings`.

While using template, you can change the elements that are defined in the `template`, to appropriate JS controls based on the column type. This can be achieved by using `actionComplete`event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For [`editMode`] property you can assign either `string` value ("dialogtemplate") or `enum` value (`ej.Grid.EditMode.DialogTemplate`).

The following code example describes the above behavior.


Place the ng-template in the "index.html" page.

{% highlight html %}

<script id="template" type="text/ng-template">
        <table cellspacing="10">
            <tr>
                <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>

{% endhighlight %}

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" (actionComplete)="onActionComplete($event)" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="ShipCity" headerText="ShipCity" ></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:  "dialogtemplate", dialogEditorTemplateID : "#template"};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
		   onActionComplete(e: any){ 
                $("#OrderDate").ejNumericTextbox();
                $("#Freight").ejNumericTextbox();
                $("#ShipCity").ejDropDownList();
            }
        }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img9.png)
{:caption}
Before the template elements are converted to JS controls

![](Editing_images/Editing_img10.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event 

### External Form

By setting the `editMode` as `externalform`, the edit form is opened outside the grid content.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" [pageSettings]="pageSize">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public pageSize;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.pageSize = { pageSize:"7"};
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "externalform" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img11.png)


Form Position:

You can position an external edit form in the following two ways. 

1. Top-right
2. Bottom left

This can be achieved by setting the `formPosition` property of `editSettings` as "topright" or "bottomleft".

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" [pageSettings]="pageSize">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
   </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public pageSize;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.pageSize = { pageSize:"7"};
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "externalform",formPosition : "topright" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img12.png)


### External Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using External template form, set `editMode` as externalformtemplate and specify the template id to `externalFormTemplateID` property of `editSettings`.

While using template, you can change the elements that are defined in the template, to appropriate JS controls based on the column type. This can be achieved by using `actionComplete` event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing. 
N> 2. `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For `editMode` property you can assign either `string` value ("externalformtemplate") or `enum` value (`ej.Grid.EditMode.ExternalFormTemplate`).

The following code example describes the above behavior.

Place the ng-template in the "index.html" page.

{% highlight html %}

<script id="template" type="text/ng-template">
        <table cellspacing="10">
            <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>

{% endhighlight %}

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" (actionComplete)="onActionComplete($event)" [pageSettings]="pageSize">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="ShipCity" headerText="ShipCity" ></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public pageSize;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "externalformtemplate",externalFormTemplateID : "#template"};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
		   this.pageSize = { pageSize:"5"};
		   onActionComplete(e: any){ 
                $("#OrderDate").ejNumericTextbox();
                $("#Freight").ejNumericTextbox();
                $("#ShipCity").ejDropDownList();
            }
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img13.png)
{:caption}
Before the template elements are converted to JS controls

![](Editing_images/Editing_img14.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event

### Batch / Excel-like

Users can start editing by clicking a cell and typing data into it. Edited cell will be marked while navigating to next cell or any other row, so that you know which fields or cells has been edited. Set `editMode` as `batch` to enable batch editing.

N> Refer the KB [link](http://www.syncfusion.com/kb/3016/how-to-suppress-grid-confirmation-messages# "link") for "How to suppress grid confirmation messages" in batch mode.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode : "batch" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img15.png)


## Confirmation messages

To show the confirm dialog while saving or discarding the batch changes (discarding during the grid action like filtering, sorting and paging), set `showConfirmDialog` as `true`.

N> `showConfirmDialog` property is only for batch editing mode.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "batch",showConfirmDialog:true };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


To show delete confirm dialog while deleting a record, set `showDeleteConfirmDialog` as true.

N> `showDeleteConfirmDialog` property is for all type of `editMode`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" editType="dropdownedit"></e-column>
		<e-column field="OrderDate" headerText="OrderDate" editType="datepicker" format="{0:dd/MM/yyyy}"></e-column>
     </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,editMode : "batch", showDeleteConfirmDialog:true };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img17.png)


## Column Validation

We can validate the value of the added or edited record cell before saving.

The below validation script files are needed when editing is enabled with validation.

1. jquery.validate.min.js
2. jquery.validate.unobtrusive.min.js
 
 
### jQuery Validation


You can set validation rules using `validationRules` property of `columns`. The following are jQuery validation methods.

__List__ __of__ __Jquery__ __validation__ __methods__

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
Requires an element.</td></tr>
<tr>
<td>
remote</td><td>
Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in given value range.</td></tr>
<tr>
<td>
min</td><td>
The element requires a given minimum.</td></tr>
<tr>
<td>
max</td><td>
The element requires a given maximum.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in a given value range.</td></tr>
<tr>
<td>
email</td><td>
The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
The element requires a valid URL</td></tr>
<tr>
<td>
date</td><td>
Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
Requires the element to be the same as another.</td></tr>
</table>

Grid supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [link](http://jqueryvalidation.org/documentation/# "link") for more information.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID" [validationRules]= "{required: true, number: true }"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" [validationRules]= "{ required: true, minlength: 3 }"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit" [validationRules]= "{ range: [0, 1000]  }" ></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" ></e-column>
   </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img18.png)


## Persisting data in Server

Edited data can be persisted in database using RESTful web services. 

All the CRUD operations in grid are done through DataManager. DataManager have an option to bind all the CRUD related data in server side. Please refer the ['link'](http://help.syncfusion.com/js/datamanager/overview# "link") to know about the DataManager.

For you information ODataAdaptor persist data in server as per OData protocol.

In the below section, we have explained how to get the edited data details at the server side using URLAdaptor. 

### URL Adaptor

You can use the `UrlAdaptor` of `ejDataManger` when binding datasource from remote data. At initial load of Grid, using URL property of DataManager, data are fetched from remote data and bound to Grid. You can map CRUD operation in Grid to Server-Side Controller action using the properties `insertUrl`, `removeUrl`, `updateUrl`, `crudUrl` and `batchUrl`.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>   
	    <e-column field="Freight" headerText="Freight" editType="numericedit" format="{0:C}" ></e-column>
        <e-column field="ShipName" headerText="ShipName"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
    </e-columns>
</ej-grid> 

{% endhighlight %}

{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
      public editSettings;
      public toolbarItems;
       constructor()
        {
          public gridData = ej.DataManager({
                url : "Home/DataSource",
                adaptor : "UrlAdaptor",
                updateUrl : "Home/Update",
			    insertUrl : "Home/Insert",
			    removeUrl : "Home/Delete",
           });
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %} 
    
Also when you use `UrlAdaptor`, you need to return the data as `JSON` and the JSON object must contain a property as `result` with dataSource as its value and one more property `count` with the dataSource total records count as its value.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult DataSource(DataManager dm)
{
	IEnumerable DataSource = OrderRepository.GetAllRecords();
	DataResult result = new DataResult();
	DataOperations operation = new DataOperations();
	result.result = DataSource;
	result.count = result.result.AsQueryable().Count();
	if (dm.Skip > 0)
		result.result = operation.PerformSkip(result.result, dm.Skip);
	if (dm.Take > 0)
		result.result = operation.PerformTake(result.result, dm.Take);
	return Json(result, JsonRequestBehavior.AllowGet);
}
public class DataResult
{
	public IEnumerable result { get; set; }
	public int count { get; set; }
}
{% endhighlight %}

The grid actions (sorting, filtering, paging, searching, and aggregates) details are obtained in the 'DataManager' class. While initializing the grid, paging only enabled hence in the below screen shot paging details are bound to the DataManager class.

Please refer the below screen shot.

![](Editing_images/Editing_img20.png)


Also, using 'DataOperations' helper class you can perform grid action at server side. The in-built methods that we have provided in the DataOperations class are listed below.

1. PerformSorting
2. PerformFiltering
3. PerformSearching
4. PerformSkip
5. PerformTake
6. PerformWhereFilter
7. PerformSelect
8. Execute

### Accessing CRUD action request details in server side:

The 'Server-Side' function must be declared with the following parameter name for each editing functionality.

Parameters Table

<table>
        <tr>
            <th>
                Action
            </th>
            <th>
                Parameter Name</th>
            <th>
                Example
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Update,Insert
            </td>
            <td>
                value
            </td>
            <td rowspan="2">
                public ActionResult Update(EditableOrder value){ }
            </td>
        </tr>
        <tr>
           
            <td>
                public ActionResult Insert(EditableOrder value){ }
            </td>
        </tr>
        <tr>
            <td>
                Remove
            </td>
            <td>
                key
            </td>
            <td>
                public ActionResult Remove(int key){ }
            </td>
        </tr>
        <tr>
            <td>
                Batch Add
            </td>
            <td>
                added
            </td>
            <td rowspan="3">
                public ActionResult BatchUpdate(string action, List &lt;editableorder&gt; added, List &lt;editableorder&gt; changed, List &lt;editableorder&gt; deleted, int? key){ }
            </td>
        </tr>
        <tr>
            <td>
                Batch Update
            </td>
            <td>
                changed
            </td>
            
        </tr>
        <tr>
            <td>
                Batch Delete
            </td>
            <td>
                deleted
            </td>
           
        </tr>
        <tr>
            <td>
                Crud Update,Crud Insert
            </td>
            <td>
                value, action
            </td>
            <td>
                public ActionResult CrudUrl(EditableOrder value, string action){ }
            </td>
        </tr>
		<tr>
            <td>
                Crud Remove
            </td>
            <td>
                action, key, keyColumn
            </td>
            <td>
               public ActionResult CrudUrl(string action, int? key, string keyColumn){ }
            </td>
        </tr>
		<tr>
            <td>
               Crud Remove - Multi Delete
            </td>
            <td>
                action, key, deleted
            </td>
            <td>
               public ActionResult CrudUrl(string action, string key, List <EditableOrder> deleted){ }
            </td>
        </tr>
    </table>

	
### Insert Record:

Using `insertUrl` property, you can specify the controller action mapping URL to perform insert operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Insert(EditableOrder value)
{
	//Insert record in database
}
{% endhighlight %}

The newly added record details are bound to the 'value' parameter. Please refer the below image.


![](Editing_images/Editing_img21.png)


### Update Record:

Using `updateUrl` property, you can specify the controller action mapping URL to perform save/update operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Update(EditableOrder value)
{
	//Update record in database
}
{% endhighlight %}

The updated record details are bound to the 'value' parameter. Please refer the below image.

![](Editing_images/Editing_img22.png)


### Delete Record:

Using `removeUrl` property, you can specify the controller action mapping URL to perform delete operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Remove(int key)
{
	//Delete record in database
}
{% endhighlight %}

The deleted record primary key value is bound to the 'key' parameter. Please refer the below image.

![](Editing_images/Editing_img23.png)


### CRUD URL:

Instead of specifying separate controller action method for CRUD (insert, update and delete)operation, using `crudUrl` property you can specify the controller action mapping URL to perform all the CRUD operation at server side using single method.

The action parameter of `crudUrl` is used to get the corresponding CRUD action.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>   
	    <e-column field="Freight" headerText="Freight" editType="numericedit" format="{0:C}" ></e-column>
        <e-column field="ShipName" headerText="ShipName"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
     </e-columns>
   </ej-grid> 

{% endhighlight %}

{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
       public editSettings;
       public toolbarItems;
       constructor()
        {
          public gridData = ej.DataManager({
                url : "Home/DataSource",
                crudUrl : "Home/CrudUpdate",
			     adaptor : "UrlAdaptor"
           });
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true s};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %} 

{% highlight cs %}
public ActionResult CrudUpdate(EditableOrder value, string action)
{
	//Delete record in database
}
{% endhighlight %}

Please refer the below image to know about the action parameter

![](Editing_images/Editing_img24.png)


N> If you specify `insertUrl` along with `CrudUrl` then while adding `insertUrl` only called.

### Batch URL:

The `batchUrl` property supports only for batch editing mode. You can specify the controller action mapping URL to perform Batch operation at server side.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>   
	    <e-column field="Freight" headerText="Freight" editType="numericedit" format="{0:C}" ></e-column>
        <e-column field="ShipName" headerText="ShipName"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
     </e-columns>
   </ej-grid> 

{% endhighlight %}

{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
       public editSettings;
       public toolbarItems;
       constructor()
        {
          public gridData = ej.DataManager({
                url : "Home/DataSource",
                batchUrl : "Home/BatchUpdate",
			    adaptor : "UrlAdaptor"
           });
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"batch" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %} 


{% highlight cs %}

	public ActionResult BatchUpdate(string action, List<EditableOrder> added, List<EditableOrder> changed, List<EditableOrder> deleted, int? key)
		{
				//Save the batch changes in database
	    }

{% endhighlight %}


Please refer the below image for more information about batch parameters

![](Editing_images/Editing_img25.png)


## Adding New Row Position

To add new row in the top or bottom position of grid content, set `rowPosition` property of `editSettings` depending on the requirement.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"  headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,rowPosition : "bottom" };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img26.png)


## Render with blank row for easy add new

The blank add new row is displayed in the grid content during grid initialization itself to add a new record easily. To enable show add new row by default, set `showAddNewRow` property of `editSettings` as `true`.

The blank add new row is displayed either in the top or bottom of the corresponding page, its position is based on the `rowPosition` property of `editSettings`.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,showAddNewRow : true };
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img27.png)


N> 1. If it is remote, then the newly added record is placed based on the index from current view data. 
N> 2. If it is local, then the newly added record is added at the top of the page even if the added new `rowPosition` is mentioned as "bottom".


## Default column values on add new

While adding new record in grid, there is an option to set the default value for the columns. Using `defaultValue` property of `columns` you can set the default values for that particular column while editing or adding a new row.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [toolbarSettings]="toolbarItems" [editSettings]="editSettings" >
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true" headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCity" headerText="ShipCity" defaultValue="Bern"></e-column>
	    <e-column field="Freight" headerText="Freight" editType="numericedit" defaultValue="45"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"  defaultValue="Brazil"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public toolbarItems;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true};
	       this.toolbarItems={ showToolbar : true, toolbarItems : ["add", "edit", "delete", "update", "cancel"]};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img28.png)