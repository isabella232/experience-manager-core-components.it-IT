---
title: Componente carosello
seo-title: Componente carosello
description: 'null'
seo-description: Il componente Carosello consente all’autore del contenuto di presentare il contenuto in un carosello a rotazione.
uuid: 34934491-bd85-4f1e-ae22-bb48ed4dbd5c
content-type: riferimento
topic-tags: core-components
discoiquuid: 3510812b-9d3e-40fe-b986-0f15d40b42ad
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d37cde072dea612ccb55ad31b4aaf42f17839cb4

---


# Componente carosello{#carousel-component}

Il componente Carosello dei componenti core consente all’autore del contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Con il componente Carosello, l’autore del contenuto organizza il contenuto in un carosello rotante di diapositive.

La finestra di dialogo [di](#edit-dialog) modifica consente all’autore del contenuto di creare, assegnare un nome e ordinare più diapositive, nonché attivare la transizione automatica con ritardo. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, l’autore del modello può definire quali componenti possono essere aggiunti al carosello, attivare o disattivare le transizioni automatiche e personalizzare gli stili.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Carosello è v1, introdotto con la release 2.2.0 dei componenti core a ottobre 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Carosello ed esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Carosello [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di aggiungere, rinominare e ridisporre le diapositive nonché di definire le impostazioni di transizione automatica.

### Scheda Articoli {#items-tab}

![](assets/screen-shot-2019-08-29-12.01.39.png)

Usate il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all'elenco, che contiene le seguenti colonne:

* **Icona** - L'icona del tipo di componente della scheda per una facile identificazione nell'elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina** - Toccate o fate clic per eliminare la scheda dal componente Tabulazioni.
* **Riordina** - Toccate o fate clic e trascinate per ordinare le schede.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.01.57.png)

Nella scheda **Proprietà** , l'autore del contenuto può impostare le diapositive per la transizione automatica.

* **Transizione automatica delle diapositive** - Quando è attiva, il componente passa automaticamente alla diapositiva successiva dopo un ritardo specificato.
* **Ritardo** transizione: quando è selezionata l'opzione Transizione automatica diapositive, questo valore viene utilizzato per definire il ritardo tra le transizioni (in millisecondi).
* **Disattiva pausa automatica al passaggio del mouse** : quando si selezionano le diapositive **di transizione** automatica, la transizione del carosello si interrompe automaticamente ogni volta che il cursore passa sul carosello. Selezionate questa opzione per evitare che la transizione venga messa in pausa.

>[!NOTE]
>
>I controlli di avanzamento delle diapositive non sono attivati in modalità **Modifica** . Per interagire con il carosello come lettore del contenuto pubblicato, utilizzate la modalità [**** Anteprima](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) o l’opzione **[Visualizza come pubblicato](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** .
>
>La funzione di avanzamento automatico non è abilitata in modalità **Modifica** . Usate l’opzione **[Visualizza come pubblicato](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** per visualizzare la funzione di avanzamento automatico come lettore del contenuto pubblicato.

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.02.22.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per le etichette di accessibilità [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA per il componente.

* **Etichetta** - Valore di un attributo etichetta ARIA per il componente

## Select Panel {#select-panel}

L’autore del contenuto può usare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un’altra diapositiva da modificare e per riordinare facilmente l’ordine delle diapositive.

![](assets/screenshot_2018-10-11at165417.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, le diapositive configurate vengono visualizzate come un elenco a discesa.

* L'elenco è ordinato dalla disposizione assegnata delle diapositive e si riflette nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguito dalla descrizione della diapositiva con il carattere più chiaro.

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* Toccando o facendo clic su una voce nel menu a discesa, passa alla diapositiva la vista nell’editor.
* La diapositiva può essere riordinata in posizione utilizzando le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti al componente carosello come diapositive, nonché definire le impostazioni predefinite per la transizione automatica e quali stili personalizzati sono disponibili per l’autore del contenuto.

### Scheda Proprietà {#properties-tab-1}

La scheda **Proprietà** consente di definire le impostazioni predefinite per le transizioni di diapositiva quando un autore di contenuto aggiunge il componente carosello a una pagina.

![](assets/screenshot_2018-11-28at141824.png)

* **Transizione automatica diapositive** - Definisce se per impostazione predefinita l’opzione per spostare automaticamente il carosello nella diapositiva successiva è abilitata quando l’autore del contenuto aggiunge il componente carosello a una pagina.
* **Ritardo** transizione - Definisce il valore predefinito del ritardo di transizione tra le diapositive (in millisecondi) quando un autore di contenuto aggiunge il componente carosello a una pagina.
* **Disattiva pausa automatica al passaggio del mouse** - Definisce se per impostazione predefinita l'opzione per disattivare la pausa automatica delle diapositive è abilitata quando l'autore del contenuto seleziona le diapositive **di transizione** automatica.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda Componenti **** consentiti viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto al componente Carosello come diapositive.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si [definisce il criterio e le proprietà di un Contenitore di layout nell'Editor modelli.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Scheda Stili {#styles-tab}

Il componente Carosello supporta AEM [Style System](authoring.md#component-styling).
