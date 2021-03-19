---
title: Plug-in Maven di AEM as a Cloud Service SDK Build Analyzer
description: Documentazione per il plug-in locale Maven build analyzer
feature: Componenti core, AEM Project Archetype
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 3%

---


# AEM come plug-in Maven di Cloud Service SDK Build Analyzer {#maven-analyzer-plugin}

Il plug-in Maven AEM as a Cloud Service SDK Build Analyzer analizza la struttura dei vari progetti di pacchetti di contenuto.

Per informazioni su come includerlo in un progetto Maven, consulta la [documentazione del plug-in Maven](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) .

>[!NOTE]
>
>È consigliabile aggiornare il progetto Maven per fare riferimento all’ultima versione del plug-in presente nell’archivio centrale Maven, nella posizione seguente: https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

Di seguito è riportata una tabella che descrive gli analizzatori eseguiti come parte di questo passaggio. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modulo | Funzione, esempio e risoluzione dei problemi | SDK locale | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Controlla se tutte le dichiarazioni Import-Package di tutti i bundle OSGI sono soddisfatte dalla dichiarazione Export-Package di altri bundle inclusi nel progetto Maven. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Per risolvere i problemi, controlla se il bundle che fornisce il pacchetto è incluso nella distribuzione oppure in alternativa osserva il manifesto del bundle che ti aspetteresti di esportare per determinare se è stato utilizzato il nome o la versione errata. | Sì | Sì |
| `requirements-capabilities` | Controlla se tutte le dichiarazioni dei requisiti rese nei bundle OSGI sono soddisfatte dalle dichiarazioni delle capacità di altri bundle inclusi nel progetto Maven. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Per risolvere i problemi, osserva il manifesto del bundle che ti aspetteresti di dichiarare una funzionalità per determinare il motivo della sua mancanza, o controlla nel manifesto del bundle che richiede per vedere che il requisito in esso è corretto. | Sì | Sì |
| `bundle-content` | Visualizza un avviso se un bundle contiene il contenuto iniziale specificato con Sling-Initial-Content, che è problematico nell’ambiente cluster di AEM come Cloud Service. L&#39;avviso si presenta così: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Per risolvere i problemi relativi alla conversione del contenuto iniziale in istruzioni di reindirizzamento, consulta la documentazione di reindirizzamento . | Sì | Sì |
| `bundle-resources` | Visualizza un avviso se un bundle contiene risorse specificate con l&#39;intestazione Sling-Bundle-Resources , che è problematica nell&#39;ambiente cluster AEM come Cloud Service. L&#39;avviso si presenta così:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Per risolvere i problemi relativi alla conversione delle risorse in istruzioni di reindirizzamento, consulta [Repoinit Documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | Sì | Sì |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Questi analizzatori controllano alcuni dettagli relativi al [pacchetto di contenuti al processo di conversione del modello di feature](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) che crea artefatti conformi al modello di feature Sling. Eventuali errori devono essere segnalati all’Assistenza clienti di Adobe. | Sì | Sì |
| `api-regions-crossfeature-dups` | Convalida che i bundle OSGI del cliente non abbiano dichiarazioni di pacchetto di esportazione che sovrascrivono AEM come API pubblica del Cloud Service<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Per risolvere il problema, interrompi l&#39;esportazione di un pacchetto che fa parte dell&#39;API pubblica AEM. | Sì | Sì |
| `repoinit` | Controlla la sintassi di tutte le sezioni di reindirizzamento | Sì | Sì |
| `bundle-nativecode` | Convalida che i bundle OSGI non installino il codice nativo. | Sì | Sì |