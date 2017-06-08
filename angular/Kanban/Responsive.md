---
layout: post
title:  Responsive
description: Responsive
documentation: ug
platform: Angular-2
keywords: responsive,kanban responsive
---

# Responsive

The Kanban control has support for responsive behavior based on client browser’s width and height. To enable responsive, [`isResponsive`](https://help.syncfusion.com/api/js/ejkanban#members:isresponsive) property should be true.There are two modes of responsive layout is available in Kanban based on client width. They are.

* Mobile(<480px)
* Desktop(>480px)

You can check the image representation of touch actions from the below image.

![](Responsive_images/KanbanOverlayImage.png)

## Width

By default, the Kanban is adaptable to its parent container. It can adjust its width of columns based on parent container width. You can also assign width of [`e-kanban-columns`](https://help.syncfusion.com/api/js/ejkanban#members:columns) in percentage. 

The following code example describes the above behavior.


{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" [isResponsive]="true" fields.primaryKey="Id" fields.content="Summary" fields.tag="Tags" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog" width="10%"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress" width="10%"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done" width="10%"></e-kanban-column>
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
    }
}

{% endhighlight %}

N> `allowScrolling` should be false while defining width in percentage.

## Min Width

Min Width is used to maintain minimum width for the Kanban. If the Kanban width is less than [`minWidth`](https://help.syncfusion.com/api/js/ejkanban#members:minwidth) then the scrollbar will be displayed to maintain minimum width.

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" minWidth="700" keyField="Status" [isResponsive]="true" fields.primaryKey="Id" fields.content="Summary" fields.tag="Tags" [query]="query">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog" width="120"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress" width="110"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done" width="110"></e-kanban-column>
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
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Responsive_images/responsive_img1.png)
