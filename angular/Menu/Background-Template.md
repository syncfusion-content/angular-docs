---
layout: post
title: Background-Template
description: background template
platform: angular
control: Menu
documentation: ug
api: /api/angular/ejmenu
---

# Background Template

**Menu** control also provides support for template support. Normally **Menu** control can be created by using **UL** and **LI** tags in the preferred way. But in template supporting, you can customize the appearance of sub menu items rendering. 

Initialize the Template **Menu** as illustrated in the following code example. 

Add the following code in your **HTML** page.

{% highlight html %}

<div id="menu_controls" style="height:300px">
    <ej-menu id="menutemplate">

        <li><a>Books</a>
            <ul>
                <li>
                    <div class="temp temp1">
                        <span>BOOKS</span>
                        <ul>
                            <li><a>New Releases</a></li>
                            <li><a>Bestsellers</a></li>
                            <li><a>Upcoming</a></li>
                            <li><a>Box Sets</a></li>
                        </ul>
                        <ul>
                            <li><a>HTML Basics</a></li>
                            <li><a>JavaScript</a></li>
                            <li><a>JQuery</a></li>
                            <li><a>PHP Basics</a></li>
                        </ul>
                    </div>
                </li>
            </ul>
        </li>
        <li><a>Cameras</a>
            <ul>
                <li>
                    <div class=" temp temp2">
                        <div>
                            <span>CAMERAS</span>
                            <ul>
                                <li><a>Point & Shoots</a></li>
                                <li><a>Digital SLR</a></li>
                                <li><a>Camcorders</a></li>
                                <li><a>Bestsellers</a></li>
                            </ul>
                            <ul>
                                <li><a>Still Camera</a></li>
                                <li><a>Digital Camera</a></li>
                                <li><a>Video Camera</a></li>
                                <li><a>Virtual Camera</a></li>
                            </ul>
                        </div>
                    </div>
                </li>
            </ul>
        </li>
        <li><a>Movies</a>
            <ul>
                <li>
                    <div class="temp temp3">
                        <div>
                            <span>MOVIES</span>
                            <ul>
                                <li><a>Genobili Actions</a></li>
                                <li><a>Jackie Rocks</a></li>
                                <li><a>Men In Blue</a></li>
                                <li><a>Human vs Alien</a></li>
                            </ul>
                            <ul>
                                <li><a>Million Dreams</a></li>
                                <li><a>Kung-fu</a></li>
                            </ul>
                        </div>
                    </div>
                </li>
            </ul>
        </li>
        <li><a>Musics</a>
            <ul>
                <li>
                    <div class="temp temp4">
                        <div>
                            <span>MUSICS</span>
                            <ul>
                                <li><a>New Releases</a></li>
                                <li><a>Bestsellers</a></li>
                                <li><a>Devotional</a></li>
                                <li><a>Sufi & Ghazal</a></li>
                            </ul>
                            <ul>
                                <li><a>Pop songs</a></li>
                                <li><a>Rock Music</a></li>
                            </ul>
                        </div>
                    </div>
                </li>
            </ul>
        </li>
        <li><a>Gaming</a>
            <ul>
                <li>
                    <div class="temp temp5">
                        <div>
                            <span>GAMING</span>
                            <ul>
                                <li><a>Upcoming</a></li>
                                <li><a>PC</a></li>
                                <li><a>PS Vista</a></li>
                                <li><a>PS3</a></li>
                                <li><a>XBox</a></li>
                                <li><a>Consoles</a></li>
                            </ul>
                            <ul>
                                <li><a>FIFA 2999</a></li>
                                <li><a>NBA Actions</a></li>
                                <li><a>Crick Champions</a></li>
                                <li><a>Carom legend</a></li>
                            </ul>
                        </div>
                    </div>
                </li>
            </ul>
        </li>

    </ej-menu>
</div>

{% endhighlight %}

{% highlight typescript %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html',
  styleUrls: ['./menu.component.css'],
  encapsulation: ViewEncapsulation.None,
})
export class DefaultComponent {
 
}

{% endhighlight %}



Add the following code in your style sheet.

{% highlight css %}


<style type="text/css">
    .temp {
        height: 237px;
        width: 375px;
        font-family: segoe UI;
        cursor: default;
        background-size: 100% 100%;
    }

    .temp span {
        color: red;
        float: left;
        font-size: 20px;
        left: 20px;
        position: relative;
        top: 25px;
        width: 100px;
    }

    .temp ul {
        float: left;
        font-size: 14px;
        left: -79px;
        list-style-type: none;
        margin: 0;
        padding: 0;
        position: relative;
        top: 50px;
        width: 128px;
    }

    .temp ul li {
        font-size: 13px;
    }

    .temp ul li a {
        text-decoration: underline;
        cursor: pointer;
        color: #000;
    }

    .temp1 {
        background-image: url("1.jpg");
    }

    .temp2 {
        background-image: url("2.jpg");
    }

    .temp3 {
        background-image: url("3.jpg");
    }

    .temp4 {
        background-image: url("4.jpg");
    }

    .e-menu.e-horizontal li > ul, .e-menu.e-horizontal li > ul > li:hover {
        background-color: #fff;
    }

    .e-menu.e-horizontal > li > ul:after {
        border-color: transparent transparent #fff;
    }
</style>


{% endhighlight %}



Execute the above code to render the following output.                       

![](/angular/Menu/Background-Template_images/Background-Template_img1.png) 




