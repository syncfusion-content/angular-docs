---
layout: post
title: Resource Histogram View
description: resource histogram view
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Resource Histogram

A resource histogram displays the scheduled working time range of resources for its assigned tasks. Using this, you can easily identify the resource's availability and its working time. The resource histogram is used to allocate the resources properly throughout the project and find the details about allocated resources and the allocated time ranges of a specific resource.

## Data binding
You can render the histogram view for both project view Gantt and resource view Gantt by using the `viewType` as `histogramView`. 
The following code example explains how to bind the resource histogram view for project view Gantt.

{% highlight javascript %}
<ej-gantt id="GanttContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          taskNameMapping="taskName"
          startDateMapping="startDate" 
          endDateMapping="endDate"  
          progressMapping="progress" 
          durationMapping="duration"
          predecessorMapping="predecessor"
          childMapping="subtasks" 
          viewType="projectView"
          resourceInfoMapping= "resourceId"
          resourceNameMapping= "resourceName"				
          resourceIdMapping= "resourceId"
          [resources]= "resourceData">
</ej-gantt>
<ej-gantt id="HistogramContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          taskNameMapping="taskName"
          startDateMapping="startDate" 
          endDateMapping="endDate" 
          progressMapping="progress" 
          durationMapping="duration" 
          predecessorMapping="predecessor"
          childMapping="subtasks" 
          resourceInfoMapping= "resourceId"
          resourceNameMapping= "resourceName"
          resourceIdMapping= "resourceId"				
          viewType = "histogramView"
          [resources]= "resourceData" (load)="load($event)">
</ej-gantt>
{% endhighlight %}

{% highlight javascript %}
import {
    Component
} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public ganttData: any;
    public resourceData: Array < any > ;
    constructor() {
        this.ganttData = [
            //..
        ];
        this.resourceData = [
            //..
        ];
    }
    load(args) {
        let proxy = $('#HistogramContainer').ejGantt('instance');
        proxy.isProjectViewData = true;
    }
}
{% endhighlight %}
N> You should bind the data source and necessary mapping properties to render the histogram view. You can differentiate whether the bound data source is project view data or resource view data using the `ganttObject.isProjectViewData` boolean property and `load` event. Set this property to `true` if the provided data is project view and set to `false` for resource view data.

## Synchronize resource histogram view Gantt with other views

You can synchronize the splitter position and horizontal scroller position in chart side and task values of the project view/resource view Gantt control with resource histogram view Gantt by using the `actionComplete` and `splitterResized` events.

### Synchronize with project view

The following code snippet shows how to synchronize the resource histogram view Gantt with project view Gantt.

{% highlight javascript %}
<ej-gantt id="GanttContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          viewType="projectView"
          (actionComplete)="actionComplete($event)"
          (splitterResized)="splitterResized($event)">
</ej-gantt>
<ej-gantt id="HistogramContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          viewType = "histogramView"
          (load)="load($event)"
          (actionComplete)="actionComplete($event)"
          (splitterResized)="splitterResized($event)">
</ej-gantt>
{% endhighlight %}

{% highlight javascript %}
import {
    Component
} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public ganttData: any;
    public resourceData: Array < any > ;
    constructor() {
        this.ganttData = [
            //..
        ];
        this.resourceData = [
            //..
        ];
    }
    load(args) {
        let proxy = $('#HistogramContainer').ejGantt('instance');
        proxy.isProjectViewData = true;
    }
    actionComplete(args) {
        if (args.requestType == "scroll" && args.scrollDirection == "horizontal") {
            var scrollLeft = args.scrollLeft;
            if (args.model.viewType == "projectView" && !args.isScrollByMethod) {
                $("#HistogramContainer").ejGantt("setChartScrollLeft", scrollLeft);
            } else if (args.model.viewType == "histogramView" && !args.isScrollByMethod) {
                $("#GanttContainer").ejGantt("setChartScrollLeft", scrollLeft);
            }
        } else if (args.requestType == "recordUpdate") {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.data, "update");
            if (args.updatedRecords && args.updatedRecords.length > 0) {
                for (var count = 0; count < args.updatedRecords.length; count++) {
                    $("#HistogramContainer").ejGantt("updateHistogramTask", args.updatedRecords[count], "update");
                }
            }
        } else if (args.requestType == "save" && args.modifiedRecord) {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.modifiedRecord, "update");
        } else if (args.requestType == "save" && args.addedRecord) {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.addedRecord, "add");
        } else if (args.requestType == "delete") {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.data, "delete");
        }
    }
    splitterResized(args) {
        if (args.isOnResize == false) return;
        if (args.model.viewType == "projectView") {
            $("#HistogramContainer").ejGantt("setSplitterPosition", args.currentSplitterPosition);
        } else if (args.model.viewType == "histogramView") {
            $("#GanttContainer").ejGantt("setSplitterPosition", args.currentSplitterPosition);
        }
    }
}
{% endhighlight %}

The following screenshot shows the resource histogram with project view Gantt.
![](HistogramView_images/HistogramView_1.png)

### Synchronize with resource view
The following code snippet shows how to synchronize the resource histogram view Gantt with resource view Gantt.
{% highlight javascript %}
<ej-gantt id="GanttContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          taskNameMapping="taskName"
          startDateMapping="startDate" 
          endDateMapping="endDate" 
          progressMapping="progress" 
          durationMapping="duration" 
          predecessorMapping="predecessor"            
          resourceInfoMapping= "resourceId"
          resourceNameMapping= "resourceName" 
          groupNameMapping= "groupName"
          groupIdMapping= "groupId"
          [groupCollection]="groupData"				
          resourceIdMapping= "resourceId"
          [resources]= "resourceData"      
          viewType="resourceView"
          (actionComplete)="actionComplete($event)"
          (splitterResized)="splitterResized($event)">
</ej-gantt>
<ej-gantt id="HistogramContainer" [dataSource]="ganttData" taskIdMapping="taskID" 
          taskNameMapping="taskName"
          startDateMapping="startDate" 
          endDateMapping="endDate" 
          progressMapping="progress" 
          durationMapping="duration" 
          predecessorMapping="predecessor"            
          resourceInfoMapping= "resourceId"
          resourceNameMapping= "resourceName"
          resourceIdMapping= "resourceId"				
          groupNameMapping= "groupName"
          groupIdMapping= "groupId"
          [groupCollection]="groupData" 				
          viewType = "histogramView"
          [resources]= "resourceData" (load)="load()"
          (actionComplete)="actionComplete($event)"
          (splitterResized)="splitterResized($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}
import {
    Component
} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public ganttData: any;
    public resourceData: Array < any > ;
    public groupData: Array < any > ;
    constructor() {
        this.ganttData = [
            //..
        ];
        this.resourceData = [
            //..
        ];
        this.groupData = [
            //..
        ];
    }
    load(args) {
        let proxy = $('#HistogramContainer').ejGantt('instance');
        proxy.isProjectViewData = false;
    }
    actionComplete(args) {
        if (args.requestType == "scroll" && args.scrollDirection == "horizontal") {
            var scrollLeft = args.scrollLeft;
            if (args.model.viewType == "resourceView" && !args.isScrollByMethod) {
                $("#HistogramContainer").ejGantt("setChartScrollLeft", scrollLeft);
            } else if (args.model.viewType == "histogramView" && !args.isScrollByMethod) {
                $("#GanttContainer").ejGantt("setChartScrollLeft", scrollLeft);
            }
        }
        //task drag and drop action and edit action
        else if (args.requestType == "save" && args.modifiedRecord || args.requestType == "recordUpdate") {
            var data = args.requestType == "save" ? args.modifiedRecord : args.item ? args.item : args.data;
            $("#HistogramContainer").ejGantt("updateHistogramTask", data, "update");
            //row delete & group delete
            if (args.updatedRecords) {
                for (var i = 0; i < args.updatedRecords.length; i++) {
                    var data = args.updatedRecords[i];
                    $("#HistogramContainer").ejGantt("updateHistogramTask", data, "update");
                }
            }
        }
        //add row
        else if (args.requestType == "save" && args.addedRecord) {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.addedRecord, "add");
        }
        //task delete
        else if (args.requestType == "delete") {
            $("#HistogramContainer").ejGantt("updateHistogramTask", args.data, "delete");
        }
    }
    splitterResized(args) {
        if (args.isOnResize == false) return;
        if (args.model.viewType == "resourceView") {
            $("#HistogramContainer").ejGantt("setSplitterPosition", args.currentSplitterPosition);
        } else if (args.model.viewType == "histogramView") {
            $("#GanttContainer").ejGantt("setSplitterPosition", args.currentSplitterPosition);
        }
    }
}
{% endhighlight %}

The following screenshot shows the resource histogram for resource view Gantt.
![](HistogramView_images/HistogramView_2.png)