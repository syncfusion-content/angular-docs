---
layout: post
title: Localization
description: localization
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Localization

Localization is the process of customizing the User Interface (UI) based on a culture, specific to a particular country or region, in order to display regional data. The culture is represented by a unique string like `en``-``US` for US English and `fr``-``FR` for French.

Localization is the key feature that provides solutions to global customers with the help of localized control. It is necessary to include the specific culture script files (ej.culture.fr-FR.min.js file for French culture) in the reference section, which is available in the following location.

`(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n`

Also it is possible to localize all the texts in the Gantt control with specific culture by referring the ej.localetexts.fr-FR.min.js file which is available in the following location.

`(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i10n`

The following code example explains on how to localize the control in French culture

Refer the required culture files in app.module.ts file as follows,

{% highlight javascript %}

import { EJAngular2Module } from 'ej-angular2';
...
import 'syncfusion-ej-global/i18n/ej.culture.fr-FR.min.js';
import 'syncfusion-ej-global/l10n/ej.localetexts.fr-FR.min.js';

{% endhighlight %}

{% highlight javascript %}

<ej-gantt
    //...
    locale= "fr-FR">
</ej-gantt>

{% endhighlight %}

![](Localization_images/Localization_img2.png)

Which will localize all the text and date formats to French culture. If we still need to customize the localized text, we can define them locally in the sample as explained below.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public holidays:any;
    constructor() {    
    ej.Gantt.Locale["fr-FR"] = {
        emptyRecord: "Aucun enregistrement ?? afficher",

        alertTexts: {

            indentAlert: "Il n'y a aucune trace de Gantt est s??lectionn?? pour effectuer le retrait",

            outdentAlert: "Il n'y a aucune trace de Gantt est s??lectionn?? pour effectuer le retrait n??gatif",

            predecessorEditingValidationAlert: "Cyclique d??pendance survenu, S'il vous pla??t Consultez le pr??d??cesseur",

            predecessorAddingValidationAlert: "Remplissez toutes les colonnes dans la table pr??d??cesseur",

            idValidationAlert: "Duplicate ID",

            dateValidationAlert: "Invalid Date de fin",

            dialogResourceAlert: "Remplissez toutes les colonnes du tableau des ressources"

        },

        //headerText to be displayed in TreeGrid 

        columnHeaderTexts: {

            taskId: "T??che Ia",

            taskName: "T??che T??che",

            startDate: "D??marrer Date",

            endDate: "Fin Date",

            resourceInfo: "Ressources",

            duration: "Dur??e",

            status: "Progr??s",

            predecessor: "Pr??d??cesseur",

            baselineStartDate: "Baseline D??marrer Date",

            baselineEndDate: "Baseline Fin Date"

        },

        //string to display in dialog 

        editDialogTexts: {

            addFormTitle: "Nouveau T??che",

            editFormTitle: "Modifier T??che",

            saveButton: "Sauver",

            cancelButton: "Annuler"

        },

        columnDialogTexts: {

            field: "Champ",

            headerText: "En-t??te",

            editType: "Modifier le type",

            filterEditType: "Modifier le type de filtre",

            allowFiltering: "Autoriser le filtrage",

            allowFilteringBlankContent: "Autoriser le filtrage du contenu Blank",

            allowSorting: "Autoriser tri",

            visible: "Visible",

            width: "Largeur",

            textAlign: "Alignement du texte",

            headerTextAlign: "Alignement du texte en-t??te",

            columnsDropdownData: "Colonne Chute de donn??es vers le bas",

            dropdownTableText: "Texte",

            dropdownTableValue: "Valeur",

            addData: "Ajouter",

            deleteData: "Retirer",

            allowCellSelection: "Autoriser la s??lection de cellules",

            clipMode: "Mode Clip",

            tooltip: "Info-bulle",

            headerTooltip: "Header Tooltip"

        },

        editTypeTexts: {

            string: "Cha??ne",

            numeric: "Num??rique",

            datePicker: "S??lecteur de date",

            dateTimePicker: "Date Time Picker",

            dropdown: "Menu d??roulant",

            boolean: "Boolean"

        },

        textAlignTypes: {

            right: "Droite",

            left: "La gauche",

            center: "centre"

        },

        clipModeTexts: {

            clip: "Agrafe",

            ellipsis: "Ellipse"

        },

        toolboxTooltipTexts: {

            addTool: "Ajouter",

            editTool: "modifier",

            saveTool: "Mettre ?? jour",

            deleteTool: "Effacer",

            cancelTool: "Annuler",

            searchTool: "Chercher",

            indentTool: "tiret",

            outdentTool: "Retrait n??gatif",

            expandAllTool: "D??velopper tout",

            collapseAllTool: "R??duire tout",

            nextTimeSpanTool: "Suivant Timespan",

            prevTimeSpanTool: "Pr??c??dent Timespan",

            criticalPathTool: "Chemin critique",

            excelExportTool: "Exportation Excel",

            pdfExportTool: "Exportation PDF"

        },

        durationUnitTexts: {

            days: "journ??es",

            hours: "heures",

            minutes: "minutes",

            day: "journ??e",

            hour: "heure",

            minute: "minute"

        },

        durationUnitEditText: {

            minute: ["m", "min", "minute", "minutes"],

            hour: ["h", "heure", "heure", "heures"],

            day: ["r??", "dy", "journ??e", "journ??es"]

        },

        workUnitTexts: {

            days: "journ??es",

            hours: "heures",

            minutes: "minutes"

        },

        taskTypeTexts: {

            fixedWork: "travail fixe",

            fixedUnit: "Unit??s fixes",

            fixedDuration: "Dur??e fixe"

        },

        effortDrivenTexts: {

            yes: "Oui",

            no: "Non"

        },

        contextMenuTexts: {

            taskDetailsText: "D??tails de la t??che ...",

            addNewTaskText: "Ajouter une nouvelle t??che",

            indentText: "tiret",

            outdentText: "Retrait n??gatif",

            deleteText: "Effacer",

            aboveText: "Au dessus de",

            belowText: "Au dessous de"

        },

        newTaskTexts: {

            newTaskName: "Nouvelle t??che"

        },

        columnMenuTexts: {

            sortAscendingText: "Trier par ordre croissant",

            sortDescendingText: "Trier par ordre d??croissant",

            columnsText: "colonnes",

            insertColumnLeft: "Ins??rez la colonne de gauche",

            insertColumnRight: "Ins??rez la colonne de droite",

            deleteColumn: "Supprimer la colonne",

            renameColumn: "Renommer la colonne"

        },

        taskModeTexts: {

            manual: "Manuel",

            auto: "Auto"

        },

        columnDialogTitle: {

            insertColumn: "Ins??rer une colonne",

            deleteColumn: "Supprimer la colonne",

            renameColumn: "Renommer la colonne"

        },

        deleteColumnText: "??tes-vous s??r de vouloir supprimer cette colonne?",

        okButtonText: "D'accord",

        cancelButtonText: "Annuler",

        confirmDeleteText: "Confirmation de la suppression",

        predecessorEditingTexts: {

            fromText: "De",

            toText: "??"

        },

        dialogTabTitleTexts: {

            generalTabText: "G??n??ral",

            predecessorsTabText: "Pr??d??cesseurs",

            resourcesTabText: "Ressources",

            customFieldsTabText: "Les champs personnalis??s",

            notesTabText: "Remarques"

        },

        predecessorCollectionText: [{

                id: "SS",

                text: "D??marrer-D??marrer",

                value: "D??marrer-D??marrer"

            },

            {

                id: "SF",

                text: "D??marrer-terminer",

                value: "D??marrer-terminer"

            },

            {

                id: "FS",

                text: "terminer-D??marrer",

                value: "terminer-D??marrer"

            },

            {

                id: "FF",

                text: "terminer-terminer",

                value: "terminer-terminer"

            }

        ],

    }
  }
}

{% endhighlight %}


{% highlight javascript %} 
 
<ej-gantt
    //...
    locale= "fr-FR">
</ej-gantt>

{% endhighlight %}

![](Localization_images/Localization_img1.png)

## Date format

The default date format used in the Gantt control is ???MM/dd/yyyy???. Date formats will be changed based on the culture referred in the control. But if you still need to change the date format we can define the desired format using the dateFormat property. The same have been explained in the following code example.

{% highlight javascript %}

<ej-gantt
    //...
    locale= "fr-FR"
    dateFormat= "dd/MM/yyyy"
    [scheduleHeaderSettings]="scheduleHeaderSettings"
    >
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public scheduleHeaderSettings: any;
    constructor() {
        this.scheduleHeaderSettings = {
            weekHeaderFormat: "dd/MM/yyyy"
        }
    }
}

{% endhighlight %}

![](Localization_images/Localization_img3.png)

