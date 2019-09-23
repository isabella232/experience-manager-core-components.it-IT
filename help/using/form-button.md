---
title: Componente Pulsante Modulo
seo-title: Componente Pulsante Modulo
description: 'null'
seo-description: Il componente Principale Modulo nascosto consente di includere un campo nascosto in un modulo.
uuid: 22c53cd0-d0bc-4e5d-89f3-5ac4f61a9100
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: a6e2974a-243f-40ab-903c-c7d3e8615bcc
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
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente Pulsante Modulo{#form-button-component}

Il componente di base Pulsante Modulo del componente permette di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante Modulo componente di base consente di creare un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

Le proprietà del pulsante possono essere definite dall'editor del contenuto nella finestra di dialogo [di](form-button.md)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante Modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-button-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/screen_shot_2018-01-12at120021.png)

### HTML {#html}

```
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="button aem-GridColumn aem-GridColumn--default--12">
<button type="BUTTON" class="cmp-form-button" name="loveToast" value="ILoveToast">Click here if you love toast!</button>
</div>

</form>
</div>
```

### JSON {#json}

```
"button":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           ":type":"core/wcm/sandbox/components/form/button/v2/button",
                           "name":"loveToast",
                           "jcr:title":"Click here if you love toast!",
                           "type":"button",
                           "value":"ILoveToast"
                        }
```

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante Modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all'autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-01-12at120433.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo** - Testo visualizzato sul pulsante

   * Se non ne è stato fornito nessuno, per impostazione predefinita viene utilizzato il tipo di pulsante

* **Nome** - Il nome del pulsante, inviato con i dati del modulo
* **Valore** - Il valore del pulsante, inviato con i dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante Modulo supporta AEM [Style System](authoring.md#component-styling).