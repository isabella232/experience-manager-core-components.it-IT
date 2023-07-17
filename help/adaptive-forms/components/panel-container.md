---
title: Componente core dei moduli adattivi - Contenitore di pannelli
description: Utilizzo o personalizzazione del componente core contenitore di pannelli dei moduli adattivi.
role: Architect, Developer, Admin, User
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '1402'
ht-degree: 98%

---

# Contenitore di pannelli {#panel-container-adaptive-forms-core-component}

In un modulo adattivo, un pannello è un elemento contenitore che può essere utilizzato per raggruppare gli elementi modulo correlati. Consente di raggruppare e organizzare diversi elementi modulo in modo logico e significativo. Questo consente di migliorare la struttura e la leggibilità complessiva del modulo, facilitando agli utenti la comprensione e la navigazione del modulo.

I pannelli possono anche essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare. Consente inoltre di includere altri componenti come testo, casella di controllo, pulsante e così via.

Può anche essere utilizzato per impostare diverse azioni basate su regole come l’invio di un modulo, l’apertura di un sito web, la visualizzazione o meno dei componenti o l’aggiunta di un’istanza di un pannello.

**Esempio**

![](/help/adaptive-forms/assets/panel-container.png)

## Utilizzo {#reasons-to-use-panel-container}

Esistono diversi motivi per utilizzare un pannello in un modulo, tra cui:

* **Organizzazione degli elementi del modulo**: è possibile utilizzare un pannello per raggruppare gli elementi del modulo correlati, facilitando agli utenti la comprensione e la navigazione del modulo.

* **Miglioramento della struttura dei moduli**: raggruppando gli elementi dei moduli in pannelli, è possibile migliorare la struttura complessiva e la leggibilità del modulo, facilitandone la comprensione.

* **Creazione di sezioni comprimibili**: i pannelli possono essere utilizzati per creare sezioni comprimibili, utili per nascondere campi modulo complessi o meno utilizzati, mantenendo il modulo semplice e facile da usare.

* **Ottimizzazione dell’usabilità**: l’utilizzo dei pannelli per organizzare gli elementi dei moduli rende il modulo più intuitivo e facile da utilizzare, con conseguente aumento dei tassi di completamento.

## Versione e compatibilità {#version-and-compatibility}

Il componente core del contenitore di pannelli dei moduli adattivi è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità con AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.4](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni le informazioni più recenti sul componente core del contenitore di pannelli dei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del contenitore di pannelli per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni del contenitore di pannelli con facilità per un’esperienza utente diretta.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/basic-panel.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona l’opzione per nascondere il componente del modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Ripeti pannello {#repeat-panel}

![scheda ripeti](/help/adaptive-forms/assets/repeat-panel.png)

È possibile utilizzare le opzioni di ripetibilità per duplicare il contenitore di pannelli e i relativi componenti secondari, definire un numero di ripetizioni minimo e massimo e facilitare la replica di sezioni simili all’interno di un modulo. Quando si interagisce con il componente Contenitore di pannelli e si accede alle relative impostazioni, vengono visualizzate le seguenti opzioni:

* **Rendi ripetibile la procedura guidata**: una funzione di attivazione/disattivazione che consente agli utenti di abilitare o disabilitare la funzione di ripetibilità.
* **Numero minimo di ripetizioni**: stabilisce il numero minimo di volte in cui il contenitore di pannelli può essere ripetuto. Il valore zero indica che il pannello della procedura guidata non è ripetuto. Il valore predefinito è zero.
* **Numero massimo di ripetizioni**: imposta il numero massimo di volte in cui il contenitore di pannelli può essere ripetuto. Per impostazione predefinita, questo valore è illimitato.

Per gestire in modo efficace le sezioni ripetibili all’interno del contenitore di pannelli, segui i passaggi descritti nell’articolo [Creazione di moduli con sezioni ripetibili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=it).

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/helpcontent-panel.png)


* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/accessibilty-panel.png)


* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

* **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina o in un frammento di esperienza di AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)
