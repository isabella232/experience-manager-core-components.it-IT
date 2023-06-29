---
title: Componente core moduli adattivi - Schede orizzontali
description: Utilizzo o personalizzazione del componente core delle schede orizzontali dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: fbdf330b-3b85-4f94-9dab-eea8465fba67
source-git-commit: b2c35d78ba0473273852deb678b34b5dd96cf51e
workflow-type: tm+mt
source-wordcount: '1733'
ht-degree: 88%

---

# Schede orizzontali {#horizontal-tabs-adaptive-forms-core-component}

Le schede orizzontali in un modulo adattivo fanno riferimento a un pattern di progettazione in cui più sezioni di un modulo sono raggruppate e visualizzate come schede separate, allineate orizzontalmente. L’utente può passare da una scheda all’altra per accedere a diverse sezioni del modulo. Ogni scheda funge da attivatore per mostrare e nascondere il relativo contenuto del modulo. Le schede orizzontali consentono di organizzare i moduli lunghi in sezioni gestibili e di migliorare l’esperienza di utilizzo. Le schede possono essere utili per rendere un modulo più accessibile agli utenti con disabilità, consentendo di passare da una sezione all’altra tramite la navigazione con tastiera.

Le schede vengono solitamente create come una serie di collegamenti o pulsanti dove ogni collegamento o pulsante corrisponde a una sezione del modulo. Facendo clic su una scheda, il contenuto del modulo si aggiorna dinamicamente mostrando la sezione corrispondente.

## Utilizzo {#reasons-to-use-horizontal-tabs}

I motivi comuni per utilizzare le schede orizzontali in un modulo adattivo sono i seguenti:

* **Migliore fruibilità**: le schede orizzontali facilitano la navigazione all’interno del modulo, soprattutto se il modulo contiene più sezioni o un numero elevato di campi.

* **Gestione Spazio**: le schede orizzontali consentono di risparmiare spazio sullo schermo raggruppando le sezioni correlate del modulo in schede e visualizzando una sola sezione alla volta.

* **Organizzazione migliore**: le schede forniscono una struttura chiara e organizzata per un modulo, semplificandone la comprensione e la compilazione.

* **Maggiore coinvolgimento dell&#39;utente**: le schede orizzontali possono rendere un modulo più accattivante e coinvolgente dal punto di vista visivo, il che può migliorare la sua frequenza di completamento.

## Versione e compatibilità {#version-and-compatibility}

Il componente core delle schede orizzontali dei moduli adattivi è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità con AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.4](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).


<!-- ## Sample Component Output {#sample-component-output}

To experience the Horizontal-tabs  Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_Horizontal-tabs ). -->


## Dettagli tecnici {#technical-details}

Ottieni le informazioni più recenti sul componente core delle schede orizzontali dei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageHorizontal tabs/v1/pageHorizontal tabs). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza con le schede orizzontali per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni delle schede orizzontali con facilità per un’esperienza di utilizzo semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/tabs-on-top-basic.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Ripeti Schede in alto {#repeat-tabs-on-top}

![Scheda Accessibilità](/help/adaptive-forms/assets/repeat-tabsontop.png)

È possibile utilizzare le opzioni di ripetibilità per duplicare il componente Schede orizzontali e i relativi componenti figlio, definire un conteggio di ripetizioni minimo e massimo e facilitare la replica di sezioni simili all’interno di un modulo. Quando si interagisce con il componente Schede orizzontali e si accede alle relative impostazioni, vengono visualizzate le seguenti opzioni:

* **Rendi ripetibili le tabulazioni orizzontali**: funzione di attivazione/disattivazione che consente agli utenti di abilitare o disabilitare la funzionalità di ripetibilità.
* **Numero minimo di ripetizioni**: stabilisce il numero minimo di volte in cui il componente Schede orizzontali può essere ripetuto. Il valore zero indica che il componente Schede orizzontali non è ripetuto. Il valore predefinito è zero.
* **Numero massimo di ripetizioni**: imposta il numero massimo di volte in cui il componente Schede orizzontali può essere ripetuto. Per impostazione predefinita, questo valore è illimitato.

Per gestire in modo efficace le sezioni ripetibili nelle schede Orizzontali, segui i passaggi descritti in [Creazione di moduli con sezioni ripetibili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) articolo.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/items-tabs-on-top.png)

Il pulsante **Aggiungi** consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

* **Icona**: l’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione**: descrizione utilizzata come testo del pannello. Per impostazione predefinita, il nome del componente selezionato per il pannello.
* **Elimina** - Tocca o fai clic per eliminare il pannello dal componente Schede orizzontali.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/helpcontent-tabs-on-top.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/accessibilty-tabs-on-top.png)

* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente Schede orizzontali di Forms adattivo, puoi impostare quanto segue:

* Componenti core che un creatore di moduli può aggiungere alle schede orizzontali nell’editor di Forms adattivo
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente Schede orizzontali nell’editor di Forms adattivo.

Questo permette di rendere il processo di creazione e personalizzazione dei moduli più semplice ed efficace.

### Scheda Componenti Consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** consente all’editor modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Schede orizzontali nell’editor di moduli adattivi.

### Scheda Stili {#styles-tab}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core delle schede orizzontali nei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

**Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core delle Schede orizzontali nei moduli adattivi.

**Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.