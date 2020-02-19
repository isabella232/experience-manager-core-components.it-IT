---
title: Componente nascosto modulo (v1)
description: Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.
index: n
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Form Hidden Component (v1) {#form-hidden-component-v}

Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente di base Modulo nascosto consente la creazione di campi nascosti per riportare in AEM le informazioni sulla pagina corrente e deve essere utilizzato insieme al componente [Contenitore di](form-container-v1.md)moduli.

Le proprietà del campo possono essere definite dall’editor del contenuto nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Nascosto modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente nascosto modulo.

| Versione di AEM | Componente nascosto modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>In questo documento viene descritta la versione 1 del componente Nascosto modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Nascosto modulo, consultare il documento [Modulo nascosto componente](/help/components/forms/form-hidden.md) .

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](/help/versions.md#release-history-and-compatibility) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del campo nascosto.

![](/help/assets/chlimage_1-26.png)

* **Nome** - Il nome del campo, inviato con i dati del modulo
* **Valore** - Il valore del campo, inviato con i dati del modulo
* **Identificatore** - L&#39;identificatore deve essere univoco sulla pagina e può essere utilizzato per eseguire il binding degli script a questo campo del modulo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile alcuna finestra di dialogo per il componente Nascosto modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Nascosto modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.
