---
title: Componente testo
description: Il componente Testo è un componente per la modifica e composizione di testo RTF che offre funzioni di modifica diretta.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Componente testo{#text-component}

Il componente di base Testo è un componente RTF per la modifica e la composizione di testo che supporta la modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un potente editor Rich Text che consente di modificare facilmente il testo in un editor semplificato e in linea e in un formato a schermo intero.

La finestra di dialogo [di](#edit-dialog) modifica offre funzioni di modifica in linea con opzioni limitate e funzionalità complete disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, le opzioni di formattazione del testo, come titoli, caratteri speciali e stili di paragrafo, possono essere configurate per il modello per l&#39;autore del contenuto.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/text-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente di testo e per visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_text)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_text_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Il componente Testo e l’Editor Rich Text {#the-text-component-and-the-rich-text-editor}

Il componente di testo Componenti di base sfrutta l’editor Rich Text (RTE) AEM. L’editor Rich Text offre agli autori dei contenuti un’ampia gamma di funzionalità per la modifica del contenuto testuale. L&#39;editor Rich Text è molto flessibile nella sua configurazione e offre una serie di opzioni. Per ulteriori informazioni sulla configurazione dell’editor Rich Text, consultate gli articoli [Configurare l’editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) Rich Text e [Configurare i plug-in](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)Editor Rich Text.

Il resto di questo articolo illustra la configurazione standard del componente di testo Componenti di base con la configurazione standard dell’editor Rich Text.

>[!NOTE]
>
>Solo le opzioni abilitate dalle configurazioni [dell’interfaccia utente dell’editor Rich Text](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) sono disponibili nel componente Testo.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti di formattazione RTF standard che l’utente si aspetta di utilizzare per comporre del testo.

![Finestra di dialogo di modifica del componente Testo](/help/assets/text-edit.png)

### Grassetto

![Icona Grassetto](/help/assets/text-bold.png)

Utilizzato per applicare la formattazione in grassetto al testo selezionato o per formattare il testo in grassetto immesso dopo il cursore.

**Ctrl+B** può essere utilizzato come scelta rapida da tastiera.

### Corsivo

![Icona Corsivo](/help/assets/text-italic.png)

Utilizzato per applicare la formattazione in corsivo al testo selezionato o per personalizzare il testo immesso dopo il cursore.

**Ctrl+I** può essere utilizzato come scelta rapida da tastiera.

### Sottolineato

![Icona Sottolineato](/help/assets/text-underline.png)

Utilizzato per applicare la formattazione sottolineata al testo selezionato o al testo sottolineato immesso dopo il cursore.

**Ctrl+U** può essere utilizzato come scelta rapida da tastiera.

### Pedice

![Icona Pedice](/help/assets/text-subscript.png)

Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come pedice.

### Apice

![Icona Apice](/help/assets/text-superscript.png)

Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come apice.

### Incolla come testo

![Icona Incolla come testo](/help/assets/text-paste-text.png)

Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

Quando si seleziona questa opzione, si apre una finestra in cui il testo può essere incollato come testo normale senza formattazione come anteprima prima di essere inserito nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![Incolla come esempio di testo](/help/assets/text-paste-text-example.png)

### Incolla da Word

![Icona Incolla da Word](/help/assets/text-paste-word.png)

Quando si seleziona questa opzione, si apre una finestra in cui è possibile incollare il testo, mantenendo la formattazione come anteprima prima di inserirlo nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![Incolla da esempio di Word](/help/assets/text-paste-word-example.png)

### Collegamento ipertestuale

![Icona Collegamento ipertestuale](/help/assets/text-hyperlink.png)

Utilizzare questa opzione per convertire il testo selezionato in un collegamento ipertestuale o per modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per impostare il collegamento.

![Esempio di collegamento ipertestuale](/help/assets/text-hyperlink-example.png)

* Immettere il percorso
   * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
   * Se il collegamento non è all’interno di AEM, immettete l’URL assoluto
      * I percorsi non assoluti vengono interpretati come relativi a AEM
* Immettere testo descrittivo alternativo per il collegamento
* Seleziona il comportamento del collegamento
   * Destinazione
   * Stessa scheda
   * Nuova scheda
   * Frame principale
   * Frame superiore

   Toccate o fate clic sul segno di spunta per applicare il collegamento o sulla x per annullare.

### Scollega

![Icona Scollega](/help/assets/text-unlink.png)

Utilizzare questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

### Trova

![Icona Trova](/help/assets/text-find.png)

Utilizzare questa opzione per cercare nel testo l&#39;occorrenza di una stringa di testo specificata. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca.

![Trova esempio](/help/assets/text-find-example.png)

Immettere il testo per il quale si desidera eseguire la ricerca e toccare o fare clic su **Trova** per iniziare la ricerca. Toccate o fate clic sulla x per annullare.
Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Toccate o fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo attenuata per cercare l&#39;occorrenza successiva.

![Trova esempio trovato](/help/assets/text-find-example-found.png)

Se non vengono trovate altre occorrenze, verrà visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

![Trova esempio nessun&#39;altra occorrenza](/help/assets/text-find-example-found-end.png)

### Sostituisci

![Icona Sostituisci](/help/assets/text-replace.png)

Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Selezionando questa opzione si apre una finestra in cui specificare le opzioni di ricerca e sostituzione.

![Replace example](/help/assets/text-replace-example.png)

Immettere il testo per il quale si desidera eseguire la ricerca e il testo con cui sostituire il testo.

* Toccate o fate clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.
* Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.
* Selezionate **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l&#39;occorrenza successiva oppure fate clic sul pulsante **Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Sostituisci** è attivo solo una volta raggiunta una corrispondenza.

La finestra di dialogo Trova e sostituisci diventa trasparente quando si fa clic su Trova e diventa opaca quando si fa clic su Sostituisci. Questo consente all’autore di rivedere il testo che verrà sostituito dall’autore.

>[!NOTE]
>
>Quando si utilizza la funzionalità replace, la stringa replace da sostituire deve essere immessa contemporaneamente alla stringa find. È comunque possibile fare clic su find per cercare la stringa prima di sostituirla. Se la stringa di sostituzione viene immessa dopo aver fatto clic su Trova, la ricerca viene reimpostata all’inizio del testo.


### Allinea testo a sinistra

![Allinea a sinistra, icona](/help/assets/text-left.png)

Utilizzato per allineare il testo al margine sinistro.

### Testo centrato

![Centra l&#39;icona del testo](/help/assets/text-center.png)

Utilizzato per centrare il testo.

### Allinea testo a destra

![Allinea a destra, icona](/help/assets/text-right.png)

Utilizzato per allineare il testo al margine destro.

### Proiettile

![Icona Bullet](/help/assets/text-bullet.png)

Consente di formattare il testo selezionato come elenco puntato o di iniziare l&#39;inserimento di un elenco puntato dopo il cursore.

Per terminare un elenco puntato, toccate o fate di nuovo clic sul pulsante **Bullet** oppure immettete due ritorni a capo.

### Numerato

![Icona elenco numerato](/help/assets/text-numbered.png)

Utilizzato per formattare il testo selezionato come elenco numerato o per iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

Per terminare un elenco numerato, toccate o fate di nuovo clic sul pulsante **Numerato** oppure immettete due ritorni a capo.

### Rientro negativo

![Icona Rientro](/help/assets/text-outdent.png)

Consente di ridurre il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

Attiva solo se il testo o la posizione selezionati del cursore sono già rientrati.

### Rientro

![Icona Rientro](/help/assets/text-outdent.png)

Utilizzato per aumentare il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

### Tabella

![Icona Tabella](/help/assets/text-table.png)

Utilizzato per inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

![Esempio di tabella](/help/assets/text-table-example.png)

* **Colonne** - Il numero di colonne della tabella (obbligatorio)
* **Righe** - Il numero di righe della tabella (obbligatorio)
* **Larghezza** - La larghezza della tabella
* **Altezza** - L&#39;altezza della tabella
* **Margine** celle - Spazio intorno al contenuto della cella
* **Spaziatura** celle - Spazio tra celle
* **Bordo** - Lo spessore delle linee dei bordi della tabella
   * Se per l’intestazione della tabella:
      * La prima riga deve essere utilizzata
      * Utilizzare la prima colonna
      * Utilizzare la prima riga e la prima colonna
      * Oppure non utilizzare alcuna intestazione.
* **Didascalia** - La didascalia della tabella

### Controllo ortografia

![Icona Controllo ortografia](/help/assets/text-spellcheck.png)

Utilizzato per il controllo dell&#39;ortografia del contenuto di testo. Eventuali errori ortografici sono sottolineati con linee rosse rotte.

Ulteriori dettagli sul controllo ortografia e la personalizzazione dei dizionari di controllo ortografia sono disponibili nel documento [Configurare i plug-in](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)Editor Rich Text.

### Caratteri speciali {#special-characters}

![Icona caratteri speciali](/help/assets/text-special-characters.png)

Utilizzato per inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

![Esempio di caratteri speciali](/help/assets/text-special-characters-example.png)

Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Toccate o fate clic sulla x per chiudere la finestra di selezione.

### Modifica origine

![Icona modifica sorgente](/help/assets/text-source.png)

Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

Toccate o fate clic sull’icona Modifica **** sorgente per cambiare il contenuto del testo dalla visualizzazione formattata per visualizzare l’HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disattivate. Toccate o fate di nuovo clic sull’icona **Sorgente modifica** per tornare alla visualizzazione formattata.

>[!CAUTION]
>
>Come sempre con l&#39;accesso a HTML non elaborato, occorre prestare attenzione quando si utilizza l&#39;opzione di modifica **** origine!
>
>L&#39;HTML immesso tramite Modifica **** origine viene analizzato per rilevare i rischi XSS e gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, l’HTML con formato non corretto immesso in **Modifica** origine può interrompere il modello per la pagina, dando luogo a una formattazione imprevista o rendendo la pagina risultante inutilizzabile.

>[!NOTE]
>
>Poiché l&#39;HTML immesso tramite **Source Edit** (Modifica **origine) è sottoposto a scansione per individuare rischi XSS e per rimuovere automaticamente quelli trovati, il contenuto effettivo persistente può variare da quello immesso in** Source Edit (Modificaorigine). Per questo motivo, per salvare le modifiche effettuate tramite Modifica **** sorgente, prima di salvare è necessario uscire da Modifica **** sorgente per visualizzare il testo nell’editor normale.

### Formato paragrafo

![Icona formato paragrafo](/help/assets/text-paragraph.png)

Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale è selezionato il formato del paragrafo.

![Esempio di formato paragrafo](/help/assets/text-paragraph-example.png)

### Modifica in linea {#in-line-editing}

Anche il componente di testo può essere modificato in linea, ma a causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passare alla modalità a schermo intero.

![Esempio di modifica in linea](/help/assets/text-edit-inline-example.png)

### Impostazione e ID {#setting-id}

Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Scheda Plugin {#plugins-tab}

La scheda Plugins viene utilizzata per attivare e disattivare le varie opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Funzioni {#features}

![Funzioni della finestra di dialogo Progettazione](/help/assets/text-design-features.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato da parola
* Trova e sostituisci
* Controllo ortografia
* Opzioni di modifica delle immagini inserite
* Modifica sorgente HTML

### Formattazione {#formatting}

![Formattazione della finestra di dialogo Progettazione](/help/assets/text-design-formatting.png)

Le seguenti opzioni di formattazione possono essere attivate o disattivate per il componente.

* Tabella
* Elenchi (elenco, numero, rientro, rientro)
* Allineamento (sinistra, destra, centrato)
* Grassetto, corsivo, sottolineato
* Collegamento (e scollegamento)
* Pedice

### Stili paragrafo {#paragraph-styles}

![Finestra di dialogo Progettazione, stili di paragrafo](/help/assets/text-design-paragraph.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando attivato, è possibile definire i formati consentiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immettete il codice dello stile e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere uno stile, toccate o fate clic sul pulsante **Elimina** .
* Per ridisporre l&#39;ordine dei formati, toccate o fate clic e trascinate le maniglie.

### Caratteri speciali {#configuring-special-characters}

![Caratteri speciali della finestra di dialogo Progettazione](/help/assets/text-design-special-characters.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Se attivati, i caratteri consentiti possono essere definiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immettete il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un carattere toccate o fate clic sul pulsante **Elimina** .
* Per riordinare i caratteri, toccate o fate clic e trascinate le maniglie.

## Scheda Stili {#styles-tab}

Il componente Testo supporta il sistema [](/help/get-started/authoring.md#component-styling)di stile AEM.
