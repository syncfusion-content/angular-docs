---
layout: post
title: Appearance-And-Styling
description: Appearance And Styling
platform: Angular
control: RangeNavigator
documentation: ug
---

### Appearance and Styling

**Angular RangeNavigator** is enriched with lots of customization options for labels, gridlines and slider to develop high quality graphic rich control.

#### Customize labels

The labels are found along the range, displaying the value of the data it correspond, both on (higher level label) and below (lower level label) the **RangeNavigator**. **RangeNavigator** labels are further customized using "**font**" property in label Settings. 

{% highlight ts %}
      
this.labelSettings = {
    // customizing higher level labels.
    higherLevel: {
        style: {
            font: {
                color: '#ff0000',
                style: 'Normal',
                size: '12px',
                opacity: 1,
                weight: 'regular'
            },

        },
    },
    // customizing lower level labels.
    lowerLevel: {
        style: {
            font: {
                color: '#ff0000',
                style: 'Normal',
                size: '12px',
                opacity: 1,
                weight: 'regular'
            },
        },
    }
};

{% endhighlight %}

{% highlight html %}

<ej-rangenavigator [labelSettings]="labelSettings">
</ej-rangenavigator>

{% endhighlight %}

![](Appearance-And-Styling_images/Appearance-And-Styling_img1.png) 


##### Label Placement

Labels in **RangeNavigator** are placed inside or outside of the control. You can customize both the higher and lower level labels using **labelPlacement** property in label setting of **RangeNavigator**. By default **labelPlacement** is "outside" for the both higher and lower level labels.

The following screen shot illustrates both the lower and higher level labels that are placed outside the control with **labelPlacement** specified as outside.

{% highlight ts %}

// change Placement of higher and lower level label             
this.labelSettings = {
    higherLevel: {
        labelPlacement: "inside",
    },
    lowerLevel: {
        labelPlacement: "inside"
    }
};

{% endhighlight %}

{% highlight html %}

<ej-rangenavigator [labelSettings]="labelSettings">
</ej-rangenavigator>

{% endhighlight %}

The following screenshot illustrates a **RangeNavigator** with labels inside the control after specifying the **labelPlacement** as inside.



![](Appearance-And-Styling_images/Appearance-And-Styling_img2.png) 

#### Customize RangeNavigator

RangeNavigator is customized using **navigatorStyleSettings** properties. You can customize the selected and unselected region color using **selectedRegionColor**, **unselectedRegionColor** in **navigatorStyleSettings** and the thumb of the slider using **thumbColor, thumbRadius** and **thumbStroke** in **navigatorStyleSettings.  majorGridLineStyle** and **minorGridLineStyle**  are used to customize the grid line color and visibility.

{% highlight ts %}
   
//  To customize the navigator element     
this.navigatorStyleSettings = {

    unselectedRegionColor: "white",
    selectedRegionColor: "#5EABDE",
    thumbColor: "white",
    thumbRadius: 10,
    thumbStroke: "#303030",
    background: "transparent",
    border: {
        color: "black",
        width: 3
    },
    majorGridLineStyle: {
        color: "transparent"
    },
    minorGridLineStyle: {
        color: "transparent"
    }
};
//  To customize the labels
this.labelSettings = {

    higherLevel: {
        style: {
            font: {
                color: 'black',
                size: '13px',
                opacity: 1
            },
            horizontalAlignment: "left"
        },
        intervalType: 'years',
        labelPlacement: "inside"
    },
    lowerLevel: {
        style: {
            font: {
                color: 'black',
                size: '12px',
                opacity: 1
            },
            horizontalAlignment: "center"
        },
        intervalType: 'quarters',
        labelPlacement: "inside"
    }
};

{% endhighlight %}

{% highlight html %}

<ej-rangenavigator [labelSettings]="labelSettings" [navigatorStyleSettings]="navigatorStyleSettings">
</ej-rangenavigator>

{% endhighlight %}

![](Appearance-And-Styling_images/Appearance-And-Styling_img3.png) 

#### Themes

**RangeNavigator** theme is a set of pre-defined options that are applied to the control before each **RangeNavigator** is instantiated. Following predefined themes are available in Angular **RangeNavigator**.

1. flatlight
2. flatdark
3. gradientlight 
4. gradientdark 
5. azure                      
6. azuredark               
7. lime 
8. limedark
9. saffron
10. saffrondark
11. gradientazure
12. gradientazuredark
13. gradientlime
14. gradientlimedark
15. gradientsaffron
16. gradientsaffrondark

{% highlight html %}

<ej-rangenavigator theme="azuredark">
</ej-rangenavigator>

{% endhighlight %}



![](Appearance-And-Styling_images/Appearance-And-Styling_img4.png) 
