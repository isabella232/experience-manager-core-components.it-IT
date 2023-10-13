---
title: Supporto Dynamic Media di nuova generazione
description: Scopri come configurare i Componenti core Immagine e Teaser per supportare le risorse Dynamic Media di nuova generazione remote.
role: Architect, Developer, Admin, User
exl-id: b462c1f3-a6c8-4a2a-abf4-d08ec82d4371
source-git-commit: 79cedf7099e2dc267a4cb1c25c06d4f0460367b2
workflow-type: ht
source-wordcount: '470'
ht-degree: 100%

---

# Supporto Dynamic Media di nuova generazione {#next-gen-dm-support}

Scopri come configurare i Componenti core Immagine e Teaser per supportare le risorse Dynamic Media di nuova generazione remote.

## Scarica la versione più recente di AEM {#latest}

Il supporto per le risorse remote di Dynamic Media di nuova generazione richiede:

* AEM 6.5 SP 18+ o AEM as a Cloud Service
* Componenti Core versione 2.23.2 o successiva

## Configurare HTTPS {#https}

In genere si consiglia di eseguire tutte le istanze di produzione AEM utilizzando HTTP. Tuttavia, gli ambienti di sviluppo locali potrebbero non essere configurati come tali. In ogni caso, le risorse remote di Dynamic Medie di nuova generazione richiedono HTTPS per funzionare.

Per configurare HTTPS ovunque desideri utilizzare le risorse remote, inclusi gli ambienti di sviluppo, [utilizza questa guida](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html?lang=it).

## Configurare OSGi {#osgi}

La posizione delle risorse remote deve essere definita in una configurazione OSGi. Configura la configurazione OSGi della **Configurazione Dynamic Media di nuova generazione** come segue, sostituendo i valori con quelli dell’ambiente delle risorse remote.

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![Finestra di configurazione OSGi della configurazione di Dynamic Media di nuova generazione](/help/assets/remote-assets-osgi.png)

Per informazioni dettagliate su come configurare OSGi, consulta i seguenti documenti:

* [Configurazione di OSGi per Adobe Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html?lang=it) per AEM as a Cloud Service
* [Configurazione di OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?lang=it) per AEM 6.5

## Verificare la configurazione {#verify}

Ora puoi verificare che la funzione risorse remote di Dynamic Media di nuova generazione funzioni. A questo scopo, puoi installare il sito di esempio WKND e i Componenti core.

* È richiesta la versione 2.23.2 o successiva dei [Componenti core](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip).
* È richiesta la versione 3.2.0 o successiva del.[sito di esempio WKND](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip).

Una volta installati i Componenti core e il sito WKND, puoi testare la funzione in qualsiasi pagina WKND.

1. Accedi all’istanza di AEM utilizzando HTTPS.

1. Apri una pagina di dimostrazione WKND nell’editor pagina, ad esempio `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. Aggiungi un componente immagine alla pagina.

1. Nella finestra di dialogo Configurazione del componente, deseleziona l’opzione **Eredita immagine in primo piano dalla pagina** sulla scheda **Risorsa** e fai clic su **Scegli**.

1. Se la configurazione è corretta, viene visualizzato un elenco a discesa con le opzioni **Locale** e **Remota**. Seleziona **Remota**.

   ![Opzioni di selezione remota e locale per la selezione delle immagini](/help/assets/remote-asset-selection.png)

1. Verrà aperta una finestra di dialogo e sarà necessario eseguire l’autenticazione al servizio remoto.

1. Una volta autenticato, si aprirà un browser risorse del servizio remoto. Seleziona la risorsa desiderata e tocca o fai clic su **Seleziona**.

   ![Selezione di una risorsa remota](/help/assets/remote-asset-picker.png)

La risorsa remota viene aggiunta alla pagina AEM locale e hai verificato che la funzione sia configurata correttamente.

## Utilizzo di risorse remote {#using}

Una volta configurate, è possibile selezionare le risorse remote da cui selezionare le risorse utilizzando i Componenti core, ad esempio nel [componente Immagine](/help/components/image.md) e [componente Teaser.](/help/components/teaser.md)
