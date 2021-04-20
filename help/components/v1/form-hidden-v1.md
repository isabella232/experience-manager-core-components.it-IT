---
title: Componente nascosto per modulo (v1)
description: Il componente di base Nascosto per modulo consente la visualizzazione di un campo nascosto.
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 2%

---


# Componente nascosto per modulo (v1) {#form-hidden-component-v}

Il componente di base Nascosto per modulo consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente di base Nascosto per modulo consente la creazione di campi nascosti per riportare in AEM le informazioni sulla pagina corrente e deve essere utilizzato insieme al [componente contenitore modulo](form-container-v1.md).

Le proprietà del campo possono essere definite dall&#39;editor dei contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente nascosto per modulo, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità della v1 del componente nascosto modulo.

| Versione di AEM | Componente nascosto per modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>In questo documento viene descritta la versione 1 del componente nascosto per modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Nascosto per modulo, consultare il documento [Componente nascosto per modulo](/help/components/forms/form-hidden.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md#release-history-and-compatibility) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del campo nascosto.

![](/help/assets/chlimage_1-26.png)

* **Nome** : il nome del campo che viene inviato insieme ai dati del modulo
* **Valore** : valore del campo, inviato insieme ai dati del modulo
* **Identificatore** : l’identificatore deve essere univoco sulla pagina e può essere utilizzato per associare gli script a questo campo del modulo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste una finestra di dialogo di progettazione per il componente Nascosto modulo .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Nascosto per modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
