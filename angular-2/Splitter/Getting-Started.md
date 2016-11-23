---
layout: post
title: Getting-Started
description: getting started
platform: angular2
control: Splitter
documentation: ug
---

# Getting Started

This section helps to get started of the Splitter component in an Angular2 application.

![](Getting_Started_images/Getting_Started_img1.png) 

## Create a Splitter

The following steps guide you to add a Splitter component.

To get start with how to use the Splitter component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/overview).

Create a simple Splitter by adding ej-splitter attribute for initializing an empty Splitter component on the application. 

{% highlight html %}
  
    <ej-splitter id="outterSpliter" class="ang-splitter" e-height ="100%" e-width="485" e-properties="proper" e- enableautoresize="true">
    </ej-splitter>


{% endhighlight %}

> _Note:_ _You can find the Splitter properties from the_ [API reference](https://help.syncfusion.com/api/js/ejsplitter) _document__

## Configure Splitter Panes

To configure properties for Splitter component, define properties in the component’s constructor file.

{% highlight ts %}

    export class AppComponent {
        proper:Array<{paneSize:string}>;     
        constructor() {
        this.proper = [{ paneSize: "50%" }, {paneSize:"50%"}]    
        }
    }

{% endhighlight %}

Now assign the defined variables to paneSize properties. Add required properties to the component.

{% highlight html %}

    <ej-splitter id="outterSpliter" class="ang-splitter" e-height ="100%" e-width="485" e-properties="proper" e- enableautoresize="true">
    </ej-splitter>

{% endhighlight %}

Configure the Splitter panes with images. Save the images in the corresponding location.

{% highlight html %}

    <div class="cols-sample-area" style="height:400px; margin:0 auto;">
    <ej-splitter id="outterSpliter" class="ang-splitter" e-height ="100%" e-width="485" e-properties="proper"  e-enableautoresize="true">
    <div>
    <div class="cont">
    <h3 class="h3">AngularJS</h3>    
    </div>
    </div>
    <div class="cont">
    <div class="_content">
    Select any product from the tree to show the description.
    </div>
    <div class="mobile spe" style="display:none">
    <h3>Mobile</h3>
    <img src="app/content/images/Splitter/mobile.jpeg" />
    </div>
    <div class="harddisk spe" style="display:none">
    <h3>Harddisk</h3>
    <img src="app/content/images/Splitter/harddisk.jpg" />
    </div>
    <div class="logo spe" style="display:none">
    <h3>Logo</h3>
    <img src="app/content/images/Splitter/logo.png" />
    </div>
    </div>
    </ej-splitter>
    </div>

{% endhighlight %}

## Configure Tree View 

For adding Treeview component, you have to use **ej-treeview** directive to corresponding element. You need to use **nodeSelect** event handler to perform any action while selection the node in Tree view.
Add the following code example in HTML file to configure Tree View.

{% highlight html %}

    <ej-treeview  class="visibleHide" (nodeSelect)= "treeClicked($event)"  [fields]= "fields" >           
    </ej-treeview>

{% endhighlight %}

To configure “li” contents for Splitter component, define “li” contents in an object array and fields in the component’s constructor file.

{% highlight ts %}

    export class AppComponent {
        localData:Array<{}>;
        fields:Object;
        constructor() {
        this.localData=[
        { id: 1, name: "Mobile", hasChild: true, expanded: false },
        { id: "mobile", pid:1,name: "Galaxy"},
        { id: 3, name: "Harddisk", hasChild: true, expanded: false },
        { id: "harddisk", pid:3,name: "Segate"},
        { id: 5, name: "Logo", hasChild: true, expanded: false },
        { id: "logo", pid:5,name: "Amazon"},
        ];
        this.fields = { id: "id", parentId: "pid", text: "name", hasChild: "hasChild", dataSource: this.localData, expanded: "expanded" };
        }
        }
    }

{% endhighlight %}

## Set Actions

Add the **nodeSelect** event in component constructor’s file to set the action to view the images for “li” content of the Tree view.

{% highlight ts %}

    export class AppComponent {
        treeClicked(sender){        
        if (sender.currentElement.hasClass('e-item last')) {
                    var content = $('.' + sender.currentElement[0].id).html();
                    $('._content').html(content);        
        }
        }
    }

{% endhighlight %}

