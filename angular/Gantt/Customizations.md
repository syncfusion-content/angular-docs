---
layout: post
title: Customization
description: Customization
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Customizations 

Gantt provides support for the following UI customizations,

* Taskbar template
* Task label template
* Tooltip template

## Taskbar template

You can design your own taskbars to view the tasks in Gantt by using [taskbarTemplate](/api/js/ejgantt#members:taskbartemplate "taskbarTemplate") property. And it is possible to map the JsRender script or script element’s ID to this property. It is also possible to customize the parent taskbars and milestones with custom templates by using [parentTaskbarTemplate](/api/js/ejgantt#members:parenttaskbartemplate "parentTaskbarTemplate") and [milestoneTemplate](/api/js/ejgantt#members:milestonetemplate "milestoneTemplate") properties. 

The following code example shows how to define template for taskbars in Gantt. 
Write the following jsRender code in index.html file.

{% highlight javascript %}
<script type="text/x-jsrender" id="taskbarTemplate">
    <div class="e-gantt-template-taskbar bg-color">
        <div>
            //…
        </div>
        <div class="e-gantt-template-progressbar">
        </div>
    </div>
</script>
<script type="text/x-jsrender" id="parentTaskbarTemplate">
    <div class="e-gantt-template-taskbar">
        //…
        <div class="e-gantt-template-progressbar">
        </div>
    </div>
</script>
<script type="text/x-jsrender" id="milestoneTemplate">
    <div class="e-gantt-template-milestone" style="background-color:transparent;">
        <div class="e-gantt-milestone milestone-top"></div>
        <div class="e-gantt-milestone milestone-bottom"></div>
    </div>
</script>
{% endhighlight %}


{% highlight javascript %}

<ej-gantt
    taskbarTemplate= "#taskbarTemplate"
    parentTaskbarTemplate= "#parentTaskbarTemplate"
    milestoneTemplate= "#milestoneTemplate">
</ej-gantt>

{% endhighlight %}

The DOM structure and class names mentioned in the above code snippet is mandatory for providing the editing support in custom templates.

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/customizations/taskbartemplate) here to view the online demo sample for Taskbar templates in Gantt.

The following screenshot shows the template for taskbars in Gantt.

![](Customization_images/Customization_img1.png)

## Task label template

By default, task name will be displayed to the left and resource names will be displayed to the right of the taskbars as task labels. But these task labels are customizable.

### Mapping datasource fields as task labels

It is also possible to set any datasource fields as task labels using [rightTaskLabelMapping](/api/js/ejgantt#members:righttasklabelmapping "rightTaskLabelMapping") and [leftTaskLabelMapping](/api/js/ejgantt#members:lefttasklabelmapping "leftTaskLabelMapping") properties.

The following code example explains how to set task name field as right label and task ID field as left label,

{% highlight javascript %}

<ej-gantt
    rightTaskLabelMapping= "taskName"
    leftTaskLabelMapping= "taskID">
</ej-gantt>

{% endhighlight %}

The following screenshot shows Gantt with task labels mapped with different datasource fields

![](Customization_images/Customization_img4.png)

### Task label templates

It is possible to customize the task labels with templates, by using [rightTaskLabelTemplate](/api/js/ejgantt#members:righttasklabeltemplate "rightTaskLabelTemplate") and [leftTaskLabelTemplate](/api/js/ejgantt#members:lefttasklabeltemplate "leftTaskLabelTemplate") properties.

The following code example explains how to map custom templates to task labels and place this in index.html file.

{% highlight javascript %}

<script id="rightlabelTemplate" type="text/x-jsrender">

    {{"{{"}}if #data['resourceNames']{{}}}}

    <div>

        {{"{{"}}for resourceInfo{{}}}}

        <img src="14.2.0.26/themes/web/content/images/gantt/{{"{{"}}:resourceName{{}}}}.png" height="30px" />

        <span style="margin-left:5px;">{{"{{"}}:resourceName{{}}}}</span> {{"{{"}}:~_getSeparator(#get("array").data.length,#index){{}}}} {{"{{"}}/for{{}}}}

    </div>

    {{/if}}

</script>

<script id="leftlabelTemplate" type="text/x-jsrender">

    <div style="padding-top:5px;">

        <span>{{"{{"}}:#data['taskName']{{}}}}  [{{"{{"}}:status{{}}}}%]</span>

    </div>

</script>

{% endhighlight %}

{% highlight javascript %}

<ej-gantt
    rightTaskLabelTemplate= "#rightlabelTemplate"
    leftTaskLabelTemplate= "#leftlabelTemplate">
</ej-gantt>

{% endhighlight %}

You can find the online demo sample for task label templates in Gantt [here](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/customizations/tasklabeltemplate)

The following screenshot shows Gantt with task label templates.

![](Customization_images/Customization_img2.png)

## Tooltip template

The default tooltip in Gantt can be customized by using the [taskbarTooltipTemplateId](/api/js/ejgantt#members:taskbartooltiptemplateid "taskbarTooltipTemplateId") property. We need to map the JsRender script element’s ID value to this property.

The following code example shows how to customize the tooltip.

{% highlight javascript %}
<script type="text/x-jsrender" id="tooltipTemplate">

    <table>

       {{"{{"}}if #data['resourceNames']{{}}}}

        <tr>

            <td rowspan="3" style="padding:3px"><img src="14.2.0.26/themes/web/content/images/gantt/{{"{{"}}:#data['resourceNames']{{}}}}.png" height="40px" /></td>

            <td style="padding:3px"><b>Task done By:</b></td>

            <td style="padding:3px">{{"{{"}}:#data['resourceNames']{{}}}}</td>

        </tr>

        {{/if{{}}}}

        <tr>

            <td style="padding:3px"><b>Starts On:</b></td>

            <td style="padding:3px">{{"{{"}}:~_ganttDateFormatter("startDate"){{}}}}</td>

        </tr>

        <tr>

            <td style="padding:3px"><b>Ends On:</b></td>

            <td style="padding:3px">{{"{{"}}:~_ganttDateFormatter("endDate"){{}}}}</td>

        </tr>

    </table>

</script>

{% endhighlight %}

{% highlight javascript %}

<ej-gantt
    //...
    taskbarTooltipTemplateId= "tooltipTemplate">
</ej-gantt>

{% endhighlight %}

The following screenshot shows Gantt with task tooltip customization.

![](Customization_images/Customization_img3.png)

You can find the online demo sample for tooltip templates for taskbars [here](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/customizations/tooltiptemplate)