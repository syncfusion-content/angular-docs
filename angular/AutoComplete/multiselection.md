---
layout: post
title: multiple columns
description: multiple columns
platform: Angular
control: Autocomplete 
documentation: ug
---

##Multi-Selection

The AutoComplete component helps you to select multiple values from the suggestion list using the **multiSelectMode** property.

There are two types of multi-selection mode.

1. **VisualMode** – Selection values are displayed in separate box with close like button.

{% highlight html %}

   <input type="text" id="delimit" ej-autocomplete  width="300" [showPopupButton]="true" multiSelectMode="visualmode" watermarkText="Select a language" [dataSource]="language" />



{% endhighlight %}



{% highlight js %}

export class AppComponent {
  language: Array<string>;
    constructor() {
        this.language = ['ActionScript', 'AppleScript', 'ASP', 'BASIC', 'BeanShell',
            'C', 'C++', 'C#', 'Clojure', 'COBOL', 'ColdFusion', 'DataFlex', 'DCL',
            'Erlang', 'E#', 'Fortran', 'F#', 'Flex', 'Google Apps Script', 'Groovy', 'Haskell', 'Hope', 'IBM HAScript',
            'Java', 'JavaScript', 'J#', 'Lisp', 'MATLAB', 'Oak', 'Perl', 'PHP',
            'Python', 'Ruby', 'Scala', 'Scheme', 'T-SQL', 'WebQL', 'ZOPL'];
    }
}



{% endhighlight %}





Run the above code to render the following output.

![](multiplecolumns_images\multiplecolumns_img2.png)


2. **Delimiter** – Selection values are separated using the delimiter character which can be specified using **delimiterChar** property.


{% highlight html %}

    <input type="text" id="delimit" ej-autocomplete  width="300" [showPopupButton]="true" multiSelectMode="delimiter" watermarkText="Select a language" [dataSource]="language" />


{% endhighlight %}



Run the above code to render the following output.

![](multiplecolumns_images\multiplecolumns_img3.png)



