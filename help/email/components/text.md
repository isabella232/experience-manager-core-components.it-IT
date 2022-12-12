---
title: Componente Testo e-mail
description: Il componente Testo e-mail è un componente per la modifica e la composizione come testo formattato che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '2328'
ht-degree: 100%

---


# Componente Testo e-mail {#email-text-component}

Il componente Testo e-mail è un componente per la modifica e la composizione come testo formattato che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Testo e-mail offre un efficiente editor Rich Text che consente di modificare facilmente il testo in un editor in linea semplificato e in formato a schermo intero.

* La [finestra di dialogo per la modifica](#edit-dialog) offre funzioni di modifica in linea con opzioni limitate. Le funzionalità complete sono disponibili nella finestra di dialogo di modifica a schermo intero.
* La [finestra di dialogo per la progettazione](#design-dialog) consente di configurare le opzioni di formattazione del testo, come intestazioni, caratteri speciali e stili di paragrafo, per il modello utilizzabile dall’autore del contenuto.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo e-mail è la v1, introdotta con la versione X dei Componenti core e-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, consulta il documento [Versioni dei Componenti core e-mail.](/help/email/versions.md)

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Testo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_email_text).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo e-mail [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_email_text_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Il componente Testo e-mail e l’editor Rich Text {#the-text-component-and-the-rich-text-editor}

Il componente core Testo e-mail utilizza l’editor Rich Text di AEM. L’editor Rich Text offre agli autori di contenuto un’ampia gamma di funzionalità per modificare il contenuto di testo. La configurazione dell’editor Rich Text è molto flessibile e offre diverse opzioni. Ulteriori dettagli sulla configurazione dell’editor Rich Text sono disponibili negli articoli [Configurazione dell’editor Rich Text](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html?lang=it) e [Configurazione dei plug-in dell’editor Rich Text](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=it).

Il resto di questo documento illustra la configurazione standard del componente Testo e-mail con la configurazione standard dell’editor Rich Text.

>[!NOTE]
>
>Nel componente Testo e-mail sono disponibili solo le opzioni abilitate dalle [Configurazioni dell’interfaccia utente dell’editor Rich Text](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=it).

## Finestra di dialogo per la modifica {#edit-dialog}

![Finestra di dialogo per la modifica del componente Testo](/help/email/assets/email-text-edit.png)

### Opzioni di formattazione {#options}

La finestra di dialogo per la modifica offre gli strumenti di formattazione del testo standard che l’utente si aspetta per la composizione.

#### Grassetto

![Icona Grassetto](/help/assets/text-bold.png)

Consente di applicare il grassetto al testo selezionato o al testo immesso dopo il cursore.

**Ctrl+B** può essere utilizzato come scelta rapida da tastiera.

#### Corsivo

![Icona Corsivo](/help/assets/text-italic.png)

Consente di applicare il corsivo al testo selezionato o al testo immesso dopo il cursore.

**Ctrl+I** può essere utilizzato come scelta rapida da tastiera.

#### Sottolineato

![Icona Sottolineato](/help/assets/text-underline.png)

Consente di applicare la sottolineatura al testo selezionato o al testo immesso dopo il cursore.

**Ctrl+U** può essere utilizzato come scelta rapida da tastiera.

#### Pedice

![Icona Pedice](/help/assets/text-subscript.png)

Consente di formattare come pedice il testo selezionato o il testo immesso dopo il cursore.

#### Apice

![Icona Apice](/help/assets/text-superscript.png)

Consente di formattare come apice il testo selezionato o il testo immesso dopo il cursore.

#### Incolla testo semplice

![Icona Incolla testo semplice](/help/assets/text-paste-text.png)

Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

Quando si seleziona questa opzione, viene visualizzata una finestra in cui il testo copiato può essere incollato come testo normale senza formattazione in anteprima, prima di essere effettivamente inserito nel testo. Per accettare, tocca o fai clic sul segno di spunta, per annullare tocca o fai clic sulla x.

![Incolla come esempio di testo](/help/assets/text-paste-text-example.png)

#### Incolla da Word

![Icona Incolla da Word](/help/assets/text-paste-word.png)

Quando si seleziona questa opzione, viene visualizzata una finestra in cui il testo copiato può essere incollato con la formattazione originale in anteprima, prima di essere effettivamente inserito nel testo. Per accettare, tocca o fai clic sul segno di spunta, per annullare tocca o fai clic sulla x.

![Incolla da esempio di Word](/help/assets/text-paste-word-example.png)

#### Collegamento ipertestuale

![Icona Collegamento ipertestuale](/help/assets/text-hyperlink.png)

Questa opzione consente di convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione apre una finestra contenente opzioni aggiuntive per impostare il collegamento.

![Esempio di collegamento ipertestuale](/help/assets/text-hyperlink-example.png)

* Immettere il percorso
   * Utilizza la finestra di dialogo **Apri selezione** per scegliere un percorso in AEM
   * Se il collegamento non è in AEM, utilizza l’URL assoluto
      * I percorsi non assoluti vengono interpretati come relativi ad AEM
* Immetti un testo descrittivo alternativo per il collegamento
* Seleziona il comportamento del collegamento
   * Destinazione
   * Stessa scheda
   * Nuova scheda
   * Frame principale
   * Frame superiore

Tocca o fai clic sul segno di spunta per applicare il collegamento o sulla x per annullare.

#### Scollega

![Icona Scollega](/help/assets/text-unlink.png)

Questa opzione consente di rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

#### Ancoraggio {#anchor}

![Icona ancoraggio](/help/email/assets/anchor.png)

Utilizza questa opzione per inserire un ancoraggio nel testo.

#### Trova

![Icona Trova](/help/assets/text-find.png)

Questa opzione consente di cercare nel testo l’occorrenza di una stringa di testo specificata. Selezionando questa opzione, si apre una finestra per specificare le opzioni di ricerca.

![Esempio dell’opzione Trova](/help/assets/text-find-example.png)

Inserisci il testo da cercare e tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.
Se vuoi avere una corrispondenza esatta di maiuscole/minuscole, seleziona l’opzione **Rispetta maiuscole/minuscole** prima di avviare la ricerca.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene sfumata. Tocca o fai di nuovo clic sul pulsante **Trova** nella finestra di dialogo sfumata per cercare l’occorrenza successiva.

![Esempio di occorrenza trovata](/help/assets/text-find-example-found.png)

Se non vengono trovate altre occorrenze, viene visualizzato un messaggio e la ricerca riparte dall’inizio del testo.

![Esempio di nessun’altra occorrenza trovata](/help/assets/text-find-example-found-end.png)

#### Sostituisci

![Icona Sostituisci](/help/assets/text-replace.png)

Questa opzione consente di cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un’altra stringa. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca e sostituzione.

![Esempio dell’opzione Sostituisci](/help/assets/text-replace-example.png)

Immettere il testo da cercare e il testo con cui deve essere sostituito.

* Tocca o fai clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.
* Se vuoi avere una corrispondenza esatta di maiuscole/minuscole, seleziona l’opzione **Rispetta maiuscole/minuscole** prima di avviare la ricerca.
* Seleziona **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene sfumata. Fai nuovamente clic sul pulsante **Trova** nella finestra di dialogo sfumata per cercare l’occorrenza successiva oppure seleziona il pulsante **Sostituisci** per sostituire il testo evidenziato. Il pulsante **Sostituisci** è attivo solo una volta trovata una corrispondenza.

La finestra di dialogo Trova e sostituisci diventa trasparente quando si fa clic su Trova e diventa opaca quando si fa clic su Sostituisci. Ciò consente all’autore di rivedere il testo che verrà sostituito.

>[!NOTE]
>
>Quando si utilizza la funzionalità Sostituisci, la stringa da sostituire deve essere immessa contemporaneamente alla stringa da trovare. Tuttavia, è ancora possibile fare clic su Trova per cercare la stringa prima di sostituirla. Se la stringa sostitutiva viene immessa dopo aver fatto clic su Trova, la ricerca riprende dall’inizio del testo.

#### Annulla

![Icona Annulla](/help/email/assets/undo.png)

Utilizzato per annullare l’ultima modifica nell’editor Rich Text.

#### Ripristina

![Icona Ripristina](/help/email/assets/redo.png)

Utilizzato per annullare una modifica annullata utilizzando l’icona Annulla.

#### Allineato a sinistra

![Icona Allineato a sinistra](/help/assets/text-left.png)

Consente di allineare il testo al margine sinistro.

#### Centrato

![Icona Centrato](/help/assets/text-center.png)

Consente di centrare il testo.

#### Allineato a destra

![Icona Allineato a destra](/help/assets/text-right.png)

Consente di allineare il testo al margine destro.

#### Punto elenco

![Icona Punto elenco](/help/assets/text-bullet.png)

Consente di formattare il testo selezionato come elenco puntato o di iniziare l’inserimento di un elenco puntato dopo il cursore.

Per terminare un elenco puntato, tocca o fai clic nuovamente sul pulsante **Punto elenco** oppure immetti due ritorni a capo.

#### Numero

![Icona Numero](/help/assets/text-numbered.png)

Consente di formattare il testo selezionato come elenco numerato o di iniziare l’inserimento di un elenco numerato dopo il cursore.

Per terminare un elenco numerato, tocca o fai clic nuovamente sul pulsante **Numero** oppure immetti due ritorni a capo.

#### Riduci rientro

![Icona Riduci rientro](/help/assets/text-outdent.png)

Consente di ridurre il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

L’opzione è attiva solo se il testo selezionato o la posizione del cursore è già rientrata.

#### Rientro

![Icona Rientro](/help/assets/text-indent.png)

Consente di aumentare il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

#### Tabella

![Icona Tabella](/help/assets/text-table.png)

Consente di inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

![Esempio di tabella](/help/assets/text-table-example.png)

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

#### Immagine

![Icona immagine](/help/email/assets/image-icon.png)

Utilizzato per allineare un’immagine inserita.

#### Controllo ortografico

![Icona Controllo ortografico](/help/assets/text-spellcheck.png)

Consente di verificare l’ortografia del testo. Eventuali errori di ortografia appaiono sottolineati con linee tratteggiate rosse.

Ulteriori dettagli sul controllo ortografico e sulla personalizzazione dei dizionari del controllo ortografico sono disponibili nel documento [Configurazione dei plug-in dell’editor RTF](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html?lang=it).

#### Caratteri speciali {#special-characters}

![Icona Caratteri speciali](/help/assets/text-special-characters.png)

Consente di inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

![Esempio di caratteri speciali](/help/assets/text-special-characters-example.png)

Tocca o fai clic sul carattere desiderato per inserirlo nel testo dopo il cursore. Si possono inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra per selezione.

#### Modifica origine

![Icona Modifica origine](/help/assets/text-source.png)

Consente di visualizzare e modificare l’origine HTML del testo.

Per modificare il testo dalla vista formattata, tocca o fai clic sull’icona **Modifica origine** per visualizzare il codice HTML. In questa modalità, tutte le altre opzioni di formattazione sono disabilitate. Tocca o fai clic di nuovo sull’icona **Modifica origine** per tornare alla vista formattata.

>[!CAUTION]
>
>Come sempre quando si accede al codice HTML, utilizza l’opzione **Modifica origine** con molta attenzione!
>
>Il codice HTML immesso tramite l’opzione **Modifica origine** viene analizzato per rilevare eventuali rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, il codice HTML non corretto eventualmente immesso tramite **Modifica origine** può alterare il modello della pagina, causando formattazioni impreviste e rendendo inutilizzabile la pagina risultante.

>[!NOTE]
>
>Poiché il codice HTML immesso tramite l’opzione **Modifica origine** viene analizzato per rilevare i rischi XSS e tutti gli script e rimuove automaticamente quelli trovati, il contenuto effettivo rimanente potrebbe variare rispetto a quello immesso in **Modifica origine**. Per questo motivo, per salvare le modifiche effettuate tramite **Modifica origine**, è necessario prima uscire da **Modifica origine** per visualizzare il testo nell’editor normale prima di salvarlo.

#### Formato paragrafo

![Icona Formato paragrafo](/help/assets/text-paragraph.png)

Consente di formattare come paragrafo il testo selezionato o il testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale si può selezionare il formato del paragrafo.

![Esempio di formato del paragrafo](/help/assets/text-paragraph-example.png)

#### Seleziona variabile di Adobe Campaign

![Icona Seleziona variabile di Adobe Campaign](/help/email/assets/select-adobe-campaign-variable-icon.png)

Apre la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) per inserire il contenuto dinamico da Adobe Campaign.

### Modifica in linea {#in-line-editing}

È possibile modificare anche il componente testo in linea. Per la modifica in linea, seleziona il componente Testo e-mail nella pagina del contenuto.

![Selezionare il componente Testo e-mail](/help/email/assets/email-text-select-component.png)

Quindi tocca o fai clic sull’icona **Modifica** sulla barra degli strumenti che compare sul componente. La barra degli strumenti cambia e presenta alcune opzioni per la formattazione del testo (incluso l’accesso all’opzione **Seleziona variabile di Adobe Campaign**) e puoi modificare il testo in linea.

![Esempio di modifica in linea](/help/email/assets/email-text-edit-inline-example.png)

Tocca o fai clic sul segno di spunta nella barra degli strumenti per salvare le modifiche o sulla X per eliminarle.

A causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passa alla modalità a schermo intero.

### Impostazione di un ID {#setting-id}

Questa opzione consente di controllare l’identificatore univoco del componente nell’HTM.

* Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
* Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
* La modifica dell’ID può avere un impatto sulle CSS.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dii contenuto.

### Scheda Plug-in {#plugins-tab}

La scheda **Plug-in** viene utilizzata per abilitare e disattivare varie opzioni di formattazione del testo disponibili per gli autori di contenuti.

### Funzioni {#features}

![Funzioni della finestra di dialogo per progettazione](/help/assets/text-design-features.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo semplice
* Incolla da Word
* Trova e sostituisci
* Annulla e ripristina
* Controllo ortografico
* Opzioni di modifica per le immagini inserite
* Modifica origine HTML

### Formattazione {#formatting}

![Opzione Formattazione della finestra di dialogo per progettazione](/help/assets/text-design-formatting.png)

Per il componente è possibile attivare o disattivare le seguenti opzioni di formattazione.

* Tabella
* Elenchi (punto elenco, numero, rientro, riduci rientro)
* Allineamento (a sinistra, a destra, centrato)
* Grassetto, corsivo, sottolineato
* Collegamento (e scollegamento)
* Apice/pedice

### Stili paragrafo {#paragraph-styles}

![Opzione Stili di paragrafo della finestra di dialogo per Progettazione](/help/assets/text-design-paragraph.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando l’opzione è attivata, è possibile definire i formati consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immetti il codice dello stile e una descrizione da visualizzare nella finestra di dialogo per modifica.
* Per rimuovere uno stile, tocca o fai clic sul pulsante **Elimina**.
* Per cambiare l’ordine dei formati, tocca o fai clic e trascina le maniglie.

### Caratteri speciali {#configuring-special-characters}

![Opzione Caratteri speciali della finestra di dialogo per progettazione](/help/assets/text-design-special-characters.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Quando è attivata, è possibile definire i caratteri consentiti.

* Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immetti il codice HTML del carattere e una descrizione da visualizzare nella finestra di dialogo per modifica.
* Per rimuovere un carattere, tocca o fai clic sul pulsante **Elimina**.
* Per cambiare l’ordine dei caratteri, tocca o fai clic e trascina le maniglie.

## Scheda Stili {#styles-tab}

Il componente Testo e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
