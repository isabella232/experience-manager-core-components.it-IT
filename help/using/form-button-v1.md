---
title: Componente pulsante modulo (v1)
description: Il componente Principale Modulo nascosto consente di includere un campo nascosto in un modulo.
index: n
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# Form Button Component (v1){#form-button-component-v}

Il componente Pulsante Modulo componente di base consente di includere un campo pulsante in un modulo per attivare un’azione.

## Utilizzo {#usage}

Il componente Pulsante Modulo componente di base consente di creare un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

Le proprietà del pulsante possono essere definite dall&#39;editor del contenuto nella finestra di dialogo [di](form-button-v1.md#main-pars_title)configurazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Pulsante modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Pulsante modulo.

| Versione di AEM | Componente pulsante modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Pulsante modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Pulsante modulo, vedere il documento sul componente [Pulsante](form-button.md) modulo.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-48.png)

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
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire i parametri del pulsante.

![](assets/chlimage_1-49.png)

* **Tipo**
   * **Pulsante**
   * **Invia**

* **Titolo** - Testo visualizzato sul pulsante
   * Se non ne è stato fornito nessuno, per impostazione predefinita viene utilizzato il tipo di pulsante

* **Nome** - Il nome del pulsante, inviato con i dati del modulo
* **Valore** - Il valore del pulsante, inviato con i dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile alcuna finestra di dialogo per il componente Pulsante modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante Modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
