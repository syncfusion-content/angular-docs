---
layout: post
title:  Workflows
description: Workflows
documentation: ug
platform: Angular
keywords: Workflows,kanban Workflows
---

# Workflows 

Workflows can be defined to set the flow of card moving between the Kanban column statuses and it is applicable to drag and drop and context menu features.

You can set [`workflows`](https://help.syncfusion.com/api/js/ejkanban#members:workflows) as array of Objects which consists of [`key`](https://help.syncfusion.com/api/js/ejkanban#members:workflows-key) and [`allowedTransitions`](https://help.syncfusion.com/api/js/ejkanban#members:workflows-allowedtransitions) properties. The `allowedTransitions` accepts more than one transition of the specific column key mentioned in `key` property.

If a card is to be dragged to not allowed transition columns , then not supported warning symbol will be displayed for denoting the error.
        
The following code example describes the above Workflow functionality.

{% highlight html %}

<ej-kanban [dataSource] ="kanbanData" keyField="Status" [allowTitle]="true" fields.content="Summary" fields.primaryKey="Id" [query]="query" [workflows]="workflow">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Testing" headerText="Testing"></e-kanban-column>
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
  constructor(private northwindService: NorthwindService) {
      this.kanbanData = northwindService.getTasks();
      this.query = ej.Query().from('kanbanData').take(20);
      this.workflow = [
          { key: "Open", allowedTransitions: "InProgress" },
          { key: "InProgress", allowedTransitions: "Testing,Close" }
      
  }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](WorkFlows_images/workflows1.png)