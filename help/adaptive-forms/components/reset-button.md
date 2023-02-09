---
title: Componente core Forms adattivo - Pulsante Ripristina
description: Utilizzo o personalizzazione del componente core del pulsante Reimpostazione adattiva di Forms.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 2%

---


# Ripristina {#reset-button}

Un pulsante di reimpostazione in un modulo adattivo è un pulsante che consente agli utenti di cancellare o reimpostare tutti i campi del modulo sui valori predefiniti. Quando si fa clic sul pulsante di ripristino, tutti i dati immessi nei campi del modulo vengono eliminati e i campi tornano allo stato originale. In genere, il pulsante di reimpostazione viene utilizzato come alternativa al pulsante di invio e consente agli utenti di ricominciare se nel modulo sono stati inseriti dati errati o indesiderati.


## Utilizzo {#reasons-to-use-reset-button}

I motivi per utilizzare un pulsante di ripristino in un modulo adattivo sono i seguenti:

* **Comodità dell&#39;utente**: Un pulsante di reimpostazione consente agli utenti di cancellare il modulo in modo semplice e rapido, senza dover eliminare manualmente ogni campo.

* **Maggiore usabilità**: Un pulsante di reimpostazione può migliorare l’esperienza utente consentendo agli utenti di correggere facilmente gli errori o modificare i loro input.

* **Prevenzione degli errori**: Utilizzando un pulsante di ripristino, gli utenti possono evitare di inviare accidentalmente dati errati, il che può causare errori o problemi di elaborazione.

* **Coerenza**: L’inclusione di un pulsante di reimpostazione in un modulo assicura coerenza nell’esperienza utente, in quanto i pulsanti di reimpostazione sono una funzione comune dei moduli.

* **Gestione migliore dei dati**: Utilizzando un pulsante di ripristino, i dati del modulo possono essere mantenuti organizzati e precisi, in quanto gli utenti hanno meno probabilità di inviare dati non coerenti o non corretti.

## Versione e compatibilità {#version-and-compatibility}

Il pulsante Adaptive Forms Reset Componente core è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa è una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni le informazioni più recenti sul componente core del pulsante di reimpostazione di Forms adattivo nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pulsante Ripristina per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni del pulsante Ripristina con facilità per un’esperienza utente semplice.

### Scheda di base {#basic-tab}

![Scheda di base](/help/adaptive-forms/assets/button_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.

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

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente pulsante Ripristina .


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core del pulsante di ripristino Forms adattivo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core del pulsante di ripristino adattivo di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.
