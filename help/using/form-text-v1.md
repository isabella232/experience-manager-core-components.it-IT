---
title: Componente Testo modulo (v 1)
seo-title: Componente Testo modulo (v 1)
description: 'null'
seo-description: Il componente Testo componente componente core consente di inserire il testo del modulo da inviare.
uuid: 30123 aba -57 a 8-4 ed 4-93 cb -6 a 3 d 2 edff 9 a 7
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: bd 4 e 9930-4 d 81-49 ae-a 3 d 1-9 a 8740418 dae
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente Testo modulo (v 1){#form-text-component-v}

Il componente Testo componente componente core consente di inserire il testo del modulo da inviare.

## Utilizzo {#usage}

Il componente Testo modulo consente di inviare diversi tipi di testo e di utilizzarli insieme al [componente Contenitore del modulo](form-container.md).

Il tipo di convalida del testo, le etichette e i messaggi di aiuto possono essere definiti dall&#39;editor contenuto nella finestra di dialogo [Configura](form-text-v1.md#main-pars_title).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Testo modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Testo modulo.

| Versione di AEM | Componente Testo modulo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Testo modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo modulo, vedere [il documento Componente](form-text.md) Testo modulo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-22.png)

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire il tipo di testo da inserire e i valori e le etichette predefiniti.

### Principale {#main}

![](assets/chlimage_1-23.png)

* **Vincolo** : il tipo di testo da inserire e verrà convalidato

   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**

* **Righe di testo** - Numero di righe da visualizzare nell&#39;area di testo (visualizzata solo quando **Vincolo** è impostato sull&#39;area **testo**)

* **Etichetta** : etichetta visualizzata per il campo
* **Nasconde la visualizzazione dell&#39;etichetta** - Necessaria se l&#39;etichetta è obbligatoria solo per scopi di accessibilità e non fa parte di ulteriori informazioni visive sul campo
* **Nome** elemento: nome del campo inviato con i dati del modulo
* **Valore** : valore predefinito precompilato nel campo

### Informazioni su {#about}

![](assets/chlimage_1-24.png)

* **Messaggio** della Guida: un suggerimento per l&#39;utente che può inserire il campo
* **Visualizza messaggio della guida come segnaposto** - Per visualizzare il messaggio di aiuto all&#39;interno dell&#39;input del modulo quando è vuoto e non attivo

### Vincoli {#constraints}

![](assets/chlimage_1-25.png)

* **Messaggio vincolo**

   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per **i tipi di testo** e **Area** di testo

* **Obbligatorio** - Se selezionato, l&#39;utente deve compilare un valore prima di inviare il modulo
* **Rendi solo lettura** - Se selezionato l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Testo modulo.

## Dettagli tecnici {#technical-details}

In github è disponibile la documentazione tecnica più recente relativa al componente [Testo modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
