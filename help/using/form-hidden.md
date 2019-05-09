---
title: Componente nascosto modulo
seo-title: Componente nascosto modulo
description: 'null'
seo-description: Il componente Modulo componente core consente la visualizzazione di un campo nascosto.
uuid: 63 a 1 b 381-f 45 c -4241-b 743-dea 8 abd 45 e 11
contentOwner: Utente
content-type: riferimento
topic-tags: componenti core
discoiquuid: 36 e 49035-7641-4 bad -8 a 61-723060032903
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente nascosto modulo{#form-hidden-component}

Il componente Modulo componente core consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente Modulo di base modulo consente la creazione di campi nascosti per trasmettere nuovamente le informazioni sulla pagina corrente ad AEM, da utilizzare insieme al [componente Contenitore del modulo](form-container.md).

Le proprietà dei campi possono essere definite dall&#39;editor contenuto nella finestra di dialogo [Configura](form-hidden.md).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Nascosto modulo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-hidden-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

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

### Dettagli tecnici {#technical-details}

In github è disponibile la documentazione tecnica più recente relativa al componente [Nascosto modulo](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire i parametri del campo nascosto.

![](assets/chlimage_1-26.png)

* **Nome Nome**
del campo, inviato con i dati del modulo
* **Valore**
Il valore del campo, inviato con i dati del modulo
* **Identificatore**
L&#39;identificatore deve essere univoco sulla pagina e può essere utilizzato per eseguire il binding degli script con questo campo

Poiché il componente Nascosto modulo in genere non dispone di attributi visibili, il segnaposto del componente nell&#39;editor visualizza i **valori dei campi Nome** e **Valore** se sono assegnati per consentire all&#39;autore di identificare il componente Nascosto nascosto.

![](assets/screenshot_2018-10-19at094927.png)

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Nascosto modulo.