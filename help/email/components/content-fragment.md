---
title: Componente Frammento di contenuto e-mail
description: Il componente Frammento di contenuto e-mail consente di visualizzare un frammento di contenuto nel contenuto.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 34%

---


# Componente Frammento di contenuto e-mail {#email-content-fragment-component}

Il componente Frammento di contenuto e-mail consente la visualizzazione di un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it) nel contenuto.

## Utilizzo {#usage}

Il componente Frammento di contenuto e-mail consente di includere un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) nel contenuto dell’e-mail. I frammenti di contenuto sono contenuti strutturati multicanale che possono essere creati a livello centrale e riutilizzati facilmente.

* Il frammento e le relative proprietà possono essere selezionati nella [finestra di dialogo per configurazione.](#configure-dialog)
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella [finestra di dialogo per progettazione.](#design-dialog)
* L’opzione di modifica apre il frammento selezionato all’interno del [editor frammento di contenuto,](#edit-dialog) personalizzati per l’utilizzo con i componenti core e-mail.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto e-mail è v1, introdotta con la versione X dei componenti core e-mail nell’ottobre 2022, ed è descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e le versioni dei componenti core e-mail, consulta il documento [Versioni dei componenti core di e-mail.](/help/email/versions.md)

## Esempio di output del componente {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Frammento di contenuto e-mail e dell’output HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_cf)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto e-mail [si trova su GitHub.](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire quale frammento di contenuto e gli elementi di tale frammento includere.

### Scheda Proprietà {#properties-tab}

![Componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Il percorso del Frammento di contenuto desiderato
   * Per individuare il Frammento è possibile utilizzare la **finestra di dialogo per selezione**

* **Modalità di visualizzazione**
   * **Elemento di testo singolo**: consente la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
* **Variante**: la variante del Frammento di contenuto da utilizzare (l’impostazione predefinita è **Principale**)

* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.

### Scheda Controllo paragrafo {#paragraph-control-tab}

![Componente Frammento di contenuto e-mail](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi**: consente di selezionare tutti o un intervallo di paragrafi
   * **Tutti**: visualizza tutti i paragrafi
   * **Intervallo**
      * Specificare gli intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Per esempio `1;3-5;7;9-*` includere il primo, il terzo al quinto, il settimo e il nono al terzo comma
* **Tratta le intestazioni come paragrafi**

## Finestra di dialogo per la modifica {#edit-dialog}

Dopo aver utilizzato il componente Frammento di contenuto e-mail per configurare un frammento di contenuto, quando selezioni il componente nell’editor di contenuti, viene visualizzata una **Modifica** opzione .

![Barra degli strumenti del componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-edit-toolbar.png)

Tocca o fai clic sul pulsante **Modifica** apre l’editor frammento di contenuto. L’editor dei frammenti di contenuto è stato esteso per includere pulsanti per **Seleziona variabile Adobe Campaign** per inserire variabili Adobe Campaign nei frammenti di contenuto.

![Editor frammento di contenuto per e-mail](/help/email/assets/email-content-fragment-editor.png)

Per ulteriori informazioni sulla modifica e la creazione di frammenti di contenuto, consulta il documento [Creazione di contenuti di frammento](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## Finestra di dialogo per la progettazione {#design-dialog}

Quando un componente Frammento di contenuto e-mail è configurato con un frammento di contenuto, quando lo selezioni nell’editor di contenuti, la barra degli strumenti mostra un pulsante per aprire l’editor frammento di contenuto.


### Scheda Principale {#main-tab}

![Finestra di dialogo Progettazione del componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)
