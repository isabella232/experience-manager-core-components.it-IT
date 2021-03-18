---
title: Componente testo (v1)
description: Il componente Testo è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.
index: n
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 3%

---


# Componente testo (v1) {#text-component-v}

Il componente Testo è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un robusto editor Rich Text che consente di modificare facilmente il testo in un editor semplificato e in linea e in un formato a schermo intero.

La [finestra di dialogo di modifica](#edit-dialog) presenta funzioni di modifica in linea con opzioni limitate e funzionalità complete disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la finestra di dialogo di progettazione [progettazione](#design-dialog), è possibile configurare per il modello per l’autore del contenuto le opzioni di formattazione del testo quali intestazioni, caratteri speciali e stili di paragrafo.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente testo, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità della v1 del componente di testo.

| Versione di AEM | Componente testo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>In questo documento viene descritta la versione 1 del componente di testo.
>
>Per informazioni dettagliate sulla versione corrente del componente di testo, consultare il documento [Componente di testo](/help/components/text.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-27.png)

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti di formattazione RTF standard che un utente si aspetta di utilizzare per comporre il testo.

![](/help/assets/chlimage_1-52.png)

* Grassetto

   ![](/help/assets/chlimage_1-53.png)

   Utilizzato per applicare la formattazione in grassetto al testo selezionato o al testo in formato grassetto immesso dopo il cursore.

   **Ctrl+** Bè può essere utilizzato come scelta rapida da tastiera.

* Corsivo

   ![](/help/assets/chlimage_1-54.png)

   Consente di applicare la formattazione in corsivo al testo selezionato o di applicare il corsivo al testo immesso dopo il cursore.

   **Ctrl+** I può essere utilizzato come scelta rapida da tastiera.

* Sottolineato

   ![](/help/assets/chlimage_1-55.png)

   Utilizzato per applicare la formattazione sottolineata al testo selezionato o al testo sottolineato immesso dopo il cursore.

   **Ctrl+** Non può essere utilizzato come scelta rapida da tastiera.

* Pedice

   ![](/help/assets/chlimage_1-56.png)

   Utilizzato per formattare come pedice il testo o il testo selezionato immesso dopo il cursore.

* Apice

   ![](/help/assets/chlimage_1-57.png)

   Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come apice.

* Incolla come testo

   ![](/help/assets/chlimage_1-58.png)

   Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

   Quando si seleziona questa opzione viene visualizzata una finestra in cui il testo può essere incollato come testo normale senza formattazione come anteprima prima di essere inserito nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

   ![](/help/assets/chlimage_1-59.png)

* Incolla da Word

   ![](/help/assets/chlimage_1-60.png)

   Quando si seleziona questa opzione viene visualizzata una finestra in cui è possibile incollare il testo mantenendo la formattazione come anteprima prima di inserirla nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

   ![](/help/assets/chlimage_1-61.png)

* Collegamento ipertestuale

   ![](/help/assets/chlimage_1-62.png)

   Utilizzare questa opzione per convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per l’impostazione del collegamento.

   ![](/help/assets/chlimage_1-63.png)

   * Inserire la posizione

      * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
      * Se il collegamento non si trova all’interno di AEM, immetti l’URL assoluto (i percorsi non assoluti vengono interpretati come relativi a AEM)
   * Inserisci un testo descrittivo alternativo per il collegamento
   * Selezionare il comportamento del collegamento

      * Target
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore

   Tocca o fai clic sul segno di spunta per applicare il collegamento o la x da annullare.

* Scollega

   ![](/help/assets/chlimage_1-64.png)

   Utilizzare questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

* Trova

   ![](/help/assets/chlimage_1-65.png)

   Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca.

   ![](/help/assets/chlimage_1-66.png)

   Inserisci il testo per il quale vuoi cercare e tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.

   Se desideri eseguire una corrispondenza esatta in base al caso, seleziona l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene oscurata. Tocca o fai di nuovo clic sul pulsante **Trova** nella finestra di dialogo oscura per cercare l&#39;occorrenza successiva.

   ![](/help/assets/chlimage_1-67.png)

   Se non vengono trovate altre occorrenze, verrà visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

   ![](/help/assets/chlimage_1-68.png)

* Sostituisci

   ![](/help/assets/chlimage_1-69.png)

   Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca e sostituzione.

   ![](/help/assets/chlimage_1-70.png)

   Immettere il testo per il quale si desidera eseguire la ricerca e il testo con cui deve essere sostituito.

   Tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.

   Se desideri eseguire una corrispondenza esatta in base al caso, seleziona l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene oscurata. Fai nuovamente clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l&#39;occorrenza successiva oppure seleziona il pulsante **Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Replace** è attivo solo una volta effettuata una corrispondenza.

   Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

* Allinea testo a sinistra

   ![](/help/assets/chlimage_1-71.png)

   Utilizzato per allineare il testo al margine sinistro.

* Testo centrato

   ![](/help/assets/chlimage_1-72.png)

   Utilizzato per centrare il testo.

* Allinea testo a destra

   ![](/help/assets/chlimage_1-73.png)

   Utilizzato per allineare il testo al margine destro.

* Proiettile

   ![](/help/assets/chlimage_1-74.png)

   Consente di formattare il testo selezionato come elenco puntato o di iniziare l’inserimento di un elenco puntato dopo il cursore.

   Per terminare un elenco puntato, toccare o fare clic nuovamente sul pulsante **Bullet** oppure immettere due ritorni a capo.

* Numerato

   ![](/help/assets/chlimage_1-75.png)

   Consente di formattare il testo selezionato come elenco numerato o di iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

   Per terminare un elenco numerato, toccare o fare clic nuovamente sul pulsante **Numbered** oppure immettere due ritorni a capo.

* Rientro negativo

   ![](/help/assets/chlimage_1-76.png)

   Consente di ridurre il livello di rientro del testo o del testo selezionato dopo il cursore.

   Attiva solo se il testo o la posizione selezionata del cursore sono già rientrati.

* Rientro

   ![](/help/assets/chlimage_1-77.png)

   Consente di aumentare il livello di rientro del testo o del testo selezionato dopo il cursore.

* Tabella

   ![](/help/assets/chlimage_1-78.png)

   Utilizzato per inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

   ![](/help/assets/chlimage_1-79.png)

   * **Colonne**  - Il numero di colonne della tabella (obbligatorio)
   * **Righe**  - Il numero di righe della tabella (obbligatorio)
   * **Larghezza**  - Larghezza della tabella
   * **Altezza**  - Altezza della tabella
   * **Margine** celle - Spazio intorno al contenuto della cella
   * **Spaziatura**  celle: lo spazio tra le celle
   * **Bordo** : il peso delle linee dei bordi della tabella
   * Se per l’intestazione della tabella:

      * La prima riga deve essere utilizzata
      * Utilizzare la prima colonna
      * Utilizzare la prima riga e la prima colonna
      * Oppure non utilizzare alcuna intestazione.
   * **Didascalia** : la didascalia della tabella


* Controllo ortografia

   ![](/help/assets/chlimage_1-80.png)

   Utilizzato per controllare l’ortografia del contenuto di testo. Eventuali errori di ortografia sono sottolineati con linee rosse rotte.

* Caratteri speciali

   ![](/help/assets/chlimage_1-81.png)

   Utilizzato per inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

   ![](/help/assets/chlimage_1-82.png)

   Tocca o fai clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra di selezione.

* Modifica origine

   ![](/help/assets/chlimage_1-83.png)

   Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

   Tocca o fai clic sull&#39;icona **Modifica origine** per modificare il contenuto del testo dalla visualizzazione formattata per visualizzare l&#39;HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disabilitate. Tocca o fai di nuovo clic sull&#39;icona **Modifica origine** per tornare alla visualizzazione formattata.

   >[!CAUTION]
   >
   >Come sempre per l&#39;accesso all&#39;HTML non elaborato, è necessario prestare attenzione quando si utilizza l&#39;opzione **Modifica origine**!
   >
   >
   >Il codice HTML immesso tramite **Modifica origine** viene analizzato per rilevare i rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, il codice HTML non corretto immesso in **Modifica origine** può interrompere il modello per la pagina, dando luogo a una formattazione o a un rendering imprevisti della pagina risultante inutilizzabile.

* Formato paragrafo

   ![](/help/assets/chlimage_1-84.png)

   Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale è selezionato il formato del paragrafo.

   ![](/help/assets/chlimage_1-85.png)

È possibile modificare anche il componente testo in linea, ma a causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passa alla modalità a schermo intero.

![](/help/assets/chlimage_1-86.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dei contenuti.

### Funzioni {#features}

![](/help/assets/chlimage_1-28.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato dalla parola
* Trova e sostituisci
* Controllo ortografia
* Modifica sorgente

### Formattazione {#formatting}

![](/help/assets/chlimage_1-29.png)

Per il componente è possibile attivare o disattivare le seguenti opzioni di formattazione.

* Tabella
* Elenchi
* Allineamento
* Grassetto, corsivo, sottolineato
* Collegamenti
* Sottoscritto

### Stili paragrafo {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando è attivata, è possibile definire i formati consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immetti il codice dello stile e una descrizione da visualizzare nella finestra di dialogo di modifica.
* Per rimuovere uno stile, tocca o fai clic sul pulsante **Elimina** .
* Per ridisporre l’ordine dei formati, tocca o fai clic e trascina le maniglie.

### Caratteri speciali {#special-characters}

![](/help/assets/chlimage_1-31.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Quando sono attivati, è possibile definire i caratteri consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immetti il codice HTML del carattere e una descrizione da visualizzare nella finestra di dialogo di modifica.
* Per rimuovere un carattere, tocca o fai clic sul pulsante **Elimina** .
* Per ridisporre l’ordine dei caratteri, tocca o fai clic e trascina le maniglie.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di testo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
