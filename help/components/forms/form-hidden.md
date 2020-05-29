---
title: Componente nascosto modulo
description: Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 3%

---


# Componente nascosto modulo{#form-hidden-component}

Il componente Principale Modulo nascosto consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente di base Modulo nascosto consente la creazione di campi nascosti per riportare in AEM le informazioni sulla pagina corrente e deve essere utilizzato insieme al componente [Contenitore di](form-container.md)moduli.

Le proprietà del campo possono essere definite dall’editor del contenuto nella finestra di dialogo [di](form-hidden.md)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Nascosto modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | - | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-hidden-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Nascosto modulo e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_form_hidden)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Nascosto modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del campo nascosto.

![Finestra di dialogo di modifica nascosta al modulo](/help/assets/form-hidden-edit.png)

* **Nome** - Il nome del campo, inviato con i dati del modulo
* **Valore** - Il valore del campo, inviato con i dati del modulo
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

Poiché in genere il componente Nascosto modulo non ha attributi visibili, il segnaposto del componente nell’editor visualizza i valori dei campi **Nome** e **Valore** , se assegnati per consentire all’autore di identificare il componente Nascosto modulo appropriato.

![Esempio di componente nascosto del modulo](/help/assets/form-hidden-example.png)

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Nascosto modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
