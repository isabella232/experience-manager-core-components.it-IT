---
title: Progettazione reattiva dei Componenti core
description: Scopri la progettazione reattiva dei Componenti core e come può influenzare il progetto.
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# Progettazione reattiva dei Componenti core {#responsive-design}

Tutti i Componenti core sono progettati per essere completamente reattivi, garantendo un’esperienza fluida su tutti i dispositivi. È importante notare che alcuni componenti avanzati, come ad esempio [carosello,](/help/components/carousel.md) [Schede,](/help/components/tabs.md) e [Componenti pannello a soffietto,](/help/components/accordion.md) può richiedere un’attenzione specifica nel contesto del progetto di attuazione al fine di mantenere la reattività in tutte le condizioni.

Date le diverse modalità in cui questi componenti possono mostrare un comportamento reattivo, e nell’impegno di Adobe di mantenere i Componenti core leggeri e pronti all’uso, la responsabilità di implementare gli aspetti reattivi dettagliati è intenzionalmente lasciata al progetto.

Ad esempio, su schermi stretti il componente Schede può adattarsi suddividendo schede ampie in nuove righe, consentendo lo scorrimento verticale, trasformando schede in elenchi a discesa o adottando uno stile Pannello a soffietto. A causa del potenziale impatto sulle prestazioni che l’implementazione di tutti questi comportamenti potrebbe causare, il [clientlibs](/help/developing/including-clientlibs.md#provided) sono intesi come punto di partenza per gli implementatori piuttosto che come soluzione esaustiva.
