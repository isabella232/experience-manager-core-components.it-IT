---
title: Componente Opzioni modulo (v1)
description: Il componente core Opzioni modulo consente la selezione di opzioni predefinite in vari formati.
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 100%

---

# Componente Opzioni modulo (v1) {#form-options-component-v}

Il componente core Opzioni modulo consente la selezione di opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente core Opzioni modulo consente di inviare diversi tipi di opzioni visualizzate in molti modi differenti ed è concepito per essere utilizzato insieme al [componente Contenitore modulo](form-container-v1.md).

La visualizzazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Opzioni modulo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Opzioni modulo.

| Versione del componente | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Opzioni modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Opzioni modulo, vedi il documento [Componente Opzioni modulo](/help/components/forms/form-options.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire il tipo di opzioni da visualizzare, le etichette e le opzioni disponibili.

![](/help/assets/chlimage_1-90.png)

* **Tipo**
Modalità di presentazione delle opzioni

   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **Elenchi a discesa**
   * **Elenchi a discesa a selezione multipla**

* **Titolo**: il titolo che verrà visualizzato come etichetta per le opzioni
* **Nome**: il nome del campo che viene inviato con i dati del modulo
* **Origine**: dove sono definite le opzioni

   * **Locale**: definito all’interno del componente
      * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un valore o sul pulsante **Elimina** per rimuovere un valore
      * **Valore**: valore salvato quando l’opzione viene selezionata al momento dell’invio del modulo
      * **Testo**: l’etichetta dell’opzione visualizzata sul modulo
      * **Attiva**: l’opzione viene contrassegnata come selezionata al caricamento del modulo
      * **Disattivato**: l’opzione non è selezionabile ma è ancora visualizzata
      * **Elenco**: per l’opzione viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco**: il percorso dell’elenco statico in AEM
            * Utilizza il pulsante Sfoglia per individuare la risorsa elenco
      * **Origine dati**: un’origine dati utilizzata per le opzioni
         * **Origine dati**: tipo di risorsa dell’origine dati
* **Messaggio di aiuto**: suggerimento per l’utente per la compilazione del campo

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione non è disponibile per il componente Opzioni modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
