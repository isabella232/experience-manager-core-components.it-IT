---
title: Introduzione ai componenti core e-mail
description: Crea contenuti e-mail coinvolgenti utilizzando la flessibilità dei componenti core e-mail e distribuiscili con la potenza di Adobe Campaign.
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 9%

---


# Introduzione ai componenti core e-mail {#email-core-components-introduction}

Crea contenuti e-mail coinvolgenti utilizzando la flessibilità dei componenti core e-mail e distribuiscili con la potenza di Adobe Campaign.

## Panoramica {#overview}

I componenti core e-mail si basano sulla stessa potente base dei componenti core. Consentono di creare contenuti e-mail mediante trascinamento semplici e flessibili, che possono quindi essere consegnati al pubblico utilizzando la potenza di Adobe Campaign.

## Vantaggi {#benefits}

Le e-mail fanno parte della brand experience e del percorso di clienti. Con i componenti core e-mail, gli autori possono creare contenuti e-mail dall’interno di AEM, offrendo un’esperienza con brand coerente e aumentando in tal modo la velocità dei contenuti.

* Proprio come per l’authoring delle pagine con i componenti core, i componenti core e-mail consentono agli autori di assemblare le e-mail senza conoscenze tecniche, garantendo al contempo che rispettino le linee guida di branding.
* La possibilità di riutilizzare risorse e contenuti incoraggia inoltre gli autori a seguire le linee guida di branding e a ottimizzare il processo di creazione dei contenuti.

## Funzioni {#features}

* I componenti e-mail core si basano sui [Componenti core,](/help/introduction.md) e quindi anche sostegno [Modelli modificabili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) e [Sistema di stili.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=it)
* Ci sono [dieci componenti pronti per la produzione ottimizzati per e-mail](#components) per creare contenuti e-mail.
* I componenti e-mail core offrono una personalizzazione avanzata grazie all’inserimento di [Variabili Adobe Campaign](campaign-variables.md) nella maggior parte dei campi di dialogo.
* La flessibilità [Componente Segmentation](/help/email/components/segmentation.md) consente una segmentazione avanzata del contenuto.
* I componenti e-mail core forniscono un output HTML ottimale grazie alla funzione [stile CSS inliner,](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation) [l&#39;attributo inliner HTML,](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) e [l&#39;impianto igienizzatore HTML.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* Puoi creare contenuti e-mail ovunque `/content`.
* I componenti core e-mail sono [open source.](https://github.com/adobe/aem-core-email-components)

## Requisiti {#requirements}

I componenti core e-mail hanno i seguenti requisiti.

| AEM | Adobe Campaign | Componenti core  |
|---|---|---|
| AEM 6.5.14.0+<br>On-Premise o AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [Versione 2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>Poiché le integrazioni Adobe Campaign non sono supportate in AEM as a Cloud Service, anche i componenti core e-mail non sono supportati in AEM as a Cloud Service.

## Componenti e-mail {#components}

La versione corrente dei componenti core e-mail include i seguenti componenti.

* [Pagina](components/page.md)
* [Contenitore](components/container.md)
* [Titolo](components/title.md)
* [Testo](components/text.md)
* [Immagine](components/image.md)
* [Pulsante](components/button.md)
* [Teaser](components/teaser.md)
* [Frammento esperienza](components/experience-fragment.md)
* [Frammento di contenuto](components/content-fragment.md)
* [Segmentazione](components/segmentation.md)

## Installazione e utilizzo {#installation-usage}

Consulta la sezione [Utilizzo dei componenti core e-mail](using.md) per informazioni dettagliate sull’installazione dei componenti core e-mail.
