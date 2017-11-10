---
layout: post
title: Easy-customization
description: easy customization
platform: Angular
control: CheckBox
documentation: ug
---

# Easy customization

## Checked status

Using **checked** property, you can set the state of Checkbox. When checked property is true then tick mark is displayed and Checkbox is in checked state. When it is false, the tick mark is not displayed and Checkbox is in unchecked state. When you want to use this **checked** property, then checkbox should be in non Tri-state and **enableTriState** property should be false.

The following steps explains you the details about rendering the Checkbox with above mentioned checked options, when the checkbox is in non tri-state.

In the **HTML** page, add the following input elements to configure Checkbox widget.


{% highlight html %}

    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox  type="checkbox"  class="nodetext" id="checkbox_nonChecked" [(checked)]="uncheckstatus" ></ej-checkbox>
			<label for="chekbox_nonChecked" class="clslab">Music</label>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="checkbox_checked" [(checked)]="checkstatus"></ej-checkbox>
			<label for="chekbox_Checked" class="clslab">Music</label>
			</td>
    </tr>
    </table>

{% endhighlight %}
  
{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    checkstatus: boolean;
	uncheckstatus:boolean;
    constructor() {
        this.checkstatus = true;
		this.uncheckstatus=false;
    }
}

{% endhighlight %}


Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img1.png) 


## Enable Tri-State

Sometimes, it is essential for you to represent the answer in partially true state. To represent the partially true types, an indeterminate state option is present. The state between checked and unchecked state is called indeterminate state. For example, a **Checkbox** presented to select files to send via FTP can use a tree view so that files can be selected one at a time, or by folder. When only some of the files in a folder are selected, then the checkbox for that folder could be in indeterminate state.

When you enable Tri-state, then the **Checkbox** includes the indeterminate state. The Checkbox has three states. **enableTriState** property specifies to enable or disable the Tri-State option for Checkbox. 

The following steps explains you the details about rendering the Checkbox with Tri-state options.

In the **HTML** page, add the following input elements to configure Checkbox widget.


{% highlight html %}
 
    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="checkbox_nonTriState" [(enableTriState)]="checkedenableTriState" [(checked)]="checked"></ej-checkbox>
            <label for="checkbox_nonTriState" class="clslab">Music</label>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="checkbox_triState" [(enableTriState)]="indeterminateenableTriState" [checkState]="indeterminate"></ej-checkbox>
            <label for="checkbox_triState" class="clslab">Indeterminate state</label>
        </td>
    </tr>
    </table>

{% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    checkedenableTriState: boolean;
    indeterminateenableTriState: boolean;
    checked: boolean;
    constructor() {
        this.checkedenableTriState = false;
        this.indeterminateenableTriState = true;
        this.checked = true;
    }
}

{% endhighlight %}

Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img2.png) 



## Check State

You require an option to set indeterminate state for Checkbox. By using Checkbox property, you can set any state that is illustrated in following table. Before using this property, enable the Tri-state for Checkbox. **enableTriState** property is set true.

List of check states

<table>
   <tr>
      <th>
         Check States
      </th>
      <th>
         Description
      </th>
   </tr>
   <tr>
      <td>
         check
      </td>
      <td>
         Check box will be in checked state
      </td>
   </tr>
   <tr>
      <td>
         uncheck
      </td>
      <td>
         Check box will be in un-checked state
      </td>
   </tr>
   <tr>
      <td>
         indeterminate
      </td>
      <td>
         Check box will be in indeterminate state
      </td>
   </tr>
</table>


The following steps explains you the details about rendering the **Checkbox** with specified checked state, when the checkbox is in tri-state.

In the **HTML** page, add the following input elements to configure **Checkbox** widget.


{% highlight html %}

    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox  type="checkbox"  class="nodetext" id="check" [(enableTriState)]="checkedenableTriState" [(checked)]="checked" [checkState]="check" ></ej-checkbox>
			<label for="check" class="clslab">Checked state</label>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="unchecked" [(enableTriState)]="uncheckedenableTriState" [checkState]="unCheck" ></ej-checkbox>
            <label for="unchecked" class="clslab">Unchecked State</label>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="indetermediate" [(enableTriState)]="indeterminateenableTriState" [checkState]="indeterminate"></ej-checkbox>
            <label for="indeterminate" class="clslab">Indeterminate state</label>
        </td>
    </tr>
    </table>

{% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    checkedenableTriState: boolean;
    uncheckedenableTriState: boolean;
    indeterminateenableTriState: boolean;
    checked: boolean;
    constructor() {
        this.checkedenableTriState = true;
        this.uncheckedenableTriState = true;
        this.indeterminateenableTriState = true;
        this.checked = true;
    }
}

{% endhighlight %}


Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img3.png) 



## Checkbox Size

You can render **Checkbox** in different sizes. The following table contains some predefined size option for rendering a **Checkbox** in easiest way. Each size option has different height and width. Mainly it avoids the complexity in rendering **Checkbox** with complex **CSS** class. 

List of checkbox size:

<table>
    <tr>
<th>CheckBox size</th><th>Description</th></tr>
<tr>
<td>small</td><td>
Creates checkbox with Built-in small size height, width specified.</td></tr>
<tr>
<td>
medium</td><td>
Creates checkbox with Built-in medium size height, width specified.</td></tr>
</table>


The following steps explains you the details about rendering the **Checkbox** with different size.

In the **HTML** page, add the following input elements to configure **Checkbox** widget.


{% highlight html %}
  
    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox  type="checkbox"  class="nodetext" id="checkbox_small" [size]="small" ></ej-checkbox>
			<label for="chekbox_small" class="clslab">Small size</label>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="checkbox_medium" [size]="medium" ></ej-checkbox>
			<label for="chekbox_medium" class="clslab">Medium size</label>
			</td>
    </tr>
    </table>


{% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {

    constructor() {

    }
}

{% endhighlight %}

Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img4.png) 


## Text

It specifies the text content for **Checkbox**. In previous programs, separate label for each Checkbox is created. You can also set the text for checkbox using **text** property. Therefore, it is not essential to add label tag for each checkbox in **HTML** code.

The following steps explains you the details about rendering the Checkbox with text content and without writing label tag in **HTML** code

In the **HTML** page, add the following input elements to configure **Checkbox** widget.


{% highlight html %}

     <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox  type="checkbox"  class="nodetext" id="checkbox_nonChecked" [(checked)]="uncheckstatus" ></ej-checkbox>
			<label for="chekbox_nonChecked" class="clslab">Music</label>
			</td>
    </tr>
    </table>

{% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
	uncheckstatus:boolean;
    constructor() {
		this.uncheckstatus=false;
    }
}

{% endhighlight %}


Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img5.png) 



## Rounded corner 

Specifies the corner of **Checkbox** in rounded shape. Checkbox doesn’t have rounded corner by default. To set rounded corner, you can enable **showRoundedCorner** property**.**

The following steps explains you the details about rendering the **Checkbox** with rounded corner.

In the **HTML** page, add the following input elements to configure **Checkbox** widget.


  {% highlight html %}

    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox  type="checkbox"  class="nodetext" id="checkbox_normalCorner" [(showRoundedCorner)]="showroundedfalse" ></ej-checkbox>
			</td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="checkbox_roundedCorner" [(showRoundedCorner)]="showroundedtrue"></ej-checkbox>
			</td>
    </tr>
    </table>

  {% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    showroundedfalse: boolean;
    showroundedtrue:boolean;
    constructor() {
        this.showroundedfalse = false;
        this.showroundedtrue=true;
    }
}

{% endhighlight %}


Execute the above code to render the following output.


![](/Angular/Checkbox/Easy-customization_images/Easy-customization_img6.png) 



