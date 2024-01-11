---
title: Consegna delle immagini ottimizzate per il web
description: Scopri in che modo i componenti core possono sfruttare le funzionalità di AEM as a Cloud Service per la consegna delle immagini ottimizzate per il web, per fornire le immagini in modo più efficiente.
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: a312eb7a1dc68a264eaf0938c450a17f7cbc4506
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 95%

---

# Consegna delle immagini ottimizzate per il web {#web-optimized-image-delivery}

Scopri in che modo i componenti core possono sfruttare le funzionalità di AEM as a Cloud Service per la consegna delle immagini ottimizzate per il web, per fornire le immagini in modo più efficiente.

## Panoramica {#overview}

La funzione di AEM as a Cloud Service per la consegna delle immagini ottimizzate per il web offre risorse immagine da DAM in [Formato WebP.](https://developers.google.com/speed/webp) WebP può ridurre la dimensione di download di un’immagine di circa il 25% in media, velocizzando così il caricamento delle pagine.

La consegna di immagini ottimizzate per il web nei componenti core è semplice da attivare e, poiché tutti i browser più comuni supportano WebP, offre all’utente finale un’esperienza trasparente. L’unica differenza che noteranno, infatti, sarà che il contenuto viene caricato più velocemente.

## Attivazione della consegna di immagini ottimizzate per il web per i componenti core {#activating}

Per abilitare la consegna di immagini ottimizzate per il web, modifica un modello di pagina e attiva semplicemente l’opzione **Abilita immagini ottimizzate per il web** nella finestra di dialogo di progettazione del [componente Immagine.](/help/components/image.md#design-dialog) Questa opzione è disponibile per le versioni v1, v2 e v3 del componente Immagine.

Se non hai familiarità con le finestre di dialogo di progettazione e i modelli di pagina AEM, [consulta questo documento.](/help/get-started/authoring.md#pre-configuring-core-components)

![Abilitazione della consegna di immagini ottimizzate per il web nella finestra di dialogo di progettazione](/help/assets/web-optimized-image-delivery.png)

Tutto qui. Le immagini vengono ora consegnate dal componente Immagine in formato WebP.

Dopo aver attivato la consegna di immagini ottimizzate per il web, potresti voler controllare anche la configurazione del dispatcher per verificare che non blocchi la richiesta al servizio di immagini. Gli URL di questo servizio si presentano come segue.

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

Possono essere generalizzati con questa espressione regolare:

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## Verifica della consegna WebP {#verifying}

La consegna delle immagini ottimizzate per il web è trasparente per il consumatore del contenuto e non influisce sul markup. L’unica cosa che l’utente finale noterà è il tempo di caricamento più veloce.

Pertanto, per osservare l’effettivo risultato, è necessario visualizzare il codice sorgente della pagina.

1. In AEM, modifica una pagina basata su un modello in cui è [attivata la consegna di immagini ottimizzate per il web](#activating) per il componente Immagine.
1. Nell’Editor pagina, seleziona il pulsante **Informazioni pagina** in alto a sinistra e quindi **Visualizza come pubblicato**.
1. Utilizzando gli strumenti di sviluppo dei browser, visualizza il codice sorgente della pagina e osserva come il markup risultante rimane invariato, mentre l’immagine nell’attributo `src` punta all’[URL del nuovo servizio per le immagini.](#activating)

## Quando la consegna delle immagini ottimizzate per il web non è disponibile {#fallback}

La consegna delle immagini ottimizzate per il web è disponibile solo in AEM as a Cloud Service. Nei casi in cui non è disponibile, ad esempio se si usa AEM 6.5 on-premise o un’istanza di sviluppo locale, la consegna delle immagini viene eseguita mediante [Adaptive Image Servlet.](/help/developing/adaptive-image-servlet.md)

Così come l’abilitazione della consegna di immagini ottimizzate per il web non influisce sul markup, anche l’utilizzo di Adaptive Image Servlet come fallback non ha alcun effetto sul markup, in quanto viene modificato solo l’URL nell’attributo `src` dell’elemento `img`.

## Domande frequenti {#faq}

### Perché non esiste un’opzione per abilitare le immagini ottimizzate per il web nel mio ambiente? {#missing-option}

La funzione è disponibile solo in AEM as a Cloud Service. Se AEM viene eseguito on-premise o in locale, il componente Immagine utilizza come [fallback](#fallback) Adaptive Image Servlet.

### Perché il servizio non funziona con l’SDK locale? {#local-sdk}

Quando utilizzi l’SDK di AEM su `localhost`, il servizio per le immagini non è disponibile e il rendering delle immagini viene eseguito come [fallback](#fallback) da Adaptive Image Servlet.

Per utilizzare il servizio di consegna delle immagini ottimizzate per il web, implementa il progetto in un ambiente di sviluppo AEMaaCS per poter testare con precisione il funzionamento del servizio per le immagini.

### Perché il servizio non funziona per alcune immagini sulla mia pagina? {#some-images}

Il servizio per le immagini funziona solo per le risorse che si trovano in `/content/dam` e non funziona per le immagini caricate direttamente nella pagina e memorizzate in un oggetto `cq:Page`. Tali risorse verranno consegnate mediante Adaptive Image Servlet come [fallback.](#fallback)

### Perché il servizio visualizza un’immagine di qualità peggiore o limita le dimensioni delle immagini? {#quality}

Il servizio per immagini ottimizzate per il web considera tutte le rappresentazioni di immagini di dimensioni pari o inferiori a 2048 px e sceglie quelle più grandi come base su cui applicare le impostazioni richieste (larghezza, ritaglio, formato, qualità, ecc.).

Il servizio per immagini non aumenta mai la risoluzione delle immagini. Queste rappresentazioni definiscono quindi le dimensioni e la qualità migliori che il servizio per immagini sarà in grado di fornire. Assicurati pertanto che tutte le risorse abbiano una rappresentazione zoom da 2048 px e, in caso contrario, elaborale di nuovo.

### L’URL delle mie immagini termina ancora con .JPG o .PNG, non con .WEBP, e non c&#39;è un attributo SRCSET o un elemento PICTURE. Il servizio utilizza effettivamente formati web ottimizzati? {#content-negotiation}

Per fornire formati WebP, il servizio di consegna delle immagini ottimizzate per il web utilizza una tecnica chiamata “negoziazione dei contenuti”. Questa consiste nel restituire un formato di file WebP anche quando si richiede un file con estensione JPG o PNG, ma solo se il browser che effettua la richiesta ha fornito un’intestazione HTTP “Accept” `image/webp`. I browser che supportano questa tecnica possono fornire tale intestazione; i browser più datati, invece, riceveranno il formato di file JPG o PNG.

Il vantaggio di questa tecnica è che l’elemento `img` e i relativi attributi possono rimanere invariati. Questo offre una compatibilità ottimale per i siti esistenti e garantisce il percorso più fluido possibile per la transizione verso la consegna di immagini ottimizzate per il web.

### Posso utilizzare la consegna di immagini ottimizzate per il web con un componente personalizzato?

Sì, il servizio di consegna delle immagini ottimizzate per il web può essere utilizzato da componenti personalizzati, creati da [estensione del componente Immagine,](/help/developing/customizing.md)

Di seguito è riportata un’interfaccia di servizio che può essere utilizzata per generare l’URL della risorsa.

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>Gli URL diretti incorporati in un’esperienza che non è generata tramite i Componenti core in esecuzione su AEM Sites CS violano i termini di licenza di Media Library.

### Qual è l’URL di un’immagine fornita dal nuovo servizio per immagini? {#url}

Consulta la sezione precedente [Attivazione della consegna di immagini ottimizzate per il web per i componenti core](#activating), dove è riportato un URL di esempio e un’espressione regolare.

### È possibile che le immagini non vengano visualizzate dopo l’abilitazione delle immagini ottimizzate per il web?

No, questo non dovrebbe mai succedere.

* In HTML, il markup non cambia quando si abilitano le immagini ottimizzate per il web; cambia solo il valore dell’attributo SRC per l’elemento immagine.
* Se il nuovo servizio per immagini non è disponibile o non è in grado di elaborare l’immagine desiderata, l’URL generato utilizzerà come [fallback Adaptive Image Servlet.](#fallback)
* Le regole del Dispatcher possono bloccare il servizio per immagini ottimizzate per il web e [devono essere verificate quando si attiva questa funzione.](#activating)
