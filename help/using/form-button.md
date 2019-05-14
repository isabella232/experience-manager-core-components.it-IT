---
title: Componente pulsante modulo
seo-title: Componente pulsante modulo
description: 'null'
seo-description: Il componente Modulo componente core consente l'inclusione di un campo nascosto in un modulo.
uuid: 22 c 53 cd 0-d 0 bc -4 e 5 d -89 f 3-5 ac 4 f 61 a 9100
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: a 6 e 2974 a -243 f -40 ab -903 c-c 7 d 3 e 8615 bcc
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


# Componente pulsante modulo{#form-button-component}

Il componente Pulsante modulo componente core consente l&#39;inclusione di un pulsante per attivare un&#39;azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante modulo componente di base consente la creazione di un campo pulsante, spesso per attivare l&#39;invio del modulo e può essere utilizzato insieme al [componente Contenitore modulo](form-container.md).

Le proprietà del pulsante possono essere definite dall&#39;editor contenuto nella finestra di dialogo [Configura](form-button.md).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante modulo è v 2, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-button-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

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

La documentazione tecnica più recente relativa al componente Pulsante modulo [è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-01-12at120433.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo** : testo visualizzato sul pulsante

   * Se nessuno fornisce impostazioni predefinite, il tipo di pulsante

* **Nome** : il nome del pulsante, che viene inviato insieme ai dati del modulo
* **Valore** : il valore del pulsante, che viene inviato insieme ai dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante modulo supporta il sistema [di stile AEM](authoring.md#component-styling).