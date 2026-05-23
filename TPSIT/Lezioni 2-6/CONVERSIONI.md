# Da Binario a Decimale

Ipotizziamo di avere il numero binario `1010`, per trasformarlo in un numero decimale bisogna applicare queste regole:

- Si legge da destra verso sinistra e si assegna una posizione a partire da 0 (come si vede in figura)
- Le posizioni assegnate ci serviranno come esponenti del 2 
- Dopo aver fatto la **cifra binaria * 2^posizione** si sommano i risultati di ciascun elevamento

![[Pasted image 20251017175147.png]]

> [!NOTE]
>  Questa regola vale anche per il sistema ottale ma con l'unica differenza che la base della potenza non é 2 ma 8. 

# Da HEX a Decimale

Anche per il sistema esadecimale si eseguono gli stessi passaggi fatti per il sistema binario con l'unica aggiunta che le lettere hanno un valore

![[Pasted image 20251017175735.png]]

---

# Da Decimale a Binario

Ipotizziamo di trasformare il numero 59 decimale in un numero binario, per farlo bisogna seguire queste regole:

- Visto che siamo nel sistema binario bisogna **dividere** il numero decimale **per** **2** 
- Si controlla se il resto della divisione é 0 o 1 e si scrive di fianco
- Si ripete la divisone finché non si arriva a 1/2 che fa 0 con resto 1
- Si leggono i resti **dal basso verso l'alto**

| DIVIDENDO | DIVISORE | QUOZIENTE | RESTO |     |
| --------- | -------- | --------- | ----- | --- |
| 59        | 2        | 29        | **1** | ^   |
| 29        | 2        | 14        | **1** | \|  |
| 14        | 2        | 7         | **0** | \|  |
| 7         | 2        | 3         | **1** | \|  |
| 3         | 2        | 1         | **1** | \|  |
| 1         | 2        | 0         | **1** | \|  |
Quindi 59 base 10 diventa in binario --> **111011**


> [!NOTE] Nota
> Questo metodo della divisone si puó usare anche con il sistema ottale ricordandosi di usare come divisore 8

---

# Da Decimale a HEX

Uguale al modo Decimale->Binario ma si usa come divisore 16 e si tiene conto che il resto puó essere anche maggiore di 9, quindi si utilizzano le lettere maiuscole:

Ipotizziamo di convertire 3157 in esadecimale:

| DIVIDENDO | DIVISORE | QUOZIENTE | RESTO  |     |
| --------- | -------- | --------- | ------ | --- |
| 3157      | 16       | 197       | 5      | ^   |
| 197       | 16       | 12        | 5      | \|  |
| 12        | 16       | 0         | 12 (C) | \|  |
Quindi **3157** in decimale diventa **C55** in **HEX**

---

# Da Binario a HEX

Per convertire un numero binario in un numero esadecimale bisogna tenere in considerazione questo fattore:

Un numero HEX puó essere espresso come massimo 4 bit (1 = 0001, F = 1111), quindi possiamo raggruppare il numero binario in gruppi da 4 bit (sempre partendo da destra) e convertirlo nel numero HEX.

| HEX | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | A    | B    | C    | D    | E    | F    |
| --- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| DEC | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   | 11   | 12   | 13   | 14   | 15   |
| BIN | 0000 | 0001 | 0010 | 0011 | 0100 | 0101 | 0110 | 0111 | 1000 | 1001 | 1010 | 1011 | 1100 | 1101 | 1110 | 1111 |

Facciamo un esempio con il numero 111001: notiamo che ha solo 6 bit perció aggiungiamo alla cifra tanti 0 quanti servono per completare il gruppo da 4, in questo caso due 0, il numero diventa quindi 00111001. Ora dividiamo in gruppi da 4:

`0011` se lo confrontiamo alla tabella vediamo che corrisponde al **3** dell'HEX
`1001` vediamo che corrisponde al numero **9** del HEX

==Quindi 111001 diventa 39 in HEX.==

---

# Da HEX a Binario

Per fare la conversione inversa bisogna fare il contrario di quello fatto sopra:

Convertire C8 in binario: 

C corrisponde a `1100` mentre 8 corrisponde a `1000`, quindi, unendo i due risultati risulta:
### 11001000

---

[<<Torna all'indice](obsidian://open?vault=Vault%20di%20denis&file=TPSIT%2FLezioni%202-6%2F0.INDICE)


