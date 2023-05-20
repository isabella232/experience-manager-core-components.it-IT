---
title: Componente Testo modulo (v1)
description: Il componente core Testo modulo consente l’inserimento di testo del modulo per l’invio.
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 100%

---

# Componente Testo modulo (v1) {#form-text-component-v}

Il componente core Testo modulo consente l’inserimento di testo del modulo per l’invio.

## Utilizzo {#usage}

Il componente Testo modulo consente l’invio di diversi tipi di testo e deve essere utilizzato insieme al componente [Contenitore modulo](form-container-v1.md).

Il tipo di convalida del testo, le etichette e i messaggi di aiuto possono essere definiti dall’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Testo modulo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Testo modulo.

| Versione di AEM | Componente Testo modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Testo modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo modulo, vedi il documento [Componente Testo modulo](/help/components/forms/form-text.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Principale {#main}

![](/help/assets/chlimage_1-23.png)

* **Vincolo**: il tipo di testo da inserire e su cui verrà effettuata la convalida

   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel**
   * **Data**
   * **Numero**
   * **Password**

* **Righe di testo**: numero di righe da visualizzare nell’area di testo (solo se l’opzione **Vincolo** Limite è impostata su **Area testo**)

* **Etichetta**: l’etichetta che verrà visualizzata per il campo
* **Nascondi l’etichetta**: opzione necessaria se l’etichetta serve solo per scopi di accessibilità e non fornisce alcuna informazione visiva aggiuntiva relativa al campo
* **Nome elemento**: il nome del campo che viene inviato con i dati del modulo
* **Valore**: il valore predefinito inserito automaticamente nel campo

### Informazioni su {#about}

![](/help/assets/chlimage_1-24.png)

* **Messaggio di aiuto**: suggerimento per l’utente per la compilazione del campo
* **Visualizza messaggio di aiuto come segnaposto**: indica se deve essere visualizzato il messaggio di aiuto nel modulo, quando il modulo è vuoto e non attivo

### Vincoli {#constraints}

![](/help/assets/chlimage_1-25.png)

* **Messaggio vincolo**

   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e **Area testo**

* **Richiesto**: se selezionata, l’utente deve necessariamente inserire un valore prima di inviare il modulo
* **Imposta per sola lettura**: se selezionata, l’utente non può modificare il valore del campo

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione non è disponibile per il componente Testo modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
