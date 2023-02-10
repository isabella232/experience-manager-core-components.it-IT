---
title: Componente core Forms adattivo - Contenitore di pannelli
description: Utilizzo o personalizzazione del componente core contenitore Pannello di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 86fa434d884b24b8d4b231c6108f5e6151a89813
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---


# Contenitore pannello {#panel-container-adaptive-forms-core-component}

In un modulo adattivo, un pannello è un elemento contenitore che può essere utilizzato per raggruppare gli elementi modulo correlati. Consente di raggruppare e organizzare diversi elementi modulo in modo logico e significativo. Questo consente di migliorare la struttura e la leggibilità complessiva del modulo, facilitando agli utenti la comprensione e la navigazione del modulo.

I pannelli possono anche essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare. Consente inoltre di includere altri componenti come testo, casella di controllo, pulsante e così via.

Può anche essere utilizzato per impostare diverse azioni basate su regole come l’invio di un modulo, l’apertura di un sito web, la visualizzazione/visualizzazione di componenti o l’aggiunta di un’istanza di un pannello.

**Esempio**

![](/help/adaptive-forms/assets/panel-container.png)

## Utilizzo {#reasons-to-use-panel-container}

Esistono diversi motivi per utilizzare un pannello in un modulo, tra cui:

* **Organizzazione degli elementi modulo**: È possibile utilizzare un pannello per raggruppare gli elementi modulo correlati, facilitando agli utenti la comprensione e la navigazione del modulo.

* **Miglioramento della struttura dei moduli**: Raggruppando gli elementi dei moduli in pannelli, è possibile migliorare la struttura complessiva e la leggibilità del modulo, facilitandone la comprensione.

* **Creazione di sezioni comprimibili**: I pannelli possono essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare.

* **Ottimizzazione dell&#39;usabilità**: L’utilizzo dei pannelli per organizzare gli elementi dei moduli rende il modulo più semplice da usare e facile da utilizzare, con conseguente aumento dei tassi di completamento.

## Versione e compatibilità {#version-and-compatibility}

Il componente core contenitore di pannello adattivo Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core del contenitore del pannello di Forms adattivo nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del contenitore di pannelli per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni del contenitore del pannello con facilità per un’esperienza utente diretta.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/panelcontainer_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto** - Scegliere &quot;Racchiudi i dati in un oggetto&quot; per inserire i dati del campo dalla procedura guidata all&#39;interno di un oggetto JSON. Se non viene selezionato, i dati di invio JSON presentano una struttura piatta per i campi della procedura guidata.

* **Layout** - È possibile disporre di un layout fisso (semplice) o flessibile (griglia reattiva) per la procedura guidata. Il layout Semplice mantiene tutto fisso nella posizione, mentre la griglia reattiva consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza Griglia reattiva per allineare &quot;Nome&quot;, &quot;Nome intermedio&quot; e &quot;Cognome&quot; in un modulo in un’unica riga.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Contenuto dell’Aiuto {#help-content}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/panelcontainer_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/panelcontainer_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale** - Il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come gli assistenti vocali. L’attributo ruolo viene utilizzato per fornire contesto e significato semantico aggiuntivi a un elemento, facilitando l’interpretazione e l’annuncio del contenuto da parte degli assistenti vocali. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di &quot;etichetta&quot; e il relativo campo di input potrebbe avere il ruolo di &quot;casella di testo&quot;. Questo consente all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input e di annunciarli correttamente all’utente.




