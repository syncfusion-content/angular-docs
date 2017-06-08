---
layout: post
title: Grouping
description: Grouping
platform: angular-2
control: ListBox
documentation: ug
---

# Grouping

The ListBox items can be categorize as follows.

## Grouping with Local Data binding

The ListBox items can be categorized by using a specific field. This is enabled by using groupBy field on data source binding. By default grouping is disabled in ListBox. The below given example explains the behavior of grouping with JSON array binding.

{% seealso %} [Data Binding](http://help.syncfusion.com/js/listbox/databinding). {% endseealso %}

The grouping will be defined based on the “groupBy” API in fields object.

{% highlight html %}

  <div class="frame">
      <ej-listbox id="selectgroup" [dataSource]="skillset" [fields]="fields"></ej-listbox>
  </div>
   
{% endhighlight %}

{% highlight ts %}

 export class GroupingComponent {
    skillset: Array<any>;
    fields: Object;
    constructor() {
        this.fields = { text: 'skill', groupBy: 'category' };
        this.skillset = [
            { skill: 'Bahrain', category: 'B' }, { skill: 'Brazil', category: 'B' }, { skill: 'Argentina', category: 'A' },
            { skill: 'Bangladesh', category: 'B' }, { skill: 'Burma', category: 'B' }, { skill: 'Afghanistan', category: 'A' }, { skill: 'Antigua and Barbuda', category: 'A' },
            { skill: 'Barbados', category: 'B' }, { skill: 'Botswana', category: 'B' }, { skill: 'Albania', category: 'A' }, { skill: 'Andorra', category: 'A' },
            { skill: 'Belarus', category: 'B' }, { skill: 'Bolivia', category: 'B' }, { skill: 'Algeria', category: 'A' }, { skill: 'Angola', category: 'A' }
        ];
    }
}
   
{% endhighlight %}

![](Grouping_images\Grouping_img2.png)