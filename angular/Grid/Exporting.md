---
layout: post
title: Export with Grid widget for Syncfusion Essential JS
description: How to export the Grid to Microsoft Word,Microsoft Excel and PDF file format
platform: Angular
control: Grid
documentation: ug
api: /api/js/ejgrid
---
# Export

To export the grid, `export` method should  be called with export mapper as parameter. To make it work from the grid toolbar, `ExcelExport`, `WordExport` and `PdfExport` toolbar items needs to be added in [`toolbarSettings.toolbarItems`](https://help.syncfusion.com/api/angular/ejgrid#members:toolbarsettings-toolbaritems) property and equivalent server action mapper should be defined in `exportToExcelAction`, `exportToWordAction`, and `exportToPdfAction` properties. The code snippet for this is

{% highlight html %}

<ej-grid #grid [allowPaging]="true" [dataSource]="gridData" [toolbarSettings]="toolbarSettings" [allowSorting]="true" (toolbarClick)="toolbar($event)">

    <e-columns>
        <e-column field="OrderID" headertext="Order ID" width="75" textalign="right"></e-column>
        <e-column field="CustomerID" headertext="Customer ID" width="80"></e-column>
        <e-column field="Freight" headertext="Freight" format="{0:C}" width="75"></e-column>
        <e-column field="OrderDate" headertext="Order Date" textalign="right" width="80" format="{0:MM/dd/yyyy}"></e-column>
        <e-column field="ShipCity" headertext="Ship City" width="110"></e-column>
    </e-columns>

</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;

	    public toolbarSettings;

        toolbar(e:any){
                if (e.itemName == "Excel Export") {
                  this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/ExcelExport');
                  e.cancel = true;
                }
                else if (e.itemName == "Word Export") {
                  this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/WordExport')
                  e.cancel = true;//prevent the default action
                }
                else if (e.itemName == "PDF Export") {
                  this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/PdfExport')
                  e.cancel = true;
               }
}

   @ViewChild('grid') Grid: EJComponents<any, any>;

    constructor() {

       this.gridData = new ej.DataManager({ url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders" });

       this.toolbarSettings = { showToolbar: true, toolbarItems: ["excelExport", "wordExport", "pdfExport"] }

       }
    }

    {% endhighlight %}

    ![](Exporting_images/Exporting_img1.png)


## Server configuration

Currently grid data can be converted to different file formats in server-side only, through **EJ's** helper functions in .NET. So, to use exporting in your projects, it is required to create a server with any of the following web services.

* Web API
* WCF Service
* ASP.NET MVC Controller Action
* ASP.NET WebMethod

Following code snippet demonstrate exporting with WebAPI controller.

{% highlight c# %}

public class OrdersController: ApiController
{
  private NORTHWNDEntities db = new NORTHWNDEntities();
  public IEnumerable < Order > Get()
  {
    return db.Orders.ToList();
  }

  [System.Web.Http.ActionName("ExcelExport")]
  [AcceptVerbs("POST")]
  public void ExcelExport()
  {
     string gridModel = HttpContext.Current.Request.Params["GridModel"];
     GridProperties gridProperty = ConvertGridObject(gridModel);
     ExcelExport exp = new ExcelExport();
     IEnumerable < Order > result = db.Orders.ToList();
     exp.Export(gridProperty, result, "Export.xlsx", ExcelVersion.Excel2010, false, false, "flat-saffron");
  }

  [System.Web.Http.ActionName("PdfExport")]
  [AcceptVerbs("POST")]
  public void PdfExport()
  {
    string gridModel = HttpContext.Current.Request.Params["GridModel"];
    GridProperties gridProperty = ConvertGridObject(gridModel);
    PdfExport exp = new PdfExport();
    IEnumerable < Order > result = db.Orders.ToList();
    exp.Export(gridProperty, result, "Export.pdf");
  }

  [System.Web.Http.ActionName("WordExport")]
  [AcceptVerbs("POST")]
  public void WordExport()
  {
    string gridModel = HttpContext.Current.Request.Params["GridModel"];
    GridProperties gridProperties = ConvertGridObject(gridModel);
    WordExport exp = new WordExport();
    IEnumerable < Order > data = db.Orders.ToList();
    exp.Export(gridProperties, (IEnumerable) data, "Export.docx");
  }

  private GridProperties ConvertGridObject(string gridProperty)
  {
    JavaScriptSerializer serializer = new JavaScriptSerializer();
    IEnumerable div = (IEnumerable) serializer.Deserialize(gridProperty, typeof(IEnumerable));
    GridProperties gridProp = new GridProperties();
    foreach(KeyValuePair < string, object > datasource in div)
    {
      var property = gridProp.GetType().GetProperty(datasource.Key, BindingFlags.Instance ' BindingFlags.Public ' BindingFlags.IgnoreCase);
      if (property != null)
      {
        Type type = property.PropertyType;
        string serialize = serializer.Serialize(datasource.Value);
        object value = serializer.Deserialize(serialize, type);
        property.SetValue(gridProp, value, null);
      }
    }
    return gridProp;
  }
}



{% endhighlight %}

### Server dependencies

Export Helper functions are available in the Assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio & Essential JavaScript builds. Full list of assemblies needed for grid Export as follows

1. Syncfusion.EJ
2. Syncfusion.EJ.Export
3. Syncfusion.Linq.Base
4. Syncfusion.Compression.Base
5. Syncfusion.DocIO.Base
6. Syncfusion.XlsIO.Base
7. Syncfusion.PDF.Base

### Supported Export types


Currently server helper functions allows following three types of exporting

* Word
* Excel
* PDF


## Multiple Grid export to single file

To export multiple grids in current page, the method `ej.Grid.exportAll` can be used with 'jquery selector' as the parameter.

The JavaScript code snippet for it is

{% highlight javascript %}

 $('#exportAll').click(function(){
   ej.Grid.exportAll('MultipleExportToExcel',['#Grid1', '#Grid2']);
 });

{% endhighlight %}


The Server side C# snippet is

{% highlight c# %}

// Excel export

public void MultipleExportToExcel(string[] GridModel)
{
    ExcelExport exp = new ExcelExport();
    var EmployeeData = new NorthwindDataContext().EmployeeViews.Take(5).ToList();
    var OrderData = new NorthwindDataContext().OrdersViews.Take(5).ToList();
    bool initial = true;
    IWorkbook book = null;
    foreach(string gridProperty in GridModel)
    {
      GridProperties gridProp = ConvertObject(gridProperty);
      if (initial)
      {
        book = exp.Export(gridProp, EmployeeData, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-saffron", true);
        initial = false;
      }
      else
      {
        exp.Export(gridProp, OrderData, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-saffron", false, book, MultipleExportType.AppendToSheet, "Second Grid");
      }
    }
}

// Word export

public void MultipleExportToWord(string[] GridModel)
{
    WordExport exp = new WordExport();
    var EmployeeData = new NorthwindDataContext().EmployeeViews.Take(5).ToList();
    var OrderData = new NorthwindDataContext().OrdersViews.Take(5).ToList();
    IWordDocument document = null;
    bool initial = true;;
    foreach(string gridProperty in GridModel)
    {
       GridProperties gridProp = ConvertObject(gridProperty);
       if (initial)
       {
         document = exp.Export(gridProp, EmployeeData, "Export.docx", true, true, "flat-saffron", true);
         initial = false;
       } 
       else
       {
         exp.Export(gridProp, OrderData, "Export.docx", true, true, "flat-saffron", false, document, "Second Grid");
       }
    }
}

// PDF export

public void MultipleExportToPdf(string[] GridModel)
{
    PdfExport exp = new PdfExport();
    var EmployeeData = new NorthwindDataContext().EmployeeViews.Take(5).ToList();
    var OrderData = new NorthwindDataContext().OrdersViews.Take(5).ToList();
    PdfDocument document = null;
    bool initial = true;
    foreach(string gridProperty in GridModel)
    {
      GridProperties gridProp = ConvertObject(gridProperty);
      if (initial)
      {
        document = exp.Export(gridProp, EmployeeData, "Export.pdf", true, true, "flat-saffron", true);
        initial = false;
      } 
      else
      {
        exp.Export(gridProp, OrderData, "Export.pdf", true, true, "flat-saffron", false, document, "Second Grid");
      }
    }
}


{% endhighlight %}

## List of properties ignored on export

Following are the list of properties that are exclude during grid export, to reduce the unwanted data transfer to server.

* dataSource
* query
* rowTemplate
* detailsTemplate
* pageSettings
* enableRTL
* cssClass


##Export only visible records

By default `pageSettings` is ignored in export to facilitate all pages export. To achieve current visible page record export, `pageSettings` should be removed from ignore list using following code.

The snippet for this is.

{% highlight javascript %}

var grid = $('#Grid').ejGrid('instance');
grid.ignoreOnExport.splice(grid.ignoreOnExport.indexOf('pageSettings'), 1);

{% endhighlight %}

On server before calling the `Export` function, the data source should be processed using DataOperations's Execute function.

{% highlight c# %}

public void ExportToExcel(string GridModel)
{
   ExcelExport exp = new ExcelExport();
   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
   GridProperties properties = ConvertGridObject(GridModel);
   var dataSource = new DataOperations().Execute(GridModel, DataSource);
   exp.Export(properties, dataSource, "Export.xlsx", ExcelVersion.Excel2010, false, false, "flat-saffron");
}

public void ExportToWord(string GridModel)
{
   WordExport exp = new WordExport();
   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
   GridProperties properties = ConvertGridObject(GridModel);
   var dataSource = new DataOperations().Execute(GridModel, DataSource);
   exp.Export(properties, dataSource, "Export.docx", false, false, "flat-saffron");
}

public void ExportToPdf(string GridModel)
{
   PdfExport exp = new PdfExport();
   var DataSource = new NorthwindDataContext().OrdersViews.ToList();
   GridProperties properties = ConvertGridProperties(GridModel);
   var dataSource = new DataOperations().Execute(GridModel, DataSource);
   exp.Export(properties, dataSource, "Export.pdf", false, false, "flat-saffron");
}

private GridProperties ConvertGridProperties(string gridProperty)
{
  JavaScriptSerializer serializer = new JavaScriptSerializer();
  IEnumerable div = (IEnumerable) serializer.Deserialize(gridProperty, typeof(IEnumerable));
  GridProperties gridProp = new GridProperties();
  foreach(KeyValuePair < string, propertiesSection > datasource in div)
  {
     var property = gridProp.GetType().GetProperty(datasource.Key, BindingFlags.Instance ' BindingFlags.Public ' BindingFlags.IgnoreCase);
     if (property != null)
     {
       Type type = property.PropertyType;
       string serialize = serializer.Serialize(datasource.Value);
       propertiesSection value = serializer.Deserialize(serialize, type);
       property.SetValue(gridProp, value, null);
     }
   }

   return gridProp;
}


{% endhighlight %}

## Local data

By default, client data source is not sent to server to prevent unwanted data transfer since all data origin is server. In case, if you don't want to query the data source again for exporting in server, the grid's client [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource) can be sent to server on export postback by removing the [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource) property in grid's ignore list. The code snippet for this as follows

{% highlight javascript %}

var grid = $('#GridId').ejGrid('instance');
grid.ignoreOnExport.splice(grid.ignoreOnExport.indexOf('dataSource'), 1);

{% endhighlight %}


##Theme

The grid export have 13 theme option to match with our [built-in control themes](https://help.syncfusion.com/js/theming-in-essential-javascript-components#). They are

* default-theme
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme

Also, it has `none` option which will export the grid without any theme.  The desired theme name can be passed as a parameter to `Export` method and the code snippet for this as follows

{% highlight c# %}

[System.Web.Http.ActionName("ExcelExport")]

[AcceptVerbs("POST")]

public void ExcelExport()
{
  string gridModel = HttpContext.Current.Request.Params["GridModel"];
  GridProperties gridProperty = ConvertGridObject(gridModel);
  ExcelExport exp = new ExcelExport();
  IEnumerable < Order > result = db.Orders.ToList();
  exp.Export(gridProperty, result, "Export.xlsx", ExcelVersion.Excel2010, false, false, " gradient-azure");
}

{% endhighlight %}

## ColumnTemplate Exporting

To export the grid with columnTemplate we have to set `IsTemplateColumnIncluded` as true in the parameter of the export method. You can handle the template elements in server side event while exporting grid to various files such as Excel, PDF and Word.

The server side events available in template column exporting and its argument types are listed in the following table.

<table>
<tr>
<th>
Event Name
</th>
<th>
Argument
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
ExcelColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of excel sheet.
</td>
</tr>
<tr>
<td>
WordColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of word.
</td>
</tr>
<tr>
<td>
PdfColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of PDF.
</td>
</tr>
</table>

You can modify the template column of exporting files using server events. The code snippet for this is

{% highlight html %}

<ej-grid #grid [dataSource]="gridData" [allowPaging]="true" [toolbarSettings]="toolbarSettings" (toolbarClick)="toolbar($event)">
    <e-columns>
        <e-column headerText="Photo">
            <ng-template e-template let-data>
                <a href="https://www.syncfusion.com">data.FirstName</a>
            </ng-template>
         </e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="FirstName" headerText="FirstName"></e-column>
        <e-column field="LastName" headerText="LastName"></e-column>
        <e-column field="Country" headerText="Country"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;

	    public toolbarSettings;

        toolbar(e:any){

            if (e.itemName == "Excel Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/ExcelExport');
                e.cancel = true;
            }
            else if (e.itemName == "Word Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/WordExport')
                e.cancel = true;//prevent the default action
            }
            else if (e.itemName == "PDF Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/PdfExport')
                e.cancel = true;
            }
    }

   @ViewChild('grid') Grid: EJComponents<any, any>;

    constructor() {

       this.gridData = new ej.DataManager({ url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Employees" });

       this.toolbarSettings = { showToolbar: true, toolbarItems: ["excelExport", "wordExport", "pdfExport"] }

      }
   }

{% endhighlight %}
 
{% highlight c# %}

public void ExcelExport(string GridModel)
{
   ExcelExport exp = new ExcelExport();
   var DataSource =  new NorthwindDataContext().EmployeeViews.ToList();
   GridProperties obj = ConvertGridObject(GridModel);
   obj.ExcelColumnTemplateInfo = templateInfo;
   exp.Export(obj, DataSource, "Export.xlsx", ExcelVersion.Excel2010, false, true, "flat-saffron");
}

public void WordExport(string GridModel)
{
  WordExport exp = new WordExport();
  var DataSource =  new NorthwindDataContext().EmployeeViews.ToList();
  GridProperties obj = ConvertGridObject(GridModel);
  obj.WordColumnTemplateInfo = WordTemplateInfo;
  exp.Export(obj, DataSource, "Export.docx", false, true, "flat-saffron");
}

public void PdfExport(string GridModel)
{
  PdfExport exp = new PdfExport();
  var DataSource = new NorthwindDataContext().EmployeeViews.ToList();
  GridProperties obj = ConvertGridObject(GridModel);
  obj.PdfColumnTemplateInfo = PdfTemplateInfo;
  exp.Export(obj, DataSource, "Export.pdf", false, true, "flat-saffron");
}

public void templateInfo(object currentCell, object row)
{
   IRange range = (IRange)currentCell;
   object templates;
   foreach (var data in row.GetType().GetProperties())
   {
     if (range.Value.Contains(data.Name))
      {
         templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
         range.Value = range.Value.Replace(data.Name, templates.ToString());
         var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
         var urls = regex.Matches(range.Value.ToString()).OfType<match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
         IHyperLink hyperlink = (range.Parent as Syncfusion.XlsIO.Implementation.WorksheetImpl).HyperLinks.Add(range);
         hyperlink.Type = ExcelHyperLinkType.Url;
         hyperlink.TextToDisplay = templates.ToString();
         hyperlink.Address = urls;
      }
   }
}

public void WordTemplateInfo(object currentCell, object row)
{
   WTableCell wCell = (WTableCell)currentCell;
   object templates;
   foreach (var data in row.GetType().GetProperties())
   {
     if (wCell.LastParagraph.Text.ToString().Contains(data.Name))
      {
        templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
        var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
        var urls = regex.Matches(wCell.LastParagraph.Text).OfType<Match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
        wCell.LastParagraph.Text = "";
        IWField field = wCell.LastParagraph.AppendHyperlink(urls, templates.ToString(), HyperlinkType.WebLink);
      }
   }
}

public void PdfTemplateInfo(object currentCell, object row)
{
  Syncfusion.Pdf.Grid.PdfGridCell range = (Syncfusion.Pdf.Grid.PdfGridCell)currentCell;
  object templates;
  range.Value = Uri.UnescapeDataString(range.Value.ToString());
  foreach (var data in row.GetType().GetProperties())
  {
     if (range.Value.ToString().Contains(data.Name))
     {
        templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
        var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
        var urls = regex.Matches(range.Value.ToString()).OfType<Match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
        RectangleF rectangle = new RectangleF(10, 40, 30, 30);
        PdfUriAnnotation uriAnnotation = new PdfUriAnnotation(rectangle, urls);
        uriAnnotation.Text = templates.ToString();
        range.Value = uriAnnotation;
      }
   }
}

{% endhighlight %}

## DetailTemplate Exporting

To export the grid with detail template we have to set `IncludeDetailRow` as true in the parameter of the export method. You can handle template elements using server side event while exporting grid to various files such as Excel, PDF and Word.

The server side events available in detail template exporting and its argument types are listed in the following table.

<table>
<tr>
<th>
Event Name
</th>
<th>
Argument
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
ExcelDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of excel sheet.
</td>
</tr>
<tr>
<td>
WordDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of word.
</td>
</tr>
<tr>
<td>
PdfDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of PDF.
</td>
</tr>
</table>

You can modify the detailTemplate of exporting files using server events. The code snippet for this is

{% highlight html %}

<ej-grid #grid [allowPaging]="true" [allowSorting]="true" [dataSource]="gridData" [detailsTemplate]="temp" [allowPaging]="true" [toolbarSettings]="toolbarSettings" (toolbarClick)="toolbar($event)">
    <e-columns>
         <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="FirstName" headerText="FirstName"></e-column>
        <e-column field="LastName" headerText="LastName"></e-column>
        <e-column field="Country" headerText="Country"></e-column>             
    </e-columns>    
    <ng-template e-details-template let-data>
        <div>
        <b> More Details: </b> <br /><br /> <b class='detail'>Last Name</b> - data.LastName <br /> <br /> <b class='detail'>Home Phone</b> - data.HomePhone <br /> <br /> <b class='detail'>Extension No.</b> - data.Extension
        </div>
    </ng-template>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;

	    public toolbarSettings;

        temp: any;

        toolbar(e:any){

            if (e.itemName == "Excel Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/ExcelExport');
                e.cancel = true;
            }
            else if (e.itemName == "Word Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/WordExport')
                e.cancel = true;//prevent the default action
            }
            else if (e.itemName == "PDF Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/PdfExport')
                e.cancel = true;
            }
    }

   @ViewChild('grid') Grid: EJComponents<any, any>;

    constructor() {

       this.gridData = new ej.DataManager({ url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Employees" });

       this.toolbarSettings = { showToolbar: true, toolbarItems: ["excelExport", "wordExport", "pdfExport"] };

       this.temp = "#template";

      }
   }

{% endhighlight %}

{% highlight c# %}

public void ExcelExport(string GridModel)
{
   ExcelExport exp = new ExcelExport();
   var DataSource = new NorthwindDataContext().EmployeeViews.ToList();
   GridProperties obj = ConvertGridObject(GridModel);
   GridExcelExport exp2 = new GridExcelExport() { IncludeDetailRow = true, Theme = "flat-saffron", FileName = "Export.xlsx" };
   obj.ExcelDetailTemplateInfo = templateInfo;
   exp.Export(obj, DataSource, exp2);
}

public void WordExport(string GridModel)
{
  WordExport exp = new WordExport();
  var DataSource = new NorthwindDataContext().EmployeeViews.ToList();
  GridProperties obj = ConvertGridObject(GridModel);
  obj.WordDetailTemplateInfo = WordDetailTemplateInfo;
  GridWordExport exp1 = new GridWordExport() { IncludeDetailRow = true, Theme = "flat-saffron", FileName = "Export.docx" };
  exp.Export(obj, DataSource, exp1);
}

public void PdfExport(string GridModel)
{
  PdfExport exp = new PdfExport();
  var DataSource = new NorthwindDataContext().EmployeeViews.ToList();
  GridProperties obj = ConvertGridObject(GridModel);     
  obj.PdfDetailTemplateInfo = PdfDetailTemplateInfo;
  GridPdfExport exp3 = new GridPdfExport() { IncludeDetailRow = true, Theme = "flat-saffron", FileName = "Export.pdf" };
  exp.Export(obj, DataSource, exp3);
}

public void templateInfo(object currentCell, object row)
{
  IRange range = (IRange)currentCell;
  object templates;
  foreach (var data in row.GetType().GetProperties())
  {
     if (range.Value.Contains(data.Name))
     {
       templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
       range.Value = range.Value.Replace(data.Name, templates.ToString());
       var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
       foreach (var c in charsToRemove)
       {
         range.Value = range.Value.ToString().Replace(c, string.Empty);
       }
       range.HorizontalAlignment = ExcelHAlign.HAlignCenter;
    }
  }
}
   
public void WordDetailTemplateInfo(object currentCell, object row)
{
   WTableCell wCell = (WTableCell)currentCell;
   object templates;
   foreach (var data in row.GetType().GetProperties())
   {
      if (wCell.LastParagraph.Text.ToString().Contains(data.Name))
      {
        templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
        wCell.LastParagraph.Text = wCell.LastParagraph.Text.ToString().Replace(data.Name, templates.ToString());
        var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
        foreach (var c in charsToRemove)
        {
           wCell.LastParagraph.Text  = wCell.LastParagraph.Text.ToString().Replace(c, string.Empty); //
        }
      }
   }
}

public void PdfDetailTemplateInfo(object currentCell, object row)
{
   Syncfusion.Pdf.Grid.PdfGridCell range = (Syncfusion.Pdf.Grid.PdfGridCell)currentCell;
   object templates;
   foreach (var data in row.GetType().GetProperties())
   {
     if (range.Value.ToString().Contains(data.Name))
     {
       templates = row.GetType().GetProperty(data.Name).GetValue(row, null);
       range.Value = range.Value.ToString().Replace(data.Name, templates.ToString());
       var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
       foreach (var c in charsToRemove)
       {
          range.Value = range.Value.ToString().Replace(c, string.Empty);
        }
     }
   }
}

private GridProperties ConvertGridObject(string gridProperty)
{
  JavaScriptSerializer serializer = new JavaScriptSerializer();
  IEnumerable div = (IEnumerable)serializer.Deserialize(gridProperty, typeof(IEnumerable));
  GridProperties gridProp = new GridProperties();
  foreach (KeyValuePair<string, object> data in div)
  {
     var property = gridProp.GetType().GetProperty(data.Key, BindingFlags.Instance | BindingFlags.Public | BindingFlags.IgnoreCase);
     if (property != null)
     {
       Type type = property.PropertyType;
       string serialize = serializer.Serialize(data.Value);
       object value = serializer.Deserialize(serialize, type);
       property.SetValue(gridProp, value, null);
     }
  }
  return gridProp;
}

{% endhighlight %}

## Exporting with Custom Summary

In Exporting, custom summary needs to be handled using `QueryCustomSummaryInfo` server-side event.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

    <ej-grid [allowPaging]="true" [dataSource]="gridData" [showSummary]="true" [summaryRows]="summaryrows">

     <e-columns>
        <e-column field="OrderID" headertext="OrderID" width="70" textalign="right"></e-column>
        <e-column field="CustomerID" headertext="Customer ID" width="70" textalign="left"></e-column>
        <e-column field="EmployeeID" headertext="Employee ID" width="70" textalign="left"></e-column>
        <e-column field="ShipCity" headertext="Ship City" idth="70" textalign="left"></e-column>
        <e-column field="Freight" headertext="Freight" width="80" format="{0:C}" textalign="right"></e-column>
     </e-columns>

  </ej-grid>
{% endhighlight  %}

{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public summaryrows;
        public toolbarSettings;
        toolbar(e:any){

            if (e.itemName == "Excel Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/ExcelExport');
                e.cancel = true;
            }
            else if (e.itemName == "Word Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/WordExport')
                e.cancel = true;//prevent the default action
            }
            else if (e.itemName == "PDF Export") {
                this.Grid.widget.export('http://js.syncfusion.com/demos/ejServices/api/grid/PdfExport')
                e.cancel = true;
            }
        };
        constructor()
        {
            //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.summaryrows = [{ 
                summaryColumns: [{ 
                  summaryType: ej.Grid.SummaryType.Custom, 
                  displayColumn: "Freight", 
                  customSummaryValue: function currency(args,data) {
                       var rs = 100000;
                       var value = 0.017;
                       return (rs * value);
                  }, 
                  format: "{0:C2}" }] 
            }];
            this.toolbarSettings = { showToolbar: true, toolbarItems: ["excelExport", "wordExport", "pdfExport"] };
        }
    }

{% endhighlight %}

{% highlight c# %}

        public void ExcelExport(string GridModel)
        {
            ExcelExport exp = new ExcelExport();
            GridExcelExport GridExp = new GridExcelExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-saffron";
            GridExp.FileName = "Export.xlsx";
            var DataSource = new NorthwindDataContext().OrdersViews.Take(100).ToList();
            GridProperties obj = ConvertGridObject(GridModel);
            exp.Export(obj, DataSource, GridExp);
        }
        public void WordExport(string GridModel)
        {
            WordExport exp = new WordExport();
            GridWordExport GridExp = new GridWordExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-saffron";
            GridExp.FileName = "Export.docx";
            var DataSource = new NorthwindDataContext().OrdersViews.Take(100).ToList();
            GridProperties obj = ConvertGridObject(GridModel);
            exp.Export(obj, DataSource, GridExp);
        }
        public void PdfExport(string GridModel)
        {
            PdfExport exp = new PdfExport();
            GridPdfExport GridExp = new GridPdfExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-saffron";
            GridExp.FileName = "Export.pdf";
            var DataSource = new NorthwindDataContext().OrdersViews.Take(100).ToList();
            GridProperties obj = ConvertGridObject(GridModel);
            exp.Export(obj, DataSource, GridExp);
        }
        private object SummaryCellInfo(IQueryable arg1, SummaryColumn arg2)
        {
            var rs = 0; double value = 0;
            if (arg2.DisplayColumn == "Freight")
            {
                rs = 100000;
                value = 0.017;
            }

            return (rs * value);
        }
        private GridProperties ConvertGridObject(string gridProperty)
        {
            JavaScriptSerializer serializer = new JavaScriptSerializer();
            IEnumerable div = (IEnumerable)serializer.Deserialize(gridProperty, typeof(IEnumerable));
            GridProperties gridProp = new GridProperties();
            foreach (KeyValuePair<string, object> ds in div)
            {
                var property = gridProp.GetType().GetProperty(ds.Key, BindingFlags.Instance | BindingFlags.Public | BindingFlags.IgnoreCase);
                if (property != null)
                {
                    Type type = property.PropertyType;
                    string serialize = serializer.Serialize(ds.Value);
                    object value = serializer.Deserialize(serialize, type);
                    property.SetValue(gridProp, value, null);
                }
            }
            return gridProp;
        }
   
{% endhighlight  %}

{% endtabs %}

## Hierarchy Grid Exporting

Grid will be exported with its child Grid. This can be achieved by enabling `IncludeChildGrid` property of the respective Exporting classes like `GridExcelExport`, `GridWordExport` and `GridPdfExport` and include the dataSource needed for ChildGrid in the GridProperties object after deserializing them. Remaining procedures will be same as the normal Grid Exporting.

N> Excel File will be exported in the collapsed state with the expand/collapse icon whereas other file-formats like PDF and Word will be exported in expanded state.

{% highlight html %}

<ej-grid id="Grid"  [allowPaging]="true"  [dataSource]="gridData" [toolbarSettings]="toolbarSettings" [exportToWordAction]= "exportWord" [exportToExcelAction]= "exportExcel" [exportToPdfAction]= "exportPdf"   [childGrid]="childData"  >
    <e-columns>
        <e-column field="EmployeeID" headerText="Employee ID"  width="85" textAlign="right"></e-column>
        <e-column field="FirstName" headerText="First Name" textAlign="left"  width="100"></e-column>
        <e-column field="Title" headerText="Title " width="120" textAlign="left"></e-column>        
        <e-column field="City" headerText="City" textAlign="left" width="10"></e-column> 
        <e-column field="Country" headerText="Country" textAlign="left" width="100"></e-column>        
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public childData: any;    
    public toolbarSettings;
    public exportPdf =  "http://js.syncfusion.com/ExportingServices/api/JSGridExport/HierarchyPdfExport";
    public exportWord = "http://js.syncfusion.com/ExportingServices/api/JSGridExport/HierarchyWordExport";
    public exportExcel =  "http://js.syncfusion.com/ExportingServices/api/JSGridExport/HierarchyExcelExport";
    constructor() {
		@ViewChild('grid') Grid: EJComponents<any, any>;
        this.gridData = (window as any).employeeView;
		
        this.toolbarSettings = { showToolbar: true, toolbarItems: ["excelExport", "wordExport", "pdfExport"] }
        this.childData = {
            dataSource: ej.DataManager({ url: "http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders", crossDomain: true, offline: true }),
            queryString: "EmployeeID",
            allowPaging: true,
			columns: [
                      { field: "OrderID", headerText: 'Order ID', textAlign: ej.TextAlign.Right, width: 75 },
                      { field: "ShipCity", headerText: 'Ship City',  width: 100 },
                      { field: "Freight", headerText: 'Freight', textAlign: ej.TextAlign.Right, format: "{0:C2}", width: 120 },
                      { field: "ShipName", headerText: 'Ship Name', width: 100 }
                    ]
        }
}

{% endhighlight %}



{% highlight c# %}
 
    public class GridController : ApiController
    {
        NorthwindDataContext db = new NorthwindDataContext();
        
        private GridProperties ConvertGridObject(string gridProperty)
        {
            JavaScriptSerializer serializer = new JavaScriptSerializer();
            IEnumerable div = (IEnumerable)serializer.Deserialize(gridProperty, typeof(IEnumerable));
            GridProperties gridProp = new GridProperties();
            foreach (KeyValuePair<string, object> data in div)
            {
                var property = gridProp.GetType().GetProperty(data.Key, BindingFlags.Instance | BindingFlags.Public | BindingFlags.IgnoreCase);
                if (property != null)
                {
                    Type type = property.PropertyType;
                    object value = null;
                    string serialize = serializer.Serialize(data.Value);
                    if (data.Key == "childGrid" && data.Value != null)
                        value = ConvertGridObject(serialize);
                    else if (data.Key == "query")
                        continue;
                    else
                        value = serializer.Deserialize(serialize, type);
                    property.SetValue(gridProp, value, null);
                }
            }
            return gridProp;
        }
        [System.Web.Http.ActionName("HierarchyExcelExport")]
        [AcceptVerbs("Post")]
        public void HierarchyExcelExport()
        {
            GridExcelExport GridExp = new GridExcelExport();
            string gridModel = HttpContext.Current.Request.Params["GridModel"];
            GridProperties gridProperty = ConvertGridObject(gridModel);
            ExcelExport exp = new ExcelExport();
            IEnumerable<Employee> result = db.Employees.ToList();
            gridProperty.ChildGrid.DataSource = db.Orders.Take(100).ToList();
            GridExp.IncludeChildGrid = true;
            GridExp.Theme = "default-theme";
            GridExp.FileName = "Export.xlsx";
            exp.Export(gridProperty, result, GridExp);
        }
        [System.Web.Http.ActionName("HierarchyPdfExport")]
        [AcceptVerbs("Post")]
        public void HierarchyPdfExport()
        {
            GridPdfExport GridExp = new GridPdfExport();
            string gridModel = HttpContext.Current.Request.Params["GridModel"];
            GridProperties gridProperty = ConvertGridObject(gridModel);
            PdfExport exp = new PdfExport();
            IEnumerable<Employee> result = db.Employees.ToList();
            gridProperty.ChildGrid.DataSource = db.Orders.Take(100).ToList();
            GridExp.IncludeChildGrid = true;
            GridExp.Theme = "default-theme";
            GridExp.FileName = "Export.pdf";
            exp.Export(gridProperty, result, GridExp);
        }
        [System.Web.Http.ActionName("HierarchyWordExport")]
        [AcceptVerbs("Post")]
        public void HierarchyWordExport()
        {
            GridWordExport GridExp = new GridWordExport();
            string gridModel = HttpContext.Current.Request.Params["GridModel"];
            GridProperties gridProperty = ConvertGridObject(gridModel);
            WordExport exp = new WordExport();
            IEnumerable<Employee> data = db.Employees.ToList();
            gridProperty.ChildGrid.DataSource = db.Orders.Take(100).ToList();
            GridExp.IncludeChildGrid = true;
            GridExp.Theme = "default-theme";
            GridExp.FileName = "Export.docx";
            exp.Export(gridProperty, (IEnumerable)data, GridExp);
        }
    }



{% endhighlight %}

The server side events available in Hierarchy Grid exporting and its argument types are listed in the following table.

<table>
<tr>
<th>
Event Name
</th>
<th>
Argument
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
ExcelChildGridInfo
</td>
<td>
current row, row data, GridProperties
</td>
<td>
Customize the cell and child Grid
</td>
</tr>
<tr>
<td>
PdfChildGridInfo
</td>
<td>
current row, row data, GridProperties
</td>
<td>
Customize the cell and child Grid
</td>
</tr>
<tr>
<td>
WordChildGridInfo
</td>
<td>
current row, row data, GridProperties
</td>
<td>
Customize the cell and child Grid
</td>
</tr>
</table>

