---
title: Componente testo (v1)
seo-title: Componente testo (v1)
description: 'null'
seo-description: Il componente Testo è un componente per la modifica e composizione di testo RTF che offre funzioni di modifica diretta.
uuid: b787ebac-fa85-416a-b96b-9d2ee85428ec
content-type: riferimento
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: d5e37dc7-dfd4-4a44-89b6-c15651472c43
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


# Componente testo (v1){#text-component-v}

Il componente Testo è un componente per la modifica e composizione di testo RTF che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un potente editor Rich Text che consente di modificare facilmente il testo in un editor semplificato e in linea e in un formato a schermo intero.

La finestra di dialogo [di](text-v1.md#main-pars_title) modifica offre funzioni di modifica in linea con opzioni limitate e funzionalità complete disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la finestra di dialogo [di](text-v1.md#main-pars_title_1995166862)progettazione, le opzioni di formattazione del testo, come titoli, caratteri speciali e stili di paragrafo, possono essere configurate per il modello per l'autore del contenuto.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Testo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Testo.

| Versione di AEM | Componente testo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Testo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo, consultare il documento [Componente](text.md) testo.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-27.png)

### HTML {#html}

```
<div class="cmp cmp-text aem-GridColumn aem-GridColumn--default--12">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.<br />
</p>
</div>
```

### JSON {#json}

```
"text": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "text": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.</p>\n",
              "richText": true,
              ":type": "weretail/components/content/text"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](versions.md#main-pars_title_236368006) .

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti di formattazione RTF standard che l’utente si aspetta di utilizzare per comporre del testo.

![](assets/chlimage_1-52.png)

* Grassetto

   ![](assets/chlimage_1-53.png)

   Utilizzato per applicare la formattazione in grassetto al testo selezionato o per formattare il testo in grassetto immesso dopo il cursore.

   **Ctrl+B** può essere utilizzato come scelta rapida da tastiera.

* Corsivo

   ![](assets/chlimage_1-54.png)

   Utilizzato per applicare la formattazione in corsivo al testo selezionato o per personalizzare il testo immesso dopo il cursore.

   **Ctrl+I** può essere utilizzato come scelta rapida da tastiera.

* Sottolineato

   ![](assets/chlimage_1-55.png)

   Utilizzato per applicare la formattazione sottolineata al testo selezionato o al testo sottolineato immesso dopo il cursore.

   **Ctrl+U** può essere utilizzato come scelta rapida da tastiera.

* Pedice

   ![](assets/chlimage_1-56.png)

   Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come pedice.

* Apice

   ![](assets/chlimage_1-57.png)

   Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come apice.

* Incolla come testo

   ![](assets/chlimage_1-58.png)

   Pastes any copied text as plain text without any formatting.

   When selecting this option a window opens where the text can be pasted as plain text with no formatting as a preview before it is inserted into the text. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

   ![](assets/chlimage_1-59.png)

* Incolla da Word

   ![](assets/chlimage_1-60.png)

   Quando si seleziona questa opzione, si apre una finestra in cui è possibile incollare il testo mantenendo la formattazione come anteprima prima di inserirlo nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

   ![](assets/chlimage_1-61.png)

* Collegamento ipertestuale

   ![](assets/chlimage_1-62.png)

   Utilizzare questa opzione per convertire il testo selezionato in un collegamento ipertestuale o per modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per impostare il collegamento.

   ![](assets/chlimage_1-63.png)

   * Immettere la posizione

      * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
      * Se il collegamento non è in AEM, inserite l’URL assoluto (i percorsi non assoluti vengono interpretati come relativi ad AEM)
   * Immettere testo descrittivo alternativo per il collegamento
   * Seleziona il comportamento del collegamento

      * Destinazione
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore
   Toccate o fate clic sul segno di spunta per applicare il collegamento o sulla x per annullare.

* Scollega

   ![](assets/chlimage_1-64.png)

   Utilizzare questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

* Trova

   ![](assets/chlimage_1-65.png)

   Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca.

   ![](assets/chlimage_1-66.png)

   Immettere il testo per il quale si desidera eseguire la ricerca e toccare o fare clic su **Trova** per iniziare la ricerca. Toccate o fate clic sulla x per annullare.

   Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Toccate o fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l'occorrenza successiva.

   ![](assets/chlimage_1-67.png)

   Se non vengono trovate altre occorrenze, verrà visualizzato un messaggio e la ricerca verrà riavviata dall'inizio del testo.

   ![](assets/chlimage_1-68.png)

* Sostituisci

   ![](assets/chlimage_1-69.png)

   Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un'altra stringa. Selezionando questa opzione si apre una finestra in cui specificare le opzioni di ricerca e sostituzione.

   ![](assets/chlimage_1-70.png)

   Immettere il testo per il quale si desidera eseguire la ricerca e il testo con cui sostituire il testo.

   Toccate o fate clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla X per annullare.

   Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l'occorrenza successiva oppure fate clic sul pulsante **Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Sostituisci** è attivo solo una volta raggiunta una corrispondenza.

   Selezionate **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

* Allinea testo a sinistra

   ![](assets/chlimage_1-71.png)

   Utilizzato per allineare il testo al margine sinistro.

* Testo centrato

   ![](assets/chlimage_1-72.png)

   Utilizzato per centrare il testo.

* Allinea testo a destra

   ![](assets/chlimage_1-73.png)

   Utilizzato per allineare il testo al margine destro.

* Proiettile

   ![](assets/chlimage_1-74.png)

   Consente di formattare il testo selezionato come elenco puntato o di iniziare l'inserimento di un elenco puntato dopo il cursore.

   Per terminare un elenco puntato, toccate o fate di nuovo clic sul pulsante **Bullet** oppure immettete due ritorni a capo.

* Numbered

   ![](assets/chlimage_1-75.png)

   Consente di formattare il testo selezionato come elenco numerato o di iniziare l'inserimento di un elenco numerato dopo il cursore.

   Per terminare un elenco numerato, toccate o fate di nuovo clic sul pulsante **Numerato** oppure immettete due ritorni a capo.

* Rientro negativo

   ![](assets/chlimage_1-76.png)

   Consente di ridurre il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

   Attiva solo se il testo o la posizione selezionati del cursore sono già rientrati.

* Rientro

   ![](assets/chlimage_1-77.png)

   Utilizzato per aumentare il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

* Tabella

   ![](assets/chlimage_1-78.png)

   Utilizzato per inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

   ![](assets/chlimage_1-79.png)

   * **Colonne** - Il numero di colonne della tabella (obbligatorio)
   * **Righe** - Il numero di righe della tabella (obbligatorio)
   * **Larghezza** - La larghezza della tabella
   * **Altezza** - L'altezza della tabella
   * **Margine celle -** Spazio intorno al contenuto della cella
   * **Spaziatura** celle - Spazio tra celle
   * **Bordo** - Lo spessore delle linee dei bordi della tabella
   * Se per l’intestazione della tabella:

      * La prima riga deve essere utilizzata
      * Utilizzare la prima colonna
      * Utilizzare la prima riga e la prima colonna
      * Oppure non utilizzare alcuna intestazione.
   * **Didascalia** - La didascalia della tabella


* Controllo ortografia

   ![](assets/chlimage_1-80.png)

   Utilizzato per il controllo dell'ortografia del contenuto di testo. Eventuali errori ortografici sono sottolineati con linee rosse rotte.

* Caratteri speciali

   ![](assets/chlimage_1-81.png)

   Utilizzato per inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

   ![](assets/chlimage_1-82.png)

   Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Toccate o fate clic sulla x per chiudere la finestra di selezione.

* Modifica origine

   ![](assets/chlimage_1-83.png)

   Utilizzato per visualizzare e modificare l'origine HTML del testo.

   Toccate o fate clic sull’icona Modifica **** sorgente per cambiare il contenuto del testo dalla visualizzazione formattata per visualizzare l’HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disattivate. Toccate o fate di nuovo clic sull’icona **Sorgente modifica** per tornare alla visualizzazione formattata.

   >[!CAUTION]
   >
   >Come sempre con l'accesso a HTML non elaborato, occorre prestare attenzione quando si utilizza l'opzione di modifica **** origine!
   >
   >
   >L'HTML immesso tramite Modifica **** origine viene analizzato per rilevare i rischi XSS e gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, l’HTML con formato non corretto immesso in **Modifica** origine può interrompere il modello per la pagina, dando luogo a una formattazione imprevista o rendendo la pagina risultante inutilizzabile.

* Formato paragrafo

   ![](assets/chlimage_1-84.png)

   Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale è selezionato il formato del paragrafo.

   ![](assets/chlimage_1-85.png)

Anche il componente di testo può essere modificato in linea, ma a causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passare alla modalità a schermo intero.

![](assets/chlimage_1-86.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Funzioni {#features}

![](assets/chlimage_1-28.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato da parola
* Trova e sostituisci
* Controllo ortografia
* Modifica origine

### Formattazione {#formatting}

![](assets/chlimage_1-29.png)

Le seguenti opzioni di formattazione possono essere attivate o disattivate per il componente.

* Tabella
* Elenchi
* Allineamento
* Grassetto, corsivo, sottolineato
* Collegamenti
* Pedice

### Stili paragrafo {#paragraph-styles}

![](assets/chlimage_1-30.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando attivato, è possibile definire i formati consentiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immettete il codice dello stile e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere uno stile, toccate o fate clic sul pulsante **Elimina** .
* Per ridisporre l'ordine dei formati, toccate o fate clic e trascinate le maniglie.

### Caratteri speciali {#special-characters}

![](assets/chlimage_1-31.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Se attivati, i caratteri consentiti possono essere definiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immettete il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un carattere toccate o fate clic sul pulsante **Elimina** .
* Per riordinare i caratteri, toccate o fate clic e trascinate le maniglie.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
