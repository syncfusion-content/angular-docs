---
title: Getting Started for CircularGauge
description: How to create a circulargauge, add scales, enable tooltip and other functionalities
platform:js
control:circulargauge
documentation:ug
keywords: ejcirculargauge, circulargauge, circulargauge widget, angular 2 circulargauge
---
#Getting Started

Before we start with the CircularGauge, please refer [this page](https://help.syncfusion.com/angular-2/overview) for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS Reference

To render the CircularGauge control, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [Angular 2](https://angular.io/) - angular 2 latest versions

The other required internal dependencies are tabulated below,

<table>
   <tr>
      <th>
         <b>Files</b>
      </th>
      <th>
         <b>Description/Usage </b>
      </th>
   </tr>
   <tr>
      <td>
         ej.core.min.js
      </td>
      <td>
        It is referred always before using all the JS controls.
      </td>
   </tr>
   <tr>
      <td>
         ej.data.min.js
      </td>
      <td>
         Used to handle data operation and is used while binding data to the JS controls.
      </td>
   </tr>
   <tr>
      <td>
        ej.circulargauge.min.js
      </td>
      <td>
        CircularGauge core script file which includes CircularGauge related scripts files.
      </td>
   </tr>
   <tr>
      <td>
        excanvas.min.js
      </td>
      <td>
        
      </td>
   </tr>
</table>

N> CircularGauge uses one or more script files, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the CircularGauge, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Preparing HTML document

Create an HTML page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

    <html>
    <head>
    <title>Angular 2 CircularGauge</title>

    <!-- Essential Studio for JavaScript  theme reference -->
    <link rel="stylesheet" href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" />

    <!-- Angular2 related script references -->
    <!-- 1. Load libraries -->
         <!-- Polyfill(s) for older browsers -->
    <script src="node_modules/core-js/client/shim.min.js"></script>   
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>

    <!-- Essential Studio for JavaScript  script references -->
    <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/excanvas.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script> 
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    
    <!-- 2. Configure SystemJS -->
    <script src="systemjs.config.js"></script>
    <script>       
      System.import('app')
            .then(null, console.error.bind(console));
    </script>

    </head>
    <!-- 3. Display the application -->
    <body>
    <ej-app>  
		    <div class="splash">
			      <div class="message">Angular 2 Syncfusion Components App</div>
			      <div class="spinner"></div>
		    </div>
	  </ej-app>
    </body>
    </html>

{% endhighlight %}

N> Uncompressed version of library files are also available which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).

## Control Initialization

* Copy CircularGauge Syncfusion Angular 2 source component(s) from the below build location and add it in `src/ej` folder (For ex., consider the `circularGauge` component).

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `circularGauge` folder inside `src` folder.

* Create `circularGauge.component.html` view file inside `src/circularGauge` folder and render ejCircularGauge Angular 2 component using the below code example. 

{% highlight html %}
	<ej-circularGauge id="defaultcircularGauge">
	</ej-circularGauge>
{% endhighlight %}

* Create `circularGauge.component.ts` model file inside the folder `src/circularGauge` and create sample component using the below code example.

{% highlight ts %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/circularGauge/circularGauge.component.html'
})
export class CircularGaugeComponent {

}
{% endhighlight %}

## Configure the routes for the Router

Before adding router configuration for above created ejCircularGauge component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

* Now, we are going to configure the route navigation link for created circularGauge sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#circularGauge" [routerLink]="['/circularGauge']">circularGauge </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejCircularGauge sample component and define the route in `src/app.routes.ts` file.

{% highlight ts %}
import { Routes } from '@angular/router';
. . . . 
import { CircularGaugeComponent } from './circularGauge/circularGauge.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'circularGauge', component: CircularGaugeComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejcircularGauge sample component into `app.module.ts` like the below code snippet.

{% highlight ts %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_CIRCULARGAUGE_COMPONENTS } from './ej/circularGauge.component';
import { CircularGaugeComponent } from './circularGauge/circularGauge.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_CIRCULARGAUGE_COMPONENTS, CircularGaugeComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

## Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to circularGauge tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-started-images/Getting-Started_img1.png) 

## Set Background Color

You can draw the speedometer with dark background and to vary the speed of the pointer, set the **readOnly** option as **False** for user interaction. 

{% highlight javascript %}

 <ej-CircularGauge e-height="500" e-width="500" e-backgroundcolor="##3D3F3D" e-readonly="false">
 </ej-CircularGauge>


{% endhighlight %}


The above code example renders a **Gauge** as shown in the following screen shot.

![](Getting-started-images/Getting-Started_img2.png)

## Provide scale values

* You can customize the pointer cap using the following options- Cap radius, Cap border color, cap background color, pointer cap border width. 

* Set the maximum speed limit in the **Gauge** as 200KmpH.

* Major Ticks and Minor Ticks have the interval values 20 and 5 respectively. Show ranges and show indicators are used to display the ranges and indicators in their respective positions.

{% highlight html %}

 <ej-CircularGauge [height]="500" [width]="500" backgroundColor="#3D3F3D" [readOnly]="false">
     <e-scales>
          <e-scale showRanges="true" showIndicators="true" maximum="200" majorIntervalValue="20" minorIntervalValue="5"
                   pointerCap.radius="15" pointerCap.borderWidth="0" pointerCap.backgroundColor="#797C79" 
                   pointerCap.borderColor="#797C79">
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}



On executing the above code, sample renders a **Circular Gauge** with customized labels as follows.

![](Getting-started-images/Getting-Started_img3.png)

## Add Label Customization

To display the values in the **Gauge,** scale labels are used. You can customize the label color.  

{% highlight html %}

<ej-CircularGauge>
    <e-scales>
       <e-scale>
            <e-labels>
                <e-label color="#ffffff"></e-label>
            </e-labels>
       </e-scale>
     </e-scales>
</ej-CircularGauge>


{% endhighlight %}



On executing the above code, sample renders a default **Circular Gauge** with customized labels as follows.

![](Getting-started-images/Getting-Started_img4.png)

## Add pointer data

You can use three pointers that denote kilometer value, rotation per minute value and torque value.The torque value pointer should not be similar to other two pointers. Set the torque pointer as marker pointer. You can set other attributes for pointer such as background color, border color, Length, width and distance from scale.

{% highlight javascript %}

<ej-CircularGauge>
    <e-scales>
        <e-scale>
            <e-pointers>
               <e-pointer [value]="140" [distanceFromScale]="60" [showBackNeedle]="false" [length]="20" type="marker" markerType="triangle"
                          [width]="10" backgroundColor="#FF940A" border.color="#FF940A">
                </e-pointer>
                <e-pointer [value]="110" [showBackNeedle]="false" [length]="150" [width]="2" needleType="rectangle" 
                           backgroundColor="#05AFFF" border.color="#05AFFF">
                </e-pointer>
                <e-pointer [value]="67" [showBackNeedle]="false" [length]="100" [width]="15" backgroundColor="#FC5D07" border.color="#FC5D07">
                </e-pointer>
             </e-pointers>
        </e-scale>
     </e-scales>
</ej-CircularGauge>


{% endhighlight %}



On executing the above code, sample renders a customized **Circular Gauge** as follows.

![](Getting-started-images/Getting-Started_img5.png)

## Add Tick Details

You can display the tick value with customization as given in the following code example. You can set width and height of the Major ticks greater than the Minor ticks. You can set dark background for tick Color to have a better visibility.

{% highlight html %}

<ej-CircularGauge>
    <e-scales>
        <e-scale>
             <e-ticks>
                <e-tick type="major" [distanceFromScale]="70" [height]="20" [width]="3" color="#ffffff"></e-tick>
                <e-tick type="minor" [distanceFromScale]="70" [height]="12" [width]="1" color="#ffffff"></e-tick>
             </e-ticks>
        </e-scale>
     </e-scales>
</ej-CircularGauge>



{% endhighlight %}



On executing the above code, sample renders a **Circular Gauge** with customized labels as follows.

![](Getting-started-images/Getting-Started_img6.png)

## Add Range Values

Ranges denote the property of scale value in the speedometer. The color values of the ranges specify the speed variation. Set **showRanges** property to **“True”** to show the ranges in the **Circular Gauge**. Select safe zone for low speed, caution zone for moderate speed and high zone for high speed.You can customize the range with the properties such as start value, end value, start width, end width,  background color , border color, etc.,

{% highlight javascript %}

 <ej-CircularGauge e-height="500" e-width="500" e-backgroundcolor="#3D3F3D" e-readonly="false">
    <e-scales>
        <e-scale>
             <e-ranges>
                <e-range [distanceFromScale]="30" [startValue]="0" [endValue]="70" backgroundColor="#5DF243" border.color="#FFFFFF">
                </e-range>
                <e-range [distanceFromScale]="30" [startValue]="70" [endValue]="140" backgroundColor="#F6FF0A" border.color="#FFFFFF">
                </e-range>
                <e-range [distanceFromScale]="30" [startValue]="140" [endValue]="200" backgroundColor="#FF1807" border.color="#FFFFFF">
                </e-range>
            </e-ranges>
        </e-scale>
     </e-scales>
</ej-CircularGauge>


{% endhighlight %}



On executing the above code, sample renders a **Circular Gauge** with customized range as follows.

![](Getting-started-images/Getting-Started_img7.png)

