---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
type: Documentation
description: Documentazione dei Componenti core di Adobe Experience Manager
git-repo: https://github.com/AdobeDocs/experience-manager-core-components.it-IT
index: y
recommendations: noDisplay
source-git-commit: 55e5ef9271b07d8fffc7b396c890af1637309ff3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Metadati per uso interno

I metadati nel sistema di authoring GitHub sono gerarchici, in base ai seguenti livelli crescenti di precedenza.

1. metadata.md
1. Sommario
1. Articolo

I metadati definiti nel file metadata.md si applicano all’intero archivio, ma possono essere ignorati a livello di sommario e articolo. Eventuali esclusioni dei metadati devono essere eseguite al livello più basso possibile.

I metadati nell’archivio experience-manager-core-components.en rappresentano il minimo richiesto.

metadata.md

* `product`
* `git-repo`
* `index: y`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

Sommario

* `sub-product`
* `user-guide-title`

Articolo

* `title`
* `description`
* `index: n` (solo per le versioni precedenti dei componenti)

Ulteriori informazioni sui metadati sono disponibili nella [guida all’authoring interno.](https://experienceleague.adobe.com/docs/authoring-guide-exl/using/authoring/features/metadata.html?lang=it#solution)
