---
layout: post
title: Orientation
description: orientation
platform: angular
control: Menu
documentation: ug
api: /api/js/ejmenu
---

# Orientation

It gets or sets the direction in which the **Menu** control renders and specifies the orientation of the normal menu.  According to the orientation property the **Menu** control renders in horizontal or vertical.

##Horizontal Menu

Horizontal orientation displays the menu items horizontally and it is the default orientation behavior of **Menu** control. 

The following steps explains you the details on rendering the **Menu** control. 

Add the **&lt;ej-menu&gt;** tag in html page.

{% highlight html %}

<div id="menu_controls" style="height:300px">
<ej-menu id="temp" height="30px" [fields.dataSource]="data" [fields]="fieldsvalues">

</ej-menu>
</div>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html',
  styleUrls: ['./menu.component.css'],
  encapsulation: ViewEncapsulation.None,
})
export class DefaultComponent {
  data: Array<any>;
  fieldsvalues: Object;
  constructor() {

    this.data = [
      { id: 1, text: 'Mail', parentId: null },
      { id: 2, text: 'Calender', parentId: null },
      { id: 3, text: 'Notes', parentId: null },
      { id: 4, text: 'Contacts', parentId: null },
      // first level child
      { id: 11, parentId: 1, text: 'Inbox', sprite: 'mailicon sprite-inbox' },
      { id: 12, parentId: 1, text: 'Drafts', sprite: 'mailicon sprite-drafts' },
      { id: 13, parentId: 1, text: 'Sent items', sprite: 'mailicon sprite-sentitems' },
      { id: 14, parentId: 1, text: 'Deleted', sprite: 'mailicon sprite-deleted' },
      { id: 15, parentId: 1, text: 'Junk mails', sprite: 'mailicon sprite-junk' },
      { id: 16, parentId: 1, text: 'Personal', sprite: 'mailicon sprite-folders' },
      { id: 17, parentId: 2, text: 'My Calender', sprite: 'mailicon sprite-calendar' },
      { id: 18, parentId: 2, text: 'Team', sprite: 'mailicon sprite-calendar' },
      { id: 19, parentId: 2, text: 'Others', sprite: 'mailicon sprite-calendar' },
      { id: 20, parentId: 3, text: 'My Reference', sprite: 'mailicon sprite-folder' },
      { id: 21, parentId: 3, text: 'Team Meeting', sprite: 'mailicon sprite-folder' },
      { id: 22, parentId: 3, text: 'Others', sprite: 'mailicon sprite-folder' },
      { id: 23, parentId: 4, text: 'Suggested', sprite: 'mailicon sprite-contacts' },
      { id: 24, parentId: 4, text: 'My Team', sprite: 'mailicon sprite-contacts' },
      { id: 25, parentId: 4, text: 'Others', sprite: 'mailicon sprite-contacts' },
      // second level child
      { id: 111, parentId: 11, text: 'Development', sprite: 'mailicon sprite-folders' },
      { id: 111, parentId: 11, text: 'Supports', sprite: 'mailicon sprite-folders' },
      { id: 111, parentId: 11, text: 'HR Team', sprite: 'mailicon sprite-folders' },
      { id: 112, parentId: 12, text: 'Support Template', sprite: 'mailicon sprite-folders' },
      { id: 112, parentId: 12, text: 'Personal', sprite: 'mailicon sprite-folders' }
    ];
    this.fieldsvalues = { dataSource: this.data, parentId: 'parentId', id: 'id', text: 'text', spriteCssClass: 'sprite' };

  }
}

{% endhighlight %}

The following screenshot displays the output of the above code.        

![](/angular/Menu/Orientation_images/Orientation_img1.png) 


##Vertical Menu

You can also render **Menu** control in vertical direction using **orientation.** To set the vertical orientation of **Menu** control, replace the following attribute in the above sample code example.

Add the following code in your **&lt;ej-menu&gt;** tag.

{% highlight html %}

<div id="menu_controls" style="height:300px">
<ej-menu id="temp" height="150px" [fields.dataSource]="data" [fields]="fieldsvalues" orientation="vertical">

</ej-menu>
</div>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html',
  styleUrls: ['./menu.component.css'],
  encapsulation: ViewEncapsulation.None,
})
export class DefaultComponent {
  data: Array<any>;
  fieldsvalues: Object;
  constructor() {

    this.data = [
      { id: 1, text: 'Mail', parentId: null },
      { id: 2, text: 'Calender', parentId: null },
      { id: 3, text: 'Notes', parentId: null },
      { id: 4, text: 'Contacts', parentId: null },
      // first level child
      { id: 11, parentId: 1, text: 'Inbox', sprite: 'mailicon sprite-inbox' },
      { id: 12, parentId: 1, text: 'Drafts', sprite: 'mailicon sprite-drafts' },
      { id: 13, parentId: 1, text: 'Sent items', sprite: 'mailicon sprite-sentitems' },
      { id: 14, parentId: 1, text: 'Deleted', sprite: 'mailicon sprite-deleted' },
      { id: 15, parentId: 1, text: 'Junk mails', sprite: 'mailicon sprite-junk' },
      { id: 16, parentId: 1, text: 'Personal', sprite: 'mailicon sprite-folders' },
      { id: 17, parentId: 2, text: 'My Calender', sprite: 'mailicon sprite-calendar' },
      { id: 18, parentId: 2, text: 'Team', sprite: 'mailicon sprite-calendar' },
      { id: 19, parentId: 2, text: 'Others', sprite: 'mailicon sprite-calendar' },
      { id: 20, parentId: 3, text: 'My Reference', sprite: 'mailicon sprite-folder' },
      { id: 21, parentId: 3, text: 'Team Meeting', sprite: 'mailicon sprite-folder' },
      { id: 22, parentId: 3, text: 'Others', sprite: 'mailicon sprite-folder' },
      { id: 23, parentId: 4, text: 'Suggested', sprite: 'mailicon sprite-contacts' },
      { id: 24, parentId: 4, text: 'My Team', sprite: 'mailicon sprite-contacts' },
      { id: 25, parentId: 4, text: 'Others', sprite: 'mailicon sprite-contacts' },
      // second level child
      { id: 111, parentId: 11, text: 'Development', sprite: 'mailicon sprite-folders' },
      { id: 111, parentId: 11, text: 'Supports', sprite: 'mailicon sprite-folders' },
      { id: 111, parentId: 11, text: 'HR Team', sprite: 'mailicon sprite-folders' },
      { id: 112, parentId: 12, text: 'Support Template', sprite: 'mailicon sprite-folders' },
      { id: 112, parentId: 12, text: 'Personal', sprite: 'mailicon sprite-folders' }
    ];
    this.fieldsvalues = { dataSource: this.data, parentId: 'parentId', id: 'id', text: 'text', spriteCssClass: 'sprite' };

  }
}

{% endhighlight %}

The following screenshot displays the output of the above code.        

![](/angular/Menu/Orientation_images/Orientation_img2.png) 
