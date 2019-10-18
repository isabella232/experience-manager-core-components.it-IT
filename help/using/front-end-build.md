---
title: Creazione front-end tipo di archivio AEM
seo-title: Creazione front-end tipo di archivio AEM
description: Un modello di progetto per le applicazioni basate su AEM
seo-description: Un modello di progetto per le applicazioni basate su AEM
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# Creazione front-end tipo di archivio AEM {#aem-project-archetype-front-end-build}

Il tipo di archivio dei progetti AEM include un meccanismo opzionale per la creazione front-end basato su Webpack con le seguenti funzionalità.

* Supporto completo per TypeScript, ES6 e ES5 (con wrapper per webpack applicabili)
* Collegamento TypeScript e JavaScript tramite un ruleset TSLint
* Uscita ES5 per il supporto dei browser legacy
* Globbing
   * Nessuna necessità di aggiungere importazioni da nessuna parte
   * Tutti i file JS e CSS possono ora essere aggiunti a ciascun componente
      * La best practice è `/clientlib/js`, `/clientlib/css`, o `/clientlib/scss`
   * Nessun `.content.xml` o `js.txt`/`css.txt` file necessari come tutto viene eseguito tramite Webpack
   * Il globo estrae tutti i file JS sotto la `/component/` cartella.
      * Webpack consente di collegare i file CSS/SCSS tramite file JS.
      * Vengono inseriti attraverso i due punti di ingresso `sites.js` e `vendors.js`.
   * L’unico file utilizzato da AEM è rappresentato dai file di output `site.js` e `site.css` in `/clientlib-site` nonché `dependencies.js` e `dependencies.css` in `/clientlib-dependencies`
* Gocce
   * Main (sito js/css)
   * Fornitori (dipendenze js/css)
* Supporto Sass/Scss completo (Sass viene compilato in CSS tramite Webpack).

## Installazione {#installation}

1. Installate [NodeJS](https://nodejs.org/en/download/) (v10+) a livello globale. Verrà installato anche npm.
1. Andate a ui.frontend nel progetto ed eseguite `npm install`.

## Utilizzo {#usage}

I seguenti script npm generano il flusso di lavoro front-end:

* `npm run dev` - build completa con ottimizzazione JS disattivata (tremolio ad albero, ecc.) e mappe sorgente abilitate e ottimizzazione CSS disattivata.
* `npm run prod` - build completa con ottimizzazione JS abilitata (tremolio ad albero, ecc.), mappe sorgente disattivate e ottimizzazione CSS abilitata.

## Output {#output}

### Generale {#general}

* Sito - `site.js` e `site.css` vengono creati in una cartella clientlib-site.
* Dipendenze - `dependencies.js` e `dependencies.css` vengono create in una cartella clientlib-dependencies.

### JavaScript {#javascript}

* Ottimizzazione - Per le build di produzione, viene rimosso tutto il JS che non viene utilizzato o chiamato.

### CSS {#css}

* Prefisso automatico - Tutti i CSS vengono eseguiti tramite un prefissatore e tutte le proprietà che richiedono il prefissaggio avranno automaticamente quelle aggiunte nel CSS.
* Ottimizzazione - Al momento del post, tutto il CSS viene eseguito tramite un ottimizzatore (cssnano) che lo normalizza in base alle seguenti regole predefinite:
   * Riduce l'espressione CSS calc laddove possibile, garantendo sia la compatibilità del browser che la compressioneEffettua la conversione tra valori di lunghezza, tempo e angolatura equivalenti. Per impostazione predefinita, i valori di lunghezza non vengono convertiti.
   * Rimuove i commenti da regole, selettori e dichiarazioni
   * Rimuove regole, regole e dichiarazioni duplicate
      * Questo funziona solo per i duplicati esatti.
   * Rimuove regole vuote, query multimediali e regole con selettori vuoti, in quanto non influiscono sull'output
   * Unisce regole adiacenti tramite selettori e coppie proprietà/valore sovrapposte
   * Assicurarsi che nel file CSS sia presente un solo @charset e spostarlo nella parte superiore del documento
   * Sostituisce la parola chiave iniziale CSS con il valore effettivo, quando l'output risultante è minore
   * Comprime le definizioni SVG in linea con SVGO
* Pulizia - Include un'attività di pulizia esplicita per eliminare i file CSS, JS e Mappa generati su richiesta.
* Mappatura origine - solo build di sviluppo

>[!NOTE]
>L'opzione front-end build utilizza file di configurazione di webpack solo per dev e solo per prod che condividono un file di configurazione comune. In questo modo le impostazioni di sviluppo e produzione possono essere modificate in modo indipendente.
