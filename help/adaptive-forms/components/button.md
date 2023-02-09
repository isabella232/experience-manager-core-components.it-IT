---
title: Componente core Forms adattivo - Pulsante
description: Utilizzo o personalizzazione del componente core del pulsante Adattivo Forms.
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 2%

---


# Componente Pulsante  {#button-component-adaptive-forms-core-component}

Un pulsante in un modulo adattivo è un elemento dell’interfaccia utente che consente agli utenti di avviare un’azione quando fanno clic su di esso. L’elemento pulsante può essere utilizzato per inviare un modulo, reimpostare un modulo o eseguire altre operazioni, ad esempio la navigazione a una pagina diversa o l’attivazione di codice personalizzato. Il pulsante può essere creato utilizzando il componente di base Pulsante .

L’Editor di regole di Forms adattive consente agli utenti di impostare varie azioni per il componente pulsante. Queste azioni includono l’apertura di un sito web, la visualizzazione o l’eliminazione di componenti modulo, l’aggiunta di un’istanza di un pannello o di un componente, l’invio o la reimpostazione di un modulo e altro ancora.

Adattivo Forms fornisce anche componenti pulsante separati per l’invio o la reimpostazione di un modulo, ma può anche essere configurato per eseguire queste azioni, se necessario.

Gli utenti possono accedere all’elenco completo delle azioni supportate per il componente pulsante utilizzando l’Editor di regole di Forms adattivo. L’Editor di regole consente agli utenti di creare regole attivate da vari eventi, ad esempio quando si fa clic su un pulsante, quando si carica un modulo o si modifica il valore di un campo. Queste regole possono quindi essere utilizzate per eseguire varie azioni, ad esempio per mostrare o nascondere i componenti, impostare i valori dei campi o inviare il modulo.

## Utilizzo {#reasons-to-use-button}

Ci sono diversi motivi per cui è utile includere un pulsante in un modulo adattivo, tra cui:

* **Invio del modulo**: Un pulsante viene in genere utilizzato per inviare un modulo, consentendo agli utenti di inviare i dati immessi sul server per l’elaborazione.

* **Ripristino del modulo**: I pulsanti possono essere utilizzati anche per reimpostare un modulo, cancellando tutti i dati immessi dall’utente.

* **Navigazione**: I pulsanti possono essere utilizzati per spostarsi tra diverse sezioni di un modulo o tra pagine diverse di un sito web.

* **Gestione degli eventi**: I pulsanti possono essere utilizzati per attivare eventi diversi come l’apertura di un sito web, l’esposizione o la visualizzazione di componenti, l’aggiunta di un’istanza di un pannello o di un componente al pulsante .

* **Interattività**: I pulsanti possono essere utilizzati per creare moduli interattivi. Ad esempio, un pulsante può essere utilizzato per aprire una finestra di dialogo modale o per attivare o disattivare una sezione del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base per pulsanti adattivi Forms v1 è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base per pulsanti adattivi di Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pulsante per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le proprietà dei pulsanti con facilità per un’esperienza utente diretta.

### Scheda di base {#basic-tab}

![Scheda di base](/help/adaptive-forms/assets/button_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Riferimento di binding del documento di record** - Questa opzione consente di associare un campo Modulo adattivo a un campo Documento di record. Quando l’utente immette un valore in un campo collegato di un modulo adattivo, tale valore viene visualizzato anche nel campo collegato del corrispondente documento di record. Ad esempio, è possibile utilizzare un riferimento di binding Documento di record per visualizzare il nome e l&#39;indirizzo di un cliente in un documento di record, in base all&#39;ID del cliente immesso nel modulo. In questo modo, AEM Forms consente di generare un documento di record e offre un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Contenuto dell’Aiuto {#help-content}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/button_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/button_accessibilitytab.png)


* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

Sulla **Accessibilità** scheda , valori impostati per [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) etichette per il componente. Sono disponibili varie opzioni per l’utilizzo del testo per l’assistente vocale:

* **Testo personalizzato**: Selezionare questa opzione per utilizzare il testo personalizzato per le etichette di accessibilità ARIA. Selezionando questa opzione viene visualizzata la finestra di dialogo Testo personalizzato. È possibile aggiungere informazioni rilevanti nella finestra di dialogo Testo personalizzato.
* **Descrizione**: Selezionare questa opzione per utilizzare la descrizione per le etichette di accessibilità ARIA.
* **Titolo**: Selezionare questa opzione per utilizzare il titolo per le etichette di accessibilità ARIA.
* **Nome**: Selezionare questa opzione per utilizzare il nome per le etichette di accessibilità ARIA.
* **Nessuno**: Selezionare questa opzione se non si desidera aggiungere etichette di accessibilità ARIA.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente pulsante.

### Scheda Stili {#styles-tab}

Il componente di base Pulsante di Forms adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente di base Pulsante di Forms adattivo.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

