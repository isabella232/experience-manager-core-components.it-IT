---
title: Componente Testo modulo
seo-title: Componente Testo modulo
description: 'null'
seo-description: Il componente Testo componente componente core consente di inserire il testo del modulo da inviare.
uuid: f 2418 d 55-0 b 59-4 c 7 c-a 541-d 12 dda 4 db 4 cf
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 3 a 970 c 4 b -806 b -4 a 0 a-b 6 b 8-b 3 dca 4 e 9 f 136
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente Testo modulo{#form-text-component}

Il componente Testo componente componente core consente di inserire il testo del modulo da inviare.

## Utilizzo {#usage}

Il componente Testo modulo consente di inviare diversi tipi di testo e di utilizzarli insieme al [componente Contenitore del modulo](form-container.md). Il tipo di convalida del testo, le etichette e i messaggi di aiuto possono essere definiti dall&#39;editor contenuto nella finestra di dialogo [Configura](#configure-dialog).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Testo modulo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-text-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

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

In github è disponibile la documentazione tecnica più recente relativa al componente [Testo modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire il tipo di testo da inserire e i valori e le etichette predefiniti.

### Scheda Principale {#main-tab}

![](assets/chlimage_1-23.png)

* **Vincola**
il tipo di testo da inserire e verrà convalidato
   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**
* **Righe
testo** Numero di righe da visualizzare nell&#39;area di testo (visualizzata solo quando **Vincolo** è impostato sull&#39;area **testo**)
* **Etichetta**
L&#39;etichetta visualizzata per il campo
* **Nascondi l&#39;etichetta da visualizzare**
qualora l&#39;etichetta sia richiesta solo per scopi di accessibilità e non imparte ulteriori informazioni visive sul campo
* **Nome
elemento** Nome del campo inviato con i dati del modulo
* **Valore**predefinito valore
precompilato nel campo

### Informazioni su {#about-tab}

![](assets/chlimage_1-24.png)

* **Messaggio**
di aiuto Un suggerimento per l&#39;utente che può inserire il campo
* **Visualizza messaggio di aiuto come segnaposto**
Per visualizzare il messaggio della Guida all&#39;interno dell&#39;input del modulo Quando è vuoto e non è attivo

### Scheda Vincoli {#constraints-tab}

![](assets/chlimage_1-25.png)

* **Messaggio vincolo**
   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per **i tipi di testo** e **Area** di testo
* **Obbligatorio**
Se selezionato, l&#39;utente deve compilare un valore prima di inviare il modulo
* **Rendi di sola lettura** Se selezionato L&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Testo modulo.