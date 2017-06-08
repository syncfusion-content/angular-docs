---
layout: post
title: Getting Started | RadioButton | Angular | Syncfusion
description: getting started
platform: Angular
control: RadioButton
documentation: ug
---

# Getting Started

This section explains the details on how to render and configure a **RadioButton** component in an Angular-2 application.

To get started with **RadioButton** component, refer the basic prerequisites and system configuration to be done form the given [getting started](https://help.syncfusion.com/Angular/overview) document.

Once you have cloned the sample Angular-2 application as mentioned in getting started document, you will have an angular application named **Angular-seeds** and is now ready use our EJ components with it. 

## Copying RadioButton source file

Copy the required Angular-2 source components file from the installed location and move it to the app/src/ej folder available inside the Angular-seeds folder.

(Installed Location)\Syncfusion\Essential Studio\{installed version}\JavaScript\assets-src\Angular\ 

> _Note:_ _core.ts file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49._

## Adding RadioButton component

1.Create a folder named "RadioButton" inside app folder.

2.Create a View file and name it as "RadioButton.component" with "html" extension and add the **RadioButton** component in it as given below. 

{% highlight html %}

      <div>
        <br />
        Category
        <br />
        <br />
        <table>
            <tr>
                <td colspan="2">
                    <input id="fresher" ej-radiobutton text="Fresher" name="category" value="fresher" />
                </td>
                <td>
                    <input id="exp" ej-radiobutton text="Experienced" name="category" value="experienced" [{checked}]="checked" />
                </td>
            </tr>
        </table>
        <br />
        <br />
        Experienced
        <br />
        <br />
        <table>
            <tr>
                <td>
                    <input id="exp1" ej-radiobutton e-text="1+ years" name="experience" value="1+years" [{checked}]="checked" />
                </td>
                <td colspan="2">
                    <input id="exp2" ej-radiobutton text="2.5+ years" name="experience" value="2+years" />
                </td>
                <td colspan="2">
                    <input id="exp5" ej-radiobutton text="5+ years" name="experience" value="5+years" />

                </td>
            </tr>
        </table>
     </div>

{% endhighlight %} 

3.Create a Model file named "RadioButton.component" with "ts" extension inside "RadioButton" folder created in step 1.

4.Now, define the **ej-app** component and RadioButton Model class inside the Model file created in the above step.

{% highlight JS %}

@Component({
     selector: 'ej-app',
     templateUrl: 'app/app.component.html',
})
export class AppComponent {
     checked: Boolean;
     constructor() {
     this.checked = true;
     }
}

{% endhighlight %}

5.To Run the application, execute the below commands in the command prompt window. 

{% highlight JS %}

npm install
npm start 

{% endhighlight %}

6.Browse the port where your application is hosted and navigate to RadioButton tab to see the output. 

![](Getting-Started_images/two-way.png)

### Databinding

With the above steps you have rendered a simple **RadioButton** component with the value set in initial rendering. 

Now, to bind the model values to the **RadioButton** component, define the model values in the **AppComponent** class available in RadioButton.component.ts file as given below.

{% highlight html %}
 <div>
        <br />
        Category
        <br />
        <br />
        <table>
            <tr>
                <td colspan="2">
                    <input id="fresher" ej-radiobutton text="Fresher" name="category" value="fresher" [{checked}]="category" />
                </td>
                <td>
                    <input id="exp" ej-radiobutton text="Experienced" name="category" value="experienced" [{checked}]="category" />
                </td>
            </tr>
        </table>
        <br />
        <br />
        Experienced
        <br />
        <br />
        <table>
            <tr>
                <td>
                    <input id="exp1" ej-radiobutton e-text="1+ years" name="experience" value="1+years" [{checked}]="experience" />
                </td>
                <td colspan="2">
                    <input id="exp2" ej-radiobutton text="2.5+ years" name="experience" value="2+years" [{checked}]="experience" />
                </td>
                <td colspan="2">
                    <input id="exp5" ej-radiobutton text="5+ years" name="experience" value="5+years" [{checked}]="experience" />

                </td>
            </tr>
        </table>
   </div>

{% endhighlight %}

{% highlight JS %}

@Component({
     selector: 'ej-app',
     templateUrl: 'app/app.component.html',
})
export class AppComponent {
     category: string;
     experience: string;
     constructor() {
        this.category = "experienced";
        this.experience = "1+years";
     }
}  

{% endhighlight %}

Execute the above code to get the following output

![](Getting-Started_images/two-way.png)