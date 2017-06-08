---
title: Globalization and Localization
description: Globalizing and localizing Scheduler
platform: Angular
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# Globalization and Localization

## Globalization

The Scheduler control is built with default **globalization** support as it format the dates according to the user’s locale automatically and processes it internally without any need for manual conversions. This kind of default handling of Scheduler dates is achieved through the built-in **ej.globalize** library which globalize the date, day and month names accordingly. 

## Localization

Scheduler also comes with default localization support which allows it to customize the display of text within the Scheduler in a user-specific culture and locale. The Schedule control can be localized in specific culture using the common API `locale` along with the collection of localized words defined for that culture using the ej.Schedule.Locale [**culture-code**].

N> By default, the Schedule control is localized in **en-US** culture.

To localize Scheduler into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.                   

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the Schedule control in **fr-FR** culture.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentDate="5/4/2014" locale="fr-FR" 
        [appointmentSettings.dataSource]=scheduleData>
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData =[{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2014, 4, 5, 10, 0),
                EndTime: new Date(2014, 4, 5, 11, 0)
            }];
            ej.Schedule.Locale["fr-FR"] = {
                ReminderWindowTitle: "fenêtre Rappel",
                CreateAppointmentTitle: "Créer un rendez",
                RecurrenceEditTitle: "Modifier Répéter rendez-vous",
                RecurrenceEditMessage: "Comment voulez-vous changer le rendez-vous dans la série?",
                RecurrenceEditOnly: "Seulement cette nomination",
                RecurrenceEditSeries: "La série entière",
                PreviousAppointment: "Nomination précédente",
                NextAppointment: "Prochain rendez-vous",
                AppointmentSubject: "Assujettir",
                StartTime: "Heure de départ",
                EndTime: "Heure de fin",
                AllDay: "Toute la journée",
                StartTimeZone: "Démarrez TimeZone",
                EndTimeZone: "End Time Zone",
                Today: "Aujourd'hui",
                Recurrence: "Répéter",
                Done: "Terminé",
                Cancel: "Annuler",
                Ok: "D'accord",
                Repeat: "Répéter",
                RepeatBy: "Répéter par",
                RepeatEvery: "Répéter chaque",
                RepeatOn: "Répéter l'opération sur",
                StartsOn: "Démarre sur",
                Ends: "Prend fin",
                Summary: "Résumé",
                Daily: "Tous les jours",
                Weekly: "Hebdomadaire",
                Monthly: "Mensuel",
                Yearly: "Annuel",
                Every: "Chaque",
                EveryWeekDay: "Tous les jours de la semaine",
                Never: "Jamais",
                After: "Après",
                Occurrence: "Occurrences",
                On: "Sur",
                Edit: "modifier",
                RecurrenceDay: "Journées",
                RecurrenceWeek: "Semaines",
                RecurrenceMonth: "Mois",
                RecurrenceYear: "Années",
                The: "le",
                OfEvery: "de toute",
                First: "Premier",
                Second: "Seconde",
                Third: "Troisième",
                Fourth: "Quatrième",
                Last: "Dernier",
                WeekDay: "Jour de la semaine",
                WeekEndDay: "Jour de weekend",
                Subject: "Assujettir",
                Categorize: "Catégories",
                DueIn: "Dû en",
                DismissAll: "Rejeter la totalité",
                Dismiss: "Rejeter",
                OpenItem: "Élément ouvert",
                Snooze: "Roupillon",
                Day: "journées",
                Week: "Semaine",
                WorkWeek: "Semaine de travail",
                Month: "Mois",
                AddEvent: "Ajouter un évènement",
                CustomView: "Vue personnalisée",
                Agenda: "Ordre du jour",
                Detailed: "Modifier Rendez-vous",
                EventBeginsin: "Nomination commence dans",
                Editevent: "Modifier Rendez-vous",
                Editseries: "Modifier la série",
                Times: "fois",
                Until: "jusqu'à",
                Eventwas: "Rendez-vous était",
                Hours: "hrs",
                Minutes: "mins",
                Overdue: "Nomination Overdue",
                Days: "journées)",
                Event: "un événement",
                Select: "sélectionner",
                Previous: "précédent",
                Next: "Prochain",
                Close: "Fermer",
                Delete: "Effacer",
                Date: "date",
                Showin: "Montre",
                Gotodate: "Aller à la date",
                Resources: "RESSOURCES",
                RecurrenceDeleteTitle: "Supprimer Répéter rendez-vous",
                Location: "Emplacement",
                Priority: "Priorité",
                RecurrenceAlert: "Alerte",
                NoTitle: "Pas de titre",
                OverFlowAppCount: "plus de nominations",
                AppointmentIndicator: "Cliquez pour plus de rendez-vous",
                WrongPattern: "Le modèle de récurrence est pas valide",
                CreateError: "La durée de la nomination doit être plus courte que la fréquence elle se produit. Raccourcir la durée, ou modifier le modèle de récurrence dans la boîte de dialogue Récurrence de rendez.",
                DragResizeError: "Vous ne pouvez pas reporter une occurrence du rendez-vous périodique si elle saute sur une occurrence ultérieure du même rendez-vous.",
                StartEndError: "L'heure de fin doit être supérieure à l'heure de début",
                MouseOverDeleteTitle: "Supprimer Nomination",
                DeleteConfirmation: "Êtes-vous sûr de vouloir supprimer ce rendez-vous?",
                Time: "Temps",
                EmptyResultText: "Pas de suggestions",
                BlockIntervalAlertTitle: "Alerte",
                BlockIntervalError: "L'intervalle de temps choisi a été bloqué et est indisponible pour la sélection."
            };                                  
        }
    }

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **locale** property for the Schedule control with the appropriate **culture-code** [**fr-FR**].

For further information on – how to refer the required culture scripts into your application, refer [here](/js/localization).

### Localizing Specific Words

To customize or localize only some specific words in the default `ej.Schedule.Locale["en-US"]` collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentDate="5/4/2014" [appointmentSettings.dataSource]=scheduleData>
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData =[{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2014, 4, 5, 10, 0),
                EndTime: new Date(2014, 4, 5, 11, 0)
            }];
            // customize the appointment window title
            ej.Schedule.Locale["en-US"]["CreateAppointmentTitle"] = "Create Event";
            // customize the view options text in the Schedule header
            ej.Schedule.Locale["en-US"]["Day"] = "1 Day";
            ej.Schedule.Locale["en-US"]["Week"] = "7 Days";
            ej.Schedule.Locale["en-US"]["WorkWeek"] = "5 Days";
            ej.Schedule.Locale["en-US"]["Month"] = "Month";                                          
        }
    }

{% endhighlight %}

## Time Zone

The Scheduler makes use of the System time zone by default. If it needs to follow some other user-specific time zone, then the API `timeZone` can be used. Also, the Scheduler can be set to observe the Daylight Saving Time (DST) with its **isDST** property which is set to **false** by default. 

When `isDST` property is set to **true**, the Scheduler internally processes the time difference values (for the Start and end time of the appointments) related to the Scheduler time zone that observes daylight savings time. 

The following code example shows the way to set the specific time zone value with the daylight savings time observed in the Scheduler.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData timeZone= "UTC +05:30" [isDST]= true>
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %} 

### Setting different TimeZone for Scheduler Appointments

Apart from the default action of applying specific timezone to the entire Scheduler, it is also possible to set different time zone values for each appointments through the properties **startTimeZone** and **endTimeZone** which can be defined as separate fields within the appointment dataSource. When these properties are not explicitly defined for appointments, the appointments Start and End time will be processed based on the Scheduler time zone.

N> The **isDST** property closely relies on the appointment fields like `StartTimeZone` and `EndTimeZone`, for appropriate time difference calculations. If these two fields are not defined for appointments, then **isDST** depends on the System **timeZone** value.

The following code snippet shows how to define isDST and the time zones for specific appointments.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData 
    [isDST]= true>
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData =[{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2014, 4, 5, 10, 0),
                EndTime: new Date(2014, 4, 5, 11, 0),
                Location: "CHINA",
                StartTimeZone: "UTC +02:00",
                EndTimeZone: "UTC +02:00"
            }];                                  
        }
    }

{% endhighlight %} 

### Customizing the TimeZone Collection

It is also possible to define or customize the default time zone collection of the Scheduler, by using the `timeZoneCollection` API as follows.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData 
    [timeZoneCollection.dataSource]=timezoneData 
    timeZoneCollection-id="id"
    timeZoneCollection-text="text"
    timeZoneCollection-value="value"> 
 </ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        public timezoneData:any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
            this.timezoneData=[{
                text: "UTC -04:00",
                id: "10",
                value: "UTC -04:00"
            }, {
                text: "UTC -03:30",
                id: "11",
                value: "UTC -03:30"
            }, {
                text: "UTC -03:00",
                id: "12",
                value: "UTC -03:00"
            }, {
                text: "UTC -02:00",
                id: "13",
                value: "UTC -02:00"
            }, {
                text: "UTC -01:00",
                id: "14",
                value: "UTC -01:00"
            }, {
                text: "UTC +00:00",
                id: "15",
                value: "UTC +00:00"
            }, {
                text: "UTC +01:00",
                id: "16",
                value: "UTC +01:00"
            }, {
                text: "UTC +02:00",
                id: "17",
                value: "UTC +02:00"
            }, {
                text: "UTC +03:00",
                id: "18",
                value: "UTC +03:00"
            }, {
                text: "UTC +03:30",
                id: "19",
                value: "UTC +03:30"
            }, {
                text: "UTC +04:00",
                id: "20",
                value: "UTC +04:00"
            }, {
                text: "UTC +04:30",
                id: "21",
                value: "UTC +04:30"
            }, {
                text: "UTC +05:00",
                id: "22",
                value: "UTC +05:00"
            }];
        }
    }

{% endhighlight %} 

N> The values defined within the **timeZoneCollection** dataSource are usually the only options displayed within the start and end time zone dropdown fields of the appointment window.

## Time Mode

The time mode of the Scheduler can be either **12** or **24 hours** format which is based on the `locale` set to the Scheduler. Since the default locale value of the Scheduler is **en-US**, therefore the time mode will be set to **12 hours** format (by default) automatically based on the culture. 

The user can also set specific time mode for the Scheduler using `timeMode` property which accepts either **String** or **enum** value. It accepts the following **enum** values,

* ej.Schedule.TimeMode.Hour12
* ej.Schedule.TimeMode.Hour24

The following code snippet shows the way to set specific **24 hour format** time mode for the Scheduler.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" timeMode="ej.Schedule.TimeMode.Hour24" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData >
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %} 

N> If the **timeMode** property is not set with specific value, then the value will be taken based on the locale assigned for the Scheduler.

## Date Format

Scheduler can be used with all valid date formats. The default date format used in Scheduler is “MM/dd/yyyy”. 

If the `dateFormat` property is not specified particularly, then it will be taken based on the locale that is assigned to the Scheduler. The default locale applied on the Scheduler is “en-US”, which makes it to follow the “MM/dd/yyyy” pattern by default.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" dateFormat="yyyy/MM/dd" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData >
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %} 

## First Day of Week

The `firstDayOfWeek` property allows to set any of the week days as start of the week/workweek/month view in Scheduler. It accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `ej.Schedule.DayOfWeek` enum type value. The default value of this `firstDayOfWeek` depends on the current culture (language) assigned to the Scheduler.

To set different first day of week in Scheduler,

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" firstDayOfWeek="Tuesday" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData >
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %} 

N> The sub-control datepicker which is used within Scheduler for start/end time fields in appointment window and for date navigation purposes will also follow the same first day of week. 
