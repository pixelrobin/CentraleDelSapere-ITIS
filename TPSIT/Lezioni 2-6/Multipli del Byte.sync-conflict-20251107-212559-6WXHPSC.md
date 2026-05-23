# Introduzione

i multipli del byte sono calcolati come **potenze del 2** partendo dal fatto che si sta operando in un **sistema binario** usando dei ==prefissi binari== diversi dai prefissi del Sistema Internazionale.

![[Pasted image 20251016214205.png]]

Ad esempio, per convertire da Prefisso binario  -> Sistema Internazionale si puó fare:
1. Si pensa a quanto corrisponde il valore binario espresso in decimale: 1 Kib quanti B sono? 2^10
2. 1 Mib sono 2^20 Byte e cosí via.
3. Mentre, 1KB quanti byte sono? 10^3, 1MB sono 10^6 byte e cosi via
4. adesso supponiamo di voler convertire 1Mib in MB
5. 1(il numero davanti a Mib)* 2^20(Mib convertito in byte)/10^6(MB convertito in byte) 	![[Pasted image 20251016220005.png]]

Se vogliamo fare l'opposto basta scambiare il numeratore con il denominatore 

![[Pasted image 20251016220127.png]]

---

## Esempi e esercizi

Convertiamo 5Gib in MB, possiamo farlo seguendo questi passaggi:

1. Vediamo che 1Gib = $2^{30}$ byte
2. Vediamo che 1 MB = $10^6$ byte
3. Possiamo quindi impostare l'espressione:
# $5*\frac{2^{30}}{10^{6}}$

Il risultato della moltiplicazione é 5368,709 MB, che se usiamo un convertitore esce lo stesso numero

---

Se invece vogliamo fare il contrario e quindi trasformare 100KB in MiB seguiamo gli stessi passaggi:

1. 1KB = $10^3$
2. 1MiB = $2^{20}$ 
3. Impostiamo la moltiplicazione

# $100*\frac{10^3}{2^{20}}$

Il risultato é 0,095 MiB che anche stavolta é corretto.


> [!CONSIGLIO] RICORDATI
> Al numeratore ci va sempre la base del numero di partenza, mentre al denominatore la base in cui si vuole arrivare

---

[<<Torna all'indice](obsidian://open?vault=Vault%20di%20denis&file=TPSIT%2FLezioni%202-6%2F0.INDICE)