---
title: Introduzione ai componenti core e-mail
description: Crea contenuti e-mail coinvolgenti utilizzando la flessibilità dei componenti core e-mail e distribuiscili con la potenza di Adobe Campaign.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '414'
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
* I componenti e-mail core forniscono una personalizzazione avanzata grazie all’inserimento di variabili Adobe Campaign nella maggior parte dei campi di dialogo.
* Il componente Segmentazione flessibile consente una segmentazione avanzata del contenuto.
* I componenti e-mail core forniscono un output HTML ottimale grazie alla funzione [stile CSS inliner,](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner) [l&#39;attributo inliner HTML,](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) e [l&#39;impianto igienizzatore HTML.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizer)
* Puoi creare contenuti e-mail ovunque `/content`.
* I componenti core e-mail sono [open source.](https://github.com/adobe/aem-core-email-components)

## Requisiti {#requirements}

I componenti core e-mail hanno i seguenti requisiti.

| AEM | Adobe Campaign | Componenti core  |
|---|---|---|
| AEM 6.5.x.y (on-premise o AMS) | Adobe Campaign Classic vX<br>o<br>Adobe Campaign Standard | [Versione x](/help/versions.md) o superiore |

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
