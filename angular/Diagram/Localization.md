---
layout: post
title: Globalize and Localize the Diagram control
description: How to globalize and localize the Diagram control?
platform: Angular
control: Diagram
documentation: ug
---

# Localization

* Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.
* The Diagram model’s `locale` property is used to define the culture code. 

The following code illustrates how to provide localization support for Context Menu items.

{% highlight html %}

<div>
    <ej-diagram  id="diagramCore" width="100%" height="700px" [nodes]="nodes" [locale]="locale">
    </ej-diagram>
</div>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/diagram/default.component.html'
})
export class ShapesComponent {
    nodes: Array<any>;
    constructor() {
        this.nodes = [
            {
                name: "rectangle1",
                offsetY: 100,
                labels: [{
                    "text": "Rectangle1"
                }]
            }];
        // Defines the context menu items with spanish language
        ej.datavisualization.Diagram.Locale["es-ES"] = {
            cut: "Corte",
            copy: "Copia",
            paste: "Pasta",
            undo: "Deshacer",
            redo: "Rehacer",
            selectAll: "Seleccionar todo",
            grouping: "Agrupación",
            group: "Grupo",
            ungroup: "Desagrupar",
            order: "Fin",
            bringToFront: "Traer a delante",
            moveForward: "Movimiento adelante",
            sendToBack: "Enviar a espalda",
            sendBackward: "Enviar hacia atrás"
        };
        this.locale = "es-ES";
    }
}

{% endhighlight %}

![](/angular/Diagram/Localization_images/Localization_img1.png)

N> You have to define the textual descriptions of the context menu items for your custom cultures.