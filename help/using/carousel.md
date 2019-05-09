---
title: Componente Carosello
seo-title: Componente Carosello
description: 'null'
seo-description: Il componente Carosello consente all'autore del contenuto di presentare il contenuto in un carosello rotante.
uuid: 34934491-bd 85-4 f 1 e-ae 22-bb 48 ed 4 dbd 5 c
content-type: riferimento
topic-tags: componenti core
discoiquuid: 3510812 b -9 d 3 e -40 fe-b 986-0 f 15 d 40 b 42 ad
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente Carosello{#carousel-component}

Il componente Carosello componente core consente all&#39;autore del contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Utilizzo del componente Carosello, l&#39;autore del contenuto per organizzare il contenuto in un carosello di diapositive.

La [finestra di dialogo](#edit-dialog) di modifica consente all&#39;autore del contenuto di creare, assegnare un nome e ordinare più diapositive, nonché di abilitare la transizione automatica con ritardo. Mediante la finestra di dialogo [](#design-dialog)di progettazione, l&#39;autore del modello può definire quali componenti aggiungere al carosello, abilitare o disabilitare le transizioni automatiche e personalizzare gli stili.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Carosello è v 1, introdotta con la release 2.2.0 dei componenti core a ottobre 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/screenshot_2018-11-28at140433.png)

### Libreria componenti {#component-library}

Per provare il componente Carosello e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Carosello è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di aggiungere, rinominare e ridisporre le diapositive e definire le impostazioni di transizione automatica.

### Scheda Elementi {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

Per aprire il selettore componenti, usate il **pulsante Aggiungi** per scegliere quale componente aggiungere come scheda. Una volta aggiunta, all&#39;elenco viene aggiunta una voce contenente le colonne seguenti:

* **Icona** : l&#39;icona del tipo di componente della scheda per facilitarne l&#39;identificazione. Passate il mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, in base al nome del componente selezionato per la scheda.
* **Elimina** : toccate o fate clic per eliminare la scheda dal componente Schede.
* **Riordina** : toccate o fate clic e trascinate per ordinare le schede.

### Scheda Proprietà {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

Nella scheda **Proprietà** , l&#39;autore del contenuto può impostare le diapositive in modo che si transigano automaticamente.

* **Transizione automatica delle diapositive** : quando è attiva, il componente avanza automaticamente alla diapositiva successiva dopo un ritardo specificato.
* **Ritardo transizione -** Quando si seleziona automaticamente le diapositive, questo valore viene usato per definire il ritardo tra transizioni (in millisecondi).
* **Disattiva la pausa automatica al passaggio del mouse** : quando **sono selezionate automaticamente le diapositive** , la transizione carosello si interrompe automaticamente ogni volta che il cursore passa sopra il carosello. Selezionate questa opzione per evitare pause.

>[!NOTE]
>
>I controlli progressivi delle diapositive non sono attivati in modalità **Modifica** . Utilizzare [**la modalità Anteprima**](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) o l&#39;opzione **[Visualizza come pubblicato](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** per interagire con il carosello come un lettore del contenuto pubblicato.
>
>La funzione Avanzamento automatico non è abilitata in modalità **Modifica** . L&#39;opzione **[Visualizza come pubblicato](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** consente di visualizzare la funzione automatica come lettore del contenuto pubblicato.

## Seleziona pannello {#select-panel}

L&#39;autore del contenuto può utilizzare l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a una diapositiva diversa e riorganizzare l&#39;ordine delle diapositive.

![](assets/screenshot_2018-10-11at165417.png)

Una volta selezionata l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, le diapositive configurate vengono visualizzate come a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle diapositive e si riflette nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguita dalla descrizione della diapositiva in font più chiaro.

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* Toccando o facendo clic su una voce nel menu a discesa, viene attivata la visualizzazione nell&#39;editor a quella diapositiva.
* La diapositiva può essere riorganizzata in locale utilizzando le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire quali componenti aggiungere come diapositive al componente carosello, nonché definire i valori predefiniti di transizione automatica e gli stili personalizzati disponibili per l&#39;autore del contenuto.

### Scheda Proprietà {#properties-tab-1}

La **scheda Proprietà** viene utilizzata per definire le impostazioni predefinite per le transizioni delle diapositive quando un autore aggiunge il componente Carosello a una pagina.

![](assets/screenshot_2018-11-28at141824.png)

* **Scorrimento automatico delle diapositive** - Definisce se per impostazione predefinita l&#39;opzione di avanzamento automatico della sequenza alla diapositiva successiva viene attivata quando l&#39;autore del contenuto aggiunge il componente carosello a una pagina.
* **Ritardo transizione** - Definisce il valore predefinito del ritardo di transizione tra le diapositive (in millisecondi) quando un autore aggiunge il componente carosello a una pagina.
* **Disattiva pausa automatica al passaggio del mouse** - Definisce se per impostazione predefinita l&#39;opzione Disattiva la pausa automatica delle diapositive è abilitata quando **l&#39;autore del contenuto seleziona automaticamente le diapositive** .

### Scheda Componenti consentiti {#allowed-components-tab}

La **scheda Componenti** consentiti viene utilizzata per definire quali componenti possono essere aggiunti come diapositive al componente Carosello dall&#39;autore del contenuto.

Le funzioni scheda Componenti consentiti funzionano come la scheda con lo stesso nome quando [si definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Scheda Stili {#styles-tab}

Il componente Carosello supporta il sistema [di stile AEM](authoring.md#component-styling).