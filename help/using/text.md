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
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente testo{#text-component}

Il componente Testo componente core è un componente Rich Text che consente di modificare e comporre le funzioni locali.

## Utilizzo {#usage}

Il componente Testo offre un editor Rich Text affidabile che semplifica la modifica del testo in un editor in linea, in-line e a schermo intero.

The [edit dialog](#edit-dialog) features in-line editing with limited options with full functionality available in the full-screen edit dialog. Using the [design dialog](#design-dialog), text formatting options such as headings, special characters, and paragraph styles can be configured for the template for the content author.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Testo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](text-v1.md) | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Text Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/text.html).

### Technical Details {#technical-details}

The latest technical documentation about the Text Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## The Text Component and the Rich Text Editor {#the-text-component-and-the-rich-text-editor}

Il componente Testo componenti core sfrutta l&#39;editor Rich Text (Rich Text Editor) di AEM. L&#39;editor Rich Text offre agli autori dei contenuti un&#39;ampia gamma di funzionalità per modificare il contenuto del testo. L&#39;editor Rich Text è molto flessibile nella configurazione e offre diverse opzioni. Further details about how the RTE can be configured can be found in the articles [Configure the Rich Text Editor](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/rich-text-editor.html) and [Configure the Rich Text Editor plug-ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

Il resto di questo articolo illustra la configurazione standard del componente Testo componenti core con la configurazione RTE out-of-the-box.

>[!NOTE]
>
>Only options enabled by [UI configurations of the RTE](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-5/sites/administering/using/rich-text-editor.html) are available by in the Text Component.

## Edit Dialog {#edit-dialog}

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

Enter the text for which you want to search and tap or click **Find** to begin the search. Toccate o fate clic sul x per annullare.
If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.
Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Tap or click the **Find** button again in the dimmed dialog to search for the next occurrence.

![](assets/screen_shot_2018-01-11at130145.png)

Se non vengono trovate occorrenze aggiuntive, viene visualizzato un messaggio e la ricerca verrà riavviata dall&#39;inizio del testo.

![](assets/screen_shot_2018-01-11at130241.png)

### Sostituisci

![](assets/screen_shot_2018-01-11at125910.png)

Utilizzare questa opzione per cercare il testo per occorrenze di una stringa di testo specificata e sostituire le corrispondenze con un&#39;altra stringa. Se selezionate questa opzione, viene aperta una finestra che consente di specificare le opzioni di ricerca e sostituzione.

![](assets/screen_shot_2018-01-11at130441.png)

Inserite il testo da cercare e il testo da sostituire.

Tap or click **Find** to begin the search. Tocca o fai clic sul segno x per annullare.

If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.

Se viene trovata una corrispondenza, questa viene evidenziata e la finestra di dialogo di ricerca viene disattivata. Click the **Find** button again in the dimmed dialog to search for the next occurrence or select the **Replace** button to replace the highlighted, matched text. Note that the **Replace** button is only active once a match is made.

Select **Replace all** to replace all occurrences of the text at once.

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

To end a bulleted list, tap or click the **Bullet** button again or enter two carriage returns.

### Numerato

![](assets/screen_shot_2018-01-11at142030.png)

Utilizzato per formattare il testo selezionato come elenco numerato o iniziare l&#39;inserimento di un elenco numerato dopo il cursore.

To end a numbered list, tap or click the **Numbered** button again or enter two carriage returns.

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

Further details about spell checking and customizing spell check dictionaries can be found in the document [Configure the Rich Text Editor Plug-Ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

### Caratteri speciali {#special-characters}

![](assets/screen_shot_2018-01-11at142600.png)

Utilizzato per inserire caratteri speciali nel testo. Quando selezionate questa opzione, viene aperta una finestra in cui vengono visualizzati i caratteri disponibili.

![](assets/screen_shot_2018-01-11at142635.png)

Toccate o fate clic sul carattere desiderato per inserirlo nel testo dopo il cursore. È possibile inserire più caratteri. Tocca o fai clic sulla x per chiudere la finestra di selezione.

### Modifica origine

![](assets/screen_shot_2018-01-11at142746.png)

Utilizzato per visualizzare e modificare l&#39;origine HTML del testo.

Tap or click the **Source Edit** icon to change the content of the text from the formatted view to view the raw HTML. In questa modalità, tutte le altre opzioni di formattazione sono disattivate. Tap or click the **Source Edit** icon again to return to the formatted view.

>[!CAUTION]
>
>As always the case with access to raw HTML, care must be exercised when using the **Source Edit** option!
>
>HTML entered via **Source Edit** is scanned for XSS risks and any scripts that are inserted are removed and will not appear on the resulting page. However malformed HTML entered in **Source Edit** can break the template for the page resulting in unexpected formatting or rendering the resulting page unusable.

>[!NOTE]
>
>Because HTML entered via **Source Edit** is scanned for XSS risks and any scripts and automatically removes those found, the actual content persisted may vary from what was entered in **Source Edit**. For this reason, in order to save changes made using **Source Edit**, you must first exit **Source Edit** to view the text in the normal editor before saving.

### Formato paragrafo

![](assets/screen_shot_2018-01-11at142752.png)

Utilizzato per applicare la formattazione del paragrafo al testo selezionato o al testo inserito dopo il cursore. Selezionando questa opzione si apre un menu a discesa da cui è selezionato il formato paragrafo.

![](assets/screen_shot_2018-01-11at142828.png)

Anche il componente Testo può essere modificato in linea, ma non tutte le opzioni di formattazione sono disponibili in linea a causa di limitazioni dello spazio. Per visualizzare tutte le opzioni, passate alla modalità schermo intero.

![](assets/screen_shot_2018-01-11at142921.png)

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori dei contenuti.

### Plugins Tab {#plugins-tab}

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

* Tap or click the **Add** button to insert a new style.
* Inserite il codice dello stile e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* To remove a style tap or click the **Delete** button.
* Per riorganizzare l&#39;ordine dei formati toccate o fate clic e trascinate le maniglie.

### Configuring Special Characters {#configuring-special-characters}

![](assets/chlimage_1-31.png)

L&#39;opzione per inserire caratteri speciali può essere attivata o disattivata per il componente. Quando è attivata, è possibile definire i caratteri consentiti.

* Tap or click the **Add** button to insert a new character.
* Inserite il codice HTML del carattere e una descrizione che verrà visualizzata nella finestra di dialogo di modifica.
* To remove a character tap or click the **Delete** button.
* Per riordinare l&#39;ordine dei caratteri toccate o fate clic e trascinate le maniglie.

## Styles Tab {#styles-tab}

The Text Component supports the AEM [style system](authoring.md#component-styling).