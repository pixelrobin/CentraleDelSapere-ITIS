# Introduzione

Oltre alla **Selezione** [[IF]], esistono anche i CICLI, ovvero dei blocchi di codice che si ripete e sono: `While`,`Do-While`, `For` e adesso li vediamo nel dettaglio:

---

## `While`

Il ciclo while verifica una condizione e **SOLO SE É VERA ENTRA NEL BLOCCO**. Si forma in questo modo:

```cpp
#include <iostream>
using namespace std;

int main () {
	int n=100;
	while (n>2) {
		n=n/3;
		cout<<n;
	}
}
```

In questo esempio abbiamo inizializzato n=100, e nella condizione del ciclo abbiamo impostato n>2, perció tutte le istruzioni dentro il blocco while verranno eseguite mentre n>2, vediamolo meglio con una tracetable:

| Iterazione | N   | N/3 |
| ---------- | --- | --- |
| 1          | 100 | 33  |
| 2          | 33  | 11  |
| 3          | 11  | 3   |
| 4          | 3   | 1   |
| **5**          | **1**   | **0**   |
Alla quinta iterazione n é minore di 2, perció l'ultimo numero che verrá visualizzato a schermo sará il risultato della quarta iterazione.

---

## `Do-While`

Il ciclo Do-While é molto simile al ciclo While con l'unica differenza che **fará sempre un comando prima di verificare la condizione**. Si forma in questo modo:

```cpp
#include <iostream>
using namespace std;

int main() {
	int n;
	do {
		cout<<"Inserisci un numero maggiore di 0";
		cin>>n;
	}
	while (n<=0);
}
```

In questo caso, il ciclo do-while esegue sempre le istruzioni nel blocco `do` almeno 1 volta. In questo esempio chiede all'utente di inserire un numero maggiore di 0, quando poi esce dal blocco do entra nella condizione del `while` , e se, la condizione nel while é **VERA** allora rientra nel blocco `do`, se al contrario é falsa, continua il codice.

---

## `For`

