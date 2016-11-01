---
title: Getting started with Schedule component	
description: Rendering a basic Scheduler with local data
platform: Angular-2
control: schedule
documentation: ug
keywords: ejschedule, schedule, schedule widget
---

# Getting Started

To get start with how to use the Scheduler component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](/angular-2/overview).

Once the configurations are done, run the below commands in the command prompt to clone the repository for `SystemJS` starter and to install the required dependency packages automatically.

{% highlight html %}

    > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs
    > cd angular2-seeds
    > npm install
 
{% endhighlight %}

Once the cloned seed application is created, now it is ready to make use of any of our Syncfusion components within it.

## Copying Scheduler source file

Copy the required `schedule.component.ts` source file from the following location and add it under the **src/ej** folder within the newly cloned **angular2-seeds** folder.

* (**Installed location**)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\

N> `core.ts` source file is mandatory for all Syncfusion JavaScript Angular 2 components. 

## Adding Scheduler HTML file

Create a folder named **schedule** within the **src** folder. Now, create a html file and name it as **schedule.component.html** under the _src/schedule_ folder. Place the Scheduler rendering code within this file as depicted below,

{% highlight html %}

    <ej-schedule id="Schedule1" width="100%" height="525px" currentView="week" currentDate="5/4/2014">
    </ej-schedule>

{% endhighlight %}

## Data-binding

The above code example creats an empty Scheduler with no data bind to it. To bind specific appointment data on the Scheduler, then the **dataSource** property needs to be defined as shown below.

{% highlight html %}

    <ej-schedule id="Schedule1" width="100%" height="525px" currentView="week" currentDate="5/4/2014"
        [appointmentSettings.dataSource]=scheduleData >
    </ej-schedule> 

{% endhighlight %} 

Create a **schedule.component.ts** file under the same **src/schedule** folder, where the schedule model data needs to be defined and passed to the Scheduler dataSource.

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %}

## Configure the Router and Navigation

Configure the route navigation link for the newly created Scheduler sample within the **src/app.component.html** file as shown below,

{% highlight html %}

	<ul class="nav navbar-nav">
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#" [routerLink]="['/']">Syncfusion Angular 2</a></li>
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#home" [routerLink]="['/home']">Home</a></li>
        <!-- Schedule sample navigation link -->
        <li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#schedule" [routerLink]="['/schedule']">Schedule</a></li>
	</ul>

{% endhighlight %}

Now, import and define the Schedule sample's route within the **src/app.routes.ts** file as shown below,

{% highlight ts %}

    import { Routes } from '@angular/router';
    import { ScheduleComponent } from './schedule/schedule.component'; // imports Schedule component
    import { HomeComponent } from './home/home.component';

    export const rootRouterConfig: Routes = [
        { path: '', redirectTo: 'home', pathMatch: 'full' },
        { path: 'home', component: HomeComponent },
    	{ path: 'schedule', component: ScheduleComponent } // Schedule sample path
    ];


{% endhighlight %}

Now, finally make sure to import and declare the Scheduler's source and sample component files into the **app.module.ts** as shown in the below code snippet.

{% highlight ts %}
    
    // imports the Scheduler's source and sample component files
    import { AppComponent } from './app.component';
    import { HomeComponent } from './home/home.component';

    import { EJ_SCHEDULE_COMPONENTS } from './ej/schedule.component';
    import { ScheduleComponent } from './schedule/schedule.component';
    
    import { rootRouterConfig } from './app.routes';
    
    // Declare the source and sample files here in this module declaration part
    @NgModule({
        imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
        declarations: [AppComponent, HomeComponent, EJ_SCHEDULE_COMPONENTS, ScheduleComponent],
        bootstrap: [AppComponent]
    })

{% endhighlight %}

## Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **Schedule** tab to view the Scheduler output.



