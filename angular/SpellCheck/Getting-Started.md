---
title: Getting started with Syncfusion SpellCheck component	
description: Rendering a basic SpellCheck
platform: Angular
control: spellcheck
documentation: ug
keywords: ejSpellCheck, spellcheck, spellcheck widget, js spellcheck, getting started, initialization, service reference
---
# Getting Started 

To get start with how to use the SpellCheck component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/overview).

Once the configurations are done, Create an angular seed application by referring [here](https://help.syncfusion.com/angular-2/gettingstarted/overview).

## Create a SpellCheck control in Angular 2

To render the SpellCheck component on a page, simply define it with the `ej-spellcheck` tag as shown in the below code example.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block">
</ej-spellcheck>

{% endhighlight %}

## Service Reference

Assign the service method (CheckWords) path reference to the property `dictionaryUrl`, which is mandatory to check the spelling of the word.

The CheckWords method will perform the splitting of target sentence into separate words and check each word is that an erroneous or not. If the word is erroneous fetching the possible suggestions for it and returns those details as a result.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionary">
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>

{% endhighlight %}

{% highlight javascript %}

export class SpellCheckComponent {
    public dictionary: any;
    constructor() {
        this.dictionary = {
            dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
            customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
        };
    }
}
{% endhighlight %}

## Spell Checking

To spell check the content of the target element, you need to add one button and calling any one of the SpellCheck method `showInDialog` or `validate` by clicking the button to highlight the error words.

The following code example depicts that checking the spelling of the target element through the "validate" method.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionary" [contextMenuSettings.enable]="false">
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

export class SpellCheckComponent {
    public dictionary: any;
    constructor() {
        this.dictionary = {
            dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
            customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
        };
    }
    checkErrors() {
        let spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.validate();
    }    
}
{% endhighlight %}