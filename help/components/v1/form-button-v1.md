---
title: Componente pulsante modulo (v1)
description: Il componente di base Nascosto per modulo consente di includere un campo nascosto in un modulo.
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 3%

---

# Componente pulsante modulo (v1) {#form-button-component-v}

Il componente Pulsante modulo del componente core consente di includere un campo pulsante in un modulo per attivare un’azione.

## Utilizzo {#usage}

Il componente Pulsante modulo del componente core consente la creazione di un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [contenitore modulo](form-container-v1.md).

Le proprietà del pulsante possono essere definite dall&#39;editor dei contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente per pulsante di modulo, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della versione 1 del componente Pulsante modulo.

| Versione di AEM | Componente pulsante modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Pulsante modulo .
>
>Per informazioni dettagliate sulla versione corrente del componente Pulsante modulo, consultare il documento [Componente pulsante modulo](/help/components/forms/form-button.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del pulsante.

![](/help/assets/chlimage_1-49.png)

* **Tipo**
   * **Pulsante**
   * **Invia**

* **Titolo** : il testo visualizzato sul pulsante
   * Se non ne è stato fornito nessuno, viene impostato automaticamente sul tipo di pulsante

* **Nome** : il nome del pulsante che viene inviato insieme ai dati del modulo
* **Valore**  - Il valore del pulsante, che viene inviato insieme ai dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo di progettazione per il componente Pulsante modulo .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
