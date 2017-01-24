---
title: Getting started with Kanban component	
description: Rendering a Kanban control
platform: Angular-2
control: kanban
documentation: ug
keywords: ejkanban, kanban, kanban widget, js kanban
---
# Getting Started

Before we start with the Kanban, please refer [this page](https://help.syncfusion.com/angular-2/overview) page for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS references

To render the Kanban control, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [Angular 2](https://angular.io/) - angular 2 latest versions

The other required internal dependencies are tabulated below,

<table>
   <tr>
      <th>
         <b>Files</b>
      </th>
      <th>
         <b>Description/Usage </b>
      </th>
   </tr>
   <tr>
      <td>
         ej.core.min.js
      </td>
      <td>
        It is referred always before using all the JS controls.
      </td>
   </tr>
   <tr>
      <td>
         ej.data.min.js
      </td>
      <td>
         Used to handle data operation and is used while binding data to the JS controls.
      </td>
   </tr>
   <tr>
      <td>
        ej.touch.min.js 
      </td>
      <td>
          It is referred when using touch functionalities in Kanban.
      </td>
   </tr>
    <tr>
      <td>
        ej.draggable.min.js 
      </td>
      <td>
          It is referred when using drag and drop in Kanban.
      </td>
   </tr>
   <tr>
      <td>
        ej.kanban.min.js
      </td>
      <td>
        Kanban core script file which includes kanban related scripts files such as <i>ej.kanban.base.js</i>, <i>ej.kanban.common.js</i>,<i>ej.kanban.dragAndDrop.js</i>,<i>ej.kanban.edit.js</i>,<i>ej.kanban.adaptive.js</i>,<i>ej.kanban.filter.js</i>,<i>ej.kanban.scroller.js</i>,<i>ej.kanban.selection.js</i>,<i>ej.kanban.swimlane.js</i> and <i>ej.kanban.context.js</i><br/><br/>
      </td>
   </tr>
   <tr>
      <td>
        ej.globalize.min.js
      </td>
      <td>
       It is referred when using localization in Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.scroller.min.js
      </td>
      <td>
         It is referred when scrolling is used in the Kanban. 
      </td>
   </tr>
   <tr>
      <td>
         ej.waitingpopup.min.js
      </td>
      <td>
        It is referred when waiting popup used.
      </td>
   </tr>
   <tr>
      <td>
        ej.dropdownlist.min.js
      </td>
      <td rowspan = "5">
         These files are used while enable the Editing feature in the Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.dialog.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.button.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.datepicker.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.datetimepicker.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.editor.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.toolbar.min.js
      </td>
      <td>
        These files are used while enable the Filtering feature in the Kanban.
      </td>
   </tr>
    <tr>
      <td>
        ej.menu.min.js
      </td>
      <td rowspan = "2">
         These files are used while enable the context menu feature in the Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.checkbox.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.rte.min.js
      </td>
      <td>
        These files are used while using the cell edit type as RTE in the Kanban.
      </td>
   </tr>
</table>

N> Kanban uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the Kanban, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Preparing HTML document

Create an HTML page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Essential Studio for JavaScript">
    <meta name="author" content="Syncfusion">
    <title></title>

    <!-- Essential Studio for JavaScript  theme reference -->
    <link rel="stylesheet" href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" />

    <!-- Angular2 related script references -->
    <!-- 1. Load libraries -->
         <!-- Polyfill(s) for older browsers -->
    <script src="node_modules/core-js/client/shim.min.js"></script>   
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>

    <!-- Essential Studio for JavaScript  script references -->
    <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script> 
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    
    <!-- 2. Configure SystemJS -->
    <script src="systemjs.config.js"></script>
    <script>       
      System.import('app')
            .then(null, console.error.bind(console));
    </script>

    </head>
    <!-- 3. Display the application -->
    <body>
    <my-app>Loading...</my-app>
    </body>
    </html>

{% endhighlight %}

N> Uncompressed version of library files are also available which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).

## Control Initialization

Create a Div element within the body section of the HTML document, where the Kanban needs to be rendered.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData">
   <e-kanban-columns>
        <e-kanban-column headerText="Backlog"></e-kanban-column>
        <e-kanban-column headerText="In Progress"></e-kanban-column>
        <e-kanban-column headerText="Done"></e-kanban-column>
   </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

The below code is to retrive data from service and assigned to Kanban datasource.

{% highlight js %}

import {Component} from '@angular/core';
import {NorthwindService} from '../../services/northwind.service';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/kanban/kanban.component.html'
})
export class KanbanComponent {
    constructor(private northwindService:NorthwindService)
    {
      this.kanbanData = northwindService.getTasks();  
    }
}

{% endhighlight %}

![](Getting_Started_images/Getting_Started_img1.png)

## Mapping Values

In order to display cards in Kanban control, you need to map the database fields to Kanban cards and columns. The required mapping field are listed as follows

* 'keyField' - Map the column name to use as 'key' values to columns.
* 'columns' - Map the corresponding 'key' values of 'keyField' column to each columns.
* 'fields.content' - Map the column name to use as content to cards.
* 'fields.primaryKey' - Map the column name to use as primary Key.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.content="Summary" fields.primaryKey="Id">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

The below code is to retrive data from service and assigned to Kanban datasource.

{% highlight js %}

import {Component} from '@angular/core';
import {NorthwindService} from '../../services/northwind.service';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/kanban/kanban.component.html'
})
export class KanbanComponent {
    constructor(private northwindService:NorthwindService)
    {
      this.kanbanData = northwindService.getTasks();  
    }
}

{% endhighlight %}

![](Getting_Started_images/Getting_Started_img2.png)

## Mapping Values

'Swimlane' can be enabled by mapping the 'fields.swimlaneKey' to appropriate column name in 'dataSource'. This enables the grouping of the cards based on the mapped column values.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.content="Summary" fields.primaryKey="Id" fields.swimlaneKey="Assignee">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

The below code is to retrive data from service and assigned to Kanban datasource.

{% highlight js %}

import {Component} from '@angular/core';
import {NorthwindService} from '../../services/northwind.service';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/kanban/kanban.component.html'
})
export class KanbanComponent {
    constructor(private northwindService:NorthwindService)
    {
      this.kanbanData = northwindService.getTasks();  
    }
}

{% endhighlight %}

![](Getting_Started_images/Getting_Started_img3.png)

## Adding Filters

Filters allows to filter the collection of cards from 'dataSource' which meets the predefined 'query' in the filters collection. To enable filtering, define 'filterSettings' collection with display 'text' and 'ej.Query'.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.content="Summary" fields.primaryKey="Id" fields.swimlaneKey="Assignee">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
      <e-filterSettings>
        <e-filterSetting text="Janet Issues" query= "query1" description="Displays issues which matches the assignee as 'Janet Leverling'"></e-filterSetting>
        <e-filterSetting e-text="InProgress Issues" e-query="query2" e-description="Display the issues of 'In Progress'"></e-filterSetting>
        </e-filterSettings>
</ej-kanban>

{% endhighlight %}

The below code is to retrive data from service and assigned to Kanban datasource.

{% highlight js %}

import {Component} from '@angular/core';
import {NorthwindService} from '../../services/northwind.service';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/kanban/kanban.component.html'
})
export class KanbanComponent {
    constructor(private northwindService:NorthwindService)
    {
      this.kanbanData = northwindService.getTasks();  
      query1 = new ej.Query().where('Assignee', 'equal', 'Janet Leverling');
      query2 = new ej.Query().where('Status', 'equal', 'InProgress');
    }
}

{% endhighlight %}

![](Getting_Started_images/Getting_Started_img4.png)
