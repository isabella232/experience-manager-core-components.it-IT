---
title: Componente carosello
description: Il componente Carosello consente all’autore del contenuto di presentare il contenuto in un carosello rotante.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 1%

---


# Componente carosello{#carousel-component}

Il componente Carosello dei componenti core consente all’autore del contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Con il componente Carosello , l’autore del contenuto organizza i contenuti in un carosello rotante di diapositive.

La [finestra di dialogo di modifica](#edit-dialog) consente all’autore del contenuto di creare, assegnare un nome e ordinare più diapositive, nonché attivare la transizione automatica con ritardo. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l’autore del modello può definire quali componenti possono essere aggiunti al carosello, abilitare o disabilitare le transizioni automatiche e personalizzare gli stili.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Carosello è la v1, introdotta con la versione 2.2.0 dei componenti core a ottobre 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Carosello e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_carousel).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Carosello [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di aggiungere, rinominare e ridisporre le diapositive e di definire le impostazioni di transizione automatica.

### Scheda Elementi {#items-tab}

![Scheda Elementi della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all’elenco, che contiene le colonne seguenti:

* **Icona** : l’icona del tipo di componente della scheda per una facile identificazione nell’elenco. Passa il puntatore del mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina** : tocca o fai clic per eliminare la scheda dal componente Schede.
* **Riordina** : tocca o fai clic su e trascina per ordinare le schede.

>[!TIP]
>
>Se la finestra di visualizzazione della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono ancora essere aggiunti al componente Carosello trascinando dal browser Componenti e rilasciando il componente Carosello nell’ editor pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).[

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-properties.png)

Nella scheda **Proprietà** , l’autore del contenuto può impostare le diapositive sulla transizione automatica.

* **Transizione automatica delle diapositive**  - Quando è attivo, il componente passa automaticamente alla diapositiva successiva dopo un ritardo specificato.
* **Ritardo transizione** : quando selezioni Diapositive di transizione automatica , questo valore viene utilizzato per definire il ritardo tra le transizioni (in millisecondi).
* **Disattiva la pausa automatica al passaggio del mouse**  - Quando si seleziona l’opzione Transizione  **automatica** slidesis (Transizione automatica), la transizione del carosello si interrompe automaticamente ogni volta che il cursore passa sopra il carosello. Seleziona questa opzione in modo che la transizione non venga sospesa.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

>[!NOTE]
>
>I controlli di avanzamento della diapositiva non sono attivati in modalità **Modifica**. Utilizza l&#39;opzione [**Anteprima** modalità](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) o **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per interagire con il carosello come lettore del contenuto pubblicato.
>
>La funzione di avanzamento automatico non è abilitata in modalità **Modifica** . Utilizza l’opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per visualizzare la funzione di avanzamento automatico come lettore del contenuto pubblicato.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo dell’etichetta ARIA per il componente

## Seleziona il pannello {#select-panel}

L’autore del contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a una diapositiva diversa da modificare e per ridisporre facilmente l’ordine delle diapositive.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, le diapositive configurate vengono visualizzate come un elenco a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle diapositive e si riflette nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguito dalla descrizione della diapositiva con carattere più chiaro.

![Seleziona pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, la visualizzazione nell’editor passa a quella diapositiva.
* La diapositiva può essere riordinata in posizione utilizzando le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come diapositive al componente carosello, definire i valori predefiniti di transizione automatica e quali stili personalizzati sono disponibili per l’autore del contenuto.

### Scheda Proprietà {#properties-tab-1}

La scheda **Proprietà** viene utilizzata per definire le impostazioni predefinite per le transizioni di diapositiva quando un autore di contenuti aggiunge il componente carosello a una pagina.

![Finestra di dialogo Progettazione del componente Carosello](/help/assets/carousel-design.png)

* **Transizione automatica diapositive**  - Definisce se per impostazione predefinita l’opzione per passare automaticamente il carosello alla diapositiva successiva è abilitata quando l’autore del contenuto aggiunge il componente carosello a una pagina.
* **Ritardo transizione** : definisce il valore predefinito del ritardo di transizione tra le diapositive (in millisecondi) quando un autore di contenuti aggiunge il componente carosello a una pagina.
* **Disattiva pausa automatica al passaggio del mouse**  - Definisce se per impostazione predefinita l&#39;opzione per disattivare la pausa automatica delle diapositive è abilitata quando l&#39;autore del contenuto seleziona  **Transizione automatica** slidesis.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto come diapositive al componente Carosello.

La scheda Componenti consentiti funziona allo stesso modo della scheda dello stesso nome quando [definisci i criteri e le proprietà di un contenitore di layout nell’Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Stili {#styles-tab}

Il componente Carosello supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Carosello supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
