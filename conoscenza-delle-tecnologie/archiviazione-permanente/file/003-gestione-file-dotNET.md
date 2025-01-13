# Gestione dei File di Testo con .NET

Le classi FileStream, StreamReader e StreamWriter sono gli strumenti che .NET ci mette a disposizione per lavorare con i file di testo. Queste classi seguono un pattern comune nella programmazione ad oggetti: la separazione delle responsabilità.
Vedremo come FileStream gestisce il flusso di dati a basso livello, mentre StreamReader e StreamWriter ci permettono di lavorare con il testo in modo più intuitivo. Questi strumenti ci permettono di leggere e scrivere file in modo efficiente e sicuro, gestendo automaticamente molte delle complessità sottostanti.

## FileStream

FileStream è la classe fondamentale per gestire il flusso di dati da e verso i file. Puoi immaginarla come un "tubo" che collega il tuo programma al file sul disco. Questa classe:

- Gestisce l'accesso ai file a basso livello
- Lavora con i dati come sequenze di byte
- Offre controllo preciso sulla modalità di accesso
- Gestisce automaticamente le risorse di sistema

Per esempio, per aprire un file in lettura senza condivisione:
```csharp
using (FileStream fileStream = new FileStream("dati.txt", FileMode.Open, FileAccess.Read, FileShare.None))
{
    // Operazioni sul file
}
```

FileStream è importante perché:
- Garantisce l'accesso sicuro ai file
- Previene i conflitti tra programmi
- Gestisce automaticamente la chiusura del file
- Ottimizza le prestazioni di lettura/scrittura

## StreamReader
StreamReader è una classe specializzata nella lettura di file di testo. È come un traduttore che converte i byte del file in caratteri e stringhe che possiamo facilmente utilizzare nel nostro codice. StreamReader:

- Legge il testo riga per riga
- Gestisce automaticamente la codifica dei caratteri
- Offre metodi semplici come ReadLine() e ReadToEnd()
- Funziona con diverse codifiche (UTF-8, ASCII, etc.)

Esempio di utilizzo:
```csharp
using (StreamReader reader = new StreamReader(fileStream))
{
    string linea;
    while ((linea = reader.ReadLine()) != null)
    {
        Console.WriteLine(linea);
    }
}
```

StreamReader è fondamentale perché:
- Semplifica la lettura di file di testo
- Gestisce automaticamente i buffer di memoria
- Supporta file di grandi dimensioni
- Converte automaticamente i caratteri speciali

## StreamWriter
StreamWriter è il complemento di StreamReader, specializzato nella scrittura di testo nei file. È come una penna che scrive in modo ordinato e gestisce automaticamente la formattazione. StreamWriter:

- Scrive testo riga per riga
- Gestisce automaticamente la codifica dei caratteri
- Offre metodi come WriteLine() e Write()
- Può aggiungere testo a file esistenti

Esempio pratico:
```csharp
using (StreamWriter writer = new StreamWriter(fileStream))
{
    writer.WriteLine("Prima riga");
    writer.WriteLine("Seconda riga");
}
```

StreamWriter è essenziale perché:
- Semplifica la scrittura di file di testo
- Gestisce automaticamente il buffering
- Previene problemi di corruzione dei file
- Supporta diverse codifiche di caratteri

La combinazione di queste tre classi segue il principio di "separazione delle responsabilità" della programmazione orientata agli oggetti perché:
- FileStream gestisce l'accesso al file fisico
- StreamReader si occupa della lettura e decodifica
- StreamWriter gestisce la scrittura e la codifica
- Ogni classe ha un compito specifico e ben definito

Questo approccio modulare rende il codice:
- Più facile da capire e mantenere
- Più robusto e sicuro
- Più efficiente nell'uso delle risorse
- Più facile da testare e debuggare