---
title: Componente testo
seo-title: Componente testo
description: Il componente Testo è un componente RTF che consente di modificare e comporre in locale le funzioni di modifica locale.
seo-description: Il componente Testo è un componente RTF che consente di modificare e comporre in locale le funzioni di modifica locale.
uuid: 5 f 8 eee 8 f -7317-4712-a 77 f-e 34 e 8 a 024187
contentOwner: Utente
content-type: riferimento
topic-tags: componenti core
discoiquuid: 9 a 290584-565 e -4392-999 c -999 ee 4 a 93 da 1
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente testo{#text-component}

Il componente Testo componente core è un componente Rich Text che consente di modificare e comporre le funzioni locali.

## Utilizzo {#usage}

Il componente Testo offre un editor Rich Text affidabile che semplifica la modifica del testo in un editor in linea, in-line e a schermo intero.

La [finestra di dialogo](#edit-dialog) di modifica presenta funzioni di modifica in linea con opzioni limitate, disponibili nella finestra di dialogo di modifica a schermo intero. Utilizzando la [finestra di dialogo di progettazione](#design-dialog), le opzioni di formattazione del testo quali le intestazioni, i caratteri speciali e gli stili di paragrafo possono essere configurate per il modello relativo all&#39;autore del contenuto.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Testo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](text-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-27.png)

### Libreria componenti

Per provare il componente Testo e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/text.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Testo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Componente Testo e Editor Rich Text {#the-text-component-and-the-rich-text-editor}

Il componente Testo componenti core sfrutta l&#39;editor Rich Text (Rich Text Editor) di AEM. L&#39;editor Rich Text offre agli autori dei contenuti un&#39;ampia gamma di funzionalità per modificare il contenuto del testo. L&#39;editor Rich Text è molto flessibile nella configurazione e offre diverse opzioni. Ulteriori dettagli su come l&#39;editor Rich Text può essere configurato negli articoli [Configurate l&#39;Editor Rich Text](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/rich-text-editor.html) e [Configurate i plug-in Editor Rich Text](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

Il resto di questo articolo illustra la configurazione standard del componente Testo componenti core con la configurazione RTE out-of-the-box.

>[!NOTE]
>
>Nel componente Testo sono disponibili solo le opzioni abilitate dalle [configurazioni dell&#39;interfaccia utente dell&#39;editor Rich Text](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-5/sites/administering/using/rich-text-editor.html) .

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica offre gli strumenti standard di formattazione RTF che l&#39;utente dovrà comporre.

![](assets/screen_shot_2018-01-11at143025.png)

### Grassetto

![](assets/screen_shot_2018-01-11at125602.png)

Utilizzato per applicare la formattazione in grassetto al testo selezionato o in formato grassetto, inserito dopo il cursore.

**Ctrl + B** può essere usato come scelta rapida da tastiera.

### Corsivo

![](assets/screen_shot_2018-01-11at125609.png)

Utilizzato per applicare la formattazione in corsivo al testo selezionato o in corsivo, inserito dopo il cursore.

**Ctrl + I** Può essere usato come scelta rapida da tastiera.

### Sottolineato

![](assets/screen_shot_2018-01-11at125615.png)

Utilizzato per applicare la formattazione sottolineata al testo selezionato o sottolineare il testo inserito dopo il cursore.

**Ctrl + U** può essere usato come scelta rapida da tastiera.

### Pedice

![](assets/screen_shot_2018-01-11at125703.png)

Utilizzato per formattare il testo selezionato o il testo immesso dopo il cursore come pedice.

### Apice

![](assets/screen_shot_2018-01-11at125708.png)

Utilizzato per formattare il testo selezionato o il testo immesso dopo il cursore come apice.

### Incolla come testo

![](assets/screen_shot_2018-01-11at125713.png)

Incolla qualsiasi testo copiato come testo normale senza formattazione.

Quando si seleziona questa opzione, si apre una finestra in cui il testo può essere incollato come testo normale senza formattazione prima che venga inserito nel testo. Accettate toccando o facendo clic sul segno di spunta, toccando o facendo clic sulla x.

![](assets/screen_shot_2018-01-11at143234.png)

### Incolla da Word

![](assets/screen_shot_2018-01-11at125717.png)

Quando si seleziona questa opzione, si apre una finestra in cui si può incollarne la formattazione come anteprima prima che venga inserita nel testo. Accettate toccando o facendo clic sul segno di spunta, toccando o facendo clic sulla x.

![](assets/screen_shot_2018-01-11at143250.png)

### Collegamento ipertestuale

![](assets/screen_shot_2018-01-11at125839.png)

Utilizzate questa opzione per convertire il testo selezionato in un collegamento ipertestuale o modificare un collegamento già definito. Questa opzione è attiva solo quando il testo è già selezionato e apre una finestra con opzioni aggiuntive per l&#39;impostazione del collegamento.

![](assets/screen_shot_2018-01-11at130003.png)

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

### Scollega

![](assets/screen_shot_2018-01-11at125901.png)

Utilizzate questa opzione per rimuovere un collegamento già applicato al testo selezionato. Questa opzione è attiva solo quando un collegamento è già selezionato.

### Trova

![](assets/screen_shot_2018-01-11at125906.png)

Utilizzare questa opzione per cercare il testo per l&#39;occorrenza di una stringa di testo specificata. Selezionate questa opzione per aprire una finestra che consente di specificare le opzioni di ricerca.

![](assets/screen_shot_2018-01-11at130107.png)

Inserite il testo per il quale desiderate cercare e toccate o fate clic su **Trova** per avviare la ricerca. Toccate o fate clic sul x per annullare.
Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l&#39;opzione **Corrispondenza maiuscole/minuscole** prima di avviare la ricerca.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Toccate o fate clic nuovamente sul **pulsante Trova** nella finestra di dialogo disattiva per cercare l&#39;occorrenza successiva.

![](assets/screen_shot_2018-01-11at130145.png)

Se non vengono trovate occorrenze aggiuntive, viene visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

![](assets/screen_shot_2018-01-11at130241.png)

### Sostituisci

![](assets/screen_shot_2018-01-11at125910.png)

Utilizzare questa opzione per cercare il testo per occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Se selezionate questa opzione, viene aperta una finestra che consente di specificare le opzioni di ricerca e sostituzione.

![](assets/screen_shot_2018-01-11at130441.png)

Inserite il testo da cercare e il testo da sostituire.

Tocca o fai clic su **Trova** per avviare la ricerca. Tocca o fai clic sul segno x per annullare.

Se desiderate eseguire una corrispondenza esatta in base al caso, selezionate l&#39;opzione **Corrispondenza maiuscole/minuscole** prima di avviare la ricerca.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Fare di nuovo clic sul pulsante **Trova** nella finestra di dialogo disattiva per cercare l&#39;occorrenza successiva o fare clic sul **pulsante Sostituisci** per sostituire il testo evidenziato e corrispondente. Il pulsante **Sostituisci** è attivo solo quando viene effettuata una corrispondenza.

Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del testo contemporaneamente.

### Allinea testo a sinistra

![](assets/screen_shot_2018-01-11at142012.png)

Utilizzato per allineare il testo al margine sinistro.

### Testo centrato

![](assets/screen_shot_2018-01-11at142017.png)

Utilizzato per centrare il testo.

### Allinea testo a destra

![](assets/screen_shot_2018-01-11at142021.png)

Utilizzato per allineare il testo al margine destro.

### Proiettile

![](assets/screen_shot_2018-01-11at142025.png)

Utilizzato per formattare il testo selezionato come elenco puntato o iniziare l&#39;inserimento di un elenco puntato dopo il cursore.

Per terminare un elenco puntato, toccate o fate di nuovo clic sul pulsante **Bullet** oppure immettete due ritorni a capo.

### Numerato

![](assets/screen_shot_2018-01-11at142030.png)

Utilizzato per formattare il testo selezionato come elenco numerato o iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

Per terminare un elenco numerato, toccare o fare di nuovo clic sul pulsante **Numerato** oppure immettere due ritorni a capo.

### Rientro negativo

![](assets/screen_shot_2018-01-11at141917.png)

Utilizzato per diminuire il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

Attivo solo se il testo o la posizione selezionati del cursore è già rientrato.

### Rientro

![](assets/screen_shot_2018-01-11at141922.png)

Utilizzato per aumentare il livello di rientro del testo selezionato o del testo immesso dopo il cursore.

### Tabella

![](assets/screen_shot_2018-01-11at141928.png)

Utilizzato per inserire una tabella nel testo. Quando si seleziona questa opzione si apre una finestra per specificare i dettagli della tabella.

![](assets/screen_shot_2018-01-11at142405.png)

* **Colonne**
Il numero di colonne della tabella (obbligatorio)
* **Righe**
Il numero di righe della tabella (obbligatorio)
* **Larghezza Larghezza**
della tabella
* **Altezza**:
altezza della tabella
* **Spaziatura**
celle Intorno al contenuto della cella
* **Spaziatura**
celle Spazio tra celle
* **Bordo**:
spessore delle linee dei bordi della tabella
* Se per l&#39;intestazione della tabella:
   * La prima riga deve essere utilizzata
   * La prima colonna deve essere utilizzata
   * È necessario utilizzare la prima riga e la prima colonna
   * Oppure non è necessario utilizzare nessuna intestazione.
* **Didascalia**:
didascalia della tabella

### Controllo ortografia

![](assets/screen_shot_2018-01-11at141935.png)

Utilizzato per controllare l&#39;ortografia del contenuto del testo. I possibili errori ortografici sono sottolineati con linee rosse interrotte.

Ulteriori dettagli sul controllo ortografia e la personalizzazione dei dizionari controllo ortografia sono disponibili nel documento [Configura i plug-in Editor Rich Text](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

### Caratteri speciali {#special-characters}

![](assets/screen_shot_2018-01-11at142600.png)

Utilizzato per inserire caratteri speciali nel testo. Quando selezionate questa opzione, viene aperta una finestra in cui vengono visualizzati i caratteri disponibili.

![](assets/screen_shot_2018-01-11at142635.png)

Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra di selezione.

### Modifica origine

![](assets/screen_shot_2018-01-11at142746.png)

Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

Toccate o fate clic sull&#39; **icona Modifica** sorgente per modificare il contenuto del testo dalla visualizzazione formattata per visualizzare l&#39;HTML non elaborato. In questa modalità, tutte le altre opzioni di formattazione sono disattivate. Toccate o fate di nuovo **clic sull&#39;icona Modifica** sorgente per tornare alla visualizzazione formattata.

>[!CAUTION]
>
>Come sempre con l&#39;accesso all&#39;HTML non elaborato, l&#39;attenzione deve essere esercitata quando si utilizza l&#39; **opzione Modifica** origine.
>
>Il codice HTML immesso tramite **Modifica** origine viene analizzato per i rischi XSS e tutti gli script inseriti vengono rimossi e non verranno visualizzati nella pagina risultante. Tuttavia, l&#39;HTML corrotto immesso in **Modifica origine** può interrompere il modello per la pagina, determinando la formattazione imprevista o il rendering della pagina risultante.

>[!NOTE]
>
>Poiché HTML immesso tramite **Modifica origine** viene analizzato per i rischi XSS ed eventuali script e rimuove quelli rilevati, il contenuto effettivo persistente può variare rispetto a quanto è stato immesso in **Modifica origine**. Per salvare le modifiche effettuate utilizzando Modifica **origine**, dovete prima uscire da Modifica **sorgente** per visualizzare il testo nell&#39;editor normale prima di salvare.

### Formato paragrafo

![](assets/screen_shot_2018-01-11at142752.png)

Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa da cui è selezionato il formato paragrafo.

![](assets/screen_shot_2018-01-11at142828.png)

Anche il componente Testo può essere modificato in linea, ma non tutte le opzioni di formattazione sono disponibili in linea a causa di limitazioni dello spazio. Per visualizzare tutte le opzioni, passate alla modalità schermo intero.

![](assets/screen_shot_2018-01-11at142921.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dei contenuti.

### Scheda Plug-in {#plugins-tab}

La scheda Plug-in consente di abilitare e disabilitare diverse opzioni di formattazione del testo disponibili per gli autori di contenuto.

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

### Configurazione di caratteri speciali {#configuring-special-characters}

![](assets/chlimage_1-31.png)

L&#39;opzione per inserire caratteri speciali può essere attivata o disattivata per il componente. Quando è attivata, è possibile definire i caratteri consentiti.

* Toccate o fate clic sul **pulsante Aggiungi** per inserire un nuovo carattere.
* Inserite il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* Per rimuovere un tocco di caratteri o fare clic sul **pulsante Elimina** .
* Per riordinare l&#39;ordine dei caratteri toccate o fate clic e trascinate le maniglie.

## Scheda Stili {#styles-tab}

Il componente Testo supporta il sistema [di stile AEM](authoring.md#component-styling).