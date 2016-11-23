---
layout: post
title: Getting-Started
description: getting started
platform: angular2
control: Tile
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Tile component with the step-by-step instructions.

## Create a Tile Component

The following steps guide you to add a Tile component.

1)	To get start with how to use the Tile component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/gettingstarted/overview).

2)	Create a simple Tile by adding ej-tile attribute for initializing a Tile component on the application. 

    {% highlight html %}

        <div class="tiles">
                <div class="e-tile-column">
                    <ej-tile id="tile" imagePosition="fill" tileSize="medium" imageUrl='http://js.syncfusion.com/ug/web/content/tile/map.png' [caption]="caption">
                    </ej-tile>
                   
                </div>
       </div>

    {% endhighlight %}
    
Add the following code in the component’s constructor file for given the text of the Tile component.

    {% highlight javascript %}

        export class AppComponent {
             caption: any;
             constructor() {
                this.caption = { text: "Maps" };
             }
       }

    {% endhighlight %}

Get the following output from the above-mentioned code

![](Getting-Started_images\getting-started-img1.png)

You can easily design a home page using tile control for easy navigation. Therefore, you require many different sizes of tiles aligned in a grid-like manner. The tiles will be aligned automatically to define the necessary tile elements inside the wrapper element, that contains a “e-tile-column” class. You can define all columns elements under the wrapper element with the tile “e-tile-group” class to make ‘n’ number of tiles as a grouped tile. Add the below mentioned code to the corresponding view page.

{% highlight html %}
    
<div class="tiles">
    <div class="cols-sample-area">
        <div id="scrollTarget">
            <div class="e-tile-group">
                <div class="e-tile-column">
                    <ej-tile id="tile1" imagePosition="fill" tileSize="medium" imageUrl='http://js.syncfusion.com/ug/web/content/tile/people_1.png' [caption]="caption1">
                    </ej-tile>
                    <div class="e-tile-small-col-2">
                        <ej-tile id="tile2" imagePosition="center" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/alerts.png'>
                        </ej-tile>
                        <ej-tile id="tile3" imagePosition="center" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/bing.png'>
                        </ej-tile>
                        <ej-tile id="tile4" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/camera.png'>
                        </ej-tile>
                        <ej-tile id="tile5" tileSize="small" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/messages.png'>
                        </ej-tile>
                    </div>
                    <ej-tile id="tile6" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/games.png' [caption]="caption2">
                    </ej-tile>
                    <ej-tile id="tile7" tileSize="medium" imageUrl='http://js.syncfusion.com/ug/web/content/tile/map.png' [caption]="caption3">
                    </ej-tile>
                    <ej-tile id="tile8" tileSize="wide" imageUrl='http://js.syncfusion.com/ug/web/content/tile/sports.png' [caption]="caption4" imagePosition="fill">
                    </ej-tile>
                </div>
                <div class="e-tile-column">
                    <ej-tile id="tile9" tileSize="medium" imagePosition="fill" imageUrl='http://js.syncfusion.com/ug/web/content/tile/people_2.png' [caption]="caption5">
                    </ej-tile>
                    <ej-tile id="tile10" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/pictures.png' [caption]="caption6">
                    </ej-tile>
                    <ej-tile id="tile11" tileSize="wide" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/weather.png' [caption]="caption7">
                    </ej-tile>
                    <ej-tile id="tile12" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/music.png' [caption]="caption8">
                    </ej-tile>
                    <ej-tile id="tile13" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/favs.png' [caption]="caption9">
                    </ej-tile>
                </div>
            </div>
        </div>
    </div>
</div>
    
{% endhighlight %}

Add the following code in the component’s constructor file for given the text of the Tile component.

{% highlight javascript %}

 export class AppComponent {
    caption1: any;
    caption2: any;
    caption3: any;
    caption4: any;
    caption5: any;
    caption6: any;
    caption7: any;
    caption8: any;
    caption9: any;
    constructor() {
        this.caption1 = { text: "People" };
        this.caption2 = { text: "Play" };
        this.caption3 = { text: "Maps" };
        this.caption4 = { text: "Sports" };
        this.caption5 = { text: "People" };
        this.caption6 = { text: "Photo" };
        this.caption7 = { text: "Weather" };
        this.caption8 = { text: "Music" };
        this.caption9 = { text: "Favorites" };
    }
 }

{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images\getting-started-img2.png)


N> You can find the Tile component properties from the [API reference](https://help.syncfusion.com/api/js/ejtile).
