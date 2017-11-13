---
layout: post
title: Cleanup elements when copy paste from MSWord to RichTextEditor widget
description: Cleanup elements when copy paste from MSWord to RichTextEditor widget
platform: angular
control: RTE
documentation: ug
keywords: RichTextEditor, cleanup, paste-cleanup
api: /api/js/ejrte
---

# Clean unwanted elements and styles when copy paste from Microsoft Word

While copy pasting content from MSWord document, the content will be processed in the paste action event.[pasteCleanupSettings](https://help.syncfusion.com/api/js/ejrte#members:pasteCleanupSettings) API can be used for removing unwanted elements.
This will convert an unformatted html element (MOS XML format) content to a proper html element.Table elements also will be converted with proper elements. 
<table>
<tr>
    <th> Options <br/><br/></th>
    <th> Description <br/><br/></th>
</tr>
<tr>
    <td> {{'[listConversion](https://help.syncfusion.com/api/js/ejrte#members:pasteCleanupSettings-listconversion)'| markdownify }} <br/><br/></td>
    <td>List Conversion option convert the list elements into a proper format pasted from MSWord document to editor. <br/><br/></td>
</tr>
<tr>
    <td> {{'[cleanCSS ](https://help.syncfusion.com/api/js/ejrte#members:pasteCleanupSettings-cleanCSS )'| markdownify }} <br/><br/></td>
    <td>Clean Css is used to clean the unwanted css in the elements pasted from MSWord document to editor <br/><br/></td>
</tr>
<tr>
    <td> {{'[removeStyles  ](https://help.syncfusion.com/api/js/ejrte#members:pasteCleanupSettings-removeStyles  )'| markdownify }} <br/><br/></td>
    <td>Remove styles will remove all styles in the elements pasted from MSWord document to editor. <br/><br/></td>
</tr>
<tr>
    <td> {{'[cleanElements   ](https://help.syncfusion.com/api/js/ejrte#members:pasteCleanupSettings-cleanElements   )'| markdownify }} <br/><br/></td>
    <td>Clean Elements is used to clean the unwanted elements pasted from MSWord document to editor.<br/><br/></td>
</tr>
</table>
 
{% highlight html %}

<textarea ej-rte id="rteSample" rows="10" cols="30" [value]="val"  width=100% minWidth="100px" style="width: 740px; height: 440px" [pasteCleanupSettings]="pasteCleanupSettings">       
</textarea>

{% endhighlight %}

{% highlight ts %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val:any;
    pasteCleanupSettings: any;

    constructor() {
       this.val="The RichTextEditor (RTE) control enables you to edit the contents with insert table and images.It also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
       this.pasteCleanupSettings={
               listConversion:true,
               cleanCSS:true,
               removeStyles:true,
               cleanElements:true
           };
    }
    
}

{% endhighlight %}

Pasted Content before Cleanup:
![](Clean-Elements-images/beforecleanup.png)

![](Clean-Elements-images/Element1.png)

Pasted Content after Cleanup:
![](Clean-Elements-images/Aftercleanup.png)

![](Clean-Elements-images/Element2.png)