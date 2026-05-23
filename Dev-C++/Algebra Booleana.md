# Introduzione

L’**algebra booleana** è un sistema matematico basato su due soli valori:
- `1` → **vero (TRUE)**
- `0` → **falso (FALSE)**

---

## Operatori Fondamentali

## `OR (||)` 

Questo operatore richiede **ALMENO 1** dei due valori uguale a **1**, questa é la tabella dell'OR:


| A   | B   | A OR B |
| --- | --- | ------ |
| 0   | 0   | 0      |
| 1   | 0   | 1      |
| 0   | 1   | 1      |
| 1   | 1   | 1      |

Quindi nell'operatore **OR** si ottiene 0 solo se **ENTRAMBI** i valori sono 0

---

## `AND (&&)`

Questo operatore logico richiede **ENRAMBI I VALORI UGALI A 1**.


| A   | B   | A AND B |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 1   | 0   | 0       |
| 0   | 1   | 0       |
| 1   | 1   | 1       |

Quindi nell'operatore **AND** si ottiene 0 quando **ANCHE 1 VALORE É 0**.

---

## `NOT (!=)`

Questo operatore logico richiede **1 SOLO IMPUT** e ne inverte il valore:


| A   | NOT A |
| --- | ----- |
| 0   | 1     |
| 1   | 0     |

---

## Algebra Booleana Avanzata

Oltre ai 3 operatori fondamentali ci sono altri operatori logici: `XOR` ,`NAND`, `NOR` :

## `XOR`

Significa **"eXclusive OR"** e restituisce 1 quando i valori di ingresso sono diversi:


| A   | B   | XOR |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 0   |
Quando quindi entrambi i valori di ingresso sono uguali `XOR` restituisce 0

---

## `NAND` 

Significa **"NOT AND"** e inverte il risultato dell'AND dei due valori di ingresso:


| A   | B   | A AND B | NAND |
| --- | --- | ------- | ---- |
| 0   | 0   | 0       | 1    |
| 0   | 1   | 0       | 1    |
| 1   | 0   | 0       | 1    |
| 1   | 1   | 1       | 0    |
`NAND` Restituisce 0 solo quando **entrambi** i valori di ingresso sono **1**.

---

## `NOR`

Simile a NAND, **inverte** il risultato di **A OR B**:


| A   | B   | A OR B | NOR |
| --- | --- | ------ | --- |
| 0   | 0   | 0      | 1   |
| 0   | 1   | 1      | 0   |
| 1   | 0   | 1      | 0   |
| 1   | 1   | 1      | 0   |
`NOR` Restituisce **1** solo quando **entrambi** i valori di ingresso sono uguali a 0.

---

# Teoremi di De Morgan

I teoremi di De Morgan sono molti utili per riscrivere alcune operazioni booleane rendendo il codice piú chiaro:

## `NOT(A AND B) = NOT(A) OR NOT(B)`

Facendo la tabella possiamo vedere che le espressioni sono uguali


| A   | B   | NOT(A) | NOT(B) | A AND B | NOT(A AND B) | NOT(A) OR NOT(B) |
| --- | --- | ------ | ------ | ------- | ------------ | ---------------- |
| 0   | 0   | 1      | 1      | 0       | **1**        | **1**                |
| 1   | 0   | 0      | 1      | 0       | **1**        | **1**                |
| 0   | 1   | 1      | 0      | 0       | **1**        | **1**                |
| 1   | 1   | 0      | 0      | 1       | **0**        | **0**                |
Come si nota dalla tabella le ultime due colonne sono uguali e quindi il teorema é valido.

---

# `NOT(A OR B) = NOT(A) AND NOT(B)`

Rifacciamo la tabella per verificare il teorema:


| A   | B   | NOT (A) | NOT (B) | A OR B | NOT(A OR B) | NOT(A) AND NOT(B) |
| --- | --- | ------- | ------- | ------ | ----------- | ----------------- |
| 0   | 0   | 1       | 1       | 0      | **1**           | **1**                 |
| 1   | 0   | 0       | 1       | 1      | **0**           | **0**                 |
| 0   | 1   | 1       | 0       | 1      | **0**           | **0**                 |
| 1   | 1   | 0       | 0       | 1      | **0**           | **0**                 |
Possiamo riconfermare dalla tabella che anche il secondo teorema di De Morgan é confermato

----

[<< Torna all'indice](0.README%20INFORMATICA.md)