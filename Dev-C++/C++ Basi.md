# Introduzione a C++

In questo file vediamo alcune basi del linguaggio C++:

- Importare le librerie con `#include <nome libreria>`
- Usare `cin` per leggere da tastiera
- Usare `cout` per stampare a schermo
- La direttiva `using namespace std;`
- `endl` per andare a capo
- `;` per indicare la fine di un'istruzione
---

## Esempio di programma

```cpp
#include <iostream> //include le librerie
using namespace std; //importante 

int main() {
    
    cout << "Inserisci un numero: ";
    cin >> numero; // Lettura da tastiera
    
    cout << "Hai inserito: " << numero << endl;
    
    return 0;
}
```

[<< Torna all'indice](0.README%20INFORMATICA.md)

