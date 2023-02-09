---
title: Componente core Forms adattivo - Procedura guidata
description: Utilizzo o personalizzazione del componente di base della procedura guidata Forms adattiva.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1681'
ht-degree: 1%

---


# Wizard {#wizard-adaptive-forms-core-component}

Un layout guidato in un modulo adattivo si riferisce a un modulo suddiviso in più passaggi o pagine, in cui l’utente si sposta nel modulo un passaggio alla volta. Questo layout è denominato &quot;procedura guidata&quot; perché guida l’utente all’interno del modulo in un processo dettagliato.

Ogni passaggio della procedura guidata contiene in genere un gruppo di campi modulo correlati e un meccanismo di navigazione, ad esempio i pulsanti Avanti e Indietro, per spostarsi tra i passaggi. L’utente può procedere al passaggio successivo solo una volta completato il passaggio corrente e tutti i campi obbligatori sono stati compilati.

Il layout guidato è utile per i moduli che contengono molti campi o informazioni da raccogliere, in quanto suddivide il modulo in blocchi più piccoli e gestibili. Aiuta inoltre gli utenti a concentrarsi su un insieme di campi alla volta, il che può rendere il processo di compilazione del modulo meno schiacciante.

Tuttavia, può anche aumentare la complessità del modulo, in quanto l’utente deve passare attraverso più pagine per compilare il modulo. Pertanto, è necessario valutare i requisiti del modulo e le esigenze dell’utente prima di decidere di utilizzare un layout della procedura guidata.

È possibile utilizzare il componente di base layout guidato in un modulo adattivo per creare il layout della procedura guidata.


**Esempio**

![](/help/adaptive-forms/assets/wizard.png)

## Utilizzo {#reasons-to-use-wizard-in-an-adaptive-form}

Ci sono diversi motivi per cui può essere utile utilizzare un layout guidato in un modulo adattivo:

* **Semplicità**: La suddivisione di un modulo in più passaggi può facilitare la comprensione e il completamento da parte degli utenti, in quanto può concentrarsi su un set di campi alla volta.

* **Organizzazione**: Un layout guidato consente di organizzare i moduli in base all&#39;argomento o allo scopo, nonché di raggruppare i campi correlati, in modo da rendere il processo di compilazione del modulo più logico ed efficiente.

* **Convalida**: Un layout della procedura guidata consente una convalida dettagliata, che consente agli utenti di identificare e correggere gli errori mentre si spostano, anziché attendere fino alla fine del modulo.

* **Indicatore di avanzamento**: Un layout della procedura guidata può visualizzare l’avanzamento del modulo, consentendo all’utente di comprendere la parte del modulo da completare.

* **Forme lunghe**: Se il modulo contiene molti campi, può essere schiacciante per l&#39;utente vederli tutti in una sola volta, quindi suddividerli in blocchi più piccoli e più gestibili può rendere meno intimidatorio.

* **Evitare l&#39;abbandono**: Un layout della procedura guidata può anche contribuire a ridurre l’abbandono del modulo, in quanto gli utenti hanno maggiori probabilità di completare un modulo se possono vedere l’avanzamento e comprendere quanto resta da fare.

* **Esperienza mobile**: Un layout della procedura guidata può essere utile anche per i moduli a cui si accede tramite dispositivi mobili, in quanto consente di caricare pagine più piccole che vengono caricate più velocemente e sono più facili da navigare.

Nel complesso, un layout guidato può rendere il processo di compilazione del modulo più gestibile ed efficiente per gli utenti, ma è importante considerare la complessità del modulo e le esigenze dell&#39;utente prima di decidere di utilizzare questo tipo di layout.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base Layout guidato adattivo di Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base per il titolo di Forms adattivo, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza della procedura guidata per i visitatori tramite la finestra di dialogo Configura . Puoi inoltre definire le opzioni della procedura guidata in modo semplice e intuitivo.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/wizard_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto** - Scegliere &quot;Racchiudi i dati in un oggetto&quot; per inserire i dati del campo dalla procedura guidata all&#39;interno di un oggetto JSON. Se non viene selezionato, i dati di invio JSON presentano una struttura piatta per i campi della procedura guidata.

* **Layout** - È possibile disporre di un layout fisso (semplice) o flessibile (griglia reattiva) per la procedura guidata. Il layout Semplice mantiene tutto fisso nella posizione, mentre la griglia reattiva consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza Griglia reattiva per allineare &quot;Nome&quot;, &quot;Nome intermedio&quot; e &quot;Cognome&quot; in un modulo in un’unica riga.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente fluida per la raccolta e la gestione dei dati.

* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Aiuto {#help-tab}

![Scheda Aiuto](/help/adaptive-forms/assets/wizard_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.


### Scheda Accessibilità {#accessibility}

![Scheda Base](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale** - Il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come gli assistenti vocali. L’attributo ruolo viene utilizzato per fornire contesto e significato semantico aggiuntivi a un elemento, facilitando l’interpretazione e l’annuncio del contenuto da parte degli assistenti vocali. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di &quot;etichetta&quot; e il relativo campo di input potrebbe avere il ruolo di &quot;casella di testo&quot;. Questo consente all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input e di annunciarli correttamente all’utente.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente Creazione guidata Forms adattiva, è possibile impostare quanto segue:

* Componenti core che un creatore di moduli può aggiungere alla procedura guidata nell’editor Forms adattivo
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente Wizard nell&#39;editor di Forms adattivo.

Questo consente di semplificare e personalizzare i moduli.

### Scheda Componenti consentiti {#allowed-components-tab}

La **Componenti consentiti** scheda consente all’editor modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Wizard nell’editor di Forms adattivo.

### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core della procedura guidata adattiva Forms supporta la AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente Wizard.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

