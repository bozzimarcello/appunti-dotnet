# File System - Concetti Fondamentali

Il file system è il cuore di come un computer organizza e gestisce i dati. In questa sezione esploreremo i concetti fondamentali che permettono ai nostri programmi di interagire con i file e le directory del computer in modo sicuro ed efficiente.
Un file system è come una libreria ben organizzata: ogni libro (file) ha il suo posto specifico, è catalogato in scaffali (directory), e ha delle regole precise su chi può leggerlo o modificarlo. Vedremo come il sistema operativo gestisce questa organizzazione attraverso volumi logici, come assegna i permessi, e come controlla chi può fare cosa con ogni file.

## File

Un file è l'unità base di memorizzazione nel computer. Puoi immaginarlo come un contenitore che può conservare qualsiasi tipo di informazione digitale: testo, immagini, programmi, ecc. Ogni file ha attributi specifici come:

- Nome e estensione (es: relazione.txt)
- Dimensione
- Data di creazione e ultima modifica
- Proprietario e permessi

## Directory (o Cartelle)

Le directory sono contenitori speciali che possono contenere sia file che altre directory. Creano una struttura gerarchica che aiuta a organizzare i file in modo logico, proprio come gli scaffali e i cassetti in una biblioteca. Una directory può essere:

- Root (directory radice, il livello più alto)
- Parent (directory genitore che ne contiene altre)
- Child (directory contenuta in un'altra)

## Volume Logico

Un volume logico è una porzione di spazio di archiviazione che il sistema operativo tratta come un'unità indipendente. Nei sistemi Windows sono le famose unità C:, D:, ecc. Un volume logico:

- Può essere un intero disco fisico o parte di esso
- Ha il proprio file system
- Può essere formattato indipendentemente
- Può avere diverse dimensioni e caratteristiche

## Percorso Assoluto di un File

Un percorso assoluto è come l'indirizzo completo di un file nel sistema, partendo dalla radice (root) del file system fino alla sua posizione esatta. Proprio come per raggiungere una casa abbiamo bisogno dell'indirizzo completo con nazione, città, via e numero civico, il percorso assoluto ci dice esattamente dove trovare un file specificando ogni directory che dobbiamo attraversare per raggiungerlo.
In Windows, un percorso assoluto inizia sempre con la lettera del volume logico seguita da ":", per esempio:

C:\Users\Mario\Documents\relazione.txt

In sistemi Unix/Linux, il percorso assoluto inizia sempre con il carattere "/" che rappresenta la directory root:

/home/mario/documents/relazione.txt

Il percorso assoluto è importante perché:

- Identifica un file in modo univoco nel sistema
- Funziona indipendentemente dalla posizione corrente nel file system
- È necessario quando dobbiamo fare riferimento a file in posizioni diverse del sistema
- Viene utilizzato spesso nelle configurazioni dei programmi dove non possiamo permetterci ambiguità

Questo concetto è fondamentale nella programmazione perché quando scriviamo codice che deve accedere ai file, dobbiamo spesso specificare percorsi assoluti per essere sicuri che il nostro programma trovi i file corretti indipendentemente da dove viene eseguito.

## Sistemi di Storage

I sistemi di storage sono le tecnologie hardware e software che permettono la memorizzazione dei dati. Includono:

- Dischi rigidi (HDD)
- Unità a stato solido (SSD)
- Storage di rete (NAS, SAN)
- Storage cloud
- Ogni tipo ha i suoi vantaggi in termini di velocità, capacità e costo.

## Proprietario di un File

Ogni file ha un proprietario, tipicamente l'utente che lo ha creato. Il concetto di proprietario è fondamentale per la sicurezza perché:

- Determina chi ha il controllo principale sul file
- Può modificare i permessi del file
- Può trasferire la proprietà ad altri utenti
- Ha sempre accesso completo al file (a meno di restrizioni specifiche)

## Permessi sui File

I permessi definiscono cosa ogni utente può fare con un file. I permessi base sono:

- Lettura (R): capacità di vedere il contenuto
- Scrittura (W): capacità di modificare il contenuto
- Esecuzione (X): capacità di eseguire il file (se è un programma)

I permessi possono essere assegnati a:

- Proprietario
- Gruppo di utenti
- Altri utenti

## Modalità di Accesso ai File

Quando un programma vuole utilizzare un file, deve specificare che cosa vuole fare con il file ovvero la modalità di accesso:

- Lettura (Read): solo per leggere il contenuto
- Scrittura (Write): per modificare il contenuto
- Append: per aggiungere contenuto alla fine
- Lettura/Scrittura (Read/Write): accesso completo

Inoltre, è possibile specificare come si vuole accedere al file ovvero se l'accesso deve essere:

- Esclusivo (un solo programma alla volta) o Condiviso (più programmi possono accedere contemporaneamente)
- Sincrono (le operazioni vengono completate in ordine) o Asincrono (le operazioni possono sovrapporsi)

Il sistema operativo usa queste informazioni per:

- Prevenire conflitti tra programmi
- Proteggere i dati da accessi non autorizzati
- Ottimizzare le prestazioni
- Garantire l'integrità dei dati
