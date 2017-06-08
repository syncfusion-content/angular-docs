---
layout: post
title: Splitter Integration
description: Splitter Integration
platform: Angular-2
control: Splitter
documentation: ug
---

# Splitter Integration

**Splitter** allows you to use other **Essential JavaScript** products inside the pane. The integrated function of those components can be used in other panes of the Splitter.

## Configuring other components in Splitter

The following steps explain the implementation of Splitter integration.

In the **HTML** page set the **&lt;div&gt;** element for rendering Splitter with two panes. The first pane has the **TreeView** content and the next one has some content that is related to TreeView.

Define treeview **nodeSelect** event in HTML page.


{% highlight html %}

    <div class="content-container-fluid">
    <div class="row">
    <div class="cols-sample-area" style="height:400px; margin:0 auto;">
        <ej-splitter id="outterSpliter" class="ang-splitter" height ="100%" width="485" [properties]="proper"
            enableAutoResize="true">
            <div>					
                <div class="cont">
                    <h3 class="h3">AngularJS</h3>
                    <ej-treeview  class="visibleHide" (nodeSelect)="treeClicked($event)" [fields]="fields">                                
                    </ej-treeview>
                </div>
            </div>                    
                <div class="cont">
                    <div class="_content">
                        Select any product from the tree to show the description.
                    </div>
                    <div class="tools" style="display:none">
                    <h3>Tools</h3>
                            Essential Tools is an collection of user interface components used to create interactive
                            JavaScript applications.
                    </div>
                    <div class="chart" style="display:none">
                        <h3>Chart</h3>
                Essential Chart is a business-oriented charting component.
                    </div>
                    <div class="grid" style="display:none">
                    <h3>Grid</h3>
                Essential JavaScript Grid offers full featured a Grid control with extensive support for
                Grouping and the display of hierarchical data.
                    </div>
                </div>
                </ej-splitter>
            </div>                                     
        </div>
    </div>
{% endhighlight %}

Define Splitter pane properties and Treeview fields in constructor file.

{% highlight javascript %}

    export class AppComponent {
    proper:Array<{paneSize:string}>;
    localData:Array<{}>;
    fields:Object;
    constructor() {
	this.proper = [{ paneSize: "50%" }, {paneSize:"50%"}]
    this.localData=[
      { id: 1, name: "Tools", hasChild: true, expanded: false },
      { id: "tools", pid:1,name: "Description"},
      { id: 3, name: "Chart", hasChild: true, expanded: false },
      { id: "chart", pid:3,name: "Description"},
      { id: 5, name: "Grid", hasChild: true, expanded: false },
      { id: "grid", pid:5,name: "Description"},
    ];
    this.fields = { id: "id", parentId: "pid", text: "name", hasChild: "hasChild", dataSource: this.localData, expanded: "expanded" };
    }
    treeClicked(sender){        
    if (sender.currentElement.hasClass('e-item last')) {
                var content = $('.' + sender.currentElement[0].id).html();
                $('._content').html(content);        
    }
    }
    }

{% endhighlight %}

When the node is selected in TreeView, the integrated output is displayed in the second pane.

The output for the above code as follows,

![](Splitter-Integration_images\Splitter-Integration_img1.png) 

![](Splitter-Integration_images\Splitter-Integration_img2.png) 