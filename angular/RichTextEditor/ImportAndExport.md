---
layout: post
title: Import and Export in Angular RichTextEditor widget | Syncfusion
description: Import content from word document into the RichTextEditor and Export the RichTextEditor content into word or PDF document.
platform: Angular
control: RichTextEditor
documentation: ug
---
# Import and Export in Angular RichTextEditor

Import feature provides support to import a word document into the editor `textarea`. To enable import option in the RTE tool bar,  `import` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. In `importSettings` url option, the server page for import is needed to be mapped. When you click the toolbar import icon, it opens a dialog to browse the select a word file. The selected word file will be imported into the editor `textarea`.

{% highlight html %}

<textarea id="texteditor" ej-rte [(tools)]="tools" [importSettings.url]="url"></textarea>

{% endhighlight  %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    url: string;
    tools: Object;
    constructor() {
        this.url = "http://js.syncfusion.com/ejServices/api/RTE/Import";
        this.tools = {
            importExport: ["import"]
        };
    }
}

{% endhighlight %}

## Server configuration

Currently word document can be imported in server-side only, through **EJ's** helper functions in .NET. So, to use RTE import in your projects, it is required to create a server with any of the following web services. 

* Web API 
* WCF Service
* ASP.NET MVC Controller Action 
* ASP.NET WebMethod 

Following code snippet demonstrate import with WebAPI controller.

{% highlight c# %}

     public class RTEController : ApiController
    {
        [HttpPost]
        public string Import()
        {
            string HtmlString = string.Empty;
            if (HttpContext.Current.Request.Files.AllKeys.Any())
            {
                string RTEID = HttpContext.Current.Request.QueryString["rteid"];
                var fileName = RTEID + "_importUpload";
                var httpPostedFile = HttpContext.Current.Request.Files[fileName];
                if (httpPostedFile != null)
                {
                    using (var mStream = new MemoryStream())
                    {
                        new WordDocument(httpPostedFile.InputStream).Save(mStream, FormatType.Html);
                        mStream.Position = 0;
                        HtmlString = new StreamReader(mStream).ReadToEnd();
                    };

                    HtmlString = ExtractBodyContent(HtmlString);

                    foreach (var item in DecodeKeys())
                    {
                        HtmlString = HtmlString.Replace(item.Key, item.Value);
                    }
                }
                else HttpContext.Current.Response.Write("Select any file to upload.");

            }
            return HtmlString;
        }

        public IDictionary<string, string> DecodeKeys()
        {
            IDictionary<string, string> KeyValuePair = new Dictionary<string, string>()
            {
               {"\"", "'"},{"\r", " "},{"\n", "<br/> "},{"\r\n", " "},{"( )+", " "},{"&nbsp;", " "},{"&bull;", "*"},{"&lsaquo;", "<"},
               {"&rsaquo;", ">"},{"&trade;", "(tm)"},{"&copy;", "(c)"},{"&reg;", "(r)"}
            };

            return KeyValuePair;
        }

        public string ExtractBodyContent(string html)
        {
            if (html.Contains("<html") && html.Contains("<body"))
            {
                return html.Remove(0, html.IndexOf("<body>") + 6).Replace("</body></html>", "");

            }
            return html;
        }

    }

{% endhighlight  %}

### Server Dependencies

Full list of assemblies needed for RTE Import are as follows

    1.  Syncfusion.EJ
    2.  Syncfusion.EJ.Export
    3.  Syncfusion.Linq.Base
    4.  Syncfusion.Compression.Base
    5.  Syncfusion.DocIO.Base

![Angular RichTextEditor Server Dependencies](ImportAndExport_images/import_images.png)

### Export 

Export feature provides support to export editor `textarea` content into word and PDF files. To enable Export option in the RTE tool bar,  `wordExport` , `pdfExport` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. `exportToWordSettings` consists of url and fileName sub properties. In url property, the server page for export to word is needed to be mapped and In fileName property, the name for the exported word file is given. `exportToPdfSettings` consists of url and fileName sub properties. In url property, the server page for export to PDF is needed to be mapped and In fileName property, the name for the exported PDF file is given. When you click the toolbar pdfExport or wordExport icon, the contents of RTE are sent to the server. It performs XHTML Validation on the editor `textarea` content on the server. Once the XHTML validation and formatting is successful, it exports the content into a Word or PDF File.

{% highlight html %}
    
 <textarea id="texteditor" ej-rte [minWidth]="150" [value]="val" [(tools)]="tools" [exportToWordSettings.url]="wordurl" [exportToWordSettings.fileName]="word" [exportToPdfSettings.url]="pdfurl" [exportToPdfSettings.fileName]="pdf"></textarea>

{% endhighlight  %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    wordurl: string;
    pdfurl: string;
    tools: Object;
    val: string;
    word: string;
    pdf: string;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.wordurl = "http://js.syncfusion.com/ejServices/api/RTE/WordExport";
        this.pdfurl = "http://js.syncfusion.com/ejServices/api/RTE/PdfExport";
        this.tools = {
            importExport: ["wordExport", "pdfExport"]
        };
        this.word = "wordSample";
        this.pdf = "pdfSample";
    }
}

{% endhighlight %}

## Server configuration

Currently RTE content can be converted to word or PDF file formats in server-side only, through **EJ's** helper functions in .NET. So, to use exporting in your projects, it is required to create a server with any of the following web services. 

* Web API 
* WCF Service
* ASP.NET MVC Controller Action 
* ASP.NET WebMethod 

Following code snippet demonstrate exporting with WebAPI controller.

{% highlight c# %}

     public class RTEController : ApiController
    {
        //Export to Word Document
        [HttpPost]
        public void ExportToWord()
        {

            string RTEID = HttpContext.Current.Request.QueryString["rteid"];
            string FileName = HttpContext.Current.Request.Params[RTEID + "_inputFile"];
            string htmlText = HttpContext.Current.Request.Params[RTEID + "_inputVal"];
            WordDocument document = GetDocument(htmlText);
            document.Save(FileName + ".docx", FormatType.Docx, HttpContext.Current.Response, HttpContentDisposition.Attachment);
        }
        
        //Export to PDF Document
        [HttpPost]
        public void ExportToPDF()
        {
            string RTEID = HttpContext.Current.Request.QueryString["rteid"];
            string FileName = HttpContext.Current.Request.Params[RTEID + "_inputFile"];
            string htmlText = HttpContext.Current.Request.Params[RTEID + "_inputVal"];
            WordDocument document = GetDocument(htmlText);
            DocToPDFConverter converter = new DocToPDFConverter();
            PdfDocument pdfDocument = converter.ConvertToPDF(document);
            pdfDocument.Save(FileName + ".pdf",HttpContext.Current.Response,HttpReadType.Save);
        }

        public WordDocument GetDocument(string htmlText) 
        {
            WordDocument document = null;
            MemoryStream stream = new MemoryStream();
            StreamWriter writer = new StreamWriter(stream, System.Text.Encoding.Default);
            htmlText = htmlText.Replace("\"", "'");
            XmlConversion XmlText = new XmlConversion(htmlText);
            XhtmlConversion XhtmlText = new XhtmlConversion(XmlText);
            writer.Write(XhtmlText.ToString());
            writer.Flush();
            stream.Position = 0;
            document = new WordDocument(stream, FormatType.Html, XHTMLValidationType.None);
            return document;
        }
    }

{% endhighlight  %}

### Server Dependencies

Export Helper functions are available in the Assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio builds. Full list of assemblies needed for RTE Export as follows

    1.  Syncfusion.EJ
    2.  Syncfusion.EJ.Export
    3.  Syncfusion.Linq.Base
    4.  Syncfusion.Compression.Base
    5.  Syncfusion.DocIO.Base
    6.  Syncfusion.PDF.Base

### Word Export
![Angular RichTextEditor Word Export](ImportAndExport_images/export_word_images.png)
### PDF Export
![Angular RichTextEditor PDF Export](ImportAndExport_images/export_pdf_images.png)
