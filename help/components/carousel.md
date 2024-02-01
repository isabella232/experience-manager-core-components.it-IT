---
title: Componente Carosello
description: Il componente Carosello consente all’autore di contenuto di presentare il contenuto in un carosello rotante.
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 94%

---


# Componente Carosello{#carousel-component}

Il componente core Carosello consente all’autore di contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Con il componente Carosello, l’autore di contenuto può organizzare il contenuto in un carosello rotante di diapositive.

La [finestra di dialogo per modifica](#edit-dialog) consente all’autore di contenuto di creare, denominare e ordinare più diapositive, nonché attivare la transizione automatica con ritardo. Utilizzando la [finestra di dialogo per progettazione](#design-dialog), l’autore del modello può definire quali componenti possono essere aggiunti al carosello, abilitare o disabilitare le transizioni automatiche e personalizzare gli stili.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Carosello è la v1, introdotta con la versione 2.2.0 dei Componenti core a ottobre 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Carosello e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_carousel_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Carosello [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Collegamento direttio a un pannello {#deep-linking}

I componenti Carosello, [Schede](tabs.md) e [Pannello a soffietto](accordion.md) supportano il collegamento diretto a un pannello all’interno del componente.

Per effettuare questo collegamento:

1. Visualizza la pagina del componente utilizzando l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** nell’editor di pagine.
1. Esamina il contenuto della pagina e identifica l’ID del pannello.
   * Esempio `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. L’ID diventa l’ancoraggio che puoi aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

Navigando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e lo visualizza. Se il pannello è configurato per non essere visualizzato per impostazione predefinita, verrà fatto scorrere automaticamente.

## Carosello e design reattivo {#responsive-design}

Tutti i Componenti core sono progettati per essere completamente reattivi, garantendo un’esperienza fluida su tutti i dispositivi.

Alcuni componenti avanzati, come il componente Carosello, possono richiedere una considerazione specifica nel contesto del progetto di implementazione per mantenere la reattività in tutte le condizioni. Consulta il documento [Progettazione reattiva dei Componenti core](/help/responsive.md) per ulteriori informazioni.

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di aggiungere, rinominare e ridisporre le diapositive e di definire le impostazioni di transizione automatica.

### Scheda Elementi {#items-tab}

![Scheda Elementi della finestra di dialogo per modifica del componente Carosello](/help/assets/carousel-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene le seguenti colonne:

* **Icona**: l’icona del tipo di componente della scheda per una facile identificazione nell’elenco. Passa il puntatore del mouse sulla voce per visualizzare il nome completo del componente sotto forma di descrizione comando.
* **Descrizione**: la descrizione utilizzata come testo della scheda; per impostazione predefinita è il nome del componente selezionato per la scheda.
* **Elimina**: tocca o fai clic per eliminare la scheda dal componente Schede.
* **Riordina**: tocca o fai clic e trascina per ordinare le schede.

>[!TIP]
>
>Se il riquadro di visualizzazione della pagina viene ridotto in modo che la finestra di dialogo per modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono comunque essere aggiunti al componente Carosello [trascinandoli dal browser dei componenti e rilasciandoli sul componente Carosello nell’editor di pagine](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#inserting-a-component-from-the-components-browser).

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Carosello](/help/assets/carousel-edit-properties.png)

Nella scheda **Proprietà**, l’autore di contenuto può impostare la transizione automatica delle diapositive.

* **Elemento attivo**: l’autore di contenuto può definire quale scheda è attiva al caricamento della pagina.
* **Transizione automatica diapositive**: se selezionata, il componente avanza automaticamente alla diapositiva successiva dopo un tempo di ritardo specificato.
* **Ritardo transizione**: se è selezionata l’opzione Transizione automatica diapositive, questo valore viene utilizzato per definire il ritardo tra le transizioni (espresso in millisecondi).
* **Disabilita pausa automatica al passaggio del mouse**: se è selezionata l’opzione **Transizione automatica diapositive**, la transizione del carosello si interrompe automaticamente ogni volta che il cursore passa sopra il carosello. Seleziona questa opzione per evitare che la transizione venga sospesa.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

>[!NOTE]
>
>I controlli di avanzamento delle diapositiva non sono attivi in modalità **Modifica**. Utilizza la modalità [**Anteprima** oppure](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#preview-mode) l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** per interagire con il carosello come farebbe un normale lettore del contenuto pubblicato.
>
>La funzione di avanzamento automatico non è abilitata in modalità **Modifica**. Utilizza l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** per visualizzare la funzione di avanzamento automatico come farebbe un normale lettore del contenuto pubblicato.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo per modifica del componente Carosello](/help/assets/carousel-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: valore di un attributo aria-label per il carosello che ne descrive il contenuto
* **Precedente**: valore di un attributo aria-label per l’etichetta del pulsante Precedente della navigazione del carosello
* **Successivo**: valore di un attributo aria-label per l’etichetta del pulsante Successivo della navigazione del carosello
* **Riproduci**: valore di un attributo aria-label per l’etichetta del pulsante Riproduci della navigazione del carosello
* **Pausa**: valore di un attributo aria-label per l’etichetta del pulsante Pausa della navigazione del carosello
* **Tablist**: valore di un attributo aria-label per l’etichetta dell’elenco degli elementi della navigazione del carosello
* **Imposta l’aria-label dell’elemento sul relativo titolo**: se questa opzione è selezionata, il titolo degli elementi del carosello viene impostato automaticamente sulla relativa descrizione aria-label.

## Seleziona pannello {#select-panel}

L’autore di contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a una diapositiva diversa da modificare e per cambiare facilmente l’ordine delle diapositive.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, le diapositive configurate vengono visualizzate come un elenco a discesa.

* L’elenco viene ordinato in base alla disposizione assegnata alle diapositive, che si evidenzia nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguito dalla descrizione della diapositiva in caratteri più chiari.

![Seleziona pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, nell’editor viene visualizzata la diapositiva corrispondente.
* La diapositiva può essere riposizionata tramite le maniglie di trascinamento.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come diapositive al componente Carosello, i valori predefiniti della transizione automatica e quali stili personalizzati sono disponibili per l’autore di contenuto.

### Scheda Proprietà {#properties-tab-1}

La scheda **Proprietà** viene utilizzata per definire le impostazioni predefinite delle transizioni delle diapositive, quando un autore di contenuto aggiunge il componente Carosello a una pagina.

![Finestra di dialogo per progettazione del componente Carosello](/help/assets/carousel-design.png)

* **Transizione automatica diapositive**: definisce se per impostazione predefinita l’opzione per far avanzare il carosello alla diapositiva successiva è abilitata, quando l’autore di contenuto aggiunge il componente Carosello a una pagina.
* **Anteponi elementi di controllo**: se questa opzione è selezionata, gli elementi di controllo vengono posizionati prima degli elementi del carosello, per migliorarne l’accessibilità.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore di contenuto come elementi del componente Carosello.

La scheda Componenti consentiti funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore layout nell’editor di modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Stili {#styles-tab}

Il componente Carosello supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Carosello supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
