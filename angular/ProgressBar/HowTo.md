---
layout: post
title: How to - ProgressBar widget for Syncfusion Essential JS
description: How To Section in ProgressBar widget for Syncfusion Essential JS
platform: angular
control: ProgressBar
documentation: ug
keywords: ProgressBar, events, 
api: /api/angular/ejprogressbar
---

# How To

## How to increment & show the progressbar movement

You can increment the progress percentage and show case the movement by using the below code

{% highlight html %}

<div class="frame">
            <div class="control">
               <ej-progressbar id="progressBar"  height="20"  width="200" (create)="create()" > </ej-progressbar > 
            <div class="startButton">
                <input type="checkbox" id="startButton" />
                 <label for="startButton">Toggle</label>
            </div>
           </div>   
 </div> 

{% endhighlight %}

{% highlight ts %}

import {Component} from '@angular/core';
import { ViewEncapsulation } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './Progressbar.component.html',
    styleUrls: ['./Progressbar.component.css'],
    encapsulation: ViewEncapsulation.None
})
export class ProgressbarComponent {
    constructor() {           
    }
    create(){
	var progressObj, buttonObj, k = 10, timer = window.clearInterval(timer),showComplete=true ;
        $(function () {
            // declaration
            $("#progressBar").ejProgressBar({
                height: 22,
                value: 10,
               
                complete: function(args) {
            progressObj.option("text", "Completed");
            timer = window.clearInterval(timer);
            k = 0;
            
            buttonObj.setModel({ "toggleState": false, "defaultText": "Restart" });
        }
            });
            progressObj = $("#progressBar").data("ejProgressBar");
            progressObj.option("text", progressObj.getPercentage() + " %");

            $("#startButton").ejToggleButton({
                defaultText: "Start",
                activeText: "Pause",
                size: "small",
                click: function(args) {
            if (args.isChecked) 
                timer = window.setInterval(function() {
            progressObj.option("text", ++k + " %");
            progressObj.option("percentage", k);
        }, 100);
            else {
                buttonObj.setModel({ "defaultText": "Start" });
                timer = window.clearInterval(timer);
            }
        }
            });
            buttonObj = $("#startButton").data("ejToggleButton");

            $("#selectControls").ejDropDownList({
                popupShown: "adjustPopUpPosition",
                showCheckbox: true,
                checkAll: true,
                change: function(args) {
            if (args.isChecked) {
                switch (args.value) {
                    case "start": progressObj.option(args.value, function(args) {
            //jQuery.addEventLog("Progressbar has been <span class='eventTitle'>started</span>.</br>");
        }); break;
                    case "change": progressObj.option(args.value, function(args) {
            //jQuery.addEventLog("Progressbar value has been <span class='eventTitle'>changed</span> to " + args.percentage + "%.</br>");
        }); break;
                    case "complete": showComplete=true; break;
                }
            }
            else if(args.value=="complete") 
			{             
                 showComplete=false; 
            }
            else
			   progressObj.option(args.value, null)            
        }
            });
        });
	
	}
}

{% endhighlight %}

{% highlight css %}

 .frame {
            border: 1px solid #BBBCBB;
            border-radius: 10px 10px 10px 10px;
            padding: 50px 60px;
            margin-top: 40px;
            width: 400px;
            }
       
        .txt {
           font-size: 20px;
           margin-top: 12px;
           text-align: center;
           }
        .startButton {
             margin-left: 96px;
             margin-top: 10px;
           }

{% endhighlight %}

The progress bar movement will be as shown below:

![](HowTo_images/HowTo_img1.jpeg)

