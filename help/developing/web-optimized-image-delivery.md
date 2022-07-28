---
title: Distribuzione delle immagini ottimizzata per il web
description: Scopri in che modo i componenti core possono sfruttare AEM funzionalità di distribuzione delle immagini ottimizzate per il web di as a Cloud Service per fornire le immagini in modo più efficiente.
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: a134c2593593efef4df7b01e3a870e03e9860640
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Distribuzione delle immagini ottimizzata per il web {#web-optimized-image-delivery}

Scopri in che modo i componenti core possono sfruttare AEM funzionalità di distribuzione delle immagini ottimizzate per il web di as a Cloud Service per fornire le immagini in modo più efficiente.

>[!NOTE]
>
>Il servizio di distribuzione delle immagini ottimizzato per il web è una funzionalità prerelease con la versione di giugno 2022 di AEM as a Cloud Service con GA prevista per luglio.
>
>Per ulteriori informazioni sulle funzioni prerelease di AEMaaCS, consulta il documento [Canale pre-rilascio Adobe Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=it)

## Panoramica {#overview}

La funzione di distribuzione delle immagini ottimizzata per il web di AEM as a Cloud Service offre risorse di immagini da DAM in [Formato WebP.](https://developers.google.com/speed/webp) WebP può ridurre le dimensioni di download di un&#39;immagine di circa il 25% in media, il che si traduce in un caricamento più rapido della pagina.

L’attivazione della distribuzione di immagini ottimizzate per il web nei componenti core è semplice e, poiché tutti i browser più comuni supportano WebP, l’esperienza è trasparente per l’utente finale. L’unica differenza che noteranno è che il contenuto viene caricato più velocemente!

## Attivazione della distribuzione di immagini ottimizzate per il web per i componenti core {#activating}

Per abilitare la distribuzione di immagini ottimizzate per il web, modifica un modello di pagina e attiva semplicemente l’opzione **Abilita immagini ottimizzate per il web** nella finestra di dialogo di progettazione [Componente immagine.](/help/components/image.md#design-dialog) Questa opzione è disponibile per le versioni v1, v2 e v3 del componente immagine.

Se non hai familiarità con le finestre di dialogo di progettazione e i modelli di pagina AEM, [consulta questo documento.](/help/get-started/authoring.md#pre-configuring-core-components)

![Abilitazione della distribuzione di immagini ottimizzate per il web nella finestra di dialogo di progettazione](/help/assets/web-optimized-image-delivery.png)

Tutto qui. Le immagini vengono ora consegnate dal componente Immagine in formato WebP.

Dopo aver attivato la distribuzione di immagini ottimizzata per il web, potresti voler controllare anche la configurazione del dispatcher per verificare che non blocchi la richiesta al servizio di immagini. Gli URL di questo servizio si presentano come segue.

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

Questa espressione regolare può essere generalizzata.

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## Verifica della consegna WebP {#verifying}

La distribuzione delle immagini ottimizzata per il web è trasparente per il consumatore del contenuto e non influisce sul markup. L&#39;unica cosa che un utente finale noterà è il tempo di caricamento più veloce.

Pertanto, per osservare l’effettivo cambiamento di comportamento, è necessario visualizzare l’origine della pagina.

1. In AEM, modifica una pagina basata sul modello in cui [attivazione della distribuzione di immagini ottimizzate per il web](#activating) per il componente immagine.
1. Nell’editor di pagine, seleziona la **Informazioni pagina** in alto a sinistra e quindi **Visualizza come pubblicato**.
1. Utilizzando gli strumenti di sviluppo dei browser, visualizzare l’origine della pagina e vedere come il markup di cui è stato effettuato il rendering rimane invariato, ma che l’immagine nel `src` punti di attributo [l’URL del nuovo servizio immagine.](#activating)

## Quando la distribuzione delle immagini ottimizzata per il web non è disponibile {#fallback}

La distribuzione delle immagini ottimizzata per il web è disponibile solo in AEM as a Cloud Service. Nei casi in cui non è disponibile, ad esempio l’esecuzione di AEM 6.5 on-premise o su un’istanza di sviluppo locale, la consegna delle immagini torna all’utilizzo [Servlet di immagine adattiva.](/help/developing/adaptive-image-servlet.md)

Così come l’abilitazione della distribuzione di immagini ottimizzate per il web non influisce sul markup, anche il ritorno al servlet di immagini adattive non ha alcun effetto sul markup, in quanto solo l’URL nel `src` dell&#39;attributo `img` viene modificato.

## Domande frequenti {#faq}

### Perché non esiste un&#39;opzione simile per abilitare le immagini ottimizzate per il web nel mio ambiente? {#missing-option}

La funzione è disponibile solo su AEM as a Cloud Service. Esecuzione AEM locale o locale, il componente immagine [cascata](#fallback) all’utilizzo del servlet di immagini adattive.

### Perché il servizio non funziona con l&#39;SDK locale? {#local-sdk}

Quando utilizzi l’SDK AEM su `localhost`, il servizio immagine non è disponibile e il rendering delle immagini [cascata](#fallback) all’utilizzo del servlet di immagini adattive.

Per utilizzare il servizio di distribuzione delle immagini ottimizzato per il web, implementa il progetto in un ambiente di sviluppo AEMaaCS per poter testare con precisione il funzionamento del servizio di immagini con il servizio.

### Perché il servizio non funziona per alcune immagini sulla mia pagina? {#some-images}

Il servizio immagine funziona solo per le risorse situate in `/content/dam` e non funziona per le immagini caricate direttamente nella pagina e memorizzate in un `cq:Page` oggetto. Tali risorse verranno comunque consegnate con l&#39;Adaptive Image Servlet come [fallback.](#fallback)

### Perché il servizio visualizza un&#39;immagine di qualità peggiore o limita le dimensioni delle immagini? {#quality}

Il servizio di immagini ottimizzato per il web considera tutte le rappresentazioni di immagini di dimensioni pari o inferiori a 2048 px e sceglie quelle più grandi come base su cui applicare le impostazioni richieste (larghezza, ritaglio, formato, qualità, ecc.).

Il servizio immagine non aggiornerà mai le immagini. Queste rappresentazioni definiscono quindi le dimensioni e la qualità migliori che il servizio di immagini sarà in grado di fornire. Assicurati quindi che tutte le risorse abbiano il rendering dello zoom di 2048px e, in caso contrario, rielaborale.

### L&#39;URL delle mie immagini termina ancora con .JPG o .PNG, non con .WEBP, e non c&#39;è un attributo SRCSET o un elemento PICTURE. Questo utilizza davvero formati web ottimizzati? {#content-negotiation}

Per fornire formati WebP, il servizio di distribuzione delle immagini ottimizzato per il Web utilizza una tecnica chiamata &quot;negoziazione dei contenuti&quot;. Ciò consiste nel restituire un formato di file WebP, anche quando si richiede un&#39;estensione di file JPG o PNG, ma solo quando il browser che effettua la richiesta ha fornito un `image/webp` Intestazione di accettazione HTTP. I browser che supportano questa tecnica possono quindi fornire questa intestazione, e i browser più vecchi otterranno ancora il formato di file JPG o PNG.

Il vantaggio di questa tecnica è che la `img` L’elemento e i relativi attributi possono rimanere invariati, il che porterà a una compatibilità ottimale per i siti esistenti e garantirà il percorso più fluido possibile per la transizione verso la distribuzione di immagini ottimizzate per il web.

### Posso utilizzare la distribuzione di immagini ottimizzate per il web con il mio componente?

Sì, il servizio di distribuzione delle immagini ottimizzato per il web può essere utilizzato da componenti personalizzati. L&#39;Adobe raccomanda [estensione del componente immagine](/help/developing/customizing.md) in questo caso.

Di seguito è riportata un’interfaccia di servizio che può essere utilizzata per generare l’URL della risorsa.

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

Questo servizio considera una risorsa come primo parametro obbligatorio e può prendere una mappa opzionale delle trasformazioni di immagine desiderate da applicare che possono contenere i seguenti parametri.

* `path` - ID risorsa da consegnare, deve essere di modello `([^:\[\]\|\*\/]+)` (ad esempio: `unicorn–1234`)
* `seoname` - Il nome SEO-centric definito dall&#39;utente da aggiungere all&#39;URL dell&#39;immagine, può contenere trattini, deve essere di tipo pattern `([\w-]+)` (ad esempio: `my-friend-the-unicorn`)
* `format` - Il formato dell&#39;immagine desiderato può essere `gif`, `png`, `png8`, `jpg`, `pjpg`, `bjpg`, `webp`, `webpll`, `webply` (ad esempio: `webp`)
* `preferwebp` - Se possibile, distribuire l&#39;output WebP ignorando il `format` parametro ([consulta Domande frequenti sulla negoziazione dei contenuti](#content-negotiation)), booleano (ad esempio: `true`)
* `width` - La risoluzione dell&#39;immagine desiderata in pixel deve essere maggiore di 1 (ad es.: `400`)
* `quality` - La compressione desiderata, tra `1` e `100` (ad esempio: `75`)
* `c` - Le coordinate di ritaglio dell&#39;immagine desiderate, valori di pixel separati da virgole (ad es.: `100,100,400,200`)
* `r` - La rotazione desiderata dell&#39;immagine può essere `90`, `180`, `270` (ad esempio: `90`)
* `flip` - Riflettendo l&#39;immagine desiderata, è possibile `h`, `v`, `hv` (ad esempio: `h`)

### Qual è l’URL di un’immagine fornita dal nuovo servizio immagine? {#url}

Vedi la sezione precedente [Attivazione della distribuzione di immagini ottimizzate per il web per i componenti core](#activating) per un URL di esempio e un’espressione regolare.

### È possibile che le immagini non vengano visualizzate dopo l&#39;abilitazione delle immagini ottimizzate per il Web?

No, questo non dovrebbe mai succedere.

* In HTML, il markup non cambia quando si abilitano immagini ottimizzate per il web, cambia solo il valore dell’attributo SRC sull’elemento immagine.
* Quando il nuovo servizio immagine non è disponibile o non può elaborare l&#39;immagine desiderata, l&#39;URL generato [fallback a Adaptive Image Servlet.](#fallback)
* Le regole del Dispatcher possono bloccare il servizio immagine ottimizzato per il web e [deve essere selezionato quando si attiva la funzione.](#activating)
