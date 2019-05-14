---
title: Personalizzazione dei componenti core
seo-title: Personalizzazione dei componenti core
description: I componenti core implementano diversi pattern che consentono di personalizzare agevolmente, dal semplice stile alla funzionalità avanzata di riutilizzo delle funzionalità.
seo-description: I componenti core AEM implementano diversi pattern che consentono di personalizzare agevolmente, dal semplice stile a quello avanzato delle funzionalità.
uuid: 38 d 22 b 85-4867-4716-817 a -10 ee 2 f 8 de 6 f 5
contentOwner: Utente
content-type: riferimento
topic-tags: sviluppo
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 3 c 9 e 0 ade -1 ce 0-4 e 34-ae 04-8 da 63 f 9 b 6 c 4 f
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# Personalizzazione dei componenti core{#customizing-core-components}

I [componenti core](developing.md) implementano diversi pattern che consentono di personalizzare agevolmente, dal semplice stile alla funzionalità avanzata di riutilizzo delle funzionalità.

## Architettura flessibile {#flexible-architecture}

I componenti core sono stati progettati dall&#39;inizio per essere flessibili ed estensibili. Un&#39;occhiata alla panoramica dell&#39;architettura mostra dove possono essere personalizzate le personalizzazioni.

![Architettura componenti core](assets/screen_shot_2018-12-07at093742.png)

* [La finestra di dialogo Progettazione](authoring.md#edit-and-design-dialogs) definisce ciò che gli autori possono o non possono fare nella finestra di dialogo di modifica.
* [La finestra di dialogo](authoring.md#edit-and-design-dialogs) di modifica mostra agli autori solo le opzioni consentite.
* [Il modello Sling](#customizing-the-logic-of-a-core-component) verifica e prepara il contenuto della visualizzazione (modello).
* [Il risultato del modello Sling](#customizing-the-logic-of-a-core-component) può essere serializzato su JSON per i casi d&#39;uso SPA.
* [HTL esegue il rendering](#customizing-the-markup) del lato server HTML per il rendering sul lato server tradizionale.
* [L&#39;output HTML](#customizing-the-markup) è semantica, accessibile, motore di ricerca e facile da usare.

E tutti i componenti core implementano il [sistema di stile](customizing.md).

## Pattern di personalizzazione {#customization-patterns}

### Personalizzazione delle finestre di dialogo {#customizing-dialogs}

Potrebbe essere necessario personalizzare le opzioni di configurazione disponibili in una finestra di dialogo del componente principale, che sia la finestra di dialogo [Progettazione o la finestra di dialogo di modifica](authoring.md).

Ciascuna finestra di dialogo ha una struttura di nodo coerente. Si consiglia di replicare questa struttura in un componente ereditario, in modo che [Sling Resource Fusion](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) e [Nascondi condizioni](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) possano essere utilizzati per nascondere, sostituire o riordinare sezioni della finestra di dialogo originale. La struttura da replicare viene definita come qualsiasi altro livello fino al livello di nodo dell&#39;elemento tabulazione.

Per essere totalmente compatibili con le modifiche apportate a una finestra di dialogo nella versione corrente, è molto importante che le strutture sotto il livello di elemento della scheda non vengano toccate (nascosta, aggiunta, sostituita, riordinata, ecc.). Al contrario, un elemento di tabulazione dell&#39;elemento principale deve essere nascosto tramite la `sling:hideResource` proprietà (vedere [Sling Resource Fusion Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)) e nuovi elementi di tabulazione che contengono i campi di configurazione dei contenitori. `sling:orderBefore` può essere utilizzato per riordinare gli elementi delle schede, se necessario.

La finestra di dialogo seguente illustra la struttura di finestra di dialogo consigliata e come nascondere e sostituire una scheda ereditata come descritto in precedenza:

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### Personalizzazione della logica di un componente core {#customizing-the-logic-of-a-core-component}

La logica di Business per i componenti core è implementata in Sling Models (Modelli Sling). Questa logica può essere estesa utilizzando un pattern di delega Sling.

Ad esempio, il componente core del titolo utilizza la `jcr:title` proprietà della risorsa richiesta per fornire il testo del titolo. Se non `jcr:title` viene definita alcuna proprietà, viene implementata una fallback al titolo della pagina corrente. Desideriamo modificare il comportamento in modo che il titolo della pagina corrente venga sempre visualizzato.

Poiché l&#39;implementazione dei modelli dei componenti core è privata, deve essere estesa con un pattern di delega.

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

Per ulteriori dettagli sul pattern di delega, consultate il pattern di delega github Wiki Articolo [Delega pattern per Sling Models](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### Personalizzazione della marcatura {#customizing-the-markup}

A volte, lo stile avanzato richiede una struttura di marcatura diversa.

Questa operazione può essere eseguita semplicemente copiando i file HTL che devono essere modificati dal componente Core al componente proxy.

Riassumendo l&#39;esempio del componente Breadcrumb di base, per personalizzare il relativo output di marcatura, il `breadcrumb.html` file deve essere copiato nel componente specifico del sito `sling:resourceSuperTypes` che indica il componente Breadcrumb di base.

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

### Formattazione dei componenti {#styling-the-components}

La prima forma di personalizzazione consiste nell&#39;applicare stili CSS.

Per semplificare questa procedura, i componenti core eseguono il rendering semantica e seguono una convenzione di denominazione standardizzata ispirata a [Bootstrap](https://getbootstrap.com/). Inoltre, per eseguire facilmente il targeting e lo spazio nomi degli stili per i singoli componenti, ogni componente core viene racchiuso in un elemento DIV con le &quot;classi `cmp`&quot; e &quot; `cmp-<name>`&quot;.

Ad esempio, guardando il file HTL del componente BREADCRUMB v 1: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html), viene visualizzata la gerarchia degli `ol.breadcrumb > li.breadcrumb-item > a`elementi. Pertanto, per fare in modo che una regola CSS influisca solo sulla classe breadcrumb del componente, tutte le regole devono essere denominate come indicato di seguito:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Inoltre, ogni componente core sfrutta la funzionalità Sistema [di stile AEM](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) che consente agli autori di modelli di definire nomi di classi CSS aggiuntivi che possono essere applicati al componente dagli autori delle pagine. Questo consente di definire per ogni modello un elenco di stili di componente consentiti e se uno di essi deve essere applicato per impostazione predefinita a tutti i componenti di quel tipo.

## Compatibilità con l&#39;aggiornamento delle personalizzazioni {#upgrade-compatibility-of-customizations}

Sono possibili tre tipi diversi di aggiornamento:

* aggiornamento della versione di AEM
* aggiornamento dei componenti core a una nuova versione secondaria
* aggiornamento dei componenti core a una versione principale

In genere, l&#39;aggiornamento di AEM a una nuova versione non influisce sui componenti core né sulle personalizzazioni effettuate, a condizione che le versioni dei componenti supportino anche la nuova versione AEM alla quale viene trasferito, e che le personalizzazioni non [vengano utilizzate o rimosse](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

L&#39;aggiornamento dei componenti core senza passare a una versione principale più recente non dovrebbe influire sulle personalizzazioni, purché vengano utilizzati i pattern di personalizzazione descritti in questa pagina.

Il passaggio a una versione principale più recente dei Componenti core è compatibile solo con la struttura del contenuto, ma potrebbe essere necessario refacificare le personalizzazioni. I registri di modifica cancellati verranno pubblicati per ogni versione di componente in modo da evidenziare le modifiche che influenzano il tipo di personalizzazioni descritte in questa pagina.

## Supporto delle personalizzazioni {#support-of-customizations}

Come per qualsiasi componente AEM, sono disponibili diverse informazioni relative alle personalizzazioni:

1. **Non modificare mai direttamente il codice dei componenti core.**

   Questo li renderebbe completamente non supportati e rende un processo più doloroso per gli aggiornamenti futuri dei componenti. Utilizzate, invece, i metodi di personalizzazione descritti in questa pagina.

1. **Il codice personalizzato è la vostra responsabilità.**

   Il programma di supporto non copre il codice personalizzato e i problemi segnalati che non possono essere riprodotti con i componenti core vaniglia [utilizzati come documentati non](using.md) saranno idonei.

1. **Guarda la funzionalità obsoleta e rimossa.**

   Con ogni nuova versione di AEM a cui viene aggiornato, assicurati che tutte le API utilizzate siano comunque topiche, tenendo conto della [pagina Funzioni](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) obsoleto e rimossa.

Vedere anche [la sezione Supporto](developing.md#core-component-support) componente core.

**Leggi avanti:**

* [Utilizzo dei componenti](using.md) core: diventa disponibile con componenti core nel tuo progetto.
* [Linee guida sui componenti](guidelines.md) - per apprendere i pattern di implementazione dei componenti core.
