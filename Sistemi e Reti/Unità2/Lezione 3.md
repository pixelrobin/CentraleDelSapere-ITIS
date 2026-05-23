# Multi boot e virtualizzazione

Il UEFI boot manager (spiegato nella [[Lezione 2]]) gestisce il bootstrap anche in caso di diversi sistemi operativi.
L'utente puó scegliere di scaricare molteplici OS sulla macchina con due tecniche:
1. Multi-boot: ogni sistema operativo é installato su una partizione del disco.
2. Virtualizzazione: ogni OS viene eseguito in una macchina virtuale.

## Multi boot

Un computer puó avere 2 o piú sistemi operativi sullo stesso disco MA SU PARTIZIONI DIVERSE.

Condivisione delle risorse in multi-boot:
Per condividere documenti o altro su entrambi gli OS si puó creare una partizione comune in cui si inseriscono i dati da condividere. Un altra opzione é usare un servizio di cloud storage.

## Bootstrap in multi-boot

![[Pasted image 20251022183539.png|300]]

In caso di multi-boot UEFI Boot Manager scansiona la partizione ESP in cerca del boot entry (informazioni su come avviare l'OS). se c'é un solo OS Boot Manager carica il kernel e conclude. In caso di molteplici OS Boot Manager chiama un boot loader di terze parti che mostra all'utente la lista degli OS scaricati e chiede di selezionarne uno.

Esempi di boot loader di terze parti:
- Windows boot Manager.
- GRUB2: boot loader piú usato su linux
- rEFInd: boot loader generico, puó caricare qualsiasi OS, interfaccia grafica per la selezione del OS.
- Clover: boot loader piú usato per i MAC.

## Virtualizzazione

La virtualizzazione consente di far caricare piú sistemi operativi su un computer. Si crea una macchina virtuale che emula il sistema operativo scaricato.

Ogni macchina virtuale richiede delle risorse dalla macchina host.
Terminologia relativa alla virtualizzazione:
 - Physical Machine: computer fisico su quale installare il software di virtualizzazione.
 - Host OS: sistema operativo installato sulla macchina host.
 - Guest OS: sistema operativo scaricato sulla macchina virtuale.
 - VM: virtual machine, software che emula il computer virtualizzando CPU, RAM, HDD...
 - Hypervisor: fornisce un ambiente isolato (VM) e agisce come un interfaccia grafica tra hardware del computer e i programmi nelle VM.

> [!NOTE]
> 
> L'hypervisor é la parte fondamentale delle macchine virtuali perché lavora con l'hardware e le macchine virtuali, si occupa di allocare le risorse assegnate alla VM.

### Tipi di Hypervisor:

Tipo 1 (hypervisor bare-metal): eseguiti direttamente sull'host senza la necessitá di un OS sottostante, offrono prestazioni superiori al tipo 2.

L’hypervisor di tipo 1 (detto anche **bare-metal**) è integrato nel **kernel del sistema operativo**, quindi comunica **direttamente con l’hardware**, senza altri livelli intermedi.  
Ciò gli permette di offrire **maggiore prestazione e sicurezza** rispetto agli hypervisor di tipo 2, anche se richiede **hardware dedicato** e una **configurazione più complessa**.  
È ideale per **ambienti di produzione**.

Esempi:
- **QEMU/KVM**: usati insieme su Linux; KVM è un hypervisor di tipo 1 integrato nel kernel, mentre QEMU (tipo 2) lo utilizza per accedere all’hardware. 
- **Microsoft Hyper-V**: soluzione proprietaria **integrata in Windows Server**.

Esempio pratico: un server con Hyper-V può eseguire due macchine virtuali, una con **Windows Server** e una con **CentOS Linux**, ciascuna con le proprie applicazioni.

![[Pasted image 20251022185801.png]]

---

Tipo 2 (hosted hypervisor): sono eseguiti come applicazioni sul sistema operativo del computer, non hanno accesso diretto alle risorse del computer, piú intuitivi e semplici da usare.

Gli **hypervisor di tipo 2** sono i primi ad essere stati sviluppati e funzionano come **applicazioni installate su un sistema operativo già esistente** (host OS).  
Le **macchine virtuali (VM)** create su di esso hanno un proprio **sistema operativo indipendente** (guest OS), diverso da quello del computer fisico.  
Ad esempio, si può avere **Windows 11 come host** e **Ubuntu o Windows 7 come guest**.  
Il software di virtualizzazione (hypervisor) costituisce un **livello intermedio** tra l’host e le VM.

Sono **più facili da usare** rispetto agli hypervisor di tipo 1, ma **meno performanti**, e sono ideali per **test, sviluppo o uso personale**.

Esempi di hypervisor di tipo 2:
- **Oracle VM VirtualBox**: open source, multipiattaforma, supporta dischi iSCSI.
- **Microsoft Hyper-V for Windows**: soluzione gratuita (non in Windows Home) utile per test o sviluppo; supporta Windows, Linux e FreeBSD.
- **QEMU/KVM**: può agire anche come tipo 2, eseguendo VM come processi Linux.
- **VMware**: disponibile come **Workstation (Windows/Linux)** e **Fusion (Mac)**.
- **Parallels Desktop**: ottimizzato per **Mac**, molto integrato e facile da usare.

![[Pasted image 20251022185824.png]]

## Multiboot VS Virtualizzazione

### **Multi-boot**
**Vantaggi:**
- **Prestazioni elevate**: ogni sistema operativo usa direttamente l’hardware.
- **Minor spazio occupato**: vengono caricati solo i file del sistema in uso.
**Svantaggi:**
- **Partizionamento necessario**: ogni sistema richiede una partizione separata.
- **Minore sicurezza**: i sistemi condividono l’hardware, quindi eventuali danni o virus possono colpire tutti.
- **Richiede riavvio** per passare da un sistema operativo all’altro.

---

### **Virtualizzazione**
**Vantaggi:**
- **Isolamento e sicurezza**: le VM sono indipendenti, quindi problemi o virus restano confinati.
- **Configurazione semplice**: creare una VM è rapido e intuitivo.
- **Clonazione facile**: si possono duplicare macchine virtuali identiche.
- **Alta compatibilità**: si possono eseguire molti sistemi operativi diversi.
**Svantaggi:**
- **Prestazioni inferiori** rispetto al multi-boot, perché interviene un software di virtualizzazione.
- **Maggiore uso di memoria e spazio** per il software e le immagini delle macchine virtuali.

---

[[Sistemi e Reti]]