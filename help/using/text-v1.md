---
title: Componente testo (v 1)
seo-title: Componente testo (v 1)
description: 'null'
seo-description: Il componente Testo è un componente RTF che consente di modificare e comporre in locale le funzioni di modifica locale.
uuid: b 787 ebac-fa 85-416 a-b 96 b -9 d 2 ee 85428 ec
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: d 5 e 37 dc 7-dfd 4-4 a 44-89 b 6-c 15651472 c 43
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente testo (v 1){#text-component-v}

Il componente Testo è un componente RTF che consente di modificare e comporre in locale le funzioni di modifica locale.

## Utilizzo {#usage}

Il componente Testo offre un editor Rich Text affidabile che semplifica la modifica del testo in un editor in linea, in-line e a schermo intero.

La [finestra di dialogo](text-v1.md#main-pars_title) di modifica presenta funzioni di modifica in linea con opzioni limitate, disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la [finestra di dialogo di progettazione](text-v1.md#main-pars_title_1995166862), le opzioni di formattazione del testo quali le intestazioni, i caratteri speciali e gli stili di paragrafo possono essere configurate per il modello relativo all&#39;autore del contenuto.

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Testo, originariamente introdotto con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Testo.

| Versione di AEM | Componente testo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Testo.
>
>Per informazioni dettagliate sulla versione corrente del componente Testo, consultate [il documento Componente](text.md) Testo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti standard di formattazione RTF che l&#39;utente dovrà comporre.

![](assets/chlimage_1-52.png)

* Grassetto

   ![](assets/chlimage_1-53.png)

   Utilizzato per applicare la formattazione in grassetto al testo selezionato o in formato grassetto, inserito dopo il cursore.

   **Ctrl + B** può essere usato come scelta rapida da tastiera.

* Corsivo

   ![](assets/chlimage_1-54.png)

   Utilizzato per applicare la formattazione in corsivo al testo selezionato o in corsivo, inserito dopo il cursore.

   **Ctrl + I** Può essere usato come scelta rapida da tastiera.

* Sottolineato

   ![](assets/chlimage_1-55.png)

   Utilizzato per applicare la formattazione sottolineata al testo selezionato o sottolineare il testo inserito dopo il cursore.

   **Ctrl + U** può essere usato come scelta rapida da tastiera.

* Pedice

   ![](assets/chlimage_1-56.png)

   Utilizzato per formattare il testo selezionato o il testo immesso dopo il cursore come pedice.

* Apice

   ![](assets/chlimage_1-57.png)

   Utilizzato per formattare il testo selezionato o il testo immesso dopo il cursore come apice.

* Incolla come testo

   ![](assets/chlimage_1-58.png)

   Incolla qualsiasi testo copiato come testo normale senza formattazione.

   Quando si seleziona questa opzione, si apre una finestra in cui il testo può essere incollato come testo normale senza formattazione prima che venga inserito nel testo. Per accettare toccando o facendo clic sul segno di spunta, tocca o fai clic sulla x.

   ![](assets/chlimage_1-59.png)

* Incolla da Word

   ![](assets/chlimage_1-60.png)

   Quando si seleziona questa opzione, si apre una finestra in cui si può incollarne la formattazione come anteprima prima che venga inserita nel testo. Per accettare toccando o facendo clic sul segno di spunta, tocca o fai clic sulla x.

   ![](assets/chlimage_1-61.png)

* Collegamento ipertestuale

   ![](assets/chlimage_1-62.png)

   Utilizzate questa opzione per convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per l&#39;impostazione del collegamento.

   ![](assets/chlimage_1-63.png)

   * Inserire il percorso

      * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
      * Se il collegamento non è in AEM, immettete l&#39;URL assoluto (i percorsi non assoluti vengono interpretati come relativi a AEM)
   * Inserisci testo descrittivo alternativo per il collegamento
   * Selezione del comportamento dei collegamenti

      * Destinazione
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore
   Toccate o fate clic sul segno di spunta per applicare il collegamento o la x da annullare.

* Scollega

   ![](assets/chlimage_1-64.png)

   Utilizzate questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo quando un collegamento è già selezionato.

* Trova

   ![](assets/chlimage_1-65.png)

   Utilizzare questa opzione per cercare il testo per occorrenze di una stringa di testo specificata. Selezionate questa opzione per aprire una finestra che consente di specificare le opzioni di ricerca.

   ![](assets/chlimage_1-66.png)

   Inserite il testo per il quale desiderate cercare e toccate o fate clic su **Trova** per avviare la ricerca. Toccate o fate clic sul x per annullare.

   Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l&#39;opzione **Corrispondenza maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Toccate o fate clic nuovamente sul **pulsante Trova** nella finestra di dialogo disattiva per cercare l&#39;occorrenza successiva.

   ![](assets/chlimage_1-67.png)

   Se non vengono trovate occorrenze aggiuntive, viene visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

   ![](assets/chlimage_1-68.png)

* Sostituisci

   ![](assets/chlimage_1-69.png)

   Utilizzare questa opzione per cercare il testo per occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Se selezionate questa opzione, viene aperta una finestra che consente di specificare le opzioni di ricerca e sostituzione.

   ![](assets/chlimage_1-70.png)

   Inserite il testo da cercare e il testo da sostituire.

   Tocca o fai clic su **Trova** per avviare la ricerca. Tocca o fai clic sul segno x per annullare.

   Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l&#39;opzione **Corrispondenza maiuscole/minuscole** prima di avviare la ricerca.

   Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Fare di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattiva per cercare l&#39;occorrenza successiva o fare clic sul **pulsante Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Sostituisci** è attivo solo quando viene effettuata una corrispondenza.

   Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

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

   Utilizzato per formattare il testo selezionato come elenco puntato o iniziare l&#39;inserimento di un elenco puntato dopo il cursore.

   Per terminare un elenco puntato, toccate o fate di nuovo clic sul pulsante **Bullet** oppure immettete due ritorni a capo.

* Numerato

   ![](assets/chlimage_1-75.png)

   Utilizzato per formattare il testo selezionato come elenco numerato o iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

   Per terminare un elenco numerato, toccare o fare di nuovo clic sul pulsante **Numerato** oppure immettere due ritorni a capo.

* Rientro negativo

   ![](assets/chlimage_1-76.png)

   Utilizzato per diminuire il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

   Attivo solo se il testo o la posizione selezionati del cursore è già rientrato.

* Rientro

   ![](assets/chlimage_1-77.png)

   Utilizzato per aumentare il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

* Tabella

   ![](assets/chlimage_1-78.png)

   Utilizzato per inserire una tabella nel testo. Quando si seleziona questa opzione si apre una finestra per specificare i dettagli della tabella.

   ![](assets/chlimage_1-79.png)

   * **Colonne** : numero di colonne della tabella (obbligatorio)
   * **Righe** : numero di righe della tabella (obbligatorio)
   * **Larghezza** : larghezza della tabella
   * **Altezza** : altezza della tabella
   * **Margine** celle: spazio intorno al contenuto della cella
   * **Spaziatura** celle - Spazio tra celle
   * **Bordo** : spessore delle linee dei bordi della tabella
   * Se per l&#39;intestazione della tabella:

      * La prima riga deve essere utilizzata
      * La prima colonna deve essere utilizzata
      * È necessario utilizzare la prima riga e la prima colonna
      * Oppure non è necessario utilizzare nessuna intestazione.
   * **Didascalia** - La didascalia della tabella


* Controllo ortografia

   ![](assets/chlimage_1-80.png)

   Utilizzato per controllare l&#39;ortografia del contenuto del testo. I possibili errori ortografici sono sottolineati con linee rosse interrotte.

* Caratteri speciali

   ![](assets/chlimage_1-81.png)

   Utilizzato per inserire caratteri speciali nel testo. Quando selezionate questa opzione, viene aperta una finestra in cui vengono visualizzati i caratteri disponibili.

   ![](assets/chlimage_1-82.png)

   Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra di selezione.

* Modifica origine

   ![](assets/chlimage_1-83.png)

   Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

   Toccate o fate clic sull&#39; **icona Modifica** sorgente per modificare il contenuto del testo dalla visualizzazione formattata per visualizzare l&#39;HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disattivate. Toccate o fate di nuovo **clic sull&#39;icona Modifica** sorgente per tornare alla visualizzazione formattata.

   >[!CAUTION]
   >
   >Come sempre con l&#39;accesso all&#39;HTML non elaborato, l&#39;attenzione deve essere esercitata quando si utilizza l&#39; **opzione Modifica** origine.
   >
   >
   >Il codice HTML immesso tramite **Modifica** origine viene analizzato per i rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, l&#39;HTML corrotto immesso in **Modifica origine** può interrompere il modello per la pagina, determinando la formattazione imprevista o il rendering della pagina risultante.

* Formato paragrafo

   ![](assets/chlimage_1-84.png)

   Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa da cui è selezionato il formato paragrafo.

   ![](assets/chlimage_1-85.png)

Anche il componente Testo può essere modificato in linea, ma non tutte le opzioni di formattazione sono disponibili in linea a causa di limitazioni dello spazio. Per visualizzare tutte le opzioni, passate alla modalità schermo intero.

![](assets/chlimage_1-86.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dei contenuti.

### Funzioni {#features}

![](assets/chlimage_1-28.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato dalla parola
* Trova e sostituisci
* Controllo ortografia
* Modifica dell&#39;origine

### Formattazione {#formatting}

![](assets/chlimage_1-29.png)

Le seguenti opzioni di formattazione possono essere attivate o disattivate per il componente.

* Tabella
* Elenchi
* Allineamento
* Grassetto, corsivo, sottolineato
* Collegamenti
* Sottoscript

### Stili paragrafo {#paragraph-styles}

![](assets/chlimage_1-30.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando è attivata, è possibile definire i formati consentiti.

* Toccate o fate clic sul **pulsante Aggiungi** per inserire un nuovo stile.
* Inserite il codice dello stile e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un tocco di stile o fare clic sul **pulsante Elimina** .
* Per riorganizzare l&#39;ordine dei formati toccate o fate clic e trascinate le maniglie.

### Caratteri speciali {#special-characters}

![](assets/chlimage_1-31.png)

L&#39;opzione per inserire caratteri speciali può essere attivata o disattivata per il componente. Quando è attivata, è possibile definire i caratteri consentiti.

* Toccate o fate clic sul **pulsante Aggiungi** per inserire un nuovo carattere.
* Inserite il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un tocco di caratteri o fare clic sul **pulsante Elimina** .
* Per riordinare l&#39;ordine dei caratteri toccate o fate clic e trascinate le maniglie.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Testo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
