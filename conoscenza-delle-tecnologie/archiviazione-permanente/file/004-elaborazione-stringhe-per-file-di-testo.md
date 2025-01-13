# Elaborazione delle Stringhe per i File di Testo

La manipolazione delle stringhe è una competenza cruciale quando si lavora con i file di testo. In questa sezione ci concentreremo su come .NET ci permette di elaborare il testo in modo efficace, con particolare attenzione al metodo Split della classe String.
Vedremo come questi strumenti sono particolarmente utili quando lavoriamo con file CSV, permettendoci di trasformare righe di testo in dati strutturati che possiamo utilizzare nei nostri programmi. Questa capacità di elaborazione è fondamentale per creare applicazioni che possono interpretare e manipolare dati provenienti da diverse fonti.

## String in .NET

La classe String in .NET è fondamentale per la gestione del testo. Puoi immaginarla come una sequenza immutabile di caratteri che offre molti metodi utili per l'elaborazione del testo. Le caratteristiche principali sono:

- È immutabile (una volta creata non può essere modificata)
- Offre numerosi metodi per la manipolazione del testo
- Gestisce automaticamente la codifica dei caratteri
- Supporta operazioni di ricerca e sostituzione

Per esempio, operazioni comuni sulle stringhe:
```csharp
string testo = "Hello, World!";
int lunghezza = testo.Length;           // 13
string minuscolo = testo.ToLower();     // "hello, world!"
bool contiene = testo.Contains("World"); // true
```

## Il Metodo Split

Split è uno dei metodi più potenti della classe String, pensato specificamente per dividere una stringa in parti più piccole. È come un coltello che taglia il testo in punti specifici. Il metodo Split:

- Divide una stringa in base a uno o più separatori
- Restituisce un array di stringhe
- Può ignorare le stringhe vuote
- Supporta diverse opzioni di divisione

Esempio di utilizzo base:
```csharp
string csvRiga = "Mario,17,4A";
string[] parti = csvRiga.Split(',');
// parti[0] = "Mario"
// parti[1] = "17"
// parti[2] = "4A"
```

Split è particolarmente utile perché:
- È fondamentale per l'elaborazione di file CSV
- Permette di separare dati strutturati
- Supporta casi complessi con più separatori
- È altamente configurabile

## Opzioni Avanzate di Split

Split offre diverse opzioni avanzate per gestire casi particolari:

- StringSplitOptions.RemoveEmptyEntries: rimuove le stringhe vuote dal risultato
- StringSplitOptions.TrimEntries: rimuove gli spazi all'inizio e alla fine
- Possibilità di specificare più separatori
- Limite al numero di divisioni

Esempio con opzioni avanzate:
```csharp
string dati = "Mario  ;  17  ;  4A  ";
string[] parti = dati.Split(';', 
    StringSplitOptions.RemoveEmptyEntries | 
    StringSplitOptions.TrimEntries);
// parti[0] = "Mario"
// parti[1] = "17"
// parti[2] = "4A"
```

## Elaborazione dei Dati CSV

Quando lavoriamo con file CSV, l'elaborazione delle stringhe diventa cruciale. Il processo tipico include:

- Lettura di una riga dal file
- Divisione della riga in campi usando Split
- Conversione dei campi nel tipo di dato appropriato
- Validazione dei dati

Esempio pratico di elaborazione CSV:
```csharp
using (FileStream fileStream = new FileStream("studenti.txt", FileMode.Open, FileAccess.Read))
{
    using (StreamReader reader = new StreamReader(fileStream))
    {
        string header = reader.ReadLine(); // Legge intestazioni
        // Uso dei dati dell'header

        string riga;
        while (reader.EndOfStream == false)
        {
            string riga = reader.ReadLine(); // legge una riga dati
            string[] campi = riga.Split(',');
            string nome = campi[0];
            int età = int.Parse(campi[1]);
            string classe = campi[2];
            
            // Uso dei dati elaborati
        }
    }
}
```

Questo approccio all'elaborazione delle stringhe è importante perché:
- Permette di lavorare con dati strutturati in modo efficiente
- Facilita l'importazione di dati da file esterni
- Consente la validazione e pulizia dei dati
- È fondamentale per l'interoperabilità tra sistemi