---
title: Componente Testo (v1)
description: Il componente Testo è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '1657'
ht-degree: 100%

---

# Componente Testo (v1) {#text-component-v}

Il componente Testo è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un efficiente editor RTF che consente di modificare facilmente il testo in un editor semplificato in linea e in formato a schermo intero.

La [finestra di dialogo per modifica](#edit-dialog) offre funzioni di modifica in linea con opzioni limitate. Le funzionalità complete sono disponibili nella finestra di dialogo per modifica a schermo intero. La [finestra di dialogo per progettazione](#design-dialog) consente di configurare le opzioni di formattazione del testo, come intestazioni, caratteri speciali e stili di paragrafo, per il modello utilizzabile dall’autore di contenuto.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Testo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Testo.

| Versione di AEM | Componente Testo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>In questo documento viene descritta la versione 1 del componente Testo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo, vedi il documento [Componente Testo](/help/components/text.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica offre gli strumenti di formattazione RTF standard per la composizione del testo.

![](/help/assets/chlimage_1-52.png)

* Grassetto

   ![](/help/assets/chlimage_1-53.png)

   Consente di applicare il grassetto al testo selezionato o al testo immesso dopo il cursore.

   **Ctrl+B** può essere utilizzato come scelta rapida da tastiera.

* Corsivo

   ![](/help/assets/chlimage_1-54.png)

   Consente di applicare il corsivo al testo selezionato o al testo immesso dopo il cursore.

   **Ctrl+I** può essere utilizzato come scelta rapida da tastiera.

* Sottolineato

   ![](/help/assets/chlimage_1-55.png)

   Consente di applicare la sottolineatura al testo selezionato o al testo immesso dopo il cursore.

   **Ctrl+U** può essere utilizzato come scelta rapida da tastiera.

* Pedice

   ![](/help/assets/chlimage_1-56.png)

   Consente di formattare come pedice il testo selezionato o il testo immesso dopo il cursore.

* Apice

   ![](/help/assets/chlimage_1-57.png)

   Consente di formattare come apice il testo selezionato o il testo immesso dopo il cursore.

* Incolla testo semplice

   ![](/help/assets/chlimage_1-58.png)

   Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

   Quando si seleziona questa opzione, viene visualizzata una finestra in cui il testo copiato può essere incollato come testo normale senza formattazione in anteprima, prima di essere effettivamente inserito nel testo. Per accettare, tocca o fai clic sul segno di spunta, per annullare tocca o fai clic sulla x.

   ![](/help/assets/chlimage_1-59.png)

* Incolla da Word

   ![](/help/assets/chlimage_1-60.png)

   Quando si seleziona questa opzione, viene visualizzata una finestra in cui il testo copiato può essere incollato con la formattazione originale in anteprima, prima di essere effettivamente inserito nel testo. Per accettare, tocca o fai clic sul segno di spunta, per annullare tocca o fai clic sulla x.

   ![](/help/assets/chlimage_1-61.png)

* Collegamento ipertestuale

   ![](/help/assets/chlimage_1-62.png)

   Questa opzione consente di convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per l’impostazione del collegamento.

   ![](/help/assets/chlimage_1-63.png)

   * Immetti la posizione

      * La finestra di dialogo per selezione consente di scegliere un percorso in AEM
      * Se il collegamento non si trova all’interno di AEM, immetti l’URL assoluto (i percorsi non assoluti vengono interpretati come relativi ad AEM)
   * Immetti un testo descrittivo alternativo per il collegamento
   * Seleziona il comportamento del collegamento

      * Destinazione
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore

   Tocca o fai clic sul segno di spunta per applicare il collegamento o sulla x per annullare.

* Scollega

   ![](/help/assets/chlimage_1-64.png)

   Questa opzione consente di rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

* Trova

   ![](/help/assets/chlimage_1-65.png)

   Questa opzione consente di cercare nel testo le occorrenze di una stringa di testo specificata. Selezionando questa opzione, si apre una finestra per specificare le opzioni di ricerca.

   ![](/help/assets/chlimage_1-66.png)

   Inserisci il testo da cercare e tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.

   Se vuoi avere una corrispondenza esatta di maiuscole/minuscole, seleziona l’opzione **Rispetta maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene sfumata. Tocca o fai di nuovo clic sul pulsante **Trova** nella finestra di dialogo sfumata per cercare l’occorrenza successiva.

   ![](/help/assets/chlimage_1-67.png)

   Se non vengono trovate altre occorrenze, viene visualizzato un messaggio e la ricerca riparte dall’inizio del testo.

   ![](/help/assets/chlimage_1-68.png)

* Sostituisci

   ![](/help/assets/chlimage_1-69.png)

   Questa opzione consente di cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un’altra stringa. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca e sostituzione.

   ![](/help/assets/chlimage_1-70.png)

   Immettere il testo da cercare e il testo con cui deve essere sostituito.

   Tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.

   Se vuoi avere una corrispondenza esatta di maiuscole/minuscole, seleziona l’opzione **Rispetta maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene sfumata. Fai nuovamente clic sul pulsante **Trova** nella finestra di dialogo sfumata per cercare l’occorrenza successiva oppure seleziona il pulsante **Sostituisci** per sostituire il testo evidenziato. Il pulsante **Sostituisci** è attivo solo una volta trovata una corrispondenza.

   Seleziona **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

* Allineato a sinistra

   ![](/help/assets/chlimage_1-71.png)

   Consente di allineare il testo al margine sinistro.

* Centrato

   ![](/help/assets/chlimage_1-72.png)

   Consente di centrare il testo.

* Allineato a destra

   ![](/help/assets/chlimage_1-73.png)

   Consente di allineare il testo al margine destro.

* Punto elenco

   ![](/help/assets/chlimage_1-74.png)

   Consente di formattare il testo selezionato come elenco puntato o di iniziare l’inserimento di un elenco puntato dopo il cursore.

   Per terminare un elenco puntato, tocca o fai clic nuovamente sul pulsante **Punto elenco** oppure immetti due ritorni a capo.

* Numero

   ![](/help/assets/chlimage_1-75.png)

   Consente di formattare il testo selezionato come elenco numerato o di iniziare l’inserimento di un elenco numerato dopo il cursore.

   Per terminare un elenco numerato, tocca o fai clic nuovamente sul pulsante **Numero** oppure immetti due ritorni a capo.

* Riduci rientro

   ![](/help/assets/chlimage_1-76.png)

   Consente di ridurre il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

   L’opzione è attiva solo se il testo selezionato o la posizione del cursore è già rientrata.

* Rientro

   ![](/help/assets/chlimage_1-77.png)

   Consente di aumentare il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

* Tabella

   ![](/help/assets/chlimage_1-78.png)

   Consente di inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

   ![](/help/assets/chlimage_1-79.png)

   * **Colonne**: il numero di colonne della tabella (obbligatorio)
   * **Righe**: il numero di righe della tabella (obbligatorio)
   * **Larghezza**: la larghezza della tabella
   * **Altezza**: l’altezza della tabella
   * **Margine celle**: lo spazio intorno al contenuto della cella
   * **Spaziatura celle**: lo spazio tra le celle
   * **Bordo**: lo spessore delle linee dei bordi della tabella
   * Per l’intestazione della tabella:

      * Utilizza la prima riga
      * Utilizza la prima colonna
      * Utilizza la prima riga e la prima colonna
      * In alternativa, non utilizzare alcuna intestazione
   * **Didascalia**: la didascalia della tabella


* Controllo ortografico

   ![](/help/assets/chlimage_1-80.png)

   Consente di verificare l’ortografia del testo. Eventuali errori di ortografia appaiono sottolineati con linee tratteggiate rosse.

* Caratteri speciali

   ![](/help/assets/chlimage_1-81.png)

   Consente di inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

   ![](/help/assets/chlimage_1-82.png)

   Tocca o fai clic sul carattere desiderato per inserirlo nel testo dopo il cursore. Si possono inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra per selezione.

* Modifica origine

   ![](/help/assets/chlimage_1-83.png)

   Consente di visualizzare e modificare l’origine HTML del testo.

   Per modificare il testo dalla vista formattata, tocca o fai clic sull’icona **Modifica origine** per visualizzare il codice HTML. In questa modalità, tutte le altre opzioni di formattazione sono disabilitate. Tocca o fai clic di nuovo sull’icona **Modifica origine** per tornare alla vista formattata.

   >[!CAUTION]
   >
   >Come sempre quando si accede al codice HTML, utilizza l’opzione **Modifica origine** con molta attenzione!
   >
   >
   >Il codice HTML immesso tramite l’opzione **Modifica origine** viene analizzato per rilevare eventuali rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, il codice HTML non corretto eventualmente immesso tramite **Modifica origine** può alterare il modello della pagina, causando formattazioni impreviste e rendendo inutilizzabile la pagina risultante.

* Formato paragrafo

   ![](/help/assets/chlimage_1-84.png)

   Consente di formattare come paragrafo il testo selezionato o il testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale si può selezionare il formato del paragrafo.

   ![](/help/assets/chlimage_1-85.png)

Il componente Testo può essere modificato anche in linea, ma in questo caso, a causa di limitazioni di spazio, non tutte le opzioni di formattazione sono disponibili. Per visualizzare tutte le opzioni, passa alla modalità a schermo intero.

![](/help/assets/chlimage_1-86.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dii contenuto.

### Funzioni {#features}

![](/help/assets/chlimage_1-28.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo semplice
* Incolla da Word
* Trova e sostituisci
* Controllo ortografico
* Modifica origine

### Formattazione {#formatting}

![](/help/assets/chlimage_1-29.png)

Per il componente è possibile attivare o disattivare le seguenti opzioni di formattazione.

* Tabella
* Elenchi
* Allineamento
* Grassetto, corsivo, sottolineato
* Collegamenti
* Apice/pedice

### Stili paragrafo {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando l’opzione è attivata, è possibile definire i formati consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immetti il codice dello stile e una descrizione da visualizzare nella finestra di dialogo per modifica.
* Per rimuovere uno stile, tocca o fai clic sul pulsante **Elimina**.
* Per cambiare l’ordine dei formati, tocca o fai clic e trascina le maniglie.

### Caratteri speciali {#special-characters}

![](/help/assets/chlimage_1-31.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Quando è attivata, è possibile definire i caratteri consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immetti il codice HTML del carattere e una descrizione da visualizzare nella finestra di dialogo per modifica.
* Per rimuovere un carattere, tocca o fai clic sul pulsante **Elimina**.
* Per cambiare l’ordine dei caratteri, tocca o fai clic e trascina le maniglie.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
