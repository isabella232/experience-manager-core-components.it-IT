---
title: Componente testo modulo (v1)
description: Il componente Testo modulo componente di base consente di inserire il testo del modulo da inviare.
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 8%

---


# Componente testo modulo (v1) {#form-text-component-v}

Il componente Testo modulo componente di base consente di inserire il testo del modulo da inviare.

## Utilizzo {#usage}

Il componente Testo modulo consente l’invio di diversi tipi di testo e deve essere utilizzato insieme al componente [contenitore modulo](form-container-v1.md).

Il tipo di convalida di testo, etichette e messaggi della guida può essere definito dall&#39;editor di contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Testo modulo , originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della versione 1 del componente Testo modulo .

| Versione di AEM | Componente testo modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Testo modulo .
>
>Per informazioni dettagliate sulla versione corrente del componente Testo modulo, consultare il documento [Componente Testo modulo](/help/components/forms/form-text.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Principale {#main}

![](/help/assets/chlimage_1-23.png)

* **Vincolo** : il tipo di testo da inserire e su cui verrà convalidato.

   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**

* **Righe**  di testo - Numero di righe da visualizzare nell’area di testo (solo se l’opzione  **** Limite è impostata su  **Area** di testo)

* **Etichetta** : l’etichetta che verrà visualizzata per il campo
* **Nascondere l’etichetta dalla visualizzazione**  - Necessario se l’etichetta è necessaria solo a scopo di accessibilità e non fornisce ulteriori informazioni visive sul campo
* **Nome elemento** : il nome del campo inviato con i dati del modulo
* **Valore** : valore predefinito precompilato nel campo

### Informazioni su {#about}

![](/help/assets/chlimage_1-24.png)

* **Messaggio della Guida** : un suggerimento per l’utente su cosa è possibile inserire nel campo
* **Visualizza il messaggio della guida come segnaposto** : per visualizzare il messaggio della guida all’interno del modulo di input quando è vuoto o non attivo

### Vincoli {#constraints}

![](/help/assets/chlimage_1-25.png)

* **Messaggio vincolo**

   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e **Area di testo**

* **Obbligatorio** : se selezionato, l’utente deve compilare un valore prima di inviare il modulo
* **Rendi sola**  lettura: se selezionata, l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo di progettazione per il componente Testo modulo .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
