---
title: Componente Pulsante modulo (v 1)
seo-title: Componente Pulsante modulo (v 1)
description: 'null'
seo-description: Il componente Modulo componente core consente l'inclusione di un campo nascosto in un modulo.
uuid: 0525 e 70 f -294 f -4 d 35-bf 96-fc 0 e 4 ec 225 e 9
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: ea 06 acc 0-38 e 2-4252-ac 29-07332835 b 7 c 4
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente Pulsante modulo (v 1){#form-button-component-v}

Il componente Pulsante modulo componente core consente l&#39;inclusione di un campo pulsante in un modulo per attivare un&#39;azione.

## Utilizzo {#usage}

Il componente Pulsante modulo di base consente la creazione di un campo pulsante, spesso per attivare l&#39;invio del modulo e può essere utilizzato insieme al [componente Contenitore del modulo](form-container.md).

Le proprietà del pulsante possono essere definite dall&#39;editor contenuto nella finestra di dialogo [Configura](form-button-v1.md#main-pars_title).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Pulsante modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Pulsante modulo.

| Versione di AEM | Componente pulsante modulo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Pulsante modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Pulsante modulo, vedere [il documento Componente](form-button.md) Pulsante modulo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire i parametri del pulsante.

![](assets/chlimage_1-49.png)

* **Tipo**
   * **Pulsante**
   * **Invia**

* **Titolo** : testo visualizzato sul pulsante
   * Se nessuno fornisce impostazioni predefinite, il tipo di pulsante

* **Nome** : il nome del pulsante, che viene inviato insieme ai dati del modulo
* **Valore** : il valore del pulsante, che viene inviato insieme ai dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

Non esiste alcuna finestra di dialogo per il componente Pulsante modulo.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente Pulsante modulo [è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
