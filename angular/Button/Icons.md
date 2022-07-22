---
layout: post
title: Icons in Angular Button Control | Syncfusion
description: Learn here about Icons support in Syncfusion Essential Angular Button Control, its elements, and more.
platform: Angular
control: Button
documentation: ug
---

# Icons in Angular Button

The **Essential Studio for Angular** provide icons library that contains the number of in-built icons that can be applied for CSS class names to elements and refer “ej.widgets.all.core.min.css” file. Use the following syntax to apply class names.

**Syntax**: .e-icon .e-[icon description]

{% highlight html %}

.e-icon .e-search

{% endhighlight %}

## Adding icon in Button

For example, you can render the desired icon in the button by using the following table that contains the listed icons CSS class names in the “prefixIcon” property of button component. Also, use “contentType” property to display the icon in the button. In the following code example, specify the “**ContentType**” of the button as imageonly.    

Also in the button sample, you can use the icon class names as follows,

{% highlight html %}

    <table>
    <tr>
        <td>
            <button id="buttonId" prefixIcon="e-icon e-handup" contentType="TextAndImage" type="button" ej-button text="button"></button>
    </tr>
    </table>


{% endhighlight %}

Execute the above code to render the following output.

![Angular Button icons](Icons_images/Icons_img1.png)

Icon library used in button component
{:.caption}

## List of Icons

The complete list of icons is listed in the following table.

List of icons

<table>
    <tr>
        <td>
            e-unpin
        </td>
        <td>
            <img src="Icons_images\Icons_img2.png" alt="Angular Button unpin" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-pin
        </td>
        <td>
            <img src="Icons_images\Icons_img3.png" alt="Angular Button pin" width="14pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-upload
        </td>
        <td>
            <img src="Icons_images\Icons_img4.png" alt="Angular Button upload" width="17pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-reload
        </td>
        <td>
            <img src="Icons_images\Icons_img5.png" alt="Angular Button reload" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-collapse
        </td>
        <td>
            <img src="Icons_images\Icons_img6.png" alt="Angular Button collapse" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-cancel
        </td>
        <td>
            <img src="Icons_images\Icons_img7.png" alt="Angular Button cancel" width="15pt" height="18pt">
        </td>
    </tr>
    <tr>
        <td>
            e-expand
        </td>
        <td>
            <img src="Icons_images\Icons_img8.png" alt="Angular Button expand" width="16pt" height="10pt">
        </td>
    </tr>
    <tr>
        <td>
            e-minimize
        </td>
        <td>
            <img src="Icons_images\Icons_img9.png" alt="Angular Button minimize" width="16pt" height="10pt">
        </td>
    </tr>
    <tr>
        <td>
            e-login
        </td>
        <td>
            <img src="Icons_images\Icons_img10.png" alt="Angular Button login" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-orientationlanscape
        </td>
        <td>
            <img src="Icons_images\Icons_img11.png" alt="Angular Button orientation lanscape" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-alignleft
        </td>
        <td>
            <img src="Icons_images\Icons_img12.png" alt="Angular Button align left" width="15pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-aligncenter
        </td>
        <td>
            <img src="Icons_images\Icons_img13.png" alt="Angular Button align center" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-alignright
        </td>
        <td>
            <img src="Icons_images\Icons_img14.png" alt="Angular Button align right" width="15pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-alignjustify
        </td>
        <td>
            <img src="Icons_images\Icons_img15.png" alt="Angular Button align justify" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-alignnone
        </td>
        <td>
            <img src="Icons_images\Icons_img16.png" alt="Angular Button alignnone" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-filterset
        </td>
        <td>
            <img src="Icons_images\Icons_img17.png" alt="Angular Button filterset" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-filternone
        </td>
        <td>
            <img src="Icons_images\Icons_img18.png" alt="Angular Button filter none" width="11pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheadup-2x
        </td>
        <td>
            <img src="Icons_images\Icons_img19.png" alt="Angular Button arrow head up" width="14pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheaddown-2x
        </td>
        <td>
            <img src="Icons_images\Icons_img20.png" alt="Angular Button arrow head down" width="12pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheadleft-2x
        </td>
        <td>
            <img src="Icons_images\Icons_img21.png" alt="Angular Button arrow head left" width="10pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheadright-2x
        </td>
        <td>
            <img src="Icons_images\Icons_img22.png" alt="Angular Button arrow head right" width="10pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-numbering
        </td>
        <td>
            <img src="Icons_images\Icons_img23.png" alt="Angular Button numbering" width="14pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-bullets
        </td>
        <td>
            <img src="Icons_images\Icons_img24.png" alt="Angular Button bullets" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-maximize
        </td>
        <td>
            <img src="Icons_images\Icons_img25.png" alt="Angular Button maximize" width="13pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-delete
        </td>
        <td>
            <img src="Icons_images\Icons_img26.png" alt="Angular Button delete" width="12pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-scroll
        </td>
        <td>
            <img src="Icons_images\Icons_img27.png" alt="Angular Button scroll" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-right-scroll
        </td>
        <td>
            <img src="Icons_images\Icons_img28.png" alt="Angular Button right scroll" width="16pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-search
        </td>
        <td>
            <img src="Icons_images\Icons_img29.png" alt="Angular Button search" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaback
        </td>
        <td>
            <img src="Icons_images\Icons_img30.png" alt="Angular Button mediaback" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaforward
        </td>
        <td>
            <img src="Icons_images\Icons_img31.png" alt="Angular Button mediaforward" width="11pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-medianext
        </td>
        <td>
            <img src="Icons_images\Icons_img32.png" alt="Angular Button medianext" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaprev
        </td>
        <td>
            <img src="Icons_images\Icons_img33.png" alt="Angular Button mediaprev" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaeject
        </td>
        <td>
            <img src="Icons_images\Icons_img34.png" alt="Angular Button mediaeject" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaclose
        </td>
        <td>
            <img src="Icons_images\Icons_img35.png" alt="Angular Button mediaclose" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediapause
        </td>
        <td>
            <img src="Icons_images\Icons_img36.png" alt="Angular Button mediapause" width="12pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-mediaplay
        </td>
        <td>
            <img src="Icons_images\Icons_img37.png" alt="Angular Button media play" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-righttick
        </td>
        <td>
            <img src="Icons_images\Icons_img38.png" alt="Angular Button right tick" width="15pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-smile
        </td>
        <td>
            <img src="Icons_images\Icons_img39.png" alt="Angular Button smile" width="16pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-information
        </td>
        <td>
            <img src="Icons_images\Icons_img40.png" alt="Angular Button information" width="16pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-left-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img41.png" alt="Angular Button left arrow" width="12pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-right-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img42.png" alt="Angular Button right arrow" width="10pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-file-delete
        </td>
        <td>
            <img src="Icons_images\Icons_img43.png" alt="Angular Button file delete" width="12pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-file-percentage-success
        </td>
        <td>
            <img src="Icons_images\Icons_img44.png" alt="Angular Button file percentage success" width="15pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-file-cancel
        </td>
        <td>
            <img src="Icons_images\Icons_img45.png" alt="Angular Button file cancel" width="11pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-file-percentage-failed
        </td>
        <td>
            <img src="Icons_images\Icons_img46.png" alt="Angular Button file percentage failed" width="11pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-file-retry
        </td>
        <td>
            <img src="Icons_images\Icons_img47.png" alt="Angular Button file retry" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-resize-handle
        </td>
        <td>
            <img src="Icons_images\Icons_img48.png" alt="Angular Button resize handle" width="12pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-down-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img49.png" alt="Angular Button down arrow" width="14pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-time
        </td>
        <td>
            <img src="Icons_images\Icons_img50.png" alt="Angular Button time" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-up-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img51.png" alt="Angular Button up arrow" width="12pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-date
        </td>
        <td>
            <img src="Icons_images\Icons_img52.png" alt="Angular Button date" width="14pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-datetime
        </td>
        <td>
            <img src="Icons_images\Icons_img53.png" alt="Angular Button datetime" width="16pt" height="18pt">
        </td>
    </tr>
    <tr>
        <td>
            e-collapse-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img54.png" alt="Angular Button collapse arrow" width="13pt" height="11pt">
        </td>
    </tr>
    <tr>
        <td>
            e-expand-arrow
        </td>
        <td>
            <img src="Icons_images\Icons_img55.png" alt="Angular Button expand arrow" width="12pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-restore
        </td>
        <td>
            <img src="Icons_images\Icons_img56.png" alt="Angular Button restore" width="16pt" height="19pt">
        </td>
    </tr>
    <tr>
        <td>
            e-plus
        </td>
        <td>
            <img src="Icons_images\Icons_img57.png" alt="Angular Button plus" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-minus
        </td>
        <td>
            <img src="Icons_images\Icons_img58.png" alt="Angular Button minus" width="16pt" height="10pt">
        </td>
    </tr>
    <tr>
        <td>
            e-handup
        </td>
        <td>
            <img src="Icons_images\Icons_img59.png" alt="Angular Button handup" width="12pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-clock
        </td>
        <td>
            <img src="Icons_images\Icons_img60.png" alt="Angular Button clock" width="13pt" height="11pt">
        </td>
    </tr>
    <tr>
        <td>
            e-cursor
        </td>
        <td>
            <img src="Icons_images\Icons_img61.png" alt="Angular Button cursor" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-hyperlink
        </td>
        <td>
            <img src="Icons_images\Icons_img62.png" alt="Angular Button hyperlink" width="20pt" height="12pt">
        </td>
    </tr>
    <tr>
        <td>
            e-hyperlinkbreak
        </td>
        <td>
            <img src="Icons_images\Icons_img63.png" alt="Angular Button hyperlink break" width="20pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-settings
        </td>
        <td>
            <img src="Icons_images\Icons_img64.png" alt="Angular Button settings" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-shoppingcart
        </td>
        <td>
            <img src="Icons_images\Icons_img65.png" alt="Angular Button shopping cart" width="16pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-palette
        </td>
        <td>
            <img src="Icons_images\Icons_img66.png" alt="Angular Button palette" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-warningmessage
        </td>
        <td>
            <img src="Icons_images\Icons_img67.png" alt="Angular Button warning message" width="15pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-cut
        </td>
        <td>
            <img src="Icons_images\Icons_img68.png" alt="Angular Button cut" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-copy
        </td>
        <td>
            <img src="Icons_images\Icons_img69.png" alt="Angular Button copy" width="14pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-paste
        </td>
        <td>
            <img src="Icons_images\Icons_img70.png" alt="Angular Button paste" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-edit
        </td>
        <td>
            <img src="Icons_images\Icons_img71.png" alt="Angular Button edit" width="18pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-swapleft
        </td>
        <td>
            <img src="Icons_images\Icons_img72.png" alt="Angular Button swapleft" width="16pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-swapright
        </td>
        <td>
            <img src="Icons_images\Icons_img73.png" alt="Angular Button swapright" width="16pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-swapup
        </td>
        <td>
            <img src="Icons_images\Icons_img74.png" alt="Angular Button swapup" width="16pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-swapdown
        </td>
        <td>
            <img src="Icons_images\Icons_img75.png" alt="Angular Button swapdown" width="16pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-zoomin
        </td>
        <td>
            <img src="Icons_images\Icons_img76.png" alt="Angular Button zoomin" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-zoomout
        </td>
        <td>
            <img src="Icons_images\Icons_img77.png" alt="Angular Button zoomout" width="16pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-star
        </td>
        <td>
            <img src="Icons_images\Icons_img78.png" alt="Angular Button star" width="12pt" height="11pt">
        </td>
    </tr>
    <tr>
        <td>
            e-home
        </td>
        <td>
            <img src="Icons_images\Icons_img79.png" alt="Angular Button home" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-clipboard
        </td>
        <td>
            <img src="Icons_images\Icons_img80.png" alt="Angular Button clipboard" width="14pt" height="18pt">
        </td>
    </tr>
    <tr>
        <td>
            e-userlogin
        </td>
        <td>
            <img src="Icons_images\Icons_img81.png" alt="Angular Button userlogin" width="15pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-dataexport
        </td>
        <td>
            <img src="Icons_images\Icons_img82.png" alt="Angular Button dataexport" width="19pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheadright
        </td>
        <td>
            <img src="Icons_images\Icons_img83.png" alt="Angular Button arrowheadright" width="14pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-arrowheaddown
        </td>
        <td>
            <img src="Icons_images\Icons_img84.png" alt="Angular Button arrowheaddown" width="13pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-undo
        </td>
        <td>
            <img src="Icons_images\Icons_img85.png" alt="Angular Button undo" width="13pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-redo
        </td>
        <td>
            <img src="Icons_images\Icons_img86.png" alt="Angular Button e redo" width="16pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-bold
        </td>
        <td>
            <img src="Icons_images\Icons_img87.png" alt="Angular Button e bold" width="14pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-italic
        </td>
        <td>
            <img src="Icons_images\Icons_img88.png" alt="Angular Button e italic" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-underline
        </td>
        <td>
            <img src="Icons_images\Icons_img89.png" alt="Angular Button e underline" width="17pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-strikethrough
        </td>
        <td>
            <img src="Icons_images\Icons_img90.png" alt="Angular Button e strikethrough" width="16pt" height="14pt">
        </td>
    </tr>
    <tr>
        <td>
            e-font
        </td>
        <td>
            <img src="Icons_images\Icons_img91.png" alt="Angular Button e font" width="15pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-rarrowdown
        </td>
        <td>
            <img src="Icons_images\Icons_img92.png" alt="Angular Button e rarrowdown" width="11pt" height="13pt">
        </td>
    </tr>
    <tr>
        <td>
            e-rarrowleft
        </td>
        <td>
            <img src="Icons_images\Icons_img93.png" alt="Angular Button e rarrowleft" width="16pt" height="15pt">
        </td>
    </tr>
    <tr>
        <td>
            e-rarrowup
        </td>
        <td>
            <img src="Icons_images\Icons_img94.png" alt="Angular Button e rarrowup" width="14pt" height="11pt">
        </td>
    </tr>
    <tr>
        <td>
            e-rarrowright
        </td>
        <td>
            <img src="Icons_images\Icons_img95.png" alt="Angular Button e rarrowdown" width="14pt" height="16pt">
        </td>
    </tr>
    <tr>
        <td>
            e-calender
        </td>
        <td>
            <img src="Icons_images\Icons_img96.png" alt="Angular Button e calender" width="14pt" height="17pt">
        </td>
    </tr>
    <tr>
        <td>
            e-save
        </td>
        <td>
            <img src="Icons_images\Icons_img97.png" alt="Angular Button e save" width="17pt" height="16pt">
        </td>
    </tr>
</table>