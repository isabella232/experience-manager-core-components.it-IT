---
title: Componente core Forms adattivo - Testo
description: Utilizzo o personalizzazione del componente di base Testo adattivo di Forms.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 3%

---


# Testo {#text-adaptive-forms-core-component}

In un modulo adattivo, il testo si riferisce al contenuto visualizzato sul modulo da consentire all’utente di leggere. Ciò può includere il testo utilizzato per etichettare un gruppo di elementi del modulo, come i campi di testo, nonché tutte le istruzioni o informazioni aggiuntive fornite all’utente.

Questo consente anche di suddividere la struttura di un modulo in sezioni logiche, facilitando agli utenti la comprensione e la compilazione del modulo. Inoltre, può essere utilizzato a scopo di accessibilità per fornire una breve descrizione dell’elemento a cui è associato. Tale campo di testo viene generalmente visualizzato vicino ai componenti del modulo, ad esempio prima o dopo di esso.

**Esempio**

![](/help/adaptive-forms/assets/text.png)

## Utilizzo {#reasons-to-use-text-label}

Esistono diversi motivi per utilizzare il testo in un modulo:

* **Fornire istruzioni**: Il testo può essere utilizzato per fornire istruzioni su come compilare il modulo o quali informazioni sono necessarie.

* **Fornire contesto**: Il testo può essere utilizzato per fornire contesto al modulo, ad esempio per spiegare lo scopo del modulo o l’organizzazione che raccoglie le informazioni.

* **Dividere il modulo in sezioni logiche**: Il testo può essere utilizzato per dividere un modulo in sezioni logiche, facilitando agli utenti la comprensione e la compilazione del modulo.

* **Branding e identità**: Il testo può essere utilizzato a scopo di branding e identità, ad esempio per includere nel modulo il nome dell’organizzazione.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base per il testo adattivo di Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base per il testo adattivo di Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di testo per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni di testo con facilità per un’esperienza utente diretta.

![Scheda Base](/help/adaptive-forms/assets/text_properties.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Testo .


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per il testo adattivo di Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente di base Testo adattivo di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.
