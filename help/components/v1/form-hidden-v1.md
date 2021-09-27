---
title: Componente Campo nascosto modulo (v1)
description: Il componente core Campo nascosto modulo consente la visualizzazione di un campo nascosto di un modulo.
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '335'
ht-degree: 100%

---

# Componente Campo nascosto modulo (v1) {#form-hidden-component-v}

Il componente core Campo nascosto modulo consente la visualizzazione di un campo nascosto di un modulo.

## Utilizzo {#usage}

Il componente core Campo nascosto modulo consente la creazione di campi nascosti per restituire informazioni sulla pagina corrente ad AEM e deve essere utilizzato insieme al [componente Contenitore modulo](form-container-v1.md).

Le proprietà del campo possono essere definite tramite l’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Vampo nascosto modulo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Campo nascosto modulo.

| Versione di AEM | Componente Campo nascosto modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Campo nascosto modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Campo nascosto modulo, vedi il documento [Componente Campo nascosto modulo](/help/components/forms/form-hidden.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md#release-history-and-compatibility).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire i parametri del campo nascosto.

![](/help/assets/chlimage_1-26.png)

* **Nome**: il nome del campo, che viene inviato con i dati del modulo
* **Valore**: il valore del campo, che viene inviato con i dati del modulo
* **Identificatore**: l’identificatore deve essere univoco nella pagina e può essere utilizzato per associare degli script a questo campo modulo

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione non è disponibile per il componente Campo nascosto modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Campo nascosto modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
