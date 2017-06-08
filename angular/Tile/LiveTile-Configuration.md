---
layout: post
title: LiveTile-Configuration
description: livetile configuration
platform: Angular
control: Tile
documentation: ug
---

# LiveTile Configuration

Live Tiles are used to display the current or up to date information like scores, stocks, weather, etc. You can enable Live Tile using livetile-enabled property set as true. The livetile-type property allows you to specify the type of animation while updating the information in Tile. 

There are three types of Tile animation supported: Flip, Slide and Carousel.

The livetile-imageurl property sets background image for Live Tile. This property accepts array values so you can specify the image url's for all the Tile components that are used in single Live Tile. 

You can specify time interval for each Tile ej-livetile property. Time interval is given in milliseconds. The default value is 2000.

Refer to the following code examples.

{% highlight html %}

<div class="e-tile-group">
    <div class="e-tile-column">
        <ej-tile id="tile6" tilesize="medium" imageposition="center" imageurl='http://js.syncfusion.com/ug/web/content/tile/games.png' [caption]="caption1">
        </ej-tile>
        <div class="e-tile-small-col-2">
            <ej-tile id="tile2" imageposition="center" tilesize="small" imageurl='http://js.syncfusion.com/ug/web/content/tile/alerts.png'>
            </ej-tile>
            <ej-tile id="tile3" imageposition="center" [livetile]="liveTile1" tilesize="small">
            </ej-tile>
            <ej-tile id="tile4" [livetile]="liveTile2" tilesize="small">
            </ej-tile>
            <ej-tile id="tile5" tilesize="small" [badge]="badge1" imageposition="center" imageurl='http://js.syncfusion.com/ug/web/content/tile/messages.png'>
            </ej-tile>
        </div>
        <ej-tile id="tile6" tilesize="medium" imageposition="fill" [livetile]="liveTile3" [caption]="caption2">
        </ej-tile>
        <ej-tile id="tile7" tilesize="medium" imageposition="center" [livetile]="liveTile4" [caption]="caption3">
        </ej-tile>
        <ej-tile id="tile8" tilesize="wide" imageposition="center" [livetile]="liveTile5" [caption]="caption4">
        </ej-tile>
    </div>
</div>

{% endhighlight %}

{% highlight ts %}    
   
export class AppComponent {
    caption1: any;
    caption2: any;
    caption3: any;
    caption4: any;
    liveTile1: any;
    liveTile2: any;
    liveTile3: any;
    liveTile4: any;
    liveTile5: any;
    badge1: any;
    constructor() {
        this.caption1 = { text: 'Play' };
        this.caption2 = { text: 'People' };
        this.caption3 = { text: 'Photos' };
        this.caption4 = { text: 'Weather' };
        this.liveTile1 = {
            updateInterval: 3000, enabled: true, type: 'flip', imageUrl: ['http://js.syncfusion.com/ug/web/content/tile/alerts.png',
                'http://js.syncfusion.com/ug/web/content/tile/bing.png', 'http://js.syncfusion.com/ug/web/content/tile/camera.png']
        };
        this.liveTile2 = {
            updateInterval: 3500, enabled: true, type: 'flip',
            imageUrl: ['http://js.syncfusion.com/ug/web/content/tile/alerts.png', 'http://js.syncfusion.com/ug/web/content/tile/bing.png', 'http://js.syncfusion.com/ug/web/content/tile/camera.png']
        };
        this.liveTile3 = {
            updateInterval: 5000, enabled: true, type: 'slide',
            imageUrl: ['http://js.syncfusion.com/ug/web/content/tile/people_1.png', 'http://js.syncfusion.com/ug/web/content/tile/people_2.png', 'http://js.syncfusion.com/ug/web/content/tile/people_3.png']
        };
        this.liveTile4 = {
            updateInterval: 4000, enabled: true, type: 'slide',
            imageUrl: ['http://js.syncfusion.com/ug/web/content/tile/pictures.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_1.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_2.png',
                'http://js.syncfusion.com/ug/web/content/tile/pictures.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_1.png']
        };
        this.liveTile5 = {
            updateInterval: 3000, enabled: true, type: 'carousel',
            imageUrl: ['http://js.syncfusion.com/ug/web/content/tile/weather.png', 'http://js.syncfusion.com/ug/web/content/tile/weather_1.png', 'http://js.syncfusion.com/ug/web/content/tile/weather_2.png']
        };
        this.badge1 = { enabled: 'true', value: '10' };
    }
}

{% endhighlight %}

![](LiveTile_images/livetile_image.png)