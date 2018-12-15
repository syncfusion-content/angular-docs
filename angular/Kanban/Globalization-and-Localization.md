---
layout: post
title:  Globalization and Localization
description: Globalization and Localization
documentation: ug
platform: Angular
keywords: globalization and localization,kanban globalization and localizationards
---

# Localization

## Localization

All text in Kanban can be localized using `ej.Kanban.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
[`EmptyCard`]
</td><td>
No cards to display
</td></tr>
<tr>
<td>
[`SaveButton`]
</td><td>
Save
</td></tr>
<tr>
<td>
[`CancelButton`]
</td><td>
Cancel
</td></tr>
<tr>
<td>
[`EditFormTitle`]
</td><td>
Details of
</td></tr>
<tr>
<td>
[`AddFormTitle`]
</td><td>
Add New Card
</td></tr>
<tr>
<td>
[`SwimlaneCaptionFormat`]
</td><td>
    {% raw %}"-{{:count}}{{if count == 1 }} item {{else}} items {{/if}}"{% endraw %}
</td></tr>
<tr>
<td>
[`FilterSettings`]
</td><td>
Filters:
</td></tr>
<tr>
<td>
[`Min`]
</td><td>
Min
</td></tr>
<tr>
<td>
[`Max`]
</td><td>
Max
</td></tr>
<tr>
<td>
[`FilterOfText`]
</td><td>
Of
</td></tr>
<tr>
<td>
[`Cards`]
</td><td>
Cards
</td></tr>
<tr>
<td>
[`ItemsCount`]
</td><td>
Items Count :
</td></tr>
<tr>
<td>
[`Unassigned`]
</td><td>
Unassigned
</td></tr>
<tr>
<td>
[`AddCard`]
</td><td>
Add Card
</td></tr>
<tr>
<td>
[`EditCard`]
</td><td>
Edit Card
</td></tr>
<tr>
<td>
[`DeleteCard`]
</td><td>
Delete Card
</td></tr>
<tr>
<td>
[`TopofRow`]
</td><td>
Top of Row
</td></tr>
<tr>
<td>
[`BottomofRow`]
</td><td>
Bottom of Row
</td></tr>
<tr>
<td>
[`MoveUp`]
</td><td>
Move Up
</td></tr>
<tr>
<td>
[`MoveDown`]
</td><td>
Move Down
</td></tr>
<tr>
<td>
[`MoveLeft`]
</td><td>
Move Left
</td></tr>
<tr>
<td>
[`MoveRight`]
</td><td>
Move Right
</td></tr>
<tr>
<td>
[`MovetoSwimlane`]
</td><td>
Move to Swimlane
</td></tr>
<tr>
<td>
[`HideColumn`]
</td><td>
Hide Column
</td></tr>
<tr>
<td>
[`VisibleColumns`]
</td><td>
Visible Columns
</td></tr>
<tr>
<td>
[`PrintCard`]
</td><td>
Print Card
</td></tr>
<tr>
<td>
[`Search`]
</td><td>
Search
</td></tr>
</table>

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.content="Summary" fields.primaryKey="Id" fields.swimlaneKey="Assignee" fields.tag="Tags" [query]="query" locale="de-DE" [enableTotalCount]="true">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress" constraints.max="2"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight ts %}

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
        ej.Kanban.Locale["de-DE"] = {
            EmptyCard: "Keine Karten angezeigt werden",
            SaveButton: "Speichern",
            CancelButton: "stornieren",
            EditFormTitle: "Details von ",
            AddFormTitle: "Neue Karte hinzufügen",
            SwimlaneCaptionFormat: {% raw %}"- {{:count}}{{if count == 1 }} Artikel {{else}} Artikel {{/if}}"{% endraw %},
            FilterSettings: "Filter:",
            FilterOfText: "Von",
            Max: "Max.",
            Min: "Min.",
            Cards: "Karten",
            ItemsCount: "Artikel Graf :",
            Unassigned: "Nicht zugewiesen",
        };
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Localization_images/localization_img1.png)

## Right to Left (RTL)

By default, Kanban render its text and layout from left to right. To customize Kanban’s direction, you can change direction from LTR to RTL by using `enableRTL` as true.

The following code example describes the above behavior.


{% highlight html %}

    <ej-kanban [dataSource]="kanbanData" keyField="Status" fields.content="Summary" fields.primaryKey="Id" fields.swimlaneKey="Assignee" fields.imageUrl="ImgUrl" enableRTL="true" [locale]="ar-AE">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="تراكم الأعمال غير المنجزة"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="في تَقَدم" constraints.max="2"></e-kanban-column>
        <e-kanban-column key="Close" headertext="فعله"></e-kanban-column>
    </e-kanban-columns>
    </ej-kanban> 

{% endhighlight %}

{% highlight ts %}
 
import {Component} from '@angular/core';
         @Component({
         selector: 'ej-app',
         templateUrl: 'src/kanban/kanban.component.html'
    })
    export class KanbanComponent {
    public kanbanData: any;
    constructor() {
        this.kanbanData = [{ Id: 2, Status: "InProgress", Summary: "تحسين أداء التطبيقات.", Type: " تحسين", Priority: "عادي", Tags: " تحسين", Estimate: 6, Assignee: " أندرو فولر", ImgUrl: "/images/kanban/2.png", RankId: 1 },
            { Id: 13, Status: "Open", Summary: " تحسينات API.", Type: " تحسين", Priority: "عالي", Tags: "شبكة,API", Estimate: 3.5, Assignee: " روبرت الملك", ImgUrl: "/images/kanban/7.png", RankId: 3 },
            { Id: 18, Status: "Close", Summary: " تحليل خادم SQL 2008 اتصال.", Type: " قصة", Priority: "قواطع الإفراج", Tags: "شبكة,Sql", Estimate: 2, Assignee: " أندرو فولر", ImgUrl: "/images/kanban/2.png", RankId: 4 },
            { Id: 25, Status: "Open", Summary: " تعزيز وظائف التحرير.", Type: " تحسين", Priority: "منخفض", Tags: "التحرير", Estimate: 3.5, Assignee: " أندرو فولر", ImgUrl: "/images/kanban/2.png", RankId: 5 }];
        ej.Kanban.Locale["ar-AE"] = {
            EmptyCard: "لا بطاقات لعرض",
            SaveButton: "حفظ",
            CancelButton: "إلغاء",
            EditFormTitle: "تفاصيل ",
            AddFormTitle: "إضافة بطاقة جديدة",
            SwimlaneCaptionFormat: "- 8 بند  العناصر ",
            FilterSettings: "مرشحات:",
            FilterOfText: "من",
            Max: "ماكس",
            Min: "دقيقة",
            Cards: "  بطاقات",
            ItemsCount: "عد العناصر:",
            Unassigned: "غير معين",
        };
    }
} 

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Localization_images/localization_img2.png)


