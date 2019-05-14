---
title: Componente nascosto modulo (v 1)
seo-title: Componente nascosto modulo (v 1)
description: Il componente Modulo componente core consente la visualizzazione di un campo nascosto.
seo-description: Il componente Modulo componente core consente la visualizzazione di un campo nascosto.
uuid: f 5005346-def 5-4 e 1 f -8 f 93-e 4 cfc 67 a 9329
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: d 35 f 4 e 71-ec 7 f -4128-9123-b 997 dbb 5 f 0 cf
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente nascosto modulo (v 1){#form-hidden-component-v}

Il componente Modulo componente core consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente Modulo di base modulo consente la creazione di campi nascosti per trasmettere nuovamente le informazioni sulla pagina corrente ad AEM, da utilizzare insieme al [componente Contenitore del modulo](form-container.md).

Le proprietà dei campi possono essere definite dall&#39;editor contenuto nella finestra di dialogo [Configura](#configure-dialog).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente nascosto modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Nascosto modulo.

| Versione di AEM | Componente nascosto modulo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Nascosto modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Nascosto modulo, vedere [il documento Modulo](form-hidden.md) nascosto modulo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
  <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
   <div class="visible aem-GridColumn aem-GridColumn--default--12">
    <input type="hidden" id="ghostToast" name="Invisible Toast" value="ghostToast">
   </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "hidden": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/hidden",
                  "name": "Invisible Toast",
                  "id": "ghostToast",
                  "value": "ghostToast"
                }
              },
              ":itemsOrder": [
                "hidden"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#release-history-and-compatibility) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire i parametri del campo nascosto.

![](assets/chlimage_1-26.png)

* **Nome** : nome del campo, inviato con i dati del modulo
* **Valore** : valore del campo, inviato con i dati del modulo
* **Identificatore** : l&#39;identificatore deve essere univoco sulla pagina e può essere utilizzato per eseguire il binding degli script con questo campo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Nascosto modulo.

## Dettagli tecnici {#technical-details}

In github è disponibile la documentazione tecnica più recente relativa al componente [Nascosto modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
