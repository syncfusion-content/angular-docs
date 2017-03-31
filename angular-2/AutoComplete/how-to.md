---
layout: post
title: see-also
description: see also
platform: angular-1
control: Autocomplete
documentation: ug
---


## How To

### Set Client Side Validation for Autocomplete?

Since the Autocomplete is a form control, we can set the validation for Autocomplete on form submission. We can use the **e-validationrules** property to set the validation rules and **e-validationmessage** property to display the error message on form validation.



**NOTE**

[jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js)script file should be referred for validation, for more details, refer[here.](https://jqueryvalidation.org/documentation/)

{% highlight html %}


<!DOCTYPE html>
<html lang="en" ng-app="AutoCompleteApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Autocomplete</title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/14.4.0.15/js/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/14.4.0.15/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/14.4.0.15/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="AutocompleteCtrl">

</html>



{% endhighlight %}



{% highlight html %}
    <div class="row">
    <form id="form1">       
 <input type="text" ej-autocomplete width="300" [dataSource]="countries" [fields]="fields" [validationRules]="validrules" [validationMessage]="validmessage" watermarkText="Search a country" />
         <input type="submit" value="validate" id="btn" />    
     </form>
    </div>
{% endhighlight %}



{% highlight js %}


export class AppComponent {
   countries: Array<any>;
    fields: Object;
    validrules:Object;
    validmessage:Object;
    constructor() {     
        this.countries = [

                { name: "Austria", index: "C1" },

                { name: "Australia", index: "C2" }, { name: "Antarctica", index: "C3" },

                { name: "Bangladesh", index: "C4" }, { name: "Belgium", index: "C5" },

                { name: "Brazil", index: "C6" },

                { name: "Canada", index: "C7" }, { name: "China", index: "C8" },

                { name: "Cuba", index: "C9" },

                { name: "Denmark", index: "C10" }, { name: "Dominica", index: "C11" },

                { name: "Europe", index: "C12" }, { name: "Egypt", index: "C13" },

                { name: "England", index: "C14" },

                { name: "India", index: "C15" }, { name: "Indonesia", index: "C16" }

                ];
            this.fields = { key: 'index', text: 'name' };
            this.validrules = { required: true};
            this.validmessage = {required: "please select some value"}
    }
    
}



{% endhighlight %}


![](howto_images\Validate.png)

**NOTE**

jQuery predefined error messages to that annotation attribute will be shown when this property is not defined. The below given example explain this behavior of ‘required’ attribute.


### Get the key value of the selected item?



By default, the selected item’s key value will be maintained in the **e-selectvaluebykey** model value. If we take the instance of the autocomplete and in the model, the selected value’s key will be maintained in the **e-selectvalueBykey** property.


{% highlight html %}

  <input type="text" ej-autocomplete width="300" [dataSource]="countries" [fields]="fields" [selectValueByKey]="keyvalue" watermarkText="Search a country" />

{% endhighlight %}

{% highlight js %}

export class AppComponent {
   countries: Array<any>;
    fields: Object;
    keyvalue:String;
    constructor() {     
        this.countries = [

                { name: "Austria", index: "C1" },

                { name: "Australia", index: "C2" }, { name: "Antarctica", index: "C3" },

                { name: "Bangladesh", index: "C4" }, { name: "Belgium", index: "C5" },

                { name: "Brazil", index: "C6" },

                { name: "Canada", index: "C7" }, { name: "China", index: "C8" },

                { name: "Cuba", index: "C9" },

                { name: "Denmark", index: "C10" }, { name: "Dominica", index: "C11" },

                { name: "Europe", index: "C12" }, { name: "Egypt", index: "C13" },

                { name: "England", index: "C14" },

                { name: "India", index: "C15" }, { name: "Indonesia", index: "C16" }

                ];
            this.fields = { key: 'index', text: 'name' };
            this.keyvalue = "C2"
    }
}


{% endhighlight %}


![](howto_images\get-the-key-value-of-the-selected-item_img1.png)


But when using the remote datasource, we cannot able to maintain the key value in the **e-selectvaluekey** model property. Hence in that case we can use the **e-select** property to get the key value in the select event’s argument.

{% highlight html %}

<input type="text" ej-autocomplete width="300" [query]="query" [fields]="fields" watermarkText="Search a customer" [dataSource]="dataManger" (select)="onselect($event)" />

{% endhighlight %}

{% highlight js %}

export class AppComponent {
     dataManger: any;
    fields: any;
    query: any;
    value: string;
    constructor() {
        this.fields = { text: 'ContactName', key: 'SupplierID' };
        this.dataManger = ej.DataManager({ url: 'http://mvc.syncfusion.com/Services/Northwnd.svc/' }); 
        this.query = ej.Query().from('Suppliers').select('SupplierID', 'ContactName');
    }
onselect(event) {
    //Get key here
       var mykey= event.key;
    }

}

{% endhighlight %}