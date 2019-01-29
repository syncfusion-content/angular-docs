---
title: Syncfusion Report service for .Net Core platform
description: report service for .Net Core platform
platform: Angular
control: ReportViewer
documentation: ug
keywords: IReportController, Report Controller, ApiController, ReportHelper
---

# Report Controller

The ReportViewer uses Web API services to process the report file, process the request from control, and return the processed data from control to client side.

## Create a Web API Controller for .NET Core platform
Right-click the **Project**, select **Add** and then choose **Web API Controller Class file** from the listed templates.

### References
You should add the following packages for the ReportViewer:

<table>
<tr>
<th>
Package</th>
<th>
Purpose
</th>
</tr>
<tr>
<td>Syncfusion.EJ.AspNet.Core</td>
<td>Builds the ReportViewer controls with the tag helper.</td>
</tr>
<tr>
<td>Syncfusion.EJ.ReportViewer.AspNet.Core</td>
<td>Builds the server-side implementations.</td>
</tr>
<tr>
<td>System.Data.SqlClient</td>
<td>This is an optional package for the report viewer. It should be referred in the project when rendering the RDL report, which contains the SQL Server and SQL Azure data source. Also, the package version should be higher than 4.1.0 . </td>
</tr>
</table>

If you install the above NuGet packages, it will automatically add the following ReportViewer dependent NuGet file in your application.

<table>
<tr>
<th>
Package</th>
<th>
Purpose
</th>
</tr>
<tr>
<td>Syncfusion.EJ</td>
<td>Builds the ReportViewer controls with the tag helper.</td>
</tr>
<tr>
<td>Syncfusion.Report.Net.Core</td>
<td>It is a base library for the <b>Syncfusion.EJ.ReportViewer.AspNet.Core</b>package.</td>
</tr>
<tr>
<td>Syncfusion.Compression.Net.Core</td>
<td>Supports for exporting the report to PDF, Microsoft Word, and Microsoft Excel format. It is a base library for the <b>Syncfusion.Pdf.Net.Core</b>, <b>Syncfusion.DocIO.Net.Core</b>, and <b>Syncfusion.XlsIO.Net.Core</b> packages. </td>
</tr>
<tr>
<td>Syncfusion.Pdf.Net.Core</td>
<td>Supports for exporting a report to PDF format.</td>
</tr>
<tr>
<td>Syncfusion.DocIO.Net.Core</td>
<td>Supports for exporting a report to Microsoft Word.</td>
</tr>
<tr>
<td>Syncfusion.XlsIO.Net.Core</td>
<td>Supports for exporting a report to Microsoft Excel.</td>
</tr>
<tr>
<td>Syncfusion.OfficeChart.Net.Core</td>
<td>It is a base library of the <b>Syncfusion.XlsIO.Net.Core package</b>.</td>
</tr>
<tr>
<td>Newtonsoft.Json</td>
<td>Serialize and deserialize data for the ReportViewer. It is a mandatory package for the ReportViewer, and the package version should be higher than 10.0.1 for NET Core 2.0 and others should be higher than 9.0.1.</td>
</tr>
</table>

N> Ensure whether all the above dependent packages are added properly after the NuGet package installation is completed.

### Inherit IReportController
 
The ApiController should inherit the `IReportController` interface to build the ReportViewer compatible Web API, and the `ReportHelper` should be used with `IReportController` interface implemented methods. The `ReportHelper` will perform the server-side related process and will return the required data to render the report in the Report Viewer. Here, the sample code is provided with an MVC application to build the Web API service along with the existing controller.

Add the following code example in the controller page.

~~~ csharp

using System.Collections.Generic;
using Microsoft.AspNetCore.Mvc;

namespace ReportViewerDemo.Controllers
{
    public class HomeController : ApiController, Syncfusion.EJ.ReportViewer.IReportController
    {
        // Report viewer requires a memory cache to store the information of consecutive client request and
        // have the rendered report viewer information in server.
        private Microsoft.Extensions.Caching.Memory.IMemoryCache _cache;

        // IHostingEnvironment used with sample to get the application data from wwwroot.
        private Microsoft.AspNetCore.Hosting.IHostingEnvironment _hostingEnvironment;

        // Post action to process the report from server based json parameters and send the result back to the client.
        public HomeController(Microsoft.Extensions.Caching.Memory.IMemoryCache memoryCache, 
            Microsoft.AspNetCore.Hosting.IHostingEnvironment hostingEnvironment)
        {
            _cache = memoryCache;
            _hostingEnvironment = hostingEnvironment;
        }

        public IActionResult Index()
        {
            return View();
        }

        ...
        ...
        ...

        // Post action to process the report from server based json parameters and send the result back to the client.
        public object PostReportAction([FromBody] Dictionary<string, object> jsonArray)
        {
            return Syncfusion.EJ.ReportViewer.ReportHelper.ProcessReport(jsonArray, this, this._cache);
        }

        // Method will be called to initialize the report information to load the report with ReportHelper for processing.
        public void OnInitReportOptions(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
        {
            string basePath = _hostingEnvironment.WebRootPath;
            // Here, we have loaded the sample report report from application the folder wwwroot. Sample.rdl should be there in wwwroot application folder.
            FileStream reportStream = new FileStream(basePath + @"\invoice.rdl", FileMode.Open, FileAccess.Read);
            reportOption.ReportModel.Stream = reportStream;
        }

        // Method will be called when reported is loaded with internally to start to layout process with ReportHelper.
        public void OnReportLoaded(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
        {
        }
        
        //Get action for getting resources from the report
        [ActionName("GetResource")]
        [AcceptVerbs("GET")]
        // Method will be called from Report Viewer client to get the image src for Image report item.
        public object GetResource(Syncfusion.EJ.ReportViewer.ReportResource resource)
        {
            return Syncfusion.EJ.ReportViewer.ReportHelper.GetResource(resource, this, _cache);
        }
    }
}

~~~

### IReportController

The `IReportController` interface has declaration of action methods that is defined in the WebAPI Controller for processing the RDL/RDLC files and request from the ReportViewer control. The `IReportController` has the following action methods declaration.

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Action (HttpGet) method for getting resource for a report. </td></tr>
<tr>
<td>
PostReportAction</td><td>
Action (HttpPost) method for posting the request for report process. </td></tr>
<tr>
<td>
PostFormReportAction</td><td>
Action (HttpPost) method for posting the request to export the report. It requires only in ASP.NET Core platform.</td></tr>
<tr>
<td>
OnInitReportOptions</td><td>
Triggers the report initialization method when the report has to be processed.</td></tr>
<tr>
<td>
OnReportLoaded</td><td>
Triggers the report loaded method when loading the report and subreport.</td></tr>
</table>

### ReportHelper

The class `ReportHelper` contains helper methods that help the process Post/Get request from the ReportViewer control and returns the response to ReportViewer control. The `ReportHelper` has the following methods. 

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Returns the report resource for the requested key.</td></tr>
<tr>
<td>
ProcessReport</td><td>
Processes the report request and returns the result.</td></tr>
</table>

### WebAPI Routing

You can route the WebAPI in the configure method into the Startup.cs file as follows.

~~~ csharp

 using Microsoft.AspNetCore.Builder;
 using Microsoft.AspNetCore.Hosting;
 using Microsoft.Extensions.Configuration;
 using Microsoft.Extensions.DependencyInjection;
 
 namespace ReportViewerDemo
 {
     public class Startup
     {
         public Startup(IConfiguration configuration)
         {
             Configuration = configuration;
         }
 
         public IConfiguration Configuration { get; }
 
         // This method gets called by the runtime. Use this method to add services to the container.
         public void ConfigureServices(IServiceCollection services)
         {
             services.AddMvc();
         }
 
         // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
         public void Configure(IApplicationBuilder app, IHostingEnvironment env)
         {
             if (env.IsDevelopment())
             {
                 app.UseDeveloperExceptionPage();
             }
 
             app.UseMvc();
 
             app.UseMvc(routes =>
             {
                 routes.MapRoute(
                     name: "default",
                     template: "api/{controller=ReportApi}/ {action=Index}/{id?}");
             });
         }
     }
 }
 
~~~

### Enable CORS

1 You can add cors in the ConfigureServices method to the Startup.cs file as follows.

    ~~~ csharp

    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;

    namespace ReportViewerDemo
    {
        public class Startup
        {
            public Startup(IConfiguration configuration)
            {
                Configuration = configuration;
            }

            public IConfiguration Configuration { get; }

            // This method gets called by the runtime. Use this method to add services to the container.
            public void ConfigureServices(IServiceCollection services)
            {
                services.AddMvc();
                services.AddCors(o => o.AddPolicy("MyPolicy", builder =>
                {
                    builder.AllowAnyOrigin()
                        .AllowAnyMethod()
                        .AllowAnyHeader();
                }));
            }

            // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
            public void Configure(IApplicationBuilder app, IHostingEnvironment env)
            {
                if (env.IsDevelopment())
                {
                    app.UseDeveloperExceptionPage();
                }

                app.UseMvc();

                app.UseMvc(routes =>
                {
                    routes.MapRoute(
                        name: "default",
                        template: "api/{controller=ReportApi}/{action=Index}/{id?}");
                });
            }
        }
    }

    ~~~
 
2 Add the [EnableCors] attribute to the ApiController class as follows.

    ~~~ csharp

    using System.Collections.Generic;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.AspNetCore.Cors;

    namespace ReportViewerDemo.Controllers
    {
        [EnableCors("MyPolicy")]
        public class HomeController : ApiController, Syncfusion.EJ.ReportViewer.IReportController
        {
            // Report viewer requires a memory cache to store the information of consecutive client request and
            // have the rendered report viewer information in server.
            private Microsoft.Extensions.Caching.Memory.IMemoryCache _cache;

            // IHostingEnvironment used with sample to get the application data from wwwroot.
            private Microsoft.AspNetCore.Hosting.IHostingEnvironment _hostingEnvironment;

            // Post action to process the report from server based json parameters and send the result back to the client.
            public HomeController(Microsoft.Extensions.Caching.Memory.IMemoryCache memoryCache, 
                Microsoft.AspNetCore.Hosting.IHostingEnvironment hostingEnvironment)
            {
                _cache = memoryCache;
                _hostingEnvironment = hostingEnvironment;
            }

            public IActionResult Index()
            {
                return View();
            }

            ...
            ...
            ...

            // Post action to process the report from server based json parameters and send the result back to the client.
            public object PostReportAction([FromBody] Dictionary<string, object> jsonArray)
            {
                return Syncfusion.EJ.ReportViewer.ReportHelper.ProcessReport(jsonArray, this, this._cache);
            }

            // Method will be called to initialize the report information to load the report with ReportHelper for processing.
            public void OnInitReportOptions(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
            {
                string basePath = _hostingEnvironment.WebRootPath;
                // Here, we have loaded the sample report report from application the folder wwwroot. Sample.rdl should be there in wwwroot application folder.
                FileStream reportStream = new FileStream(basePath + @"\invoice.rdl", FileMode.Open, FileAccess.Read);
                reportOption.ReportModel.Stream = reportStream;
            }

            // Method will be called when reported is loaded with internally to start to layout process with ReportHelper.
            public void OnReportLoaded(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
            {
            }
            
            //Get action for getting resources from the report
            [ActionName("GetResource")]
            [AcceptVerbs("GET")]
            // Method will be called from Report Viewer client to get the image src for Image report item.
            public object GetResource(Syncfusion.EJ.ReportViewer.ReportResource resource)
            {
                return Syncfusion.EJ.ReportViewer.ReportHelper.GetResource(resource, this, _cache);
            }
        }
    }

    ~~~

N> You cannot load the application report with path information in ASP.NET Core. So, you should load the report as `Stream` like an example provided above in `OnInitReportOptions`. If you need to get the invoice sample report, then you can obtain it from the Syncfusion ASP.NET Core sample browser installed location (wwwroot\reports\invoice.rdl).
