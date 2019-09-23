---
title: Componente Opzioni modulo
seo-title: Componente Opzioni modulo
description: Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.
seo-description: Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.
uuid: 7e8714df-75d1-4bb0-b1ee-b7c7450d806a
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 42289c2b-1671-463a-ac1d-457aa9aefa2a
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente Opzioni modulo{#form-options-component}

Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo per componenti core consente di inviare diversi tipi di opzioni presentate in diversi modi e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall'editor di contenuti nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Opzioni modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-options-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/screen_shot_2018-01-12at113648.png)

### HTML {#html}

```
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-66464844" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-858231075" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-862566768" name="hidden">

</div>
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">

    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container/container">
    
    <div class="options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="cmp-form-options">
        
            <legend class="cmp-form-options__legend">What is your favorite type of toast?</legend>
            <label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="dryToast">
                Plain dry toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="frenchToast">
                French Toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="texasToast">
                Texas Toast
            </label>

    </fieldset>

</div>

</div></form>
```

### JSON {#json}

```
"container":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           "columnCount":12,
                           "gridClassNames":"aem-Grid aem-Grid--12 aem-Grid--default--12",
                           ":items":{  
                              "options_816658469":{  
                                 "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                                 "id":"form-options-269951232",
                                 "title":"What is your favorite type of toast?",
                                 "name":"favToast",
                                 "type":"RADIO",
                                 "items":[  
                                    {  
                                       "value":"dryToast",
                                       "text":"Plain dry toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"frenchToast",
                                       "text":"French Toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"texasToast",
                                       "text":"Texas Toast",
                                       "selected":false,
                                       "disabled":false
                                    }
                                 ],
                                 ":type":"core/wcm/sandbox/components/form/options/v2/options"
                              }
                           },
                           ":itemsOrder":[  
                              "options_816658469"
                           ],
                           ":type":"core/wcm/sandbox/components/form/container/v2/container"
                        }
```

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](assets/screen_shot_2018-01-12at113153.png)

* **Tipi** - Modalità di presentazione delle opzioni
   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**
* **Titolo** Titolo che verrà visualizzato come etichetta per le opzioni
* **Nome** Il nome del campo inviato con i dati del modulo
* **Origine** Dove sono definite le opzioni
   * **Locale** definito nel componente
      * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore** Il valore salvato quando l'opzione viene selezionata all'invio del modulo
      * **Testo** Etichetta per l'opzione visualizzata sul modulo
      * **Attivo** L'opzione è contrassegnata come selezionata al caricamento del modulo
      * **Disattivato** L'opzione non è selezionabile ma continua a essere visualizzata
      * **Elenco** Per le opzioni viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco** Percorso dell’elenco statico in AEM
            * Utilizzare il pulsante Sfoglia per individuare la risorsa dell'elenco
      * **Origine** dati Un'origine dati viene utilizzata per le opzioni
         * **Origine** dati Tipo di risorsa dell'origine dati
* **Messaggio** della Guida Un suggerimento per l'utente di ciò che può essere immesso nel campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Opzioni modulo supporta AEM [Style System](authoring.md#component-styling).