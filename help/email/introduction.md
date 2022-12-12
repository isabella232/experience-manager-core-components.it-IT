---
title: Introduzione ai Componenti core E-mail
description: Crea contenuti e-mail coinvolgenti utilizzando la flessibilità dei componenti core E-mail e distribuiscili con la potenza di Adobe Campaign.
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 88%

---


# Introduzione ai Componenti core E-mail {#email-core-components-introduction}

Crea contenuti e-mail coinvolgenti utilizzando la flessibilità dei componenti core E-mail e distribuiscili con la potenza di Adobe Campaign.

## Panoramica {#overview}

I componenti core E-mail si basano sulla stessa potente base dei componenti core. Consentono di creare in modo semplice e flessibile, mediante trascinamento, i contenuti e-mail che possono quindi essere consegnati al pubblico con le potenti funzioni di Adobe Campaign.

## Vantaggi {#benefits}

Le e-mail fanno parte della brand experience e del percorso del cliente. Con i componenti core E-mail, gli autori possono creare contenuti e-mail dall’interno di AEM, offrendo un’esperienza con branding coerente e velocizzando la creazione dei contenuti.

* Proprio come per l’authoring delle pagine con i componenti core, i componenti core E-mail consentono agli autori di assemblare le e-mail senza conoscenze tecniche, garantendo al contempo il rispetto delle linee guida di branding.
* La possibilità di riutilizzare risorse e contenuti incoraggia inoltre gli autori ad aderire alle linee guida di branding e a ottimizzare il processo di creazione dei contenuti.

## Funzioni {#features}

* I componenti core E-mail si basano sui [Componenti core](/help/introduction.md) e quindi supportano anche i [modelli modificabili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) e il [sistema di stili.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=it)
* Per la creazione di contenuti e-mail sono disponibili [dieci componenti pronti per la produzione e ottimizzati per e-mail](#components).
* I componenti e-mail core offrono una personalizzazione avanzata grazie all’inserimento di [Variabili Adobe Campaign](campaign-variables.md) nella maggior parte dei campi di dialogo.
* La flessibilità [Componente Segmentation](/help/email/components/segmentation.md) consente una segmentazione avanzata del contenuto.
* I componenti core E-mail core forniscono un output HTML ottimale grazie alla [funzione inline per stili CSS](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Documentazione tecnica), alla [funzione inline per attributi HTML](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) e allo [strumento di pulizia HTML.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* Puoi creare contenuti e-mail ovunque in `/content`.
* I componenti core E-mail sono [open source.](https://github.com/adobe/aem-core-email-components)

## Requisiti {#requirements}

Di seguito sono riportati i requisiti dei componenti core E-mail.

| AEM | Adobe Campaign | Componenti core  |
|---|---|---|
| AEM 6.5.14.0+<br>On-Premise o AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [Versione 2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>Poiché le integrazioni Adobe Campaign non sono supportate in AEM as a Cloud Service, anche i componenti core E-mail non sono supportati in AEM as a Cloud Service.

## I componenti E-mail {#components}

La versione corrente dei componenti core E-mail include i seguenti componenti.

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

Per informazioni dettagliate sull’installazione dei componenti core E-mail, consulta il documento [Utilizzo dei componenti core E-mail](using.md).
