---
layout: post
title: Properties, options, methods and events of Essential JS ejBarcode widget
documentation: How to use Properties of Essential JS ejBarcode widget
platform: Angular
control: Barcode
documentation: ug
keywords: ejBarcode 
---

# Custom Design for Barcode control.
<ts root="datavisualization" />
The Barcode can be easily configured to the DOM element. you can create a Barcode with a highly customizable look and feel.

Syntax

ej-barcode


Example
{:.example}


{% highlight html %}
 
//Create the barcode by setting the symbologyType and providing input URL to the text property. QR code is rendered by default.
<ej-barcode text="http://www.syncfusion.com" id="qrbarcode" xDimension="8">
</ej-barcode>
{% endhighlight %}









## Members








### barcodeToTextGapHeight `number`
{:#members:barcodetotextgapheight}








Specifies the distance between the Barcode and text below it.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 10 pixels








Example
{:.example}


{% highlight html %}
 
// Add the below code to set barcodeToTextGapHeight during initialization 
<ej-barcode text="SYNCFUSION" id="code39" [barcodeToTextGapHeight]="50" symbologyType="code39">
</ej-barcode>
{% endhighlight %}







### barHeight `number`
{:#members:barheight}








Specifies the height of bars in the Barcode. By modifying the barHeight, the entire Barcode height can be customized. Please refer to [xDimension](/api/js/ejBarcode#xdimensionspan-classtype-signature-type-numbernumberspan) for two dimensional barcode height customization.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 150 pixels








Example
{:.example}


{% highlight html %}
 
// Add the below code to set darkBarColor during initialization 
<ej-barcode text="SYNCFUSION" id="barcode39" [barHeight]="50" symbologyType="code39">
</ej-barcode>
{% endhighlight %}







### darkBarColor `object`
{:#members:darkbarcolor}








Specifies the dark bar color of the Barcode. One dimensional barcode contains a series of dark and light bars which are usually colored as black and white respectively. 

N>    1. For the Barcode should be properly detected by all scanners, choose the best possible contrast color.
N>             2. This property is applicable only for one dimensional barcode.

Default Value:
{:.param}






* black








Example
{:.example}


{% highlight html %}
 
// Add the below code to set darkBarColor during initialization.  
 <ej-barcode text="SYNCFUSION" id="barcode39" darkBarColor="blue" symbologyType="code39">
</ej-barcode> 
{% endhighlight %}







### displayText `boolean`
{:#members:displaytext}








Specifies whether the text below the Barcode is visible or hidden.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* true








Example
{:.example}


{% highlight html %}
 
// Add the below code to hide displayText during initialization 
<ej-barcode text="SYNCFUSION" id="barcode39" [displayText]="false" symbologyType="code39">
{% endhighlight %}







### enabled `boolean`
{:#members:enabled}








Specifies whether the control is enabled.




Default Value:
{:.param}






* true







Example
{:.example}


{% highlight html %}
 
// Add the below code to disable the Barcode during initialization.  
 <ej-barcode text="SYNCFUSION" id="barcode39" [enabled]="false" symbologyType="code39">
</ej-barcode>
{% endhighlight %}







### encodeStartStopSymbol `boolean`
{:#members:encodestartstopsymbol}








Specifies the start and stop encode symbol in the Barcode. In one dimensional barcodes, an additional character is added as start and stop delimiters. These symbols are optional and the unique of the symbol allows the reader to determine the direction of the Barcode being scanned.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* true








Example
{:.example}


{% highlight html %}
 
// Add the below code to remove encodeStartStopSymbol during initialization.
<ej-barcode text="SYNCFUSION" id="barcode39" [encodeStartStopSymbol]="false" symbologyType="code39">
</ej-barcode>
{% endhighlight %}







### lightBarColor `object`
{:#members:lightbarcolor}








 Specifies the light bar color of the Barcode. One dimensional barcode contains a series of dark and light bars which are usually colored as black and white respectively.

N>    1. For the Barcode should be properly detected by all scanners, choose the best possible contrast color.
N>                     2. This property is applicable only for one dimensional barcode.

Default Value:
{:.param}






* white








Example
{:.example}


{% highlight html %}
 
// Add the below code to set lightBarColor during initialization
<ej-barcode text="SYNCFUSION" id="barcode39" lightBarColor="blue" symbologyType="code39">
</ej-barcode>  
{% endhighlight %}







### narrowBarWidth `number`
{:#members:narrowbarwidth}








Specifies the width of the narrow bars in the Barcode. The dark bars in the one dimensional barcode contains random narrow and wide bars based on the provided input which can be specified during initialization.

N>    This property is applicable only for one dimensional barcode.



Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 
// Add the below code to set narrowBarWidth during initialization 
<ej-barcode text="SYNCFUSION" id="barcode39" [narrowBarWidth]="5" symbologyType="code39"></ej-barcode>  
{% endhighlight %}









### symbologyType `enum`
{:#members:symbologytype}

<ts name="ej.datavisualization.Barcode.SymbologyType"/>

Specifies the type of the Barcode. See <a href="global.html#SymbologyType">SymbologyType</a>
<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">QRBarcode</td>
            <td class="description">Represents the QR code</td>
        </tr>
        <tr>
            <td class="name">DataMatrix</td>
            <td class="description">Represents the Data Matrix barcode</td>
        </tr>
        <tr>
            <td class="name">Code39</td>
            <td class="description">Represents the Code 39 barcode</td>
        </tr>
        <tr>
            <td class="name">Code39Extended</td>
            <td class="description">Represents the Code 39 Extended barcode</td>
        </tr>
        <tr>
            <td class="name">Code11</td>
            <td class="description">Represents the Code 11 barcode</td>
        </tr>
        <tr>
            <td class="name">Codabar</td>
            <td class="description">Represents the Codabar barcode</td>
        </tr>
        <tr>
            <td class="name">Code32</td>
            <td class="description">Represents the Code 32 barcode</td>
        </tr>
        <tr>
            <td class="name">Code93</td>
            <td class="description">Represents the Code 93 barcode</td>
        </tr>
        <tr>
            <td class="name">Code93Extended</td>
            <td class="description">Represents the Code 93 Extended barcode</td>
        </tr>
        <tr>
            <td class="name">Code128A</td>
            <td class="description">Represents the Code 128 A barcode</td>
        </tr>
        <tr>
            <td class="name">Code128B</td>
            <td class="description">Represents the Code 128 B barcode</td>
        </tr>
        <tr>
            <td class="name">Code128C</td>
            <td class="description">Represents the Code 128 C barcode</td>
        </tr>
        <tr>
            <td class="name">UpcBarcode</td>
            <td class="description">Represents the UPC barcode</td>
        </tr>
    </tbody>
</table>
Default Value:
{:.param}

* symbologyType="qrbarcode"








Example
{:.example}


{% highlight html %}
 
<ej-barcode text="http://www.syncfusion.com" id="qrbarcode" symbologyType="qrbarcode" xDimension="8">
</ej-barcode>


{% endhighlight %}




### text `string`
{:#members:text}








Specifies the text to be encoded in the Barcode.




Default Value:
{:.param}






* empty








Example
{:.example}


{% highlight html %}
 
<ej-barcode text="http://www.syncfusion.com" id="qrbarcode" xDimension="8">
</ej-barcode>
{% endhighlight %}







### textColor `object`
{:#members:textcolor}








Specifies the color of the text/data at the bottom of the Barcode.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* black








Example
{:.example}


{% highlight html %}
 
// All the below code to set the textColor while initialization
<ej-barcode text="SYNCFUSION" id="barcode39" textColor="blue" symbologyType="code39">
</ej-barcode> 
{% endhighlight %}







### wideBarWidth `number`
{:#members:widebarwidth}








Specifies the width of the wide bars in the Barcode. One dimensional barcode usually contains random narrow and wide bars based on the provided which can be customized during initialization.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 3 pixels








Example
{:.example}


{% highlight html %}
 
// Add the below code to set wideBarWidth during initialization.  
 <ej-barcode text="SYNCFUSION" id="barcode39" [wideBarWidth]="10" symbologyType="code39">
</ej-barcode>
{% endhighlight %}







### xDimension `number`
{:#members:xdimension}








Specifies the width of the narrowest element(bar or space) in a Barcode. The greater the x dimension, the more easily a barcode reader will scan.

N>    This property is applicable only for two dimensional barcode.


Default Value:
{:.param}






* 4 pixels








Example
{:.example}


{% highlight html %}
 

// Add the below code to set xDimension during initialization.  
<ej-barcode text="http://www.syncfusion.com" id="qrbarcode" xDimension="8">
</ej-barcode>
{% endhighlight %}





