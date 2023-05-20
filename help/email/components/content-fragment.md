---
title: Componente Frammento di contenuto e-mail
description: Il componente Frammento di contenuto e-mail consente di visualizzare un frammento di contenuto nel contenuto.
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---


# Componente Frammento di contenuto e-mail {#email-content-fragment-component}

Il componente Frammento di contenuto e-mail consente di visualizzare un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it) nel contenuto.

## Utilizzo {#usage}

Il componente Frammento di contenuto e-mail consente di includere un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it) nel contenuto dell’e-mail. I frammenti di contenuto sono contenuti strutturati multicanale che possono essere creati a livello centrale e riutilizzati facilmente.

* Il frammento e le relative proprietà possono essere selezionati nella [finestra di dialogo per configurazione.](#configure-dialog)
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella [finestra di dialogo per la progettazione.](#design-dialog)
* L’opzione di modifica apre il frammento selezionato all’interno dell’[editor frammento di contenuto](#edit-dialog), personalizzato per l’utilizzo con i componenti core e-mail.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto e-mail è la v1, introdotta con la versione X dei componenti core E-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei componenti core E-mail, consulta il documento [Versioni dei componenti core E-mail.](/help/email/versions.md)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto e-mail [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo per la configurazione consente all’autore del contenuto di definire il frammento di contenuto e gli elementi di quel frammento da includere.

### Scheda Proprietà {#properties-tab}

![Componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Il percorso del Frammento di contenuto desiderato
   * Per individuare il Frammento è possibile utilizzare la **finestra di dialogo per selezione**

* **Modalità di visualizzazione**
   * **Elemento di testo singolo**: consente la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
* **Variante**: la variante del Frammento di contenuto da utilizzare (l’impostazione predefinita è **Principale**)

* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile esaminando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.

### Scheda Controllo paragrafo {#paragraph-control-tab}

![Componente Frammento di contenuto e-mail](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi**: consente di selezionare tutti o un intervallo di paragrafi
   * **Tutto**: visualizza tutti i paragrafi
   * **Intervallo**
      * Specificare gli intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Per esempio `1;3-5;7;9-*` per includere il primo, dal terzo al quinto, il settimo e dal nono ai paragrafi finali
* **Tratta le intestazioni come paragrafi**

## Finestra di dialogo per la modifica {#edit-dialog}

Dopo aver utilizzato il componente Frammento di contenuto e-mail per configurare un frammento di contenuto, quando selezioni il componente nell’editor di contenuti, viene visualizzata un’opzione **Modifica**.

![Barra degli strumenti del componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-edit-toolbar.png)

Toccando o facendo clic sul pulsante **Modifica** si apre l’editor del frammento di contenuto. L’editor del frammento di contenuto è stato esteso per includere i pulsanti **Seleziona variabile di Adobe Campaign** per inserire variabili di Adobe Campaign nei frammenti di contenuto.

![Editor frammento di contenuto per e-mail](/help/email/assets/email-content-fragment-editor.png)

Per ulteriori informazioni sulla modifica e l’authoring di frammenti di contenuto, consulta il documento [Authoring dei contenuti di frammenti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html?lang=it).

## Finestra di dialogo per la progettazione {#design-dialog}

Se un componente Frammento di contenuto e-mail è configurato con un frammento di contenuto, quando lo selezioni nell’editor di contenuti, la barra degli strumenti mostra un pulsante per aprire l’editor frammento di contenuto.


### Scheda Principale {#main-tab}

![Finestra di dialogo per la progettazione del componente Frammento di contenuto e-mail](/help/email/assets/email-content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
