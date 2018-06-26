---
layout: post
title: Data-Binding
description: data binding
platform: Angular
control: TreeGrid
documentation: ug
api: /api/js/ejtreegrid
---

# Data Binding

Data Binding is the process that establishes a connection between the application and different kinds of data sources such as business objects.

## Local Data Binding

In Local Data Binding, datasource for rendering the TreeGrid control is retrieved from the same application locally.

Two types of Data Binding are possible with TreeGrid control, 

* Hierarchical Datasource Binding
* Self-Referential Data Binding (Flat Data)

### Hierarchy Datasource Binding

The following code example shows you how to bind the hierarchical local data into the TreeGrid control.

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public projectData: any;
    public columns: any;
    constructor() {
        //...
        this.columns = [{
                field: "taskID",
                headerText: "Task Id",
                editType: "numericedit"
            },
            {
                field: "taskName",
                headerText: "Task Name",
                editType: "stringedit",
                allowEditing: true,
                validationRules: {
                    maxlength: 5
                }
            },
            {
                field: "startDate",
                headerText: "Start Date",
                editType: "datepicker"
            },
            {
                field: "endDate",
                headerText: "End Date",
                editType: "datepicker",
                allowEditing: true
            },
            {
                field: "duration",
                headerText: "Duration",
                editType: "numericedit"
            },
            {
                field: "progress",
                headerText: "Status",
                editType: "numericedit"
            },
        ]
        this.projectData = [{
                taskID: 1,
                taskName: "Planning",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                progress: 100,
                duration: 5,
                subtasks: [{
                        taskID: 2,
                        taskName: "Plan timeline",
                        startDate: "02/03/2014",
                        endDate: "02/07/2014",
                        duration: 5,
                        progress: 100
                    },
                    {
                        taskID: 3,
                        taskName: "Plan budget",
                        startDate: "02/03/2014",
                        endDate: "02/07/2014",
                        duration: 5,
                        progress: 100
                    },
                    //...
                ]
            },
            //...
        ];
    }
    public treeColumnIndex = 1;
}

{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [dataSource]="projectData" [columns]="columns" childMapping="subtasks" [treeColumnIndex]=treeColumnIndex 
    //...>
</ej-treegrid>

{% endhighlight %}

The output of the above steps is as follows:

![](Data-Binding_images/Data-Binding_img1.png)

###Self-Referential Data Binding (Flat Data)

TreeGrid is rendered from Self-Referential data structures by providing two fields: **ID** field and **parent ID** field.

* **ID Field** - This field contains unique values used to identify nodes. Its name is assigned to the [`idMapping`](/api/js/ejtreegrid#idmappingspan-classtype-signature-type-stringstringspan "idMapping") property.
* **Parent ID Field** - This field contains values that indicate parent nodes. Its name is assigned to the [`parentIdMapping`](/api/js/ejtreegrid#parentidmappingspan-classtype-signature-type-stringstringspan "parentIdMapping") property.

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public projectData: any;
    public columns: any;
    constructor() {
        //...
        this.columns = [{
                field: "taskID",
                headerText: "Task Id",
                editType: "numericedit"
            },
            {
                field: "taskName",
                headerText: "Task Name",
                editType: "stringedit",
                allowEditing: true,
                validationRules: {
                    maxlength: 5
                }
            },
            {
                field: "startDate",
                headerText: "Start Date",
                editType: "datepicker"
            },
            {
                field: "endDate",
                headerText: "End Date",
                editType: "datepicker",
                allowEditing: true
            },
            {
                field: "duration",
                headerText: "Duration",
                editType: "numericedit"
            },
            {
                field: "progress",
                headerText: "Status",
                editType: "numericedit"
            },
        ]
        this.projectData = [

            {
                taskID: 1,
                taskName: "Task 1",
                startDate: "02/03/2014",
                endDate: "03/07/2014",
                duration: 5
            },

            {
                taskID: 2,
                pId: 1,
                taskName: "Child Task 1",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                duration: 5
            },

            {
                taskID: 3,
                pId: 1,
                taskName: "Child Task 2",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                duration: 5,
                progress: "100"
            },

            {
                taskID: 22,
                pId: 2,
                taskName: "Sub Child Task 1",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                duration: 5
            },

            {
                taskID: 23,
                pId: 2,
                taskName: "Sub Child Task 2",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                duration: 5,
                progress: "100"
            },

            //...

        ];
    }
    public treeColumnIndex = 1;
}

{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [dataSource]="projectData" [columns]="columns" [treeColumnIndex]=treeColumnIndex 
    idMapping="taskID"  parentIdMapping="pId"
    //...>
</ej-treegrid>

{% endhighlight %}

The following screenshot shows the output of the above steps,

![](Data-Binding_images/Data-Binding_img2.png)

## Remote data binding

### Load on demand

TreeGrid provides `Load on Demand` support for rendering remote data. Load on demand is considered in TreeGrid for the following actions, 

* Expanding root nodes.
* Navigating pages, with paging enabled in TreeGrid.

When load on demand is enabled, all the root nodes are rendered in collapsed state at initial load.

When load on demand support is enabled in TreeGrid with paging, the current or active page’s root node alone will be rendered in collapsed state. On expanding the root node, the child nodes will be loaded from the remote server. 

When a root node is expanded, its child nodes are rendered and are cached locally, such that on consecutive expand/collapse actions on root node, the child nodes are loaded from the cache instead from the remote server.

Similarly, if the user navigates to a new page, the root nodes of that specific page, will be rendered with request to the remote server.

N> 1. Load on demand support in TreeGrid can be enabled only for remote data.
N> 2. For better initial load time performance, we need to define the “hasChildMapping” property.

Load on demand support in TreeGrid can be enabled by the following ways,

1. By enabling [`enableLoadOnDemand`](https://help.syncfusion.com/api/js/ejtreegrid#members:enableLoadOnDemand "enableLoadOnDemand") property of TreeGrid control
2. By enabling **crossDomain** property while binding data source using ejDataManager control.

The following code explains how to use Load on Demand in TreeGrid Control,


{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public projectData:any;
    public columns:any;
    public dataManager:any;
  constructor() {
   //...
    this.dataManager = ej.DataManager({
        url: "http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas",
        crossDomain: true,
    });
     this.columns=[ {field: "TaskID", headerText: "Task Id", width: columnWidth},
                  { field: "TaskName", headerText: "Task Name"},
                  { field: "StartDate", headerText: "Start Date" },
                  { field: "EndDate", headerText: "End Date” },   
                  { field: "Progress", headerText: "Progress" }]
   this.projectData=  this.dataManager;
  }
    public treeColumnIndex = 1;
}

{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [dataSource]="projectData" [columns]="columns" [treeColumnIndex]=treeColumnIndex 
    idMapping="TaskID"  parentIdMapping="ParentID" hasChildMapping= "isParent" [enableVirtualization]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

The output for load on demand support in TreeGrid:

![](Data-Binding_images/Data-Binding_img3.png)
![](Data-Binding_images/Data-Binding_img4.png)

The following code snippet shows on how to enable load on demand support using  [`enableLoadOnDemand`](https://help.syncfusion.com/api/js/ejtreegrid#members:enableLoadOnDemand "enableLoadOnDemand") property.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public projectData:any;
    public dataManager:any;
  constructor() {
   //...
    this.dataManager = ej.DataManager({
        url: "http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas"
    });
   this.projectData=  this.dataManager;
  }
}

{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [enableLoadOnDemand]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

The following output shows how load on demand works for expanding action

![](Data-Binding_images/Data-Binding_img5.png)

### Load at once:

On remote data binding, for every action such as paging, sorting, filtering, the data will be fetched from remote server each time. To avoid requesting the data from the remote server for each action, we can set TreeGrid to load all the data on initialization and make all the data operations in client side. To enable this, we can use offline property of `ej.DataManager`. the following code example explains this.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public projectData:any;
    public dataManager:any;
    public columns:any;
  constructor() {
   //...
    this.dataManager = ej.DataManager({
        url: "http://js.syncfusion.com/demos/ejServices/Wcf/TreeGridGantt/TreeGantt.svc/SelfReferenceDatas",
        offline: true,
    });
   this.columns=[ {field: "TaskID", headerText: "Task Id", width: columnWidth},
                  { field: "TaskName", headerText: "Task Name"},
                  { field: "StartDate", headerText: "Start Date" },
                  { field: "EndDate", headerText: "End Date” },   
                  { field: "Progress", headerText: "Progress" }]
   this.projectData=this.dataManager;
  }
}

{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [dataSource]= "projectData"
        idMapping= "TaskID"
        parentIdMapping= "ParentID"
        hasChildMapping= "isParent"
        [enableVirtualization]= "true"
    //...>
</ej-treegrid>

{% endhighlight %}

Please refer the [link](https://help.syncfusion.com/js/datamanager/data-binding#offline-mode "offline") for further reference on offline property

**Limitations**:

1. Mapping the expand state of a record using `expandStateMapping` property is not supported in load on demand feature.
2. If a root or parent node is in collapsed state (child nodes not yet loaded), then that parent node will not be expanded while inserting new child to that parent node using toolbar icon or drag and drop actions.

