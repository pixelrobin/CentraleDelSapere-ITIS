# Introduzione

L'istruzione `if` in C++ serve per **eseguire un blocco di codice solo se una condizione è vera**.  
È uno dei costrutti fondamentali del controllo di flusso.

---

## Sintassi di base


```cpp
#include <iostream>
using namespace std;

int main() {
	int numero=5;
	
	if (numero>1) {
		cout<<"Il numero é maggiore di 1";
	}
	else {
		cout<<"Il numero é minore di 1;
	}
	return 0;
}
```

In questo caso quello che succede dentro l'if é questo:
 1. Controlla che il numero inserito sia maggiore di 1.
 2. Se É VERO allora entra nel blocco IF e stampa a schermo la frase.
	2.1.Se É FALSO allora entra nel blocco ELSE e stampa a schermo la frase.
3. Continua con il resto del codice

---

## else if 

Se si vogliono mettere piú condizioni in un unico blocco IF si puó usare else if:

```cpp
#include <iostream>
using namespace std;

int main() {
	int numero=5;
	
	if (numero>1) {
		cout<<"Il numero é maggiore di 1";
	}
	else if (n==0) {
		cout<<"Il numero é uguale a zero";
	}
	else {
		cout<<"Il numero é minore di 1";
	}
	return 0;
}

```

In questo caso succede ció:

- Verifica se n>1, se VERO entra nel primo IF
- Se FALSO, verifica se la condizione dell'else if é vera, se é cosí allora entra nel blocco else if ED ESEGUE SOLO QUEL BLOCCO, non controlla l'else
- Se ENTRAMBI SONO FALSI, allora entra nell'else

[<< Torna all'indice](0.README%20INFORMATICA.md)
