---
title: Componente Pulsante modulo (v1)
description: Il componente core Campo nascosto modulo consente di includere un campo nascosto in un modulo.
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '342'
ht-degree: 100%

---

# Componente Pulsante modulo (v1) {#form-button-component-v}

Il componente core Pulsante modulo consente di includere un campo pulsante in un modulo per attivare un’azione.

## Utilizzo {#usage}

Il componente core Pulsante modulo consente la creazione di un campo pulsante, spesso per attivare l’invio del modulo, che deve essere utilizzato insieme al componente [Contenitore modulo](form-container-v1.md).

Le proprietà del pulsante possono essere definite tramite l’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Pulsante modulo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Pulsante modulo.

| Versione di AEM | Componente Pulsante modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Pulsante modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Pulsante modulo, vedi il documento [Componente pulsante modulo](/help/components/forms/form-button.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire i parametri del pulsante.

![](/help/assets/chlimage_1-49.png)

* **Tipo**
   * **Pulsante**
   * **Invia**

* **Titolo**: il testo visualizzato sul pulsante
   * Se non viene specificato alcun testo, viene utilizzato automaticamente il tipo di pulsante

* **Nome**: il nome del pulsante, che viene inviato con i dati del modulo
* **Valore**: il valore del pulsante, che viene inviato con i dati del modulo

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione non è disponibile per il componente Pulsante modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
