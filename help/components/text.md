---
title: Componente testo
description: Il componente Testo è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '2218'
ht-degree: 4%

---


# Componente testo{#text-component}

Il componente di testo del componente di base è un componente per la modifica e la composizione di testo RTF che supporta la modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un robusto editor Rich Text che consente di modificare facilmente il testo in un editor semplificato e in linea e in un formato a schermo intero.

La [finestra di dialogo di modifica](#edit-dialog) presenta funzioni di modifica in linea con opzioni limitate e funzionalità complete disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la finestra di dialogo di progettazione [progettazione](#design-dialog), è possibile configurare per il modello per l’autore del contenuto le opzioni di formattazione del testo quali intestazioni, caratteri speciali e stili di paragrafo.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di testo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/text-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente testo e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_text) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di testo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_text_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Il componente Testo e l’ Editor Rich Text {#the-text-component-and-the-rich-text-editor}

Il componente Testo dei componenti core sfrutta l’Editor Rich Text AEM . L’editor Rich Text offre agli autori di contenuti diverse funzionalità per modificare il contenuto del testo. L’editor Rich Text è molto flessibile nella sua configurazione e offre diverse opzioni. Ulteriori dettagli sulla configurazione dell’editor Rich Text sono disponibili negli articoli [Configurare l’editor Rich Text](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) e [Configurare i plug-in dell’editor Rich Text](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

Il resto di questo articolo illustra la configurazione standard del componente di testo per componenti core con la configurazione standard dell’editor Rich Text.

>[!NOTE]
>
>Solo le opzioni abilitate dalle [configurazioni dell’interfaccia utente dell’editor Rich Text](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) sono disponibili nel componente di testo.

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti di formattazione RTF standard che un utente si aspetta di utilizzare per comporre il testo.

![Finestra di dialogo di modifica del componente testo](/help/assets/text-edit.png)

### Grassetto

![Icona Grassetto](/help/assets/text-bold.png)

Utilizzato per applicare la formattazione in grassetto al testo selezionato o al testo in formato grassetto immesso dopo il cursore.

**Ctrl+** Bè può essere utilizzato come scelta rapida da tastiera.

### Corsivo

![Icona corsivo](/help/assets/text-italic.png)

Consente di applicare la formattazione in corsivo al testo selezionato o di applicare il corsivo al testo immesso dopo il cursore.

**Ctrl+** I può essere utilizzato come scelta rapida da tastiera.

### Sottolineato

![Icona Sottolineato](/help/assets/text-underline.png)

Utilizzato per applicare la formattazione sottolineata al testo selezionato o al testo sottolineato immesso dopo il cursore.

**Ctrl+** Non può essere utilizzato come scelta rapida da tastiera.

### Pedice

![Icona pedice](/help/assets/text-subscript.png)

Utilizzato per formattare come pedice il testo o il testo selezionato immesso dopo il cursore.

### Apice

![Icona a forma di apice](/help/assets/text-superscript.png)

Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come apice.

### Incolla come testo

![Icona Incolla come testo](/help/assets/text-paste-text.png)

Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

Quando si seleziona questa opzione viene visualizzata una finestra in cui il testo può essere incollato come testo normale senza formattazione come anteprima prima di essere inserito nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![Incolla come esempio di testo](/help/assets/text-paste-text-example.png)

### Incolla da Word

![Icona Incolla da Word](/help/assets/text-paste-word.png)

Quando si seleziona questa opzione viene visualizzata una finestra in cui è possibile incollare il testo mantenendo la formattazione come anteprima prima di inserirla nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![Incolla da esempio di Word](/help/assets/text-paste-word-example.png)

### Collegamento ipertestuale

![Icona Collegamento ipertestuale](/help/assets/text-hyperlink.png)

Utilizzare questa opzione per convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per l’impostazione del collegamento.

![Esempio di collegamento ipertestuale](/help/assets/text-hyperlink-example.png)

* Immettere il percorso
   * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
   * Se il collegamento non si trova all’interno di AEM, immetti l’URL assoluto
      * I percorsi non assoluti vengono interpretati come relativi a AEM
* Inserisci un testo descrittivo alternativo per il collegamento
* Selezionare il comportamento del collegamento
   * Target
   * Stessa scheda
   * Nuova scheda
   * Frame principale
   * Frame superiore

   Tocca o fai clic sul segno di spunta per applicare il collegamento o la x da annullare.

### Scollega

![Icona Scollega](/help/assets/text-unlink.png)

Utilizzare questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

### Trova

![Icona Trova](/help/assets/text-find.png)

Utilizzare questa opzione per cercare nel testo l&#39;occorrenza di una stringa di testo specificata. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca.

![Trova esempio](/help/assets/text-find-example.png)

Inserisci il testo per il quale vuoi cercare e tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.
Se desideri eseguire una corrispondenza esatta in base al caso, seleziona l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene oscurata. Tocca o fai di nuovo clic sul pulsante **Trova** nella finestra di dialogo oscura per cercare l&#39;occorrenza successiva.

![Trova esempio trovato](/help/assets/text-find-example-found.png)

Se non vengono trovate altre occorrenze, verrà visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

![Trova esempio nessun&#39;altra occorrenza](/help/assets/text-find-example-found-end.png)

### Sostituisci

![Icona Sostituisci](/help/assets/text-replace.png)

Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca e sostituzione.

![Sostituisci esempio](/help/assets/text-replace-example.png)

Immettere il testo per il quale si desidera eseguire la ricerca e il testo con cui deve essere sostituito.

* Tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.
* Se desideri eseguire una corrispondenza esatta in base al caso, seleziona l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.
* Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene oscurata. Fai nuovamente clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l&#39;occorrenza successiva oppure seleziona il pulsante **Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Replace** è attivo solo una volta effettuata una corrispondenza.

La finestra di dialogo trova e sostituisci diventa trasparente quando si fa clic su trova e diventa opaca quando si fa clic su sostituisci. Questo consente all’autore di rivedere il testo che verrà sostituito dall’autore.

>[!NOTE]
>
>Quando si utilizza la funzionalità di sostituzione, la stringa di sostituzione da sostituire deve essere immessa contemporaneamente alla stringa di ricerca. Tuttavia è ancora possibile fare clic su trova per cercare la stringa prima di sostituirla. Se la stringa di sostituzione viene immessa dopo aver fatto clic su trova, la ricerca viene reimpostata all’inizio del testo.


### Allinea testo a sinistra

![Icona Allinea a sinistra](/help/assets/text-left.png)

Utilizzato per allineare il testo al margine sinistro.

### Testo centrato

![Icona Testo centrato](/help/assets/text-center.png)

Utilizzato per centrare il testo.

### Allinea testo a destra

![Icona Allinea a destra](/help/assets/text-right.png)

Utilizzato per allineare il testo al margine destro.

### Proiettile

![Icona punto elenco](/help/assets/text-bullet.png)

Consente di formattare il testo selezionato come elenco puntato o di iniziare l’inserimento di un elenco puntato dopo il cursore.

Per terminare un elenco puntato, toccare o fare clic nuovamente sul pulsante **Bullet** oppure immettere due ritorni a capo.

### Numerato

![Icona Elenco numerato](/help/assets/text-numbered.png)

Consente di formattare il testo selezionato come elenco numerato o di iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

Per terminare un elenco numerato, toccare o fare clic nuovamente sul pulsante **Numbered** oppure immettere due ritorni a capo.

### Rientro negativo

![Icona Outright](/help/assets/text-outdent.png)

Consente di ridurre il livello di rientro del testo o del testo selezionato dopo il cursore.

Attiva solo se il testo o la posizione selezionata del cursore sono già rientrati.

### Rientro

![Icona Rientro](/help/assets/text-outdent.png)

Consente di aumentare il livello di rientro del testo o del testo selezionato dopo il cursore.

### Tabella

![Icona Tabella](/help/assets/text-table.png)

Utilizzato per inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

![Esempio di tabella](/help/assets/text-table-example.png)

* **Colonne**  - Il numero di colonne della tabella (obbligatorio)
* **Righe**  - Il numero di righe della tabella (obbligatorio)
* **Larghezza**  - Larghezza della tabella
* **Altezza**  - Altezza della tabella
* **Margine celle** : lo spazio intorno al contenuto di una cella
* **Spaziatura**  celle: lo spazio tra le celle
* **Bordo** : il peso delle linee dei bordi della tabella
   * Se per l’intestazione della tabella:
      * La prima riga deve essere utilizzata
      * Utilizzare la prima colonna
      * Utilizzare la prima riga e la prima colonna
      * Oppure non utilizzare alcuna intestazione.
* **Didascalia** : la didascalia della tabella

### Controllo ortografia

![Icona Controllo ortografia](/help/assets/text-spellcheck.png)

Utilizzato per controllare l’ortografia del contenuto di testo. Eventuali errori di ortografia sono sottolineati con linee rosse rotte.

Ulteriori dettagli sul controllo ortografico e sulla personalizzazione dei dizionari del controllo ortografico sono disponibili nel documento [Configurare i plug-in dell’editor Rich Text](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

### Caratteri speciali {#special-characters}

![Icona dei caratteri speciali](/help/assets/text-special-characters.png)

Utilizzato per inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

![Esempio di caratteri speciali](/help/assets/text-special-characters-example.png)

Tocca o fai clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra di selezione.

### Modifica origine

![Icona di modifica sorgente](/help/assets/text-source.png)

Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

Tocca o fai clic sull&#39;icona **Modifica origine** per modificare il contenuto del testo dalla visualizzazione formattata per visualizzare l&#39;HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disabilitate. Tocca o fai di nuovo clic sull&#39;icona **Modifica origine** per tornare alla visualizzazione formattata.

>[!CAUTION]
>
>Come sempre per l&#39;accesso all&#39;HTML non elaborato, è necessario prestare attenzione quando si utilizza l&#39;opzione **Modifica origine**!
>
>Il codice HTML immesso tramite **Modifica origine** viene analizzato per rilevare i rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, il codice HTML non corretto immesso in **Modifica origine** può interrompere il modello per la pagina, dando luogo a una formattazione o a un rendering imprevisti della pagina risultante inutilizzabile.

>[!NOTE]
>
>Poiché l&#39;HTML immesso tramite **Modifica origine** viene analizzato per rilevare i rischi XSS e tutti gli script e rimuove automaticamente quelli trovati, il contenuto effettivo persistente può variare da quello immesso in **Modifica origine**. Per questo motivo, per salvare le modifiche effettuate utilizzando **Modifica origine**, è necessario prima uscire **Modifica origine** per visualizzare il testo nell&#39;editor normale prima di salvare.

### Formato paragrafo

![Icona del formato paragrafo](/help/assets/text-paragraph.png)

Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale è selezionato il formato del paragrafo.

![Esempio di formato paragrafo](/help/assets/text-paragraph-example.png)

### Modifica in linea {#in-line-editing}

È possibile modificare anche il componente testo in linea, ma a causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passa alla modalità a schermo intero.

![Esempio di modifica in linea](/help/assets/text-edit-inline-example.png)

### Impostazione e ID {#setting-id}

Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dei contenuti.

### Scheda Plug-in {#plugins-tab}

La scheda Plugins viene utilizzata per abilitare e disabilitare varie opzioni di formattazione del testo disponibili per gli autori di contenuti.

### Funzioni {#features}

![Funzioni della finestra di dialogo Progettazione](/help/assets/text-design-features.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato dalla parola
* Trova e sostituisci
* Controllo ortografia
* Opzioni di modifica dell’immagine inserita
* Modifica sorgente HTML

### Formattazione {#formatting}

![Formattazione della finestra di dialogo Progettazione](/help/assets/text-design-formatting.png)

Per il componente è possibile attivare o disattivare le seguenti opzioni di formattazione.

* Tabella
* Elenchi (punto elenco, numero, rientro, rientro)
* Allineamento (a sinistra, a destra, centrato)
* Grassetto, corsivo, sottolineato
* Collegamento (e scollegamento)
* Sottoscritto

### Stili paragrafo {#paragraph-styles}

![Stili di paragrafo della finestra di dialogo Progettazione](/help/assets/text-design-paragraph.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando è attivata, è possibile definire i formati consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immetti il codice dello stile e una descrizione da visualizzare nella finestra di dialogo di modifica.
* Per rimuovere uno stile, tocca o fai clic sul pulsante **Elimina** .
* Per ridisporre l’ordine dei formati, tocca o fai clic e trascina le maniglie.

### Caratteri speciali {#configuring-special-characters}

![Caratteri speciali della finestra di dialogo Progettazione](/help/assets/text-design-special-characters.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Quando sono attivati, è possibile definire i caratteri consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immetti il codice HTML del carattere e una descrizione da visualizzare nella finestra di dialogo di modifica.
* Per rimuovere un carattere, tocca o fai clic sul pulsante **Elimina** .
* Per ridisporre l’ordine dei caratteri, tocca o fai clic e trascina le maniglie.

## Scheda Stili {#styles-tab}

Il componente Testo supporta il AEM [sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Testo supporta il [Livello dati client Adobe.](/help/developing/data-layer/overview.md)
