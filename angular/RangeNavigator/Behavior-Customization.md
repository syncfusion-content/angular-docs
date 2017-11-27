---
layout: post
title: Behavior-Customization
description: Behavior Customization
platform: Angular
control: RangeNavigator
documentation: ug
---

### Behavior Customization

**RangeNavigator** allows you to customize the control using events. You can change the range for selected data of the **RangeNavigator** using events.

#### Deferred update

If you set **enableDeferredUpdate**to true, the **rangeChanged** event gets fired after dragging and dropping the slider. By default the **enableDeferredUpdate**is true. If **enableDeferredUpdate**is false then the **rangeChanged** event gets fired while dragging the slider.

{% highlight html %}

<ej-rangenavigator id="rangecontainer" [enableDeferredUpdate]="true">
</ej-rangenavigator>

{% endhighlight %}

![](Behavior-Customization_images/Behavior-Customization_img1.png) 


#### Handle Events

**loaded:** function

This event is handled when the **RangeNavigator** gets loaded. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 

{% highlight html %}

<ej-rangenavigator id="rangecontainer" (loaded)="rangeLoaded($event)">
</ej-rangenavigator>

  <script>     

    function rangeLoaded(sender) {
        sender.model.isResponsive = false;
    }
    
 </script>


{% endhighlight %}

**rangeChanged**: function

This event gets fired whenever the selected range changes in **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 

{% highlight html %}

<ej-rangenavigator id="rangecontainer" (rangeChanged)="rangeChanged($event)">
</ej-rangenavigator>

  <script>     
        
    function rangeChanged(sender) {
        console.log(sender.selectedRangeSettings.start);
    }
    
 </script>

{% endhighlight %}

#### Use of ZoomCoordinates

**RangeNavigator** is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in **RangeNavigator**, you can use **rangeChanged** event of **RangeNavigator** and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the **zoomFactor** and **zoomPosition** of the **RangeNavigator** to the chart axis.

{% highlight html %}

<ej-rangenavigator id="rangecontainer" (rangeChanged)="onchartloaded($event)">
</ej-rangenavigator>
  
  <script>

    // setting zoom factor and position for chart axis in rangeChanged event.
    function onchartloaded(sender) {
        var chartobj = $("#container").data("ejChart");
        if (chartobj != null) {
            chartobj.model.axes[0].zoomPosition = sender.zoomPosition;
            chartobj.model.axes[0].zoomFactor = sender.zoomFactor;
        }
        $("#container").ejChart("redraw");
    }
  </script>

{% endhighlight %}



![](Behavior-Customization_images/Behavior-Customization_img2.png) 

#### Thumb Template

You can customize Thumb template by using **leftThumbTemplate** and **rightThumbTemplate** property. You can add the required template as a "div" element with an "id" to the web page and assign the id or assign the HTML string to this property under **navigatorStyleSettings**.

{% highlight html %}

 
<script type="text/x-jsrender" id="left" >
           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black;">
                <path d="M2 2 L2 22 L22 22 L32 12 L22 2 Z" />
           </svg>
</script>
<script type="text/x-jsrender" id="right">
           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black; ">
               <path d="M2 12 L12 22 L32 22 L32 2 L12 2 Z" />
           </svg>
</script>
<script type="text/javascript" language="javascript">
                    
                    this.navigatorStyleSettings= {
                          leftThumbTemplate: 'left',
                          rightThumbTemplate: 'right',
                    };
</script>

<ej-rangenavigator id="rangecontainer" [navigatorStyleSettings]="navigatorStyleSettings">
</ej-rangenavigator>

{% endhighlight %}



The following screenshot displays the **RangeNavigator** using thumb template.

![](Behavior-Customization_images/Behavior-Customization_img3.png) 


## Value Axis Settings

You can customize the line, `Font` `Size`, gridline, tickline, range, `RangePadding` and visibility of **RangeNavigator** axis.

To enable the visibility of axis line, you need to set `Visible` property of `AxisLine` in `ValueAxisSettings`. 

You can customize the axis range by specifying `Min`, `Max` and `Interval` for `Range` property.

The `MajorGridLines` can be enabled by specifying `Visible` property. The `Size`, `Width` and `Visible` property of `MajorTickLines` is used to customize the axis tick lines.

The visibility of `ValueAxisSettings` is enabled by setting `Visible` property as true. 

{% highlight html %}

<script type="text/javascript" language="javascript">
                    
                    this.valueAxisSettings= {
                          Min:10 ,
                          Max: 50 ,
                          Interval: 5,                          
                          MajorTickLines:{
                              visible:'true'
                          },
                          Size:2,
                          Width:2,
                          MajorGridLines:{
                              visible:'true'
                          },
                    };
</script>

<ej-rangenavigator id="rangecontainer" [valueAxisSettings]="this.valueAxisSettings">
</ej-rangenavigator>



{% endhighlight %}

## Selected Range Settings

The start and end range values of selected range can be customized using `Start` and `End` property of `SelectedRangeSettings`.

{% highlight html %}

<script type="text/javascript" language="javascript">
                    
                    this.selectedRangeSettings= {
                          start:'',
                          end:''
                    };
</script>

<ej:RangeNavigator ID="Range1" [selectedRangeSettings]="this.selectedRangeSettings" >               
</ej:RangeNavigator>  

{% endhighlight %}

