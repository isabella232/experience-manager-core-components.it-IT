---
title: Componente testo modulo (v1)
description: Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 8%

---


# Componente testo modulo (v1) {#form-text-component-v}

Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.

## Utilizzo {#usage}

Il componente Testo modulo consente l&#39;invio di diversi tipi di testo e deve essere utilizzato insieme al componente contenitore [modulo](form-container-v1.md).

Il tipo di convalida del testo, etichette e messaggi della guida può essere definito dall&#39;editor di contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Testo modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Testo modulo.

| Versione di AEM | Componente testo modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Testo modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo modulo, vedere il documento [Componente Testo modulo](/help/components/forms/form-text.md).

## Esempio di output del componente {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
     <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
     <div class="cmp cmp-form-field aem-GridColumn aem-GridColumn--default--12">
   <div class="form-group">
       <label for="form-text-978484744">How many pieces of toast would you like?</label>
          <input type="number" id="form-text-978484744" name="pieces">
   </div>
  </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "text": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/text",
                  "name": "piecesOfToast",
                  "jcr:title": "How many pieces of toast would you like?",
                  "type": "number",
                  "rows": "2"
                }
              },
              ":itemsOrder": [
                "text"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, vedere le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Principale {#main}

![](/help/assets/chlimage_1-23.png)

* **Vincolo** : il tipo di testo da inserire e su cui verrà convalidato il comando

   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**

* **Righe**  di testo - Numero di righe da visualizzare nell&#39;area di testo (visualizzate solo se  **** Limite è impostata su Area **di** testo)

* **Etichetta**  - Etichetta che verrà visualizzata per il campo
* **Nascondere l&#39;etichetta per la visualizzazione**  - Necessario se l&#39;etichetta è necessaria solo a scopo di accessibilità e non invia ulteriori informazioni visive sul campo
* **Nome**  elemento: il nome del campo inviato con i dati del modulo
* **Valore**  - Valore predefinito precompilato nel campo

### Informazioni su {#about}

![](/help/assets/chlimage_1-24.png)

* **Messaggio**  della Guida: un suggerimento per l&#39;utente sulle informazioni che è possibile immettere nel campo
* **Visualizza messaggio di aiuto come segnaposto** : per visualizzare il messaggio di aiuto all&#39;interno del modulo di input quando è vuoto e non è attivo

### Vincoli {#constraints}

![](/help/assets/chlimage_1-25.png)

* **Messaggio vincolo**

   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e **Area di testo**

* **Obbligatorio** : se selezionato, l&#39;utente deve compilare un valore prima di inviare il modulo
* **Rendi sola**  lettura - Se selezionato, l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo per il componente Testo modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).
