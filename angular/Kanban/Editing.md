---
layout: post
title:  Editing
description: Editing
documentation: ug
platform: Angular
keywords: editing,kanban editing
---

# Editing

The Kanban control has support for dynamic insertion, updating and deletion of cards. 

Set [`editSettings.allowEditing`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-allowediting) and [`editSettings.allowAdding`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-allowadding) property as true to enable editing/inserting respectively. The primary key for the data source should be defined in [`fields.primaryKey`](https://help.syncfusion.com/api/js/ejkanban#members:primarykey), for editing to work properly. 

You can start the edit action by double clicking the particular card. Similarly, you can add new card to Kanban either by double clicking the particular cell or on an external button which is bound to call [`addCard`](https://help.syncfusion.com/api/js/ejkanban#methods:kanbanedit-addcard) method of Kanban. 

Deletion of the card is possible by using [`deleteCard`](https://help.syncfusion.com/api/js/ejkanban#methods:kanbanedit-deletecard) by passing primary key as attribute.

N> In Kanban, the `primary key` column will be automatically set to `read only` while editing the card which is to avoid duplicate entry in the cards.

## Configuring Edit Items

You need to configure the list of data source fields that are allowable in editing state using [`editSettings.editItems`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems) property. The [`field`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-field) property of [`editSettings.editItems`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems) needs to be mapped with data source fields.

You can map the data source field as title to edit form using [`fields.title`](https://help.syncfusion.com/api/js/ejkanban#members:fields-title) property of `fields`. By default, it’s mapped with `primaryKey`.

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" [editSettings.editItems]="editItem" editSettings.allowEditing="true" editSettings.allowAdding="true" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headertext="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headertext="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headertext="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(20);
        this.editItem = [
            { field: 'Id' },
            { field: 'Status', editType: ej.Kanban.EditingType.Dropdown },
            { field: 'Assignee', editType: ej.Kanban.EditingType.Dropdown },
            { field: 'Estimate', editType: ej.Kanban.EditingType.Numeric, editParams: { decimalPlaces: 2 } },
            { field: 'Summary', editType: ej.Kanban.EditingType.TextArea, editParams: { height: 100, width: 200 } }
        ];
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img1.png)

## Edit modes

### Dialog

Set [`editSettings.editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) as `dialog` to edit data using a dialog box, which displays the fields associated with the data card being edited. Default value is `dialog`.

N> For [`editSettings.editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) property you can assign either `string` value (“dialog").

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" [editSettings.editItems]="editItem" editSettings.allowEditing="true" editSettings.allowAdding="true" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headertext="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headertext="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headertext="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(20);
        this.editItem = [
            { field: 'Id' },
            { field: 'Status', editType: ej.Kanban.EditingType.Dropdown },
            { field: 'Assignee', editType: ej.Kanban.EditingType.Dropdown },
            { field: 'Estimate', editType: ej.Kanban.EditingType.Numeric, editParams: { decimalPlaces: 2 } },
            { field: 'Summary', editType: ej.Kanban.EditingType.TextArea }
        ];
    }
}
   
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img2.png)

### Dialog Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later. 

Using this template support, you can edit the fields that are not bound to [`editItems`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems).

To edit the cards using Dialog template form, set [`editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) as `dialogTemplate` and specify the template id to [`dialogTemplate`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-dialogtemplate) property of [`editSettings`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings).

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while save the edited card.
N> 3.  For [`editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) property you can assign `string` value `dialogTemplate`.

The following code example describes the above behavior.

Place the ng-template in the "index.html" page.

{% highlight html %}

     <script id="template" type="text/ng-template">
                        <table cellspacing="10">
                            <tr>
                                <td style="text-align: right;">Id
                                </td>
                                <td style="text-align: left">
                                    <input id="Id" name="Id" value={% raw %}"{{: Id}}"{% endraw %} class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                                </td>
                                <td style="text-align: right;">Status
                                </td>
                                <td style="text-align: left">
                                    <select id="Status" name="Status">
                                        <option value="Close">Close</option>
                                        <option value="InProgress">InProgress</option>
                                        <option value="Open">Open</option>
                                    </select>
                                </td>
                            </tr>
                            <tr>
                                <td style="text-align: right;">Estimate
                                </td>
                                <td style="text-align: left">
                                    <input type="text" id="Estimate" name="Estimate" value={% raw %}"{{:Estimate}}"{% endraw %} />
                                </td>
                                <td style="text-align: right;">Assignee
                                </td>
                                <td style="text-align: left">
                                    <select id="Assignee" name="Assignee">
                                        <option value="Nancy">Nancy</option>
                                        <option value="Andrew">Andrew</option>
                                        <option value="Janet">Janet</option>
                                        <option value="Margaret">Margaret</option>
                                        <option value="Steven">Steven</option>
                                        <option value="Michael">Michael</option>
                                        <option value="Robert">Robert</option>
                                        <option value="Laura">Laura</option>
                                    </select>
                                </td>
                            </tr>
                        </table>
      </script>

{% endhighlight %}

{% highlight html %}

<ej-kanban id="Kanban" [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" (actionComplete)="actionComplete($event)" editSettings.allowEditing="true" editSettings.allowAdding="true" editSettings.editMode="dialogtemplate" editSettings.dialogTemplate="#template">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

While using template, you can change the elements that are defined in the `template`, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using [`actionComplete`](https://help.syncfusion.com/api/js/ejkanban#events:actioncomplete) event of Kanban. Please refer to following code snippets.

{% highlight html %}

import { Component } from '@angular/core';

import {ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'src/kanban/kanban.component.html'
})

export class KanbanComponent {
    public kanbanData: any;
    constructor() {
        this.kanbanData = [
            { Id: 1, Status: "Open", Summary: "Analyze the new requirements gathered from the customer.", Type: "Story", Priority: "Low", Tags: "Analyze,Customer", Estimate: 3.5, Assignee: "Nancy", ImageUrl: "/images/kanban/1.png", RankId: 1 },
            { Id: 2, Status: "InProgress", Summary: "Improve application performance", Type: "Improvement", Priority: "Normal", Tags: "Improvement", Estimate: 6, Assignee: "Andrew", ImageUrl: "/images/kanban/2.png", RankId: 1 },
            { Id: 3, Status: "Open", Summary: "Arrange a web meeting with the customer to get new requirements.", Type: "Others", Priority: "Critical", Tags: "Meeting", Estimate: 5.5, Assignee: "Janet", ImageUrl: "/images/kanban/3.png", RankId: 2 },
            { Id: 4, Status: "InProgress", Summary: "Fix the issues reported in the IE browser.", Type: "Bug", Priority: "Release Breaker", Tags: "IE", Estimate: 2.5, Assignee: "Janet", ImageUrl: "/images/kanban/3.png", RankId: 2 },
            { Id: 5, Status: "Testing", Summary: "Fix the issues reported by the customer.", Type: "Bug", Priority: "Low", Tags: "Customer", Estimate: "3.5", Assignee: "Steven", ImageUrl: "/images/kanban/5.png", RankId: 1 },
            { Id: 6, Status: "Close", Summary: "Arrange a web meeting with the customer to get the login page requirements.", Type: "Others", Priority: "Low", Tags: "Meeting", Estimate: 2, Assignee: "Michael Suyama", ImageUrl: "/images/kanban/6.png", RankId: 1 },
            { Id: 7, Status: "Validate", Summary: "Validate new requirements", Type: "Improvement", Priority: "Low", Tags: "Validation", Estimate: 1.5, Assignee: "Robert", ImageUrl: "/images/kanban/7.png", RankId: 1 },
            { Id: 8, Status: "Close", Summary: "Login page validation", Type: "Story", Priority: "Release Breaker", Tags: "Validation,Fix", Estimate: 2.5, Assignee: "Laura", ImageUrl: "/images/kanban/8.png", RankId: 2 },
            { Id: 9, Status: "Testing", Summary: "Fix the issues reported in Safari browser.", Type: "Bug", Priority: "Release Breaker", Tags: "Fix,Safari", Estimate: 1.5, Assignee: "Nancy", ImageUrl: "/images/kanban/1.png", RankId: 2 },
            { Id: 10, Status: "Close", Summary: "Test the application in the IE browser.", Type: "Story", Priority: "Low", Tags: "Testing,IE", Estimate: 5.5, Assignee: "Margaret", ImageUrl: "/images/kanban/4.png", RankId: 3 }];
       
    }
    actionComplete(e: any) {
        if ((e.requestType == "beginedit" || e.requestType == "add") && e.model.editSettings.editMode == "dialogtemplate") {
            $("#Estimate").ejNumericTextbox({ value: parseFloat($("#Estimate").val()), width: "175px", height: "34px", decimalPlaces: 2 });
            $("#Assignee").ejDropDownList({ width: '175px' });
            $("#Status").ejDropDownList({ width: '175px' });
            if (e.requestType == "beginedit" || e.requestType == "add") {
                $("#Assignee").ejDropDownList("setSelectedValue", e.data['Assignee']);
                $("#Status").ejDropDownList("setSelectedValue", e.data['Status']);
            }
        }
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img3.png)


### External Form

Set the [`editSettings.editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) as external form to open the edit form in outside kanban content.

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" editSettings.editMode="externalform" [editSettings.editItems]="editItem" editSettings.allowEditing="true" editSettings.allowAdding="true" [query]="query" allowScrolling="true" [scrollSettings]="scrollSettings">
    <e-kanban-columns>
        <e-kanban-column key="Open" headertext="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headertext="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headertext="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(20);
        this.editItem = [
            { field: "Id", editType: ej.Kanban.EditingType.String, validationRules: { required: true, number: true } },
            { field: "Status", editType: ej.Kanban.EditingType.Dropdown },
            { field: "Summary", editType: ej.Kanban.EditingType.TextArea, validationRules: { required: true } }
        ];
        this.scrollSettings = {
            height: 300,
            width: 700,
        };
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img11.png)

### External Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later. 

Using this template support, you can edit the fields that are not bound to Kanban Edit Items.

To edit the cards using External template form, set [`editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) as `externalFormTemplate` and specify the template id to [`externalFormTemplate`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-externalformtemplate) property of [`editSettings`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings).

While using template, you can change the elements that are defined in the template, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using [`actionComplete`](https://help.syncfusion.com/api/js/ejkanban#events:actioncomplete) event of Kanban.

N> 1. `value` attribute is used to bind the corresponding field value while editing. 
N> 2. `name` attribute is used to get the changed field values while save the edited card. 
N> 3. For [`editMode`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-editmode) property you can assign `string` value `externalFormTemplate`.

The following code example describes the above behavior.

Place the ng-template in the "index.html" page.

{% highlight html %}

    <script id="template" type="text/ng-template">
        <table cellspacing="10">
            <tr>
                <td style="text-align:left;">
                    Id
                </td>
                <td style="text-align: left">
                    <input id="Id" name="Id" value={% raw %}"{{: Id}}"{% endraw %} class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Status
                </td>
                <td style="text-align: left">
                    <select id="Status" name="Status">
                        <option value="Close">Close</option>
                        <option value="InProgress">InProgress</option>
                        <option value="Open">Open</option>
                        <option value="Testing">Testing</option>
                        <option value="Validate">Validate</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Assignee
                </td>
                <td style="text-align: left">
                    <select id="Assignee" name="Assignee">
                        <option value="Nancy">Nancy</option>
                        <option value="Andrew">Andrew</option>
                        <option value="Janet">Janet</option>
                        <option value="Margaret">Margaret </option>
                        <option value="Steven">Steven</option>
                        <option value="Michael ">Michael</option>
                        <option value="Robert">Robert</option>
                        <option value="Laura">Laura</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Priority
                </td>
                <td style="text-align: left">
                    <input id="Priority" name="Priority" value={% raw %}"{{: Priority}}"{% endraw %} class="e-field e-ejinputtext valid" style="width: 175px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Summary
                </td>
                <td style="text-align: left">
                    <textarea id="Summary" name="Summary" class="e-ejinputtext" value={% raw %}"{{: Summary}}"{% endraw %} style="width: 270px; height: 95px">{{: Summary}}</textarea>
                </td>
            </tr>
        </table>
    </script>
 
{% endhighlight %}

{% highlight html %}

<ej-kanban id="Kanban" [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" (actionComplete)="actionComplete($event)" editSettings.allowEditing="true" editSettings.allowAdding="true" editSettings.editMode="externalformtemplate" editSettings.externalFormTemplate="#template" allowTitle="true" allowScrolling="true" > 
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

import {ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'src/kanban/kanban.component.html'
})

export class KanbanComponent {
    public kanbanData: any;
    constructor() {
        this.kanbanData = [
            { Id: 1, Status: "Open", Summary: "Analyze the new requirements gathered from the customer.", Type: "Story", Priority: "Low", Tags: "Analyze,Customer", Estimate: 3.5, Assignee: "Nancy", ImageUrl: "/images/kanban/1.png", RankId: 1 },
            { Id: 2, Status: "InProgress", Summary: "Improve application performance", Type: "Improvement", Priority: "Normal", Tags: "Improvement", Estimate: 6, Assignee: "Andrew", ImageUrl: "/images/kanban/2.png", RankId: 1 },
            { Id: 3, Status: "Open", Summary: "Arrange a web meeting with the customer to get new requirements.", Type: "Others", Priority: "Critical", Tags: "Meeting", Estimate: 5.5, Assignee: "Janet", ImageUrl: "/images/kanban/3.png", RankId: 2 },
            { Id: 4, Status: "InProgress", Summary: "Fix the issues reported in the IE browser.", Type: "Bug", Priority: "Release Breaker", Tags: "IE", Estimate: 2.5, Assignee: "Janet", ImageUrl: "/images/kanban/3.png", RankId: 2 },
            { Id: 5, Status: "Testing", Summary: "Fix the issues reported by the customer.", Type: "Bug", Priority: "Low", Tags: "Customer", Estimate: "3.5", Assignee: "Steven", ImageUrl: "/images/kanban/5.png", RankId: 1 },
            { Id: 6, Status: "Close", Summary: "Arrange a web meeting with the customer to get the login page requirements.", Type: "Others", Priority: "Low", Tags: "Meeting", Estimate: 2, Assignee: "Michael Suyama", ImageUrl: "/images/kanban/6.png", RankId: 1 },
            { Id: 7, Status: "Validate", Summary: "Validate new requirements", Type: "Improvement", Priority: "Low", Tags: "Validation", Estimate: 1.5, Assignee: "Robert", ImageUrl: "/images/kanban/7.png", RankId: 1 },
            { Id: 8, Status: "Close", Summary: "Login page validation", Type: "Story", Priority: "Release Breaker", Tags: "Validation,Fix", Estimate: 2.5, Assignee: "Laura", ImageUrl: "/images/kanban/8.png", RankId: 2 },
            { Id: 9, Status: "Testing", Summary: "Fix the issues reported in Safari browser.", Type: "Bug", Priority: "Release Breaker", Tags: "Fix,Safari", Estimate: 1.5, Assignee: "Nancy", ImageUrl: "/images/kanban/1.png", RankId: 2 },
            { Id: 10, Status: "Close", Summary: "Test the application in the IE browser.", Type: "Story", Priority: "Low", Tags: "Testing,IE", Estimate: 5.5, Assignee: "Margaret", ImageUrl: "/images/kanban/4.png", RankId: 3 }];
       
    }
    actionComplete(e: any) {
        if ((e.requestType == "beginedit" || e.requestType == "add") && e.model.editSettings.editMode == "externalformtemplate") {
            $("#Assignee").ejDropDownList({ width: '175px' });
            $("#Status").ejDropDownList({ width: '175px' });
            if (e.requestType == "beginedit" || e.requestType == "add") {
                $("#Assignee").ejDropDownList("setSelectedValue", e.data['Assignee']);
                $("#Status").ejDropDownList("setSelectedValue", e.data['Status']);
            }
        }
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img13.png)

## Cell edit type and its params

The edit type of bound column can be customized using [`editType`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-edittype) property of [`editItems`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems). The following Essential JavaScript controls are supported built-in by `editType`. And also you can define the model for all the edit types controls while editing through `editParams` property of `editItems`.

The following table describes [`editType`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-edittype) and their corresponding [`editParams`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-editparams) of the specific data type of the column.

<table>
<tr>
<th>
EditType</th><th>
EditParams</th>
<th>
Description</th>
<th>
Example</th>
</tr>
<tr>
<td>
Numeric</td><td>
{{ '[ejTextBoxes](https://help.syncfusion.com/api/js/ejtextboxes)' | markdownify }} </td>
<td>
control for integers, double, and decimal data’s</td>
<td>
editParams: { decimalPlaces: 2}</td>
</tr>
<tr>
<td>
String</td><td>
HTML Textbox</td>
<td>
HTML Textbox</td>
<td>
-</td>
</tr>
<tr>
<td>
DatePicker </td><td>
{{ '[ejDatePicker](https://help.syncfusion.com/api/js/ejdatepicker)' | markdownify }} </td>
<td>
control for date data</td>
<td>
editParams: { buttonText : "Now" }</td>
</tr>
<tr>
<td>
DateTimePicker </td><td>
{{ '[ejDateTimePicker](https://help.syncfusion.com/api/js/ejdatetimepicker)' | markdownify }} </td>
<td>
control for date data-time data</td>
<td>
editParams: { enabled: true }</td>
</tr>
<tr>
<td>
DropDown </td><td>
{{ '[ejDropDownList](https://help.syncfusion.com/api/js/ejdropdownlist)' | markdownify }} </td>
<td>
control for list of data</td>
<td>
editParams: { allowGrouping: true }</td>
</tr>
<tr>
<td>
RTE </td><td>
{{ '[ejRTE](https://help.syncfusion.com/api/js/ejrte)' | markdownify }} </td>
<td>
control for customizing text in RTE format</td>
<td>
editParams: { allowResize: true }</td>
</tr>
<tr>
<td>
TextArea </td><td>
HTML TextArea</td>
<td>
Control for multi-line plain-text editing</td>
<td>
editParams:{height:100,width:200}</td>
</tr>
</table>

N> 1. If [`editType`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-edittype) is not set, then by default it will display HTML textbox while editing a card.
N> 2. For [`editType`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-edittype) property you can assign either string value (“numericedit”) or `enum` value (`ej.Kanban.EditingType.Numeric`).

The following code example describes the above behavior.


{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" [editSettings.editItems]="editItem" editSettings.allowEditing="true" editSettings.allowAdding="true" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(30);
        this.editItem = [
            { field: "Id" },
            { field: "Status", editType: ej.Kanban.EditingType.Dropdown },
            { field: "Estimate", editType: ej.Kanban.EditingType.Numeric, editParams: { decimalPlaces: 2 } },
            { field: "Summary", editType: ej.Kanban.EditingType.RTE, editParams: { height: 150, minHeight: 100 } }
        ];
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img4.png)

## Column Validation

We can validate the value of the added or edited card cell before saving.

The below validation script files are needed when editing is enabled with validation.

1.	jquery.validate.min.js
2.	jquery.validate.unobtrusive.min.js

N> If you enabled the unobtrusive option, then need to refer the jquery.validate.unobtrusive.min.js
file in your application along with the other script.

### jQuery Validation

You can set validation rules using [`validationRules`](https://help.syncfusion.com/api/js/ejkanban#members:editsettings-edititems-validationrules) property of [`columns`](https://help.syncfusion.com/api/js/ejkanban#members:columns). The following are jQuery validation methods.

#### List of jQuery validation methods

<table>
<tr>
<th>
Rules</th><th>
Description</th>
</tr>
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
rangelength</td><td>
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
The element requires a valid url.</td></tr>
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

Kanban supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [`link`](https://jqueryvalidation.org/) for more information.

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" [editSettings.editItems]="editItem" editSettings.allowEditing="true" editSettings.allowAdding="true" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(30);
        this.editItem = [
            { field: "Id" },
            { field: "Status", editType: ej.Kanban.EditingType.String },
            { field: "Assignee", editType: ej.Kanban.EditingType.Dropdown },
            { field: "Estimate", editType: ej.Kanban.EditingType.Numeric, editParams: { decimalPlaces: 2 }, validationRules: { range: [0, 1000] } },
            { field: "Summary", editType: ej.Kanban.EditingType.TextArea, validationRules: { required: true } }
        ];
    }
}    

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img5.png)
