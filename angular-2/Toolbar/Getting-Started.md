---
layout: post
title: Getting-Started | Toolbar | JavaScript | Syncfusion
description: getting started
platform: js
control: Toolbar
documentation: ug
keywords: ejtoolbar, toolbar, js toolbar 
---

# Getting Started

This section explains briefly about how to create a **Toolbar** in your application with **JavaScript.**

## Create Toolbar for PDF Reader

**Toolbar** control supports displaying a list of tools in a Web page. This control is capable of customizing toolbar items with any functionality by using enriched **client-side** methods. This control consists of a collection of **unordered lists** contains text and images into a **&lt;div&gt;.** From the following section, you can learn how to customize **toolbar** control for a **PDF reader** scenario. The following screen shot shows the appearance of **toolbar** in **PDF reader** simulator application.

![](/js/Toolbar/Getting-Started_images/Getting-Started_img1.png) 

## Create Toolbar control

The **Essential JavaScript Toolbar** control can be easily configured with **HTML &lt;DIV&gt;** and **&lt;UL&gt;&lt;LI&gt;** elements. The basic rendering of **Essential JS Toolbar** is achieved by the default functionality.
 
Create an HTML file and add the following template into the **HTML** file for **Toolbar** creation.

{% highlight html %}

<!DOCTYPE html>
<html>
   <head> 
    <link href="//cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js">
    </script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    <script src="systemjs.config.js"></script>
  </head>
  <body>
   <ej-app>Loading...</ej-app>
  </body>
</html>

{% endhighlight %}
 
Add toolar tag for **Toolbar** rendering.
 
{% highlight html %}

<ej-toolbar  id="toolbaritem"></ej-toolbar>

{% endhighlight %}

Initialize the Toolbar in script

To render the ejToolbar using angular directive, we need to inject the ej angular directive with modules shown as below,

{% highlight js %}

import {Component,ViewEncapsulation} from '@angular/core';
import {encapsulation} from '@angular/core'; 
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/toolbar/toolbar.component.html'
})
export class ToolBarComponent { 
}

{% endhighlight %}

Output of the above steps

![](/js/Toolbar/Getting-Started_images/Getting-Started_img2.png)

## Initialize Toolbar Items

**Toolbar** consists of a list of items. From the following section, you can learn how to initialize the toolbar items with **UL LI** template. 							

Initialize the Toolbar items with **UL LI** template as follows. 

{% highlight html %}

<ej-toolbar  [dataSource]="data" id="toolbar" [fields]="fieldsvalues"  [enableSeparator]="separator" width="250px"></ej-toolbar>

{% endhighlight %}

Apply the given styles in the code table to show the **toolbar items** as follows. You can refer images from any location. In the following code sample, the images are referred from the given location.

[http://js.syncfusion.com/UG/Web/Content/](http://js.syncfusion.com/UG/Web/Content/)

{% highlight css %}

<style type="text/css" class="cssStyles">

        .e-tooltxt .mailtools {
            background-image: url('app/content/images/toolbar/maild.png');
        } 
        .e-tooltxt .mailtools {
            display: block;
            background-image: url('app/content/images/toolbar/maill.png');
            height: 24px;
            width: 24px;
            background-repeat: no-repeat;
        } 
        .e-tooltxt:hover .mailtools, .darktheme .cols-sample-area .e-tooltxt:hover .mailtools {
            background-image: url('app/content/images/toolbar/mailh.png');
        } 
        .mailtools.done {
            background-position: -11px -140px;
        } 
        .mailtools.movetofolder {
            background-position: -12px -40px;
        } 
        .mailtools.categorize {
            background-position: -14px -248px;
        } 
        .mailtools.flag {
            background-position: -13px -282px;
        } 
        .mailtools.forward {
            background-position: -14px -314px;
        } 
        .mailtools.newmail {
            background-position: -14px -348px;
        } 
        .mailtools.reply {
            background-position: -14px -388px;
        } 
        .frame {
            height: 280px;
            width: 695px;
            border-radius: none;
            margin-left: 0;
            margin-top: 40px;
            padding: 0;
        }

        .control {
            margin: 120px 200px 0;
        }

</style>

{% endhighlight %}

After updating the **Toolbar** **items** with their **CSS** styles, you can render the toolbar inside **&lt;script&gt;** tag.

{% highlight javascript %}

import {Component,ViewEncapsulation} from '@angular/core';
import {encapsulation} from '@angular/core'; 
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/toolbar/toolbar.component.html',
  styleUrls: ['app/components/toolbar/toolbar.component.css'],encapsulation: ViewEncapsulation.None
})
export class ToolBarComponent {
	fieldsvalues:object;
	data:array;
	separator:boolean;
    constructor() {
	this.data =  [
   {
       empid: "1", tooltiptext:"New mail",
       spriteCss: "mailtools movetofolder",

   }, {
       empid: "2", tooltiptext:"Calendar",
       spriteCss: "mailtools categorize",

   }, {
       empid: "3",tooltiptext:"Appointments",
       spriteCss: "mailtools flag",

   }, {
       empid: "4",tooltiptext:"Week",
       spriteCss: "mailtools forward",

   }, {
       empid: "5",tooltiptext:"Month",
       spriteCss: "mailtools newmail",

   },
    {
        empid: "6",tooltiptext:"Notes",
        spriteCss: "mailtools reply",

    },
    {
        empid: "7",tooltiptext:"Deleted",
        spriteCss: "mailtools done",

    }
        ];

	this.separator = true;
	
	this.fieldsvalues = {tooltipText:"tooltiptext",id:"empid", spriteCssClass:"spriteCss"};
	}
}

{% endhighlight %}

Execute the code to render a toolbar with a list of **toolbar items**.

![](/js/Toolbar/Getting-Started_images/Getting-Started_img3.png)

Toolbar with list of toolbar items
{:.caption}

## Render remaining Toolbar items

In the above output only few **toolbar items** are rendered, but you need to render all the **toolbar items** to achieve the requirements. You can separate or group the toolbar items. The separation or grouping of toolbar items is achieved when you give toolbar items as a list of **UL LI** values inside the toolbar **&lt;div&gt;** or **span** element. From the following section, you can learn how to initialize the remaining toolbar items with **UL LI** template and how to group the toolbar items. 

Initialize the Toolbar items with **UL LI** template as follows.

{% highlight html %}
    
<ej-toolbar  [dataSource]="data" id="toolbar" [fields]="fieldsvalues"  [enableSeparator]="separator" width="250px"></ej-toolbar>


{% endhighlight %}

Add the following styles in the code table to display the toolbar items as follows. 

{% highlight css %}

<style> 

      .e-tooltxt .mailtools {
            background-image: url('app/content/images/toolbar/maild.png');
        }
        .e-tooltxt .mailtools {
            display: block;
            background-image: url('app/content/images/toolbar/maill.png');
            height: 24px;
            width: 24px;
            background-repeat: no-repeat;
        }
        .e-tooltxt:hover .mailtools, .darktheme .cols-sample-area .e-tooltxt:hover .mailtools {
            background-image: url('app/content/images/toolbar/mailh.png');
        }
        .mailtools.done {
            background-position: -11px -140px;
        }
        .mailtools.movetofolder {
            background-position: -12px -40px;
        }
        .mailtools.categorize {
            background-position: -14px -248px;
        }
        .mailtools.flag {
            background-position: -13px -282px;
        }
        .mailtools.forward {
            background-position: -14px -314px;
        }
        .mailtools.newmail {
            background-position: -14px -348px;
        }
        .mailtools.reply {
            background-position: -14px -388px;
        } 
        .frame {
            height: 280px;
            width: 695px;
            border-radius: none;
            margin-left: 0;
            margin-top: 40px;
            padding: 0;
        }
        .control {
            margin: 120px 200px 0;
        }

 </style>
 
{% endhighlight %}

After updating the Toolbar items with their **CSS** styles, you can render the toolbar inside the **&lt;script&gt;** tag and also need to render the drop down list control for **select zoom value**. Basically, dropdown list control is rendered with input element. **Set Zoom value** is one of the items in the toolbar. The following code example shows how to render and initialize **drop down control** with list of **zoom values**.

{% highlight javascript %}
  
import {Component,ViewEncapsulation} from '@angular/core';
import {encapsulation} from '@angular/core'; 
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/toolbar/toolbar.component.html',
  styleUrls: ['app/components/toolbar/toolbar.component.css'],encapsulation: ViewEncapsulation.None
})
export class ToolBarComponent {
	fieldsvalues:object;
	data:array;
	separator:boolean;
    constructor() {
	this.data =  [
   {
       empid: "1", tooltiptext:"New mail",
       spriteCss: "mailtools movetofolder",

   }, {
       empid: "2", tooltiptext:"Calendar",
       spriteCss: "mailtools categorize",

   }, {
       empid: "3",tooltiptext:"Appointments",
       spriteCss: "mailtools flag",

   }, {
       empid: "4",tooltiptext:"Week",
       spriteCss: "mailtools forward",

   }, {
       empid: "5",tooltiptext:"Month",
       spriteCss: "mailtools newmail",

   },
    {
        empid: "6",tooltiptext:"Notes",
        spriteCss: "mailtools reply",

    },
    {
        empid: "7",tooltiptext:"Deleted",
        spriteCss: "mailtools done",

    }
        ];
	this.separator = true;
	this.fieldsvalues = {tooltipText:"tooltiptext",id:"empid", spriteCssClass:"spriteCss"};
	}
}
 
{% endhighlight %}

Execute the code to render a **toolbar items** with separator.

![](/js/Toolbar/Getting-Started_images/Getting-Started_img4.png)

## Add Actions to Toolbar Items

Now the **toolbar** is rendered so you need to render the header and content area to create a **PDF reader**. From the following section, you can learn how to render the **header** (Toolbar), **content****section** (PDF viewer area) and how to set the action to toolbar items.

You are not going to deal with PDF reading or rendering task here. You will only simulate the PDF Reader app to demonstrate the Toolbar control usage and will completely ignore the PDF rendering area.

Initialize the content area and header as specified in the code table.

{% highlight html %}

  <!-- control class used for aligns the pdf reader in center of a page. -->
<div class="control">
 <div class="ctrllabel"></div>
   <!-- Here Initialize the Toolbar items as like above code sample -->  
	<ej-toolbar  [dataSource]="data" id="toolbar" [fields]="fieldsvalues"  [enableSeparator]="separator" width="634px"></ej-toolbar>   
   <div id="contentSection">
      <textarea id="content" rows="10" cols="30"> 
      Description:
      Toolbar control supports displaying a list of tools within a Web page.This control is capable of 
      customizing toolbar items with any functionality by using enriched client-side methods.This control 
      is composed of collection of unordered lists containing text and images contained into a div.
      </textarea>
   </div>
</div>

{% endhighlight %}

You can apply the following styles with the above styles to design the **PDF header** and **content area**. The desired output is shown as follows.

{% highlight css %}

<style type="text/css" class="cssStyles">

        #content {
            float: left;
            height: 300px;
            width: 628px;
            position: absolute;
        }

        .control {
            margin: 110px 320px 0;
            position: relative;
        }

        .ctrllabel {
            background-image: url("http://js.syncfusion.com/UG/Web/Content/pdf-header.png");
            background-repeat: no-repeat;
            width: 634px;
            height: 32px;
        }

</style>

{% endhighlight %}

Execute the given code to render a **PDF reader** as follows.

![](/js/Toolbar/Getting-Started_images/Getting-Started_img6.png) 





