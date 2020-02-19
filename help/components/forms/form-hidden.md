---
title: Componente nascosto modulo
description: Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Componente nascosto modulo{#form-hidden-component}

Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente di base Modulo nascosto consente la creazione di campi nascosti per riportare in AEM le informazioni sulla pagina corrente e deve essere utilizzato insieme al componente [Contenitore di](form-container.md)moduli.

Le proprietà del campo possono essere definite dall’editor del contenuto nella finestra di dialogo [di](form-hidden.md)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Nascosto modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-hidden-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html).

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

La documentazione tecnica più recente sul componente Nascosto modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del campo nascosto.

![](/help/assets/chlimage_1-26.png)

* **Nome** Il nome del campo, inviato con i dati del modulo
* **Valore** Il valore del campo, inviato con i dati del modulo
* **Identificatore** L&#39;identificatore deve essere univoco sulla pagina e può essere utilizzato per eseguire il binding degli script a questo campo del modulo

Poiché in genere il componente Nascosto modulo non ha attributi visibili, il segnaposto del componente nell’editor visualizza i valori dei campi **Nome** e **Valore** , se assegnati per consentire all’autore di identificare il componente Nascosto modulo appropriato.

![](/help/assets/screenshot_2018-10-19at094927.png)

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile alcuna finestra di dialogo per il componente Nascosto modulo.
