# Formati di File per lo Scambio Dati

Nell'era moderna, i dati devono poter essere condivisi tra diversi programmi e sistemi. In questa sezione studieremo tre dei formati più importanti per lo scambio di dati: CSV, JSON e XML.
Ogni formato ha i suoi punti di forza e le sue applicazioni ideali. Il CSV è perfetto per dati tabulari semplici, il JSON è diventato lo standard per le applicazioni web moderne, mentre l'XML offre una struttura più rigorosa per dati complessi. Capire questi formati è fondamentale per chi vuole sviluppare applicazioni che comunicano con altri sistemi.

## CSV (Comma-Separated Values)

Il CSV è il formato più semplice per rappresentare dati tabulari, simile a un foglio di calcolo. Puoi immaginarlo come una tabella dove:

- Ogni riga rappresenta un record di dati
- Le colonne sono separate da un carattere specifico (solitamente la virgola)
- La prima riga spesso contiene i nomi delle colonne (header)

Per esempio, un file CSV con dati degli studenti potrebbe apparire così:
```
nome,età,classe
Mario,17,4A
Laura,16,4B
```

Il formato CSV è importante perché:
- È facilmente leggibile sia dagli umani che dai computer
- Può essere aperto con qualsiasi editor di testo
- È supportato da tutti i fogli di calcolo
- È ideale per dati semplici e strutturati

## JSON (JavaScript Object Notation)

JSON è un formato di scambio dati che organizza le informazioni in una struttura ad albero. È come un modo di descrivere oggetti usando una sintassi semplice e leggibile. Un oggetto JSON ha:

- Coppie chiave-valore per i dati semplici
- Array per le liste di elementi
- Oggetti annidati per strutture complesse
- Supporto per diversi tipi di dati (numeri, stringhe, booleani, null)

Per esempio, gli stessi dati degli studenti in JSON:
```json
{
  "studenti": [
    {
      "nome": "Mario",
      "età": 17,
      "classe": "4A"
    },
    {
      "nome": "Laura",
      "età": 16,
      "classe": "4B"
    }
  ]
}
```

JSON è diventato uno standard perché:
- È facile da leggere e scrivere per gli sviluppatori
- È il formato nativo di JavaScript
- È supportato da praticamente tutti i linguaggi di programmazione
- Permette di rappresentare strutture dati complesse

## XML (eXtensible Markup Language)

XML è un formato più formale e rigoroso che usa tag per strutturare i dati, simile all'HTML. È come un documento con un'organizzazione gerarchica molto precisa dove:

- Ogni elemento è racchiuso tra tag di apertura e chiusura
- Gli elementi possono contenere altri elementi (annidamento)
- Gli elementi possono avere attributi
- La struttura può essere validata contro uno schema

Lo stesso esempio degli studenti in XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<studenti>
    <studente>
        <nome>Mario</nome>
        <età>17</età>
        <classe>4A</classe>
    </studente>
    <studente>
        <nome>Laura</nome>
        <età>16</età>
        <classe>4B</classe>
    </studente>
</studenti>
```

L'XML è particolarmente utile perché:
- Ha una struttura molto rigorosa che può essere validata
- È eccellente per documenti complessi
- Supporta namespace per evitare conflitti tra nomi
- È ampiamente utilizzato in ambito enterprise e per configurazioni

La scelta del formato dipende dalle esigenze specifiche:
- CSV per dati semplici e tabulari
- JSON per applicazioni web e API moderne
- XML per sistemi che richiedono forte validazione e documentazione formale