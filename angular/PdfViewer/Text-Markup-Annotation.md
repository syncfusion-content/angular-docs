---
title: Text markup annotation in Angular PDF Viewer Component | Syncfusion
description: Learn here about Text markup annotation in Syncfusion Essential Angular PDF Viewer Component, its elements, and more.
platform: Angular
control: PDF viewer
documentation: ug
keywords: ejPdfViewer, PDF viewer, js pdfviewer
---

# Text Markup Annotation in Angular PDF Viewer

PDF viewer control supports adding text markup annotations in the PDF documents. The component also renders the existing text markup annotations from the PDF document when the document is loaded in it.

The following screenshot shows PDF viewer with the PDF document containing text markup annotations.
![Text markup annotation in Angular PDF Viewer](Text-Markup-Annotation_images/Text_Markup_Annotations_img1.png)

**Adding text markup annotations**

The text markup annotations are added to the PDF document using the text markup annotation tools provided in the toolbar of the PDF viewer component.

The text markup annotation tools can be enabled or disabled using the toolbar settings property.

The below code snippet describes how to show only the text markup annotation tools in the component.

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
        this.toolbarSettings = { toolbarItem: ej.PdfViewer.ToolbarItems.TextMarkupAnnotationTools };
    }
}
    
{% endhighlight %}

The colorpicker control is provided in the text markup annotation tools to select the desired color for the text markup annotation to be added in the document.

![Adding text markup annotations in Angular PDF Viewer](Text-Markup-Annotation_images/Text_Markup_Annotations_img2.png)

**Adding notes to the text markup annotation**

The notes can be added to the text markup annotations using the context menu provided in the PDF viewer component.

The below screenshot shows that the notes have been added to a text markup annotation in the PDF document.
![Adding notes to text markup annotation in Angular PDF Viewer](Text-Markup-Annotation_images/Text_Markup_Annotations_img3.png)

**Editing the text markup annotation**

The properties of the text markup annotations in the PDF document can be edited using the properties window provided in the PDF viewer component. The color, opacity, author and subject of the text markup annotation can be modified. The properties of the text markup annotation can also be locked using the locked checkbox in the properties window.

The below screenshot shows the properties window used for editing the properties of a text markup annotation.
![Editing the text markup annotation in Angular PDF Viewer](Text-Markup-Annotation_images/Text_Markup_Annotations_img4.png)

The text markup annotation in the PDF document can also be deleted from the PDF document.

**Saving the text markup annotation**

When the download tool is selected in the toolbar, the text markup annotations will be saved in the PDF document. This action will not affect the original document.
