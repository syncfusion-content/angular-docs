---
layout: post
title: Getting Started | CheckBox | Angular2 | Syncfusion
description: getting started
platform: Angular
control: CheckBox
documentation: ug
---

# Getting Started

This section explains the details on how to render and configure a **CheckBox** component in an Angular-2 application.

To get started with **CheckBox** component, you need to refer the basic prerequisites and system configuration to be done form the given [getting started](https://help.syncfusion.com/angular2/overview) document.

Once you have cloned the sample Angular-2 application as mentioned in getting started document, you will have an angular application named **angular2-seeds** and the application is now ready integrate our EJ components in it. 

## Copying CheckBox source file

Copy the required Angular-2 source components file from the installed location and move it to the app/src/ej folder available inside the angular2-seeds folder.

(Installed Location)\Syncfusion\Essential Studio\{installed version}\JavaScript\assets-src\angular2\ 

> _Note:_ _core.ts file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49._

## Adding CheckBox component

1.Create a folder named "CheckBox" inside the app folder.

2.Create a new file and name it as "Checkbox.Component" with "html" extension and add the **CheckBox** component in it as given below. 

{% highlight html %}

<div>
     Hobbies <br /><br />
     <table>
        <tr>
            <td>
                <ej-checkbox id="Checkbox1" [{checked}]="checked" size="small" text="Music"></ej-checkbox>
            </td>
            <td>
                <ej-checkbox id="Checkbox2" size="small" text="Sports"></ej-checkbox>
            </td>
            <td>
                <ej-checkbox id="Checkbox3" size="small" text="Bike Riding"> </ej-checkbox>
            </td>
        </tr>
     </table><br /><br />
     Favorite Search Engines<br /><br />
     <table>
        <tr>
            <td>
                <ej-checkbox id="Checkbox4" size="medium" [{checked}]="checked" text="Google"></ej-checkbox>
            </td>
            <td>
                <ej-checkbox id="Checkbox5" size="medium" text="Yahoo"> </ej-checkbox>
            </td>
            <td>
                <ej-checkbox id="Checkbox6" size="medium" text="Bing"> </ej-checkbox>
            </td>
        </tr>
     </table>
</div>

{% endhighlight %} 

3.Create a Model file named "CheckBox.component" with "ts" extension inside "CheckBox" folder created in step 1.

4.Now, define the **ej-app** component and CheckBox Model class inside the Model file created in the above step.

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

6.Browse the port where your application is hosted and navigate to CheckBox tab to see the output. 

![](Getting-Started_images/default.png)

### Databinding

To bind the model values to the **CheckBox** component, define the model values in the **AppComponent** class available in CheckBox.component.ts file as given below.

{% highlight HTML %}

<div>
                Hobbies <br /><br />
                <table>
                    <tr>
                        <td>
                            <ej-checkbox id="Checkbox1" [{checked}]="hobbies" size="small" text="Music" name="music" value="music"></ej-checkbox>
                        </td>
                        <td>
                            <ej-checkbox id="Checkbox2" [{checked}]="hobbies" size="small" text="Sports" name="sports" value="sports"></ej-checkbox>
                        </td>
                        <td>
                            <ej-checkbox id="Checkbox3" [{checked}]="hobbies" size="small" text="Bike Riding" name="bike" value="bike"> </ej-checkbox>
                        </td>
                    </tr>
                </table><br /><br />
                Favorite Search Engines<br /><br />
                <table>
                    <tr>
                        <td>
                            <ej-checkbox id="Checkbox4" size="medium" [{checked}]="search_engines" text="Google" name="google" value="google"></ej-checkbox>
                        </td>
                        <td>
                            <ej-checkbox id="Checkbox5" size="medium" [{checked}]="search_engines" text="Yahoo" name="yahoo" value="yahoo"> </ej-checkbox>
                        </td>
                        <td>
                            <ej-checkbox id="Checkbox6" size="medium" [{checked}]="search_engines" text="Bing" name="bing" value="bing"> </ej-checkbox>
                        </td>
                    </tr>
                </table>
            </div>

{% endhighlight %}

Define the Model class as given below.

{% highlight JavaScript%}

export class AppComponent {
     hobbies: Array<string>;
     search_engines: Array<string>;
     constructor() {
        this.hobbies = ["music", "sports"];
        this.search_engines = ["google"];
    }
}
 

{% endhighlight %}

Execute the above code to get the following output.

![](Getting-Started_images/two-way.png)