questa lezione parla dell'avvio di un computer
### 1.1 Avvio

Quando il computer si avvia la fase si chiama **bootstrap** o intercambiabilmente startup mentre la fase di **spegnimento** è il **shutdown**. Tutto ciò avviene grazie al tasto di spegnimento/accensione che permette che la corrente passi per i circuiti e faccia inizializzare l'effettivo processo di avvio, durante il processo di avvio se succedono errori il **system speaker** andrà a riprodurre dei beep e grazie alle loro caratteristiche si potrà identificare il problema.
quando il computer si spegne e riaccende si dice in tutti casi reset e la CPU è coinvolta in questo processo e quando andiamo ad avviarla esegue la prima istruzione che si chiama ==reset vector==, al suo interno è anche memorizzata un'istruzione che fa partire la UEFI oppure la BIOS 

### 1.2 Firmware

Il firmware è la parte software che interagisce con l'hardware e gestisce le interazioni in esso controllando se la **RAM** funziona correttamente, che le periferiche collegate funzionino, cercare il **drive di sistema** e avviare il ==kernel==.
le istruzioni presenti nella UEFI sono scritte in Assembly e linguaggio macchina mentre l'interfaccia della UEFI è in C.

### 1.3 Elenco dettagliato fasi di avvio

1. **Accensione e inizializzazione del firmware** e conseguente verifica dei componenti hardware 
2. **Power-on Self Test (POST)**: diagnosi e verifica dei componenti hardware e include la verifica della CPU, RAM, GPU, Memorie
3. **Inizializzazione dell'hardware**: le componenti cominciano a lavorare e si esegue la configurazione di dispositivi plug & play 
4. **Avvio dei driver**
5. **Selezione del boot loader** (ciò che carica l'OS)
6. **caricamento del kernel e avvio dell'OS**

[[Lezione 2]]