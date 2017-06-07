---
layout: post
title: Working with content related operation in RichTextEditor widget
description: Working with Content related changes in RichTextEditor widget
platform: Angular
control: RichTextEditor
documentation: ug
---
# Working with Content

The editor creates the iframe element as the content area on control initialization, it is used to display and editing the content. In Content Area, the editor displays only the body tag of a &lt; iframe &gt; document. To set or modify details in the &lt; head &gt; tag, use [Source view](#footer#source-view) of the editor.

## Iframe Attributes

The editor allows you to passing an additional attributes to body tag of a &lt; iframe &gt; element using [iframeAttributes](http://help.syncfusion.com/api/js/ejrte#members:iframeattributes) property. The property contains name/value pairs in string format, it is used to override the default appearance of the content area. 

N> the content area’s font, color, margins, and background can be overridden using iframeAttributes property. You can specifies the editable behavior (content editable) of the content also in this property.

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [iframeAttributes]="styles"></textarea>
 
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    styles: any;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images, it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.styles = { style: "background-color:#e0ffff;color:#6495ed;" };
    }
}

{% endhighlight %}

N> We can set background image for the RTE control and also default font for the Iframe using iframeAttributes.


## Adding External CSS File

The editor offers you to add external CSS file to style the &lt; iframe &gt; element.  Easily change the appearance of editor’s content using an external CSS file. For example, apply default styles for headings (h1, h2, etc.) and lists (bulleted or numbered) of the editor’s content. 

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val"></textarea>

//Add the below code in the required event in order to add externaal css file.
<script>
        var editor = $("#texteditor").ejRTE("instance");
        var iframeDoc = editor.getDocument();
        var linkTag = document.createElement("link");
        linkTag.type = "text/css";
        linkTag.rel = "stylesheet";
        linkTag.href = "Content/Css/iframe-custom.css";
        iframeDoc.head.appendChild(linkTag);
</script>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images, it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
}

{% endhighlight %}

The new file named iframe-custom.css is created and moved to the content folder with the following styles.

{% highlight html %}

h1 {
    color: navy;
    margin-left: 20px;
}

ul { 
    display: block;
    list-style-type: square;
    margin-left: 10px;
}

ol {
    display: block;
    list-style-type: circle;
    margin-right: 10px;
}

{% endhighlight %}

N> Our RTE control editor section is an iframe. An iframe has another scope, so we can't access it to style using class which is defined in main document. To set the styles for the contents that kept inside the editor(iframe) we have to append the styles link in iframe head section.

## Content Editable

The editor provides option to control the editable behavior using [allowEditing](http://help.syncfusion.com/api/js/ejrte#members:allowediting) property. When the allowEditing property is set to false, the editor disables its editing functionality. 

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [allowEditing]="false"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
}

{% endhighlight %}

The contentEditable attribute allows you to make any element of HTML content to become editable or non-editable.  

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" (create)="onCreate($event)"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "<p>The RichTextEditor (RTE) control enables you to edit the contents with insert table and images,</p>" + "<p> it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.</p>";
    } 
    onCreate(event){
        var editor = $("#texteditor").ejRTE("instance");
        var iframeDoc = editor.getDocument();
        var paragraph = $("p", iframeDoc.body);
        $($(paragraph)[1]).attr("contenteditable", "false");
    }
}

{% endhighlight %}

N> Content editable is fully compatible with latest browsers, to know more details, see [here](http://www.w3schools.com/tags/att_global_contenteditable.asp#).

## Submit Content

The editor allows you to process its content before it is being submitted to the server on form submit event. You can use this option to validate content on the client side to prevent invalid data from being submitted to the server.

This example shows how to encode the HTML content before form submit event.

{% highlight html %}

<form (ngSubmit)="onSubmit()">
    <textarea id="texteditor" ej-rte [value]="val"></textarea>
    <button type="submit" class="btn btn-default">Submit</button>
</form>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The Rich Text Editor (RTE) control is an easy to render in client side.Customer easy to edit the contents, insert table, images and get the HTML content for the displayed content.";
    }
    onSubmit() {
        var editor = $("#texteditor").data("ejRTE");
        var encoded = $('<div />').text(editor.model.value).html();
        $("#texteditor").val(encoded);
    }
}

{% endhighlight %}

## Refresh

When you move the editor’s wrapper element into another DOM element, the editor needs to be reinitialized by the [refresh](http://help.syncfusion.com/api/js/ejrte#methods:refresh) method to retain its content. The method reload the content area and rebind the events of the editor. 

{% highlight html %}

<div class="control">
       <textarea id="texteditor" ej-rte [value]="val"></textarea>
       <div id="target"></div>
       <button (click)="appendTo()">Append To</button>
       <button (click)="refresh()">Refresh</button>
</div>
  
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
    appendTo() {
        var editor = $("#texteditor").ejRTE("instance");
        editor._rteWapper.appendTo($("#target"));
    }
    refresh() {
        var editor = $("#texteditor").ejRTE("instance");
        editor.refresh();
    }
}

{% endhighlight %}

## Persistence

The editor is capable to persist its content with HTML format. By default, the persistence support is disabled in the editor. When you set the [enablePersistence](http://help.syncfusion.com/api/js/ejrte#members:enablepersistence) property to true, the persistence will be enabled in the editor.

N>  [local storage](http://www.w3schools.com/html/html5_webstorage.asp#) is not supported below ie9 version, therefore persistence support is fallback to [cookie](http://www.w3schools.com/js/js_cookies.asp#).

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [enablePersistence]="true"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
}

{% endhighlight %}

## Set Default Font Name and Size

* Set a default font name and font size to the font name and size drop-down programmatically.

N>
•	By default, the editor’s < iframe > is initialized with “Segoe UI” font name and 3(12pt) font size. <BR> 
•	To change it, select a different font name and font size from the drop-down in the editor’s toolbar. <BR>
•	To apply different font style for particular section of the content, select the text that you would like to change, and select a required font style from the drop-down to apply the changes to the selected text.<BR>

{% highlight html %}

 <textarea id="texteditor" ej-rte [value]="val" [(tools)]="tools" [minWidth]="100" [isResponsive]="true" (create)="onCreate()"></textarea>
 
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.tools = {
            font: ["fontName", "fontSize", "fontColor", "backgroundColor"]
        };
    }
    //create an instance for existing RTE control and add the below code in the required event. Here we have used create event.   
    onCreate() {
        var editor = $("#texteditor").ejRTE("instance");
        var ddl = editor._fontStyleDDL.ejDropDownList("instance");
        ddl.selectItemByIndex(7);
        var ddlSize = editor._fontSizeDDL.ejDropDownList("instance");
        ddlSize.selectItemByIndex(5);
    }
}

{% endhighlight %}

* You can set default font for &lt; iframe &gt;’s body tag using [iframeAttributes](user-interface#iframe-attributes) property.

{% highlight html %}

 <textarea id="texteditor" ej-rte [value]="val" [iframeAttributes]="attrib"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    attrib: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.attrib = { style: 'font-family:Arial;font-size:14px' };
    }
}

{% endhighlight %}

* If you want to override the default font from CSS, create a style tag with CSS styles and append it to the &lt; iframe &gt;’s head tag of the editor.

{% highlight html %}

 <textarea id="texteditor" ej-rte [value]="val" (create)="onCreate()"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
    //Add the below code in the create event or the required event in order to customize the font style using css. Here we have used create event.
    onCreate() {
        var css = "html,body{font-family:sans-serif;font-size:14px; }";
        var editorDoc = $("#texteditor").ejRTE("instance").getDocument();
        var styleTag = document.createElement("style");
        styleTag.type = "text/css";
        if (styleTag.styleSheet) {
            styleTag.styleSheet.cssText = css;
        } else {
            styleTag.appendChild(document.createTextNode(css));
        }
        editorDoc.head.appendChild(styleTag);
    }
}

{% endhighlight %}

## Adding Font Names and Font Size

If you want to add additional font names and font sizes to font drop-down, pass the font information as JSON data and bind it with instance of drop-down. 

{% highlight html %}

 <textarea id="texteditor" ej-rte [value]="val" [(tools)]="tools" (create)="onCreate()"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.tools = {
            font: ["fontName", "fontSize", "fontColor", "backgroundColor"]
        };
    }
    //create an instance for existing RTE control and add the below code in the required event. Here we have used create event.
    onCreate() {
        var editor = $("#texteditor").ejRTE("instance");
        editor.defaults.fontName.push({ text: "Calibri Light", value: "CalibriLight" }, { text: "Calibri", value: "Calibri" });
        editor.defaults.fontSize.push({ text: "8 (42pt)", value: "8" });
        var ddl = editor._fontStyleDDL.ejDropDownList("instance");
        var ddlSize = editor._fontSizeDDL.ejDropDownList("instance");
        ddl.option({ "dataSource": editor.defaults.fontName });
        ddlSize.option({ "dataSource": editor.defaults.fontSize });
        ddl.selectItemByValue("CalibriLight");
        ddlSize.selectItemByValue("8");
    }
}

{% endhighlight %}

## Insert the content at cursor

If you want to insert/paste the content at the current cursor position (or) to replace the selected content with some formatting, you can use pasteContent method in the editor.

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val"></textarea>
   
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
    }
}

{% endhighlight %}

{% highlight javascript %}

//create an instance for existing RTE control and add the below code in required event

var editor = $("#texteditor").ejRTE("instance");
var selectedHtml = editor.getSelectedHtml();
editor.pasteContent("<p style ='background-color:yellow;color:skyblue'>" + selectedHtml + "</p>");

{% endhighlight %}