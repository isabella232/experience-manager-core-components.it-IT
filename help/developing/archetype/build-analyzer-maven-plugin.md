---
title: AEM come Cloud Service SDK Build Analyzer Maven Plugin
description: Documentazione per il plug-in dell'analizzatore Maven
translation-type: tm+mt
source-git-commit: 37ec5c245d3806d98dd8a8538c81fc10154a2dfc
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---


# AEM come Cloud Service SDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

Il AEM come Cloud Service SDK Build Analyzer Maven Plugin analizza la struttura dei vari progetti di pacchetti di contenuto.

Per informazioni su come includerlo in un progetto AEM Paradiso, vedere la [Documentazione del plug-in Maven](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md).

Di seguito è riportata una tabella che descrive gli analizzatori eseguiti come parte di questo passaggio. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modulo | Funzione, esempio e risoluzione dei problemi | SDK locale | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Controlla se tutti i bundle OSGI presentano dichiarazioni Import-Package soddisfatte dalla dichiarazione Export-Package di altri pacchetti inclusi nel progetto Maven. L&#39;aspetto di un errore è il seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Per risolvere i problemi, consultate se il bundle che fornisce il pacchetto è incluso nella distribuzione, oppure guardate il manifesto del bundle che prevedete di esportare per determinare se è stato utilizzato il nome sbagliato o la versione errata. | Sì | Sì |
| `requirements-capabilities` | Controlla se tutte le dichiarazioni di requisiti effettuate nei bundle OSGI sono soddisfatte dalle dichiarazioni di capacità di altri bundle inclusi nel progetto Maven. L&#39;aspetto di un errore è il seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Per risolvere i problemi, controllate il manifesto del bundle che prevedete di dichiarare una capacità per determinare il motivo della sua assenza, o controllate il manifesto del bundle che richiede per verificare che il requisito in esso contenuto sia corretto. | Sì | Sì |
| `bundle-content` | Visualizza un avviso se un bundle contiene il contenuto iniziale specificato con Sling-Initial-Content, che è problematico in AEM come ambiente cluster di Cloud Service. L&#39;avviso è simile al seguente: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Per risolvere i problemi relativi alla conversione del contenuto iniziale in istruzioni di reindirizzamento, consulta Repoinit Documentazione. | Sì | Sì |
| `bundle-resources` | Visualizza un avviso se un bundle contiene risorse specificate con l’intestazione Sling-Bundle-Resources, problema nell’AEM come ambiente cluster di Cloud Service. L&#39;avviso è simile al seguente:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Per risolvere i problemi relativi alla conversione delle risorse in istruzioni di reindirizzamento, vedere [Repoinit Documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | Sì | Sì |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Questi analizzatori controllano alcuni dettagli relativi al pacchetto di [contenuto per il processo di conversione del modello di feature](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) che crea artefatti conformi al modello di feature Sling. Eventuali errori devono essere segnalati  Adobe Assistenza clienti. | Sì | Sì |
| `api-regions-crossfeature-dups` | Verifica che i bundle OSGI del cliente non abbiano dichiarazioni di pacchetto di esportazione che ignorano AEM come API pubblica  Cloud Service<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Per risolvere il problema, interrompete l&#39;esportazione di un pacchetto che fa parte dell&#39;API pubblica AEM. | Sì | Sì |
| `repoinit` | Controlla la sintassi di tutte le sezioni di reindirizzamento | Sì | Sì |