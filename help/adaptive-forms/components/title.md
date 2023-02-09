---
title: Componente core Forms adattivo - Titolo
description: Utilizzo o personalizzazione del componente di base Titolo Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 15%

---


# Titolo {#title-input-adaptive-forms-core-component}

In un modulo adattivo, per &quot;titolo&quot; si intende il testo visualizzato nella parte superiore del modulo, in genere sotto l’intestazione. Il titolo viene specificato utilizzando il componente Titolo . Questo componente può essere aggiunto al layout del modulo e il relativo testo può essere modificato in base allo scopo o all’argomento del modulo. Il titolo funge da etichetta o breve descrizione del modulo per l’utente e consente di distinguere il modulo da altri.

**Esempio**

![](/help/adaptive-forms/assets/title.png)

## Utilizzo {#reasons-to-use-title-in-an-adaptive-form}

È consigliabile utilizzare un titolo in un modulo per diversi motivi:

* **Chiarezza**: Un titolo identifica chiaramente lo scopo del modulo, facilitando agli utenti la comprensione delle informazioni necessarie.

* **Organizzazione**: Un titolo può essere utile per organizzare i moduli in base all’argomento o allo scopo, facilitando agli utenti la ricerca del modulo di cui hanno bisogno.

* **Accessibilità**: Un titolo è un elemento chiave per gli utenti con esigenze di accessibilità, in quanto viene letto ad alta voce dagli assistenti vocali, per aiutare gli utenti a comprendere il contesto del modulo.

* **Branding**: Un titolo può essere utilizzato anche per visualizzare il nome di un&#39;azienda o di un&#39;organizzazione, il che contribuisce a creare un senso di fiducia e familiarità con l&#39;utente.

* **Navigazione**: Un titolo può anche essere utile per spostarsi all’interno del modulo, soprattutto se il modulo è lungo o complesso.

* **Ottimizzazione dei motori di ricerca (SEO)**: L’utilizzo di un titolo nel modulo consente inoltre di utilizzare SEO, in quanto i motori di ricerca utilizzano il titolo per determinare la rilevanza di una pagina web per una query di ricerca.

Nel complesso, il titolo di un modulo è un aspetto importante dell’esperienza utente e dovrebbe essere utilizzato per fornire un’etichetta chiara e concisa per il modulo, in modo da consentire agli utenti di comprendere il contesto e lo scopo del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Titolo di Forms adattivo è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base per il titolo di Forms adattivo, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del titolo per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni titolo con facilità per un’esperienza utente diretta.

![Scheda Base](/help/adaptive-forms/assets/title_properties.png)

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.
* **Tipo/Dimensione**: definisce il livello di intestazione del titolo.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel Data Layer.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente Selezione data .

### Titolo

La scheda Titolo consente agli autori dei modelli di impostare gli elementi di intestazione HTML predefiniti e consentiti per gli autori dei moduli:

![Scheda del titolo della finestra di dialogo Progettazione](/help/assets/accordion-design-properties.png)

* **Elementi di intestazione consentiti**: Un elenco con più opzioni che consente all’autore del modello di scegliere quali elementi di intestazione può essere utilizzato dall’autore del modulo per il titolo.

* **Elemento di intestazione predefinito**: Elenco a discesa che imposta l’elemento Titolo predefinito per il componente Titolo .


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per il selettore data adattivo di Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core del selettore data adattivo di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda Formati consente di specificare i formati di data predefiniti e personalizzati.

