---
layout: post
title: Custom Buttons
description: Custom Buttons
platform: Angular
control: Button
documentation: ug
---
# Custom Buttons

Essential Angular Button control has an option of using normal ejButton as **Custom Button** to give visual weight to ejButton which helps user interface to notify and differentiate the priority action button with the other normal buttons.

Custom Buttons includes six predefined button styles and each button indicates unique sign of action to the user.

List of Custom Buttons

<table>
   <tr>
      <th>Button Types</th>
      <th>Class</th>
      <th>Description</th>
   <tr>
      <td>Primary Button</td>
      <td>e-primary</td>
      <td>Provides extra visual weight and identifies the primary action in a set of buttons</td>
  </tr>
   <tr>
      <td>Link Button</td>
      <td>e-link</td>
      <td>Deemphasize a button by making it look like a link while maintaining button behavior.</td>
  </tr>
   <tr>
     <td> Success Button</td>
      <td>e-success</td>
      <td>Indicates a successful or positive action.</td>
   </tr>
   <tr>
      <td> Information Button</td>
      <td>e-info</td>
      <td>Indicates a informative sign action to user</td>
   </tr>
   <tr>
   <td>Warning Button</td>
   <td>e-warning</td>
   <td>Indicates the warning action.</td>
   </tr>
   <tr>
   <td>Danger Button</td>
   <td>e-danger</td>
   <td>Indicates the danger sign action to user.</td>
   </tr>
</table>

To customize ejButton as anyone type of custom Buttons ,assign CSS class name of the custom button (For Ex:**e-success**) to cssClass property of ejButton.

The following steps explains you the details about customizing normal ejButton with above mentioned button types.

{% highlight html %}

    <table width="500px">
    <tr>
        <td>
            <input id="PrimaryBtn" cssClass='e-primary' size="medium" [showRoundedCorner]="true" contentType="textandimage"  type="button" text="Primary" ej-button/> 
			 <td>
            <input id="DangerBtn" cssClass='e-danger' size="medium" [showRoundedCorner]="true" contentType="textandimage"  type="button" text="Danger" ej-button/> 
			 <td>
            <input id="InfoBtn" cssClass='e-info' size="medium" [showRoundedCorner]="true" contentType="textandimage" type="button" text="Information" ej-button/> 
			 <td>
            <input id="WarningBtn" cssClass='e-warning' size="medium" [showRoundedCorner]="true" contentType="textandimage"  type="button" text="Warning" ej-button/> 
			 <td>
            <input id="SuccessBtn" cssClass='e-success' size="medium" [showRoundedCorner]="true" contentType="textandimage"  type="button" text="Success" ej-button/> 
			 <td>
            <input id="LinkBtn" cssClass='e-link' size="medium" [showRoundedCorner]="true" contentType="textandimage"  type="button" text="Link" ej-button/> 
    </tr>
    </table>

    <style>
    .frame {
            margin: auto;
            width: 400px;
        }

        .control .btnsht {
            width: 125px;
            display: inline-block;
        }
        .e-btn.e-select.e-btn-medium{
            width:115px;
        }

    </style>

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

![](Custom-Buttons_images/custom_buttons.png) 

## Image in Button  

The **Essential Studio for Angular** has an option of using custom image in a button by assigning a CSS class with background-image to prefixIcon or suffixIcon property of ejButton.Please,refer the following below steps.

Create a custom CSS class with background-image property. Use the following syntax to apply class names.  

**Syntax**: .e-icon .e-[icon name]

{% highlight html %}

    <table width="500px">
    <tr>
        <td>
            <button id="button" size="large" [showRoundedCorner]="true" contentType="textandimage"  prefixIcon="e-icon e-profile" type="button" text="Profile" ej-button></button> 
    </tr>
    </table>

    <style>
    .e-icon .e-profile{
        background-image: url('profile.png');
    }
    </style>

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

Now,assign this custom CSS class name to prefixIcon or suffixIcon property of the ejButton.


Execute the above code to render the following output.

![](Custom-Buttons_images/profile.png)



