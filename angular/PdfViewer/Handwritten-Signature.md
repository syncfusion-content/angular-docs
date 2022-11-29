---
title: Hand written signature in Angular PDF viewer Control | Syncfusion
description: Learn here about Hand written signature in Syncfusion Essential Angular PDF viewer Control, its elements, and more.
platform: Angular
control: PDF viewer
documentation: ug
keywords: ejPdfViewer, PDF viewer, js pdfviewer
---

# Handwritten Signature in Angular PDF viewer

We have provided the support for adding handwritten signature into the PDF document. The handwritten signature support reduces the paper work of reviewing the content and verify it digitally. 

The ejPdfViewer has an option in the toolbar settings to enable/disable the signature button in the default toolbar. 

The below code snippet describes how to show only the signature tool in the component.

{% highlight html %}

    <ej-pdfviewer [(serviceUrl)]="service" [(toolbarSettings)]="toolbarSettings" id="pdfviewer" style="width:100%;min-height:600px;display:block">
    </ej-pdfviewer>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/default.component.html'
})
export class DefaultComponent {
    service: string;
    toolbarSettings: object;
    constructor() {
        this.service = 'http://js.syncfusion.com/demos/ejservices/api/PdfViewer';
        this.toolbarSettings = { toolbarItem: ej.PdfViewer.ToolbarItems.SignatureTool };
    }
}
    
{% endhighlight %}

**Drawing and adding signature in the PDF document**

The handwritten signature can be added by drawing the signature content in the signature panel and on clicking the ADD button, the signature will be added in the PDF documents. The following screenshots are pictorial representation of this.

![Angular PDF viewer Signature](Signature-images/angular-pdfviewer-signature.png)

![Angular PDF viewer Drawing Signature](Signature-images/angular-pdfviewer-drawsignature.png)

![Angular PDF viewer adding Signature](Signature-images/angular-pdfviewer-addsignature.png)

**Move, Resize and Delete the Handwritten Signature**

The handwritten signature content can be moved to the specified location within the page bounds by using touch gestures, arrow keys and mouse. We can also resize the handwritten signature content with maintaining aspect ratio. 

The selected handwritten signature content can be deleted using the "Delete" option in the context menu or delete key. The following screenshots are pictorial representation of this.

![Angular PDF viewer Move Signature](Signature-images/angular-pdfviewer-move-signature.png)            

**Changing Handwritten Signature properties**

The properties (i.e. opacity and color) of a handwritten signature can be modified by color palate and opacity slider which is available in the “Properties" option in context menu. The following screenshots are pictorial representation of this. 

![Angular PDF viewer Resize Signature](Signature-images/angular-pdfviewer-resizesignature.png)      

Select the desired color from the color palette and then click on OK button.

![Angular PDF viewer Delete Signature](Signature-images/angular-pdfviewer-deleetsignature.png)  

The selected color will be updated on the signature.

![Angular PDF viewer Color Signature](Signature-images/angular-pdfviewer-colorsignature.png)  

You can also change the opacity of the added signature in the "properties" option.

![ng PDF viewer Capacity Signature](Signature-images/angular-pdfviewer-capacity-signature.png)  

**Saving the Signature**

The added signature can be saved to the PDF document and can be downloaded by clicking the download button in the toolbar. This action will not affect the original document

![Angular PDF viewer Saving the Signature](Signature-images/angular-pdfviewer-savesignature.png) 

