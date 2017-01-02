---
layout: post
title: Getting Started | Button | Angular2 | Syncfusion
description: getting started
platform: angular2
control: Button
documentation: ug
---

# Getting Started

This section explains the details on how to render and configure a Button component in an Angular2 application.

To get started, you need to refer the basic prerequisites and system configuration to be done form the given [getting started](https://help.syncfusion.com/angular2/overview) document

Once you have cloned the sample angular2 application as mentioned in getting started document, you will have an angular application named **angular2-seeds** and the application is now ready integrate our EJ components in it. 

## Copying Button source file

Copy the required Angular2 source components file from the installed location and move it to the app/src/ej folder available inside the angular2-seeds folder.

(Installed Location)\Syncfusion\Essential Studio\{installed version}\JavaScript\assets-src\angular2\ 

> _Note:_ _core.ts file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49._

## Adding Button component

1. Create a folder named Button inside the app folder.

2. Create a new file and name it as "Button.Component" with "html" extension and add the Button component in it as given below. 

{% highlight html %}

<input type="button" ej-button id="button" value="Button" />

{% endhighlight %} 

3. Create a Model file named "Button.component" with "ts" extension inside "Button" folder created in step 1.

4. Now, define the **ej-app** component and Button Model class inside the Model file created in the above step.

{% highlight JS %}

import { Component, ViewEncapsulation} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {

    constructor() {}
}

{% endhighlight %}

5. To Run the application, execute the below commands in the command prompt window. 

{% highlight JS %}

npm install
npm start 

{% endhighlight %}



### Configuring Button

This section encompasses the details on how you can configure the Button control in your application and customize it with various properties such as various size based on your requirement.
To modify the size of the Button and rename the button, add the following snippet in your app.coponent.html file.

{% highlight html %}
<table>
    <tr>
        <td >My First Button</td>
        <td>
            <input type="button" ej-button id="button" [text]="text" />
        </td>
    </tr>
</table>



{% endhighlight %}

To render the text and size properties add the following snippet in your TS file.

{% highlight JavaScript %}

export class AppComponent {
    text: string;
    constructor() {
        this.text = "Button";
    }

{% endhighlight %}

Browse the port where your application is hosted and navigate to Button tab to see the output. 


![](!Getting-Started_images/Getting-Started_img1.JPG)