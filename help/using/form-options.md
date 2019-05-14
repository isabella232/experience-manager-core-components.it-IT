---
title: Componente Opzioni modulo
seo-title: Componente Opzioni modulo
description: Il componente Opzioni modulo di base consente la selezione da opzioni predefinite in vari formati.
seo-description: Il componente Opzioni modulo di base consente la selezione da opzioni predefinite in vari formati.
uuid: 7 e 8714 df -75 d 1-4 bb 0-b 1 ee-b 7 c 7450 d 806 a
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 42289 c 2 b -1671-463 a-ac 1 d -457 aa 9 aefa 2 a
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente Opzioni modulo{#form-options-component}

Il componente Opzioni modulo componente core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo componente core consente di inviare diversi tipi di opzioni presentate in vari modi e di essere utilizzati insieme al [componente Contenitore modulo](form-container.md).

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor contenuto nella finestra di dialogo [Configura](#configure-dialog).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Opzioni modulo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-options-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

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

La documentazione tecnica più recente relativa al componente Opzioni modulo [è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](assets/screen_shot_2018-01-12at113153.png)

* **Tipi** - Modalità di presentazione delle opzioni
   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**
* **Titolo Titolo**
visualizzato come etichetta per le opzioni
* **Nome Nome**
del campo inviato con i dati del modulo
* **Sorgente**
Dove vengono definite le opzioni
   * **Locale**
definito all&#39;interno del componente
      * Toccate o fate clic sul **pulsante Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore**
Il valore salvato quando questa opzione è selezionata all&#39;invio del modulo
      * **Testo**
L&#39;etichetta dell&#39;opzione visualizzata nel modulo
      * **Attivo**
L&#39;opzione è contrassegnata come selezionata al momento del caricamento del modulo
      * **Disattivato**
L&#39;opzione non è selezionabile ma resta visualizzata
      * **List**
A static list defined elsewhere in AEM is used for the options
         * **Elenca**
il percorso dell&#39;elenco statico in AEM
            * Usare il pulsante Sfoglia per individuare la risorsa elenco
      * **Origine
dati** Un&#39;origine dati viene utilizzata per le opzioni
         * **Tipo**di risorsa Origine
dati dell&#39;origine dati
* **Messaggio**
di Aiuto Un suggerimento per l&#39;utente che può inserire il campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Opzioni modulo supporta il sistema [di stile AEM](authoring.md#component-styling).