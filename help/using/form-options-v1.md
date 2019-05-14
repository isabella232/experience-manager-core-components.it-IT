---
title: Componente Opzioni modulo (v 1)
seo-title: Componente Opzioni modulo (v 1)
description: 'null'
seo-description: Il componente Opzioni modulo di base consente la selezione da opzioni predefinite in vari formati.
uuid: a 22 ed 77 c-c 9 f 3-46 f 4-8 afe-e 478383 c 1251
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: e 1975 bfe -2 bda -409 a -998 e -1 ff 4 f 9 f 23 b 94
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
noindex: vero
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente Opzioni modulo (v 1){#form-options-component-v}

Il componente Opzioni modulo di base consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo componente core consente di inviare diversi tipi di opzioni presentate in vari modi e di essere utilizzati insieme al [componente Contenitore del modulo](form-container.md).

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor contenuto nella finestra di dialogo [Configura](form-options-v1.md#main-pars_title).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Opzioni modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Opzioni modulo.

| Versione componente | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Opzioni modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Opzioni modulo, [vedere il documento Opzioni](form-options.md) modulo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-89.png)

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](assets/chlimage_1-90.png)

* **Tipi**
in che modo verranno presentate le opzioni

   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**

* **Titolo** : titolo visualizzato come etichetta per le opzioni
* **Nome** : nome del campo inviato con i dati del modulo
* **Sorgente** - Dove sono definite le opzioni

   * **Locale** - Definito all&#39;interno del componente
      * Toccate o fate clic sul **pulsante Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore** : il valore salvato quando l&#39;opzione è selezionata al momento dell&#39;invio del modulo
      * **Testo** : etichetta per l&#39;opzione visualizzata nel modulo
      * **Attivo** : l&#39;opzione è contrassegnata come selezionata al momento del caricamento del modulo
      * **Disattivato** : l&#39;opzione non è selezionabile ma resta visualizzata
      * **Elenco** : per l&#39;opzione viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco** : percorso dell&#39;elenco statico in AEM
            * Usare il pulsante Sfoglia per individuare la risorsa elenco
      * **Origine dati** - Un&#39;origine dati viene utilizzata per le opzioni
         * **Origine dati** - tipo di risorsa dell&#39;origine dati
* **Messaggio** di Aiuto: un suggerimento per l&#39;utente che può inserire il campo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Opzioni modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente Opzioni modulo [è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
