---
title: Componente core Forms adattivo - Schede orizzontali
description: Utilizzo o personalizzazione del componente core Schede adattabili orizzontali di Forms.
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 3%

---


# Schede orizzontali {#horizontal-tabs-adaptive-forms-core-component}

Le schede orizzontali in un Modulo adattivo fanno riferimento a un pattern di progettazione in cui più sezioni di un modulo sono raggruppate e visualizzate come schede separate, allineate orizzontalmente. L’utente può passare da una scheda all’altra per accedere a diverse sezioni del modulo. Ogni scheda funge da attivatore per mostrare e nascondere il relativo contenuto del modulo. Le schede orizzontali consentono di organizzare i moduli lunghi in sezioni gestibili e di migliorare l’esperienza utente. Le schede possono essere utili per rendere un modulo più accessibile agli utenti con disabilità, in quanto possono passare da una sezione all’altra tramite la navigazione tramite tastiera.

Le schede vengono solitamente create come una serie di collegamenti o pulsanti, con ogni collegamento o pulsante corrispondente a una sezione del modulo. Quando un utente fa clic su una scheda, il contenuto del modulo viene aggiornato dinamicamente per mostrare la sezione corrispondente.

## Utilizzo {#reasons-to-use-horizontal-tabs}

I motivi comuni per utilizzare le schede orizzontali in un modulo adattivo sono i seguenti:

* **Maggiore usabilità**: Le schede orizzontali facilitano la navigazione all’interno del modulo, soprattutto se il modulo contiene più sezioni o un numero elevato di campi.

* **Gestione dello spazio**: Le schede orizzontali consentono di risparmiare spazio sullo schermo raggruppando le sezioni correlate del modulo in schede e visualizzando una sola sezione alla volta.

* **Organizzazione migliore**: Le schede forniscono una struttura chiara e organizzata per un modulo, facilitando agli utenti la comprensione e la compilazione del modulo.

* **Maggiore coinvolgimento degli utenti**: Le schede orizzontali possono rendere un modulo più accattivante e coinvolgente dal punto di vista visivo, il che può migliorare la frequenza di completamento del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Schede adattabili orizzontali Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core delle schede Adaptive Forms Horizontal nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageHorizontal schede/v1/pageSchede orizzontali). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza con le schede Orizzontali per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni Schede orizzontali con facilità per un’esperienza utente semplice.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/tabsontop_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto** - Scegliere &quot;Racchiudi i dati in un oggetto&quot; per inserire i dati del campo dalla procedura guidata all&#39;interno di un oggetto JSON. Se non viene selezionato, i dati di invio JSON presentano una struttura piatta per i campi della procedura guidata.

* **Layout** - È possibile disporre di un layout fisso (semplice) o flessibile (griglia reattiva) per la procedura guidata. Il layout Semplice mantiene tutto fisso nella posizione, mentre la griglia reattiva consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza Griglia reattiva per allineare &quot;Nome&quot;, &quot;Nome intermedio&quot; e &quot;Cognome&quot; in un modulo in un’unica riga.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/tabsontop_itemstab.png)

La **Aggiungi** consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

* **Icona** - L’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo del pannello. Per impostazione predefinita, il nome del componente selezionato per il pannello.
* **Elimina**: tocca o fai clic per eliminare il pannello dal componente Pannello a soffietto.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto dell’Aiuto {#help-content}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/tabsontop_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/tabsontop_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale** - Il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come gli assistenti vocali. L’attributo ruolo viene utilizzato per fornire contesto e significato semantico aggiuntivi a un elemento, facilitando l’interpretazione e l’annuncio del contenuto da parte degli assistenti vocali. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di &quot;etichetta&quot; e il relativo campo di input potrebbe avere il ruolo di &quot;casella di testo&quot;. Questo consente all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input e di annunciarli correttamente all’utente.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente per pannello a soffietto di Forms adattivo, puoi impostare quanto segue:

* Componenti core che un creatore di moduli può aggiungere al pannello a soffietto nell’editor di Forms adattivo
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente a soffietto nell’editor di Forms adattivo.

Questo consente di semplificare e personalizzare i moduli.

### Scheda Componenti consentiti {#allowed-components-tab}

La **Componenti consentiti** La scheda consente all’editor modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Tabulazioni orizzontali nell’editor di Forms adattivo.

### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core Schede adattabili orizzontali di Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente di base Schede orizzontali di Forms adattive.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.
