---
title: Componente core dei moduli adattivi - Contenitore di pannelli
description: Utilizzo o personalizzazione del componente core contenitore di pannelli dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 73%

---

# Contenitore di pannelli {#panel-container-adaptive-forms-core-component}

In un modulo adattivo, un pannello è un elemento contenitore che può essere utilizzato per raggruppare gli elementi modulo correlati. Consente di raggruppare e organizzare diversi elementi modulo in modo logico e significativo. Questo consente di migliorare la struttura e la leggibilità complessiva del modulo, facilitando agli utenti la comprensione e la navigazione del modulo.

I pannelli possono essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare. Consente inoltre di includere altri componenti come testo, casella di controllo, pulsante.

Può anche essere utilizzato per impostare diverse azioni basate su regole come l’invio di un modulo, l’apertura di un sito web, la visualizzazione/visualizzazione di componenti o l’aggiunta di un’istanza di un pannello.

**Esempio**

![](/help/adaptive-forms/assets/panel-container.png)

## Utilizzo {#reasons-to-use-panel-container}

Esistono diversi motivi per utilizzare un pannello in un modulo, tra cui:

* **Organizzazione degli elementi del modulo**: È possibile utilizzare un pannello per raggruppare gli elementi del modulo correlati, facilitando agli utenti la comprensione e la navigazione del modulo.

* **Miglioramento della struttura dei moduli**: raggruppando gli elementi dei moduli in pannelli, è possibile migliorare la struttura complessiva e la leggibilità del modulo, facilitandone la comprensione.

* **Creazione di sezioni comprimibili**: i pannelli possono essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare.

* **Ottimizzazione dell’usabilità**: l’utilizzo dei pannelli per organizzare gli elementi dei moduli rende il modulo più intuitivo e facile da utilizzare, con conseguente aumento dei tassi di completamento.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4 per Cloud Service e i componenti core 1.1.12 per Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM 6.5.16.0 Forms o versione successiva |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con<br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma inferiori a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni le informazioni più recenti sul componente core del contenitore di pannelli dei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del contenitore di pannelli per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni del contenitore di pannelli con facilità per un’esperienza utente diretta.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/panelcontainer_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/panelcontainer_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/panelcontainer_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo che deve essere letto da tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Contenitore pannello.

### Scheda Componenti Consentiti {#allowed-components-tab}

![Schede Componenti consentiti](/help/adaptive-forms/assets/panel_allowedcomponent.png)

La **Componenti consentiti** scheda consente all’editor modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente contenitore Pannello nell’editor di Forms adattivo.

### Scheda Componenti predefiniti {#default-component-tab}

Questa scheda consente all’editor modelli di mappare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Contenitore pannello nell’editor di Forms adattivo.

![Componente predefinito del pannello](/help/adaptive-forms/assets/panel_defaultcomponent.png)

### Impostazioni reattive {#responsive-settings}

Questa scheda consente all’editor modelli di impostare il numero di colonne da visualizzare nella griglia dinamica.

![Griglia reattiva](/help/adaptive-forms/assets/panel_responsivesettings.png)

### Scheda Impostazioni contenitore {#container-setting-tab}

La scheda delle impostazioni del contenitore consente di impostare la posizione dei componenti nell’editor di Forms adattivo.

![Impostazioni contenitore](/help/adaptive-forms/assets/panel_settings.png)

* **Layout**: Il layout Semplice mantiene tutto fisso nella posizione, mentre la griglia reattiva consente di modificare la posizione dei componenti in base alle proprie esigenze.
* **Disabilita layout**: È inoltre possibile disattivare la selezione del layout nella finestra di dialogo di modifica selezionando **Disabilita layout** casella di controllo.
* **Abilita immagine di sfondo**: Questa scheda consente di impostare l’immagine e il colore di sfondo nell’editor modelli.
* **Attiva colore di sfondo**: Questa scheda consente di impostare il colore di sfondo nell’editor modelli.

### Scheda Stili {#styles-tab}

La scheda viene utilizzata per definire e gestire gli stili CSS per un componente. Il componente core contenitore pannello adattivo Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

![Scheda Stile](/help/adaptive-forms/assets/panel_style.png)

* **Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core Forms adattivo.

* **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo in Forms adattivo . Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile all’editor, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

* **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.

