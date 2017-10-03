---
layout: post
title: Button-types
description: button types
platform: Angular
control: Toggle Button
documentation: ug
---

# Button types

**Toggle Button** is used as normal click able button, submitting form data, resetting the form data to its initial value. According to the usage of button, you can render the **Toggle Button** in the following three types by using the **type** property.

Toggle Button Types

<table>
<tr>
<th>Button Type</th><th>Description</th></tr><tr><td>
button</td><td>
The button is a click able button </td></tr>
<tr>
<td>
submit</td><td>
The button is a submit button (submits form-data)</td></tr>
<tr>
<td>
reset</td><td>
The button is a reset button (resets the form-data to its initial values)</td></tr>
</table>


The following steps explains you the details about rendering the **Toggle Button** with above mentioned types. 

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.


{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td> Normal</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="type_button"  size="large" defaultText="Play" activeText="Pause"></ej-togglebutton>
             </td>
         </tr>
         <tr>
             <td> Mini</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="type_submit"  defaultText="submit" size="large" activeText="submitted" ></ej-togglebutton>
             </td>
         </tr>
         <tr>
             <td> Small</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="type_mini"  defaultText="reset" size="large" activeText="reseted" ></ej-togglebutton>
             </td>
         </tr>
     </table>
    </div>
	
{% endhighlight %}

{% highlight html }

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    constructor() {
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/ToggleButton/Button-types_images/Button-types_img1.png) 


