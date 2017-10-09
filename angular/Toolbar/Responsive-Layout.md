---
layout: post
title: Responsive-Layout
description: responsive layout
platform: angular
control: Toolbar
documentation: ug
api: /api/js/ejtoolbar
---

# Responsive Layout

**Responsive Layout** is aimed at crafting sites to provide an optimal viewing experience easy reading and navigation with a minimum of resizing, panning, and scrolling—across a wide range of devices (from mobile phones to desktop computer monitors). You can achieve **Responsive Layout** by using default functionality of **Toolbar** with **isResponsive** as **true** and also you need to give **Toolbar** width as in percentage value and add **ej.responsive.css** file in this sample. **CDN** link for the responsive CSS file is as follows.

[http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css)

Add the above **css** link in the code sample.        

Add the following code example in your **HTML** page.

{% highlight html %}

<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area"> 
				<div class="frame">
                    <div class="control"> 
                        <ej-toolbar  id="editingtoolbar"  width="400px"  [enableSeparator]=true [isResponsive]=true >

                            <ul>
                                <li id="cut" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							<ul>
                                <li id="cut0" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy0" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste0" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold0" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine0" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough0" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left0" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center0" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right0" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify0" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							 <ul>
                                <li id="cut1" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy1" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste1" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold1" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine1" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough1" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left1" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center1" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right1" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify1" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul>
							</ej-toolbar>
                        </div>
                    </div>
                </div>
			</div>
        </div>


{% endhighlight %}


{% highlight ts %}

import {Component} from '@angular/core';
import { ViewEncapsulation } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './Toolbar.component.html',
    styleUrls: ['./Toolbar.component.css'],
    encapsulation: ViewEncapsulation.None
})
export class ToolbarComponent {
}

{% endhighlight %}

Execute the above code to render the following output.

![](Responsive-Layout_images/Responsive-Layout.png)


## responsiveType:Inline

We can set the responsiveType property to inline to display the overflown toolbar items as inline toolbar.

{% highlight html %}

<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area"> 
				<div class="frame">
                    <div class="control"> 
                        <ej-toolbar  id="editingtoolbar"  width="400px" responsiveType="inline" [enableSeparator]=true [isResponsive]=true >

                            <ul>
                                <li id="cut" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							<ul>
                                <li id="cut0" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy0" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste0" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold0" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine0" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough0" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left0" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center0" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right0" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify0" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							 <ul>
                                <li id="cut1" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy1" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste1" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold1" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine1" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough1" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left1" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center1" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right1" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify1" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul>
							</ej-toolbar>
                        </div>
                    </div>
                </div>
			</div>
        </div>


{% endhighlight %}

While setting inline responsiveType the following output will be displayed.

![](Responsive-Layout_images/Responsive-Layout-img2.png)

## responsiveType:Popup

We can set the responsiveType property to popup to display the overflown toolbar items as popup.

{% highlight html %}

<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area"> 
				<div class="frame">
                    <div class="control"> 
                        <ej-toolbar  id="editingtoolbar"  width="400px" responsiveType="popup" [enableSeparator]=true [isResponsive]=true >

                            <ul>
                                <li id="cut" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							<ul>
                                <li id="cut0" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy0" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste0" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold0" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine0" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough0" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left0" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center0" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right0" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify0" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul> 
							 <ul>
                                <li id="cut1" class="e-icon e-cut_01" title="Cut"></li>
                                <li id="copy1" class="e-icon e-copy_02" title="Copy"></li>
                                <li id="paste1" class="e-icon e-paste_01" title="Paste"></li> 
                            </ul>
                            <ul>
                                <li id="Bold1" class="e-icon e-bold_01" title="Bold"> 
                                </li> 
                                <li id="UndeLine1" class="e-icon e-underline_01" title="UnderLine"> 
                                </li>
                                <li id="StrikeThrough1" class="e-icon e-strikethrough_01" title="Strike Through"> 
                                </li>
                            </ul>
							<ul>
                                <li id="Left1" class="e-icon e-align-left_01" title="Left"> 
                                </li>
                                <li id="Center1" class="e-icon e-align-center_01" title="Center"> 
                                </li>
                                <li id="Right1" class="e-icon e-align-right_01" title="Right"> 
                                </li>
                                <li id="Justify1" class="e-icon e-align-justify_01" title="Justify"> 
                                </li>
                            </ul>
							</ej-toolbar>
                        </div>
                    </div>
                </div>
			</div>
        </div>


{% endhighlight %}

While setting popup as responsiveType the  following output will be displayed.

![](Responsive-Layout_images/Responsive-Layout.png)