---
title: Componente core moduli adattivi - Procedura guidata
description: Utilizzo o personalizzazione del componente core della procedura guidata nei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1847'
ht-degree: 100%

---

# Procedure guidata {#wizard-adaptive-forms-core-component}

Un layout della procedura guidata in un modulo adattivo si riferisce a un modulo suddiviso in più passaggi o pagine, in cui l’utente si sposta compiendo un passaggio alla volta. Questo layout è denominato “procedura guidata” perché guida l’utente all’interno del modulo in un processo graduale.

Ogni passaggio della procedura guidata contiene in genere un gruppo di campi modulo correlati e un meccanismo di navigazione, ad esempio i pulsanti “Avanti” e “Indietro”, per spostarsi tra i passaggi. L’utente può procedere al passaggio successivo solo una volta completato il passaggio corrente e tutti i campi obbligatori sono stati compilati.

Il layout della procedura guidata è utile per i moduli che contengono molti campi o informazioni da raccogliere, in quanto suddivide il modulo in blocchi più piccoli e gestibili. Aiuta inoltre gli utenti a concentrarsi su un insieme di campi alla volta, il che può rendere il processo di compilazione del modulo meno complesso.

Tuttavia, può anche aumentare la complessità del modulo, in quanto l’utente deve passare attraverso più pagine per completare il modulo. Pertanto, è necessario valutare i requisiti del modulo e le esigenze dell’utente prima di decidere di utilizzare un layout della procedura guidata.

È possibile utilizzare il componente core del layout della procedura guidata in un modulo adattivo per creare il layout della procedura guidata.


**Esempio**

![](/help/adaptive-forms/assets/wizard.png)

## Utilizzo {#reasons-to-use-wizard-in-an-adaptive-form}

Ci sono diversi motivi per cui può essere utile utilizzare un layout della procedura guidata in un modulo adattivo:

* **Semplicità**: la suddivisione di un modulo in più passaggi può facilitare la comprensione e il completamento da parte degli utenti, che possono così concentrarsi su un set di campi alla volta.

* **Organizzazione**: un layout della procedura guidata consente di organizzare i moduli in base all’argomento o allo scopo, nonché di raggruppare i campi correlati, in modo da rendere il processo di compilazione del modulo più logico ed efficiente.

* **Convalida**: un layout della procedura guidata consente una convalida per passaggi, che consente agli utenti di identificare e correggere gli errori mentre si spostano, anziché attendere fino alla fine del modulo.

* **Indicatore di avanzamento**: un layout della procedura guidata può mostrare l’avanzamento del modulo, consentendo all’utente di comprendere quanto modulo resta ancora da completare.

* **Moduli lunghi**: se il modulo contiene molti campi, può essere complicato per l’utente vederli tutti in una sola volta, quindi suddividerli in blocchi più piccoli e più gestibili può rendere il tutto meno ostile.

* **Evitare l’abbandono**: un layout della procedura guidata può anche contribuire a ridurre l’abbandono del modulo, in quanto gli utenti hanno maggiori probabilità di completare un modulo se possono vedere l’avanzamento e comprendere quanto resta da fare.

* **Esperienza mobile**: un layout della procedura guidata può essere utile anche per i moduli a cui si accede tramite dispositivi mobili, in quanto consente di caricare pagine più piccole in modo più veloce e le rende più facili da navigare.

Nel complesso, un layout della procedura guidata può rendere il processo di compilazione del modulo più gestibile ed efficiente per gli utenti, ma è importante considerare la complessità del modulo e le esigenze dell’utente prima di decidere di utilizzare questo tipo di layout.

## Versione e compatibilità {#version-and-compatibility}

Il componente core del layout della procedura guidata per moduli adattivi è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità con AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core del titolo per moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza della procedura guidata per i visitatori tramite la finestra di dialogo per la configurazione. Puoi inoltre definire le opzioni della procedura guidata facilmente per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/wizard_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Aiuto {#help-tab}

![Scheda Aiuto](/help/adaptive-forms/assets/wizard_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.


### Scheda Accessibilità {#accessibility}

![Scheda Base](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente procedura guidata dei moduli adattivi, è possibile impostare quanto segue:

* I componenti core che un creatore di moduli può aggiungere alla procedura guidata nell’editor dei moduli adattivi
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente procedura guidata nell’editor dei moduli adattivi.

Questo permette di rendere il processo di creazione e personalizzazione dei moduli più semplice ed efficace.

### Scheda Componenti Consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** permette all’editor dei modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente procedura guidata nell’editor di moduli adattivi.

![Schede Componenti consentiti](/help/adaptive-forms/assets/panel_allowedcomponent.png)

### Scheda Componenti predefiniti {#default-component-tab}

Questa scheda permette all’editor dei modelli di mappare i componenti che possono essere aggiunti come elementi ai pannelli nel componente della procedura guidata nell’editor di moduli adattivi.

![Componente predefinito del pannello](/help/adaptive-forms/assets/panel_defaultcomponent.png)

### Impostazioni reattive {#responsive-settings}

Questa scheda consente all’editor dei modelli di impostare il numero di colonne da visualizzare nella griglia dinamica.

![Griglia dinamica](/help/adaptive-forms/assets/panel_responsivesettings.png)

### Scheda Impostazioni contenitore {#container-setting-tab}

La scheda delle impostazioni contenitore consente di impostare la posizione dei componenti nell’editor di moduli adattivi.

![Impostazioni contenitore](/help/adaptive-forms/assets/panel_settings.png)

* **Layout**: il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di modificare la posizione dei componenti in base alle proprie esigenze.
* **Disabilita layout**: è inoltre possibile disabilitare la selezione del layout nella finestra di dialogo di modifica selezionando la casella di controllo **Disabilita layout**.
* **Abilita immagine di sfondo**: questa scheda consente di impostare l’immagine e il colore di sfondo nell’editor modelli.
* **Abilita colore di sfondo**: questa scheda consente di impostare il colore di sfondo nell’editor modelli.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core della procedura guidata dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Scheda Stile](/help/adaptive-forms/assets/panel_style.png)

* **Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente procedura guidata.

* **Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

