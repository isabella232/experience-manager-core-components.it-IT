---
title: Componente Opzioni modulo (v1)
description: Il componente per le opzioni del modulo dei componenti core consente la selezione da opzioni predefinite in vari formati.
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 3%

---

# Componente Opzioni modulo (v1) {#form-options-component-v}

Il componente per le opzioni del modulo dei componenti core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo per componente di base consente l’invio di diversi tipi di opzioni presentate in diversi modi e deve essere utilizzato insieme al componente [contenitore modulo](form-container-v1.md).

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor dei contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Opzioni modulo , originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della versione 1 del componente Opzioni modulo.

| Versione componente | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Opzioni modulo .
>
>Per informazioni dettagliate sulla versione corrente del componente Opzioni modulo, consultare il documento [Componente Opzioni modulo](/help/components/forms/form-options.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](/help/assets/chlimage_1-90.png)

* ****
TipiModalità di presentazione delle opzioni

   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**

* **Titolo** : il titolo che verrà visualizzato come etichetta per le opzioni
* **Nome** : nome del campo inviato con i dati del modulo
* **Origine**  - Dove sono definite le opzioni

   * **Locale**  - Definito all’interno del componente
      * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore** : valore salvato quando tale opzione viene selezionata al momento dell’invio del modulo
      * **Testo** : l’etichetta dell’opzione visualizzata sul modulo
      * **Attivo** : l’opzione viene contrassegnata come selezionata al caricamento del modulo
      * **Disabilitato** : l’opzione non è selezionabile ma è ancora visualizzata
      * **Elenco** : per l’opzione viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco** : percorso dell’elenco statico in AEM
            * Utilizzare il pulsante Sfoglia per individuare la risorsa dell’elenco
      * **Origine**  dati: un’origine dati utilizzata per le opzioni
         * **Origine**  dati: tipo di risorsa dell’origine dati
* **Messaggio della Guida** : un suggerimento per l’utente di ciò che può essere immesso nel campo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo di progettazione per il componente Opzioni modulo .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
