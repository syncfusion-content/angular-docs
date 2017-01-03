---
layout: post
title: Exporting
description: exporting
platform: angular2
control: Linear Gauge
documentation: ug
---

# Exporting

**Linear Gauge** has an exporting feature that converts **Gauge** control into image format and then export in client side. The method API **exportImage** is used to export the **LinearGauge**. It has two arguments such as **file name** and **file format** to specify the file name and file formats. For exporting refer the following code example.


{% highlight ts %}
     
//Adding label collection
this.scaleLabels= [{ font: { size: "11px", fontFamily: "Segoe UI", fontStyle: "bold" }, distanceFromScale: { x: -13 } }];

 {% endhighlight %}

{% highlight html %}


<button id="btnSubmit">Export</button>
<div id=" fileName ">FileName </div>
<div id=" fileFormat ">FileFormat </div>
<select id="fileFormat">
    <option value="JPEG">JPEG</option>
    <option value="PNG">PNG</option>
</select>

 <ej-lineargauge id="LinearGauge1"  [width]=450 labelColor="#8c8c8c">
   <e-scales>
        <e-scale backgroundColor="transparent" [labels]="scaleLabels" [showRanges]="true"
                        [length]=310 [position]="{ x: 52, y: 50 }" [showBarPointers]="false"
                                                [border]="{ color: 'transparent', width: 0 }">
          <e-markerpointers>
              <e-markerpointer  [width]="10" backgroundColor="#4D4D4D" [value]=50 [length]=10
                                                                      border.color="#4D4D4D" >
              </e-markerpointer>
           </e-markerpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" 
                                   [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
          <e-ranges>
                 <e-range [startValue]=0 [endValue]=60 backgroundColor="#F6B53F" [startWidth]=4
                                                          [endWidth]=4 border.color="#F6B53F" >
                 </e-range>
                <e-range [startValue]=60 [endValue]=100 backgroundColor="#E94649" [startWidth]=4
                                                           [endWidth]=4 border.color="#E94649" >
                 </e-range>
          </e-ranges>
        </e-scale>
     </e-scales>
  </ej-lineargauge>

{% endhighlight %}


 {% highlight javascript %}

// declaration
$("#btnSubmit").ejButton({ width: "50px", click: "buttonclickevent", });
$("#fileFormat").ejDropDownList({ selectedItemIndex: 0, width: "115" });

function buttonclickevent() {
    var FileName = $("#fileName").val();
    var FileFormat = $("#fileFormat").ejDropDownList("option", "value");
    $("#LinearGauge1").ejLinearGauge("exportImage", FileName, FileFormat);
}

{% endhighlight %}



Execute the above code to render the following output.

![](Exporting_images/Exporting_img1.png)

