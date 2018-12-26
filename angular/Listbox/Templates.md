---
layout: post
title: Syncfusion ListBox Templates
description: templates
platform: Angular
control: ListBox
documentation: ug
---

# Template Support

By default you can add any text or image to the ListBox list item. To customize the list items layout or to create your own visualized elements by using template support.

## Template Fields

To create set of div element with common syntax and assign it to the template property. You can add any HTML mark-up element inside the ListBox using this property.

To create the JSON array with text, imageName, role and country which is initialized in the dataSource property. Content template is created by using the corresponding fields and assigned in template property. The content template is customized with images and custom CSS styles to visualize the list items.

{% highlight html %}

   <div class="frame">
       <div class="ctrllabel"></div>
           <div id="controlitem">
               <ej-listbox id="selectExperts" [dataSource]="employeeList" [template]="template"></ej-listbox>
           </div>
  </div>
    
{% endhighlight %}

{% highlight ts %}

export class TemplateComponent {
    employeeList: Array<any>;
    template: Object;
    constructor() {
        this.template = '<div><img class="employeeImage" src="app/content/images/Employees/${employeeImage}.png" alt="employee"/>' +
            '<div class="ename"> ${text} </div><div class="designation"> ${designation} </div><div class="cont"> ${country} </div></div>';
        this.employeeList = [
            { text: 'Erik Linden', employeeImage: '3', designation: 'Representative', country: 'England' }, { text: 'John Linden', employeeImage: '6', designation: 'Representative', country: 'Norway' },
            { text: 'Louis', employeeImage: '7', designation: 'Representative', country: 'Australia' }, { text: 'Lawrence', employeeImage: '5', designation: 'Representative', country: 'India' }
        ];
    }
}

{% endhighlight %}

{% highlight css %}

    .employeeImage {
        margin: 0;
        padding: 3px 10px 3px 3px;
        border: 0 none;
        width: 60px;
        height: 60px;
        float: left;
    }

    .ename {
        font-weight: bold;
        padding: 6px 3px 1px 3px;
    }

    .designation, .cont {
        font-size: smaller;
        padding: 3px 3px -1px 0px;
    }

    #selectExperts li {
        width: 100%;
        height: 70px;
        padding: 5px;
    }
     
{% endhighlight %}

![Templates](Templates_Images\templates_img1.png)

