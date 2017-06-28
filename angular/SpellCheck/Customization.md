---
title: SpellCheck - Customization
description: SpellCheck Customization
platform: Angular-2
control: spellcheck
documentation: ug
keywords: customization, spellcheck customization, misspell word appearance, restrict suggestion count
---
# SpellCheck Customization

The SpellCheck provides option to customize for the following scenarios.

* Misspell Word Appearance
* Restrict Suggestion Count
    
## Misspell Word Appearance

The SpellCheck control provide the support (`misspellWordCss`) to display the error word in user defined style. By default displaying the error words with the red underline. 

The following code example depicts the way to customize the error word highlight (displaying error word with red color font and lightblue background).

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionarysettings" [contextMenuSettings.enable]="false" misspellWordCss="highlight">
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

export class SpellCheckComponent {
    public dictionarysettings: any;
    constructor() {
        this.dictionarysettings = {
            dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
            customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
        };
    }
    checkErrors() {
        let spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.showInDialog();
    }    
}
{% endhighlight %}

{% highlight css %}

<style>
        .highlight {
            background-color: lightblue;
            color: red;
        }
</style>

{% endhighlight %}

## Restrict Suggestion Count

The SpellCheck control provides option (`maxSuggestionCount`) to restrict the count that the number of items displayed in the suggestion list.

The following code example describes the way to control the suggestion count.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionarysettings" [contextMenuSettings.enable]="false" [maxSuggestionCount]="3">
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

export class SpellCheckComponent {
    public dictionarysettings: any;
    constructor() {
        this.dictionarysettings = {
            dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
            customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
        };
    }
    checkErrors() {
        let spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.showInDialog();
    }    
}
{% endhighlight %}