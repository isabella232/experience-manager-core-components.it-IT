---
title: Componente testo
description: Il componente Testo è un componente per la modifica e composizione di testo RTF che offre funzioni di modifica diretta.
translation-type: tm+mt
source-git-commit: 4df8e147fc9d0151c3a211473b067c78b807e52e

---


# Componente testo{#text-component}

Il componente di base Testo è un componente RTF per la modifica e la composizione di testo che supporta la modifica diretta.

## Utilizzo {#usage}

Il componente Testo offre un potente editor Rich Text che consente di modificare facilmente il testo in un editor semplificato e in linea e in un formato a schermo intero.

La finestra di dialogo [di](#edit-dialog) modifica offre funzioni di modifica in linea con opzioni limitate e funzionalità complete disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, le opzioni di formattazione del testo, come titoli, caratteri speciali e stili di paragrafo, possono essere configurate per il modello per l&#39;autore del contenuto.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](v1/text-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente di testo e per visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_text)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_text_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Il componente Testo e l’Editor Rich Text {#the-text-component-and-the-rich-text-editor}

Il componente di testo Componenti di base sfrutta l’editor Rich Text (RTE) di AEM. L’editor Rich Text offre agli autori dei contenuti un’ampia gamma di funzionalità per la modifica del contenuto testuale. L&#39;editor Rich Text è molto flessibile nella sua configurazione e offre una serie di opzioni. Per ulteriori informazioni sulla configurazione dell’editor Rich Text, consultate gli articoli [Configurare l’editor](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/rich-text-editor.html) Rich Text e [Configurare i plug-in](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html)Editor Rich Text.

Il resto di questo articolo illustra la configurazione standard del componente di testo Componenti di base con la configurazione standard dell’editor Rich Text.

>[!NOTE]
>
>Solo le opzioni abilitate dalle configurazioni [dell’interfaccia utente dell’editor Rich Text](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html) sono disponibili nel componente Testo.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti di formattazione RTF standard che l’utente si aspetta di utilizzare per comporre del testo.

![](/help/assets/screen_shot_2018-01-11at143025.png)

### Grassetto

![](/help/assets/screen_shot_2018-01-11at125602.png)

Utilizzato per applicare la formattazione in grassetto al testo selezionato o per formattare il testo in grassetto immesso dopo il cursore.

**Ctrl+B** può essere utilizzato come scelta rapida da tastiera.

### Corsivo

![](/help/assets/screen_shot_2018-01-11at125609.png)

Utilizzato per applicare la formattazione in corsivo al testo selezionato o per personalizzare il testo immesso dopo il cursore.

**Ctrl+I** può essere utilizzato come scelta rapida da tastiera.

### Sottolineato

![](/help/assets/screen_shot_2018-01-11at125615.png)

Utilizzato per applicare la formattazione sottolineata al testo selezionato o al testo sottolineato immesso dopo il cursore.

**Ctrl+U** può essere utilizzato come scelta rapida da tastiera.

### Pedice

![](/help/assets/screen_shot_2018-01-11at125703.png)

Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come pedice.

### Apice

![](/help/assets/screen_shot_2018-01-11at125708.png)

Utilizzato per formattare il testo o il testo selezionato immesso dopo il cursore come apice.

### Incolla come testo

![](/help/assets/screen_shot_2018-01-11at125713.png)

Incolla tutto il testo copiato come testo normale senza alcuna formattazione.

Quando si seleziona questa opzione, si apre una finestra in cui il testo può essere incollato come testo normale senza formattazione come anteprima prima di essere inserito nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![](/help/assets/screen_shot_2018-01-11at143234.png)

### Incolla da Word

![](/help/assets/screen_shot_2018-01-11at125717.png)

Quando si seleziona questa opzione, si apre una finestra in cui è possibile incollare il testo, mantenendo la formattazione come anteprima prima di inserirlo nel testo. Accetta toccando o facendo clic sul segno di spunta, annulla toccando o facendo clic sulla x.

![](/help/assets/screen_shot_2018-01-11at143250.png)

### Collegamento ipertestuale

![](/help/assets/screen_shot_2018-01-11at125839.png)

Utilizzare questa opzione per convertire il testo selezionato in un collegamento ipertestuale o per modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per impostare il collegamento.

![](/help/assets/screen_shot_2018-01-11at130003.png)

* Immettere la posizione
   * Utilizzare la finestra di dialogo Apri selezione per scegliere un percorso in AEM
   * Se il collegamento non si trova in AEM, inserite l’URL assoluto (i percorsi non assoluti vengono interpretati come relativi ad AEM)
* Immettere testo descrittivo alternativo per il collegamento
* Seleziona il comportamento del collegamento
   * Destinazione
   * Stessa scheda
   * Nuova scheda
   * Frame principale
   * Frame superiore
   Toccate o fate clic sul segno di spunta per applicare il collegamento o sulla x per annullare.

### Scollega

![](/help/assets/screen_shot_2018-01-11at125901.png)

Utilizzare questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato un collegamento.

### Trova

![](/help/assets/screen_shot_2018-01-11at125906.png)

Utilizzare questa opzione per cercare nel testo l&#39;occorrenza di una stringa di testo specificata. Selezionando questa opzione si apre una finestra per specificare le opzioni di ricerca.

![](/help/assets/screen_shot_2018-01-11at130107.png)

Immettere il testo per il quale si desidera eseguire la ricerca e toccare o fare clic su **Trova** per iniziare la ricerca. Toccate o fate clic sulla x per annullare.
Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Toccate o fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo attenuata per cercare l&#39;occorrenza successiva.

![](/help/assets/screen_shot_2018-01-11at130145.png)

Se non vengono trovate altre occorrenze, verrà visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

![](/help/assets/screen_shot_2018-01-11at130241.png)

### Sostituisci

![](/help/assets/screen_shot_2018-01-11at125910.png)

Utilizzare questa opzione per cercare nel testo le occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Selezionando questa opzione si apre una finestra in cui specificare le opzioni di ricerca e sostituzione.

![](/help/assets/screen_shot_2018-01-11at130441.png)

Immettere il testo per il quale si desidera eseguire la ricerca e il testo con cui sostituire il testo.

Toccate o fate clic su **Trova** per iniziare la ricerca. Tocca o fai clic sulla x per annullare.

Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l’opzione **Maiuscole/minuscole** prima di avviare la ricerca.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Fate di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattivata per cercare l&#39;occorrenza successiva oppure fate clic sul pulsante **Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Sostituisci** è attivo solo una volta raggiunta una corrispondenza.

Selezionate **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

Quando si utilizza la funzionalità replace, la stringa replace da sostituire deve essere immessa contemporaneamente alla stringa find. È comunque possibile fare clic su find per cercare la stringa prima di sostituirla. Se la stringa di sostituzione viene immessa dopo aver fatto clic su Trova, la ricerca viene reimpostata all’inizio del testo.

La finestra di dialogo Trova e sostituisci diventa trasparente quando si fa clic su Trova e diventa opaca quando si fa clic su Sostituisci. Questo consente all’autore di rivedere il testo che verrà sostituito dall’autore.

### Allinea testo a sinistra

![](/help/assets/screen_shot_2018-01-11at142012.png)

Utilizzato per allineare il testo al margine sinistro.

### Testo centrato

![](/help/assets/screen_shot_2018-01-11at142017.png)

Utilizzato per centrare il testo.

### Allinea testo a destra

![](/help/assets/screen_shot_2018-01-11at142021.png)

Utilizzato per allineare il testo al margine destro.

### Proiettile

![](/help/assets/screen_shot_2018-01-11at142025.png)

Consente di formattare il testo selezionato come elenco puntato o di iniziare l&#39;inserimento di un elenco puntato dopo il cursore.

Per terminare un elenco puntato, toccate o fate di nuovo clic sul pulsante **Bullet** oppure immettete due ritorni a capo.

### Numerato

![](/help/assets/screen_shot_2018-01-11at142030.png)

Utilizzato per formattare il testo selezionato come elenco numerato o per iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

Per terminare un elenco numerato, toccate o fate di nuovo clic sul pulsante **Numerato** oppure immettete due ritorni a capo.

### Rientro negativo

![](/help/assets/screen_shot_2018-01-11at141917.png)

Consente di ridurre il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

Attiva solo se il testo o la posizione selezionati del cursore sono già rientrati.

### Rientro

![](/help/assets/screen_shot_2018-01-11at141922.png)

Utilizzato per aumentare il livello di rientro del testo o del testo selezionato immesso dopo il cursore.

### Tabella

![](/help/assets/screen_shot_2018-01-11at141928.png)

Utilizzato per inserire una tabella nel testo. Selezionando questa opzione si apre una finestra per specificare i dettagli della tabella.

![](/help/assets/screen_shot_2018-01-11at142405.png)

* **Colonne** Il numero di colonne della tabella (obbligatorio)
* **Righe** Il numero di righe della tabella (obbligatorio)
* **Larghezza** La larghezza della tabella
* **Altezza** L&#39;altezza della tabella
* **Margine** celle Spazio intorno al contenuto della cella
* **Spaziatura** celle Lo spazio tra le celle
* **Bordo** Lo spessore delle linee dei bordi della tabella
* Se per l’intestazione della tabella:
   * La prima riga deve essere utilizzata
   * Utilizzare la prima colonna
   * Utilizzare la prima riga e la prima colonna
   * Oppure non utilizzare alcuna intestazione.
* **Didascalia** La didascalia della tabella

### Controllo ortografia

![](/help/assets/screen_shot_2018-01-11at141935.png)

Utilizzato per il controllo dell&#39;ortografia del contenuto di testo. Eventuali errori ortografici sono sottolineati con linee rosse rotte.

Ulteriori dettagli sul controllo ortografia e la personalizzazione dei dizionari di controllo ortografia sono disponibili nel documento [Configurare i plug-in](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html)Editor Rich Text.

### Caratteri speciali {#special-characters}

![](/help/assets/screen_shot_2018-01-11at142600.png)

Utilizzato per inserire caratteri speciali nel testo. Selezionando questa opzione si apre una finestra in cui vengono visualizzati i caratteri disponibili.

![](/help/assets/screen_shot_2018-01-11at142635.png)

Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Toccate o fate clic sulla x per chiudere la finestra di selezione.

### Modifica origine

![](/help/assets/screen_shot_2018-01-11at142746.png)

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

![](/help/assets/screen_shot_2018-01-11at142752.png)

Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa dal quale è selezionato il formato del paragrafo.

![](/help/assets/screen_shot_2018-01-11at142828.png)

Anche il componente di testo può essere modificato in linea, ma a causa dei limiti di spazio, non tutte le opzioni di formattazione sono disponibili in linea. Per visualizzare tutte le opzioni, passare alla modalità a schermo intero.

![](/help/assets/screen_shot_2018-01-11at142921.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Scheda Plugin {#plugins-tab}

La scheda Plugins viene utilizzata per attivare e disattivare le varie opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Funzioni {#features}

![](/help/assets/chlimage_1-28.png)

Le seguenti funzioni possono essere attivate o disattivate per il componente.

* Incolla testo normale
* Passato da parola
* Trova e sostituisci
* Controllo ortografia
* Modifica origine

### Formattazione {#formatting}

![](/help/assets/chlimage_1-29.png)

Le seguenti opzioni di formattazione possono essere attivate o disattivate per il componente.

* Tabella
* Elenchi
* Allineamento
* Grassetto, corsivo, sottolineato
* Collegamenti
* Pedice

### Stili paragrafo {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

Gli stili di paragrafo possono essere attivati o disattivati per il componente. Quando attivato, è possibile definire i formati consentiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo stile.
* Immettete il codice dello stile e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere uno stile, toccate o fate clic sul pulsante **Elimina** .
* Per ridisporre l&#39;ordine dei formati, toccate o fate clic e trascinate le maniglie.

### Configurazione di caratteri speciali {#configuring-special-characters}

![](/help/assets/chlimage_1-31.png)

L’opzione per l’inserimento di caratteri speciali può essere attivata o disattivata per il componente. Se attivati, i caratteri consentiti possono essere definiti.

* Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo carattere.
* Immettete il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un carattere toccate o fate clic sul pulsante **Elimina** .
* Per riordinare i caratteri, toccate o fate clic e trascinate le maniglie.

## Scheda Stili {#styles-tab}

Il componente Testo supporta il sistema [di](/help/get-started/authoring.md#component-styling)stile di AEM.
