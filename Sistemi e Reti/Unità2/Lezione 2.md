# UEFI

Il firmware maggiormente usato dai computer moderni é il **UEFI** (Unified Extensible Firmware Interface), ed  é nato per correggere gli errori del BIOS:

1. supporta il boot solo da dischi con dimensione <=2 TiB
2. l'inizializzazione e la configurazione degli hardware moderni é gestita dal sistema operativo, non dal firmware.
3. non esiste uno standard internazionale
4. difficile da modificare per aggiungere funzionalitá

> [!EXTRA]
> UEFI offre la possibilitá di gestire la procedura di avvio del PC in modo piú flessibile del BIOS. Per garantire la compatibilitá anche con dispositivi vecchi, tutti i firmware che supportano UEFI possono avviare il sistema con le stesse modalitá di BIOS (BIOS legacy)

Vantaggi di UEFI su BIOS:
- indipendente dall'architettura dell'hardware.
- puó operare sia a 32 e 64 bit con la possibilitá di mandare maggiore risorse [[RAM]] per fare compiti piú complessi.
- piú veloce all'avvio e alla ripresa dall'ibernazione[^1].
- puó caricare il sistema operativo anche su dischi >2TiB. UEFI lavora con una tabella di partizione chiamata GPT (GUID Paritition Table) e non con MBR (Master Boot Record).
- offre un interfaccia utente piú moderna.

## Specifiche standard di UEFI

si basano su quelle di EFI 1.0 di Intel. Intel ha affidato poi la gestione e evoluzione a UEFI Forum.
servizi offerti dall'interfaccia UEFI:
- EFI boot service: servizi disponibili solo in fase di bootstrap, esempi: caricamento del boot loader e del OS nella RAM.
- EFI runtime service: servizi sempre disponibili, esempi sono i servizi di gestione della memoria, dei dispositivi I/O, installazione dei driver e gestione delle interfacce utente (creazione di finestre)

![[Pasted image 20251022180551.png|700]]

Il programma EFI OS loader rintraccia la partizione del disco (EFI system partition) dove é installato l'OS e avvia il kernel.

Caratteristiche di UEFI:
- Interfaccia grafica: usare il mouse, vedere le finestre...
- Diagnostica: test piú ampi di quelli POST, in alcuni casi si usa ancora il beep in caso di errore grave.
- Antivirus: scansione del disco alla ricerca di virus.
- Accesso a internet.
- Aggiornamenti live: controllo dal sito costruttore della scheda madre se ci sono aggiornamenti
- Sicurezza.
- Supporto per hard disk > 2TiB
- HDD backup.
- Overclocking: aumentare la frequenza della CPU per migliorare le prestazioni.
- Boot logo.
- Secure Boot: impedisce durante il bootsrap l'avvio di software non compatibile con le firme crittografiche autorizzate.
- BIOS legacy.

---

## Partizionamento dell'hard disk con GPT

Con l'architettura a 64 bit hanno introdotto la partizione del disco GPT ( Globally Unique IDentifier Partion Table). La differenza tra GPT e MBR sono:
- possibilitá di creare teoricamente infinte partizioni del disco
- i dati relativi alle partizioni del sono memorizzati due volte: una volta al Primaty GPT e la seconda al Secondary GPT
- dimensione massima del disco di 8ZiB.

## Bootstrap con UEFI

Con UEFI la fase di caricamento del sistema operativo diventa piú flessibile.
Elementi di UEFI per la fase di bootstrap:
- EFI System Partition: partizione del disco dove sono salvati il boot loader, driver e altre applicazioni UEFI. Questa partizione é formattata come un file system rendendo piú facile memorizzare diversi boot loader
- UEFI Boot Manager: componente UEFI che gestisce la fase di bootstrap e mantiene l'elenco delle opzioni di boot. Una volta selezionato il sistema operativo Boot Manager manda in esecuzione EFI OS loader, che carica il sistema operativo nella memoria
- ![[Pasted image 20251022182742.png]]
- Secure Boot: prima di avviare EFI OS loader, Secure Boot verifica la firma digitale del codice, se la firma é valida il codice é autorizzato e si prosegue con l'avvio del loader. resta attivo tutto il bootstrap per verificare che il kernel e i driver siano certificati e autorizzati.
---

[[Lezione 3]]
[[Sistemi e Reti]]

[^1]: Durante l'ibernazione il PC non é né spento né sospeso. usa meno energia della sospensione con un riavvio leggermente piú lento
