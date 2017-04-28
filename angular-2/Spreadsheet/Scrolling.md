---
layout: post
title: Scrolling with Spreadsheet widget for Syncfusion Essential JS
description: How to enable Scrolling and its functionalities
platform: Angular-2
control: Spreadsheet
documentation: ug
--- 

# Scrolling

Scrolling helps you to move quickly to different areas of worksheet. Scrolling can be enabled by setting `allowScrolling` as true in `scrollSettings`. 

You can scroll through worksheet using one of the following ways,

* Using the arrow keys
* Using the scroll bars
* Using the mouse

## Set height and width for Scrolling

To set height and width in spreadsheet use `height` and `width` property in `scrollSettings`. The default value for `height` and `width` is `100%`. The height and width can be set in percentage and pixel. 

The following code example describes the above behavior.

{% highlight html %}
<ej-spreadsheet id="spreadsheet" [scrollSettings.allowScrolling]= true scrollSettings.height= "400" scrollSettings.width= "50%">
</ej-spreadsheet> 
{% endhighlight %}

{% highlight ts %}

import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet component html file.
    })
  export class AppComponent {
 }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Scrolling_images/Scrolling_img1.png)

## Responsive

Spreadsheet has support for responsive behavior based on client browser's width and height. To enable responsive, set `isResponsive` property in `scrollSettings` as true. The three modes of responsive layout available in grid based on client width. They are.

* Mobile(<420px)
* Tablet (420px to 617px)
* Desktop(>617px)

N> Default value of `isResponsive` is true.

### Mobile Mode

If client width is less than 420px, the spreadsheet will render in mobile mode. In which, you can see that spreadsheet user interface is customized and redesigned for best view in small screens. The customized feature includes filter dialog, format dialog, chart type dialog and ribbon.

![](Scrolling_images/Scrolling_img2.png)

Ribbon in mobile layout
{:.caption}

![](Scrolling_images/Scrolling_img3.png)

Format cell dialog in mobile layout.
{:.caption}

### Tablet Layout

If the client width is between 420px and 617px, then the spreadsheet will render in tablet mode. Also it has customized the dialogs to match tablet screen size.

![](Scrolling_images/Scrolling_img4.png)

Ribbon in tablet layout.
{:.caption}

## Scroll Mode

Spreadsheet supports two type of modes in scrolling. You can use `scrollMode` property in `scrollSettings` to specify the mode of scrolling.

* Normal - This mode doesn't create new row/column when the scrollbar reaches the end.
* Infinite - This mode creates new row/column when the scrollbar reaches the end.

N> Default value of scrollMode property is infinite mode.

## Virtual Scrolling

Spreadsheet has supports for virtual scrolling. This allows you to load data that you require (load data based on viewport size) without buffering the entire huge database. You can set `allowVirtualScrolling` property in `scrollSettings` as true to enable virtual scrolling.

N> Default value of `allowVirtualScrolling` property is true.

