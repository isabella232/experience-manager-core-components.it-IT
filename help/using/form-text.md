---
title: Componente testo modulo
seo-title: Componente testo modulo
description: 'null'
seo-description: Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.
uuid: f2418d55-0b59-4c7c-a541-d12dda4db4cf
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3a970c4b-806b-4a0a-b6b8-b3dca4e9f136
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente testo modulo{#form-text-component}

Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.

## Utilizzo {#usage}

Il componente Testo modulo consente di inviare diversi tipi di testo e deve essere utilizzato insieme al componente [Contenitore di](form-container.md)moduli. Il tipo di convalida del testo, etichette e messaggi di aiuto può essere definito dall'editor di contenuti nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-text-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="text aem-GridColumn aem-GridColumn--default--12">
   <div class="cmp-form-text">
      <label for="form-text-2146967">How many pieces of toast would you like?
      </label>
   <input class="cmp-form-text__text" type="number" id="form-text-2146967" name="pieces">
   </div>
</div>
```

### JSON {#json}

```
"text":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "id":"form-text-2146967",
                     "title":"How many pieces of toast would you like?",
                     "name":"pieces",
                     "value":"",
                     "helpMessage":"",
                     "type":"number",
                     "readOnly":false,
                     "required":false,
                     "requiredMessage":"",
                     "constraintMessage":"",
                     "rows":2,
                     "defaultValue":"",
                     ":type":"core/wcm/components/form/text/v2/text"
                  }
```

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Scheda Principale {#main-tab}

![](assets/chlimage_1-23.png)

* **Vincolo** Il tipo di testo da inserire e su cui verrà convalidato il valore
   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**
* **Righe** di testo Numero di righe da visualizzare nell'area di testo (solo se **Vincolo** è impostato su **Area** di testo)
* **Etichetta** Etichetta che verrà visualizzata per il campo
* **Nascondere l'etichetta per la visualizzazione** Necessaria se l'etichetta è necessaria solo a scopo di accessibilità e non immette ulteriori informazioni visive sul campo
* **Nome** elemento Il nome del campo inviato con i dati del modulo
* **Valore** predefinito precompilato nel campo

### Scheda {#about-tab}

![](assets/chlimage_1-24.png)

* **Messaggio** della Guida Un suggerimento per l'utente sulle informazioni che è possibile immettere nel campo
* **Visualizza il messaggio della Guida come segnaposto** Per visualizzare il messaggio della Guida all'interno del modulo di input quando è vuoto e non è attivo

### Scheda Vincoli {#constraints-tab}

![](assets/chlimage_1-25.png)

* **Messaggio vincolo**
   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e Area **di** testo
* **Obbligatorio** Se selezionato, l'utente deve compilare un valore prima di inviare il modulo
* **Rendi sola** lettura Se selezionata, l'utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo per il componente Testo modulo.