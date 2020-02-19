---
title: Componente Opzioni modulo (v1)
description: Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Form Options Component (v1) {#form-options-component-v}

Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo per componenti core consente di inviare diversi tipi di opzioni presentate in molti modi diversi e deve essere utilizzato insieme al componente [contenitore del](form-container-v1.md)modulo.

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor di contenuti nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Opzioni modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Opzioni modulo.

| Versione componente | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Opzioni modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Opzioni modulo, vedere il documento del componente [Opzioni](/help/components/forms/form-options.md) modulo.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-89.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="cmp cmp-options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="form-group checkbox">
        <legend>What is your favorite type of toast?</legend>
        
        <div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="dry">
              Plain dry toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="french">
              French toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="texas">
              Texas toast
            </label>
        </div>

    </fieldset>
    
</div>
    
</form></div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "options": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/options",
                  "name": "toastTypes",
                  "jcr:title": "What is your favorite type of toast?",
                  "source": "local",
                  "type": "checkbox"
                }
              },
              ":itemsOrder": [
                "options"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](/help/versions.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](/help/assets/chlimage_1-90.png)

* **Tipi** Modalità di presentazione delle opzioni

   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**

* **Titolo** - Titolo che verrà visualizzato come etichetta per le opzioni
* **Nome** - Il nome del campo inviato con i dati del modulo
* **Origine** - Posizione di definizione delle opzioni

   * **Locale** - Definito all’interno del componente
      * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore** : valore salvato quando l&#39;opzione viene selezionata all&#39;invio del modulo
      * **Testo** - Etichetta per l&#39;opzione visualizzata sul modulo
      * **Attivo** : l&#39;opzione è contrassegnata come selezionata al caricamento del modulo
      * **Disattivato** - L&#39;opzione non è selezionabile ma continua a essere visualizzata
      * **Elenco** - Per l’opzione viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco** - Percorso dell’elenco statico in AEM
            * Utilizzare il pulsante Sfoglia per individuare la risorsa dell&#39;elenco
      * **Origine** dati - Per le opzioni viene utilizzata un&#39;origine dati
         * **Origine** dati - tipo di risorsa dell&#39;origine dati
* **Messaggio** della Guida - Suggerimento per l&#39;utente di ciò che può essere immesso nel campo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile alcuna finestra di dialogo per il componente Opzioni modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.
