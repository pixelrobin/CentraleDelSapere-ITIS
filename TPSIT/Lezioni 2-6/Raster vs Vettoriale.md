# Introduzione

Si parla di file multimediali quando si elaborano informazioni ti tipo: immagine, suono, filmati.
Queste informazioni sono analogiche e devono essere convertite in digitale.

---
## Immagini

Le immagini possono essere classificate in due formati:
- **immagini scalari** o **raster**, usate per foto, scansioni ecc. In questo caso l'immagine rappresenta una matrice di numeri chiamata **bitmap**
![[Pasted image 20251017185047.png]]
- **immagini vettoriali**, utilizzate nel disegno geometrico, loghi ecc. In questo caso la scena é descritta da **forme** e **equazioni matematiche**
![[Pasted image 20251017185131.png|400]]

---

## Immagini raster monocromatiche

Per rappresentare digitalmente delle immagini analogiche é necessario trasformare l'insieme continuo di colori e luci in 2D, in un insieme di parti che possono essere codificate come numeri (**discretizzazione**) mediante un procedimento chiamato **digitalizzazione**:
- Fase 1: si sovrappone l'immagine a una **griglia** immaginaria di minuscole celle chiamate **pixel** (**picture** **element**), questa operazione é chiamata **campionamento spaziale**![[Pasted image 20251017191716.png]]
- Fase 2: vengono codificati i pixel associando a ogni punto un numero secondo una tabella di  corrispondenza (**tavolozza**) a colori e sfumature diverse, questo processo prende il nome di **quantizzazione**
![[Pasted image 20251017191822.png]]
![[Pasted image 20251017191839.png]]

> [!NOTE]
> Nelle immagini Bianco/Nero ciascun pixel puó assumere solo 2 valori: bianco o nero, quindi basta 1 bit

---

## Immagini raster a livelli di grigio

Con 1 bit per pixel si puó rappresentare solo o bianco o nero, se si vogliono aggiungere piú colori per pixel, bisogna aumentare i bit per pixel:

1. Con 4 bit possiamo codificare 16 toni di grigio
2. Con 8 bit possiamo codificare 256 toni di grigio

![[Pasted image 20251017192107.png]]

Se si vuole calcolare quanto spazio occupa un immagine in toni di grigio si puó fare facilmente seguendo questi passaggi:
- Calcolare l'occupazione di un immagine a 256 toni di grigio con risoluzione 640x480 pixel
- per 256 toni di grigio servono 8 bit per pixel, quindi 1 byte per pixel
- noi abbiamo 640x480 pixel, ovvero 307200 pixel in totale
- dato che ogni pixel richiede 1 byte, il totale sará 307200 byte, circa 300KB

---

## Immagini raster a colori

Per codificare le immagini a colori si assegna al pixel un numero o una sua sfumatura. Il colore si ottiene da almeno tre colori base chiamati **primari** e sono **RGB** **(red, green, blue)** oppure CMYK (ciano, magenta, giallo, nero).

- Il metodo *RGB* usa la ==sintesi additiva== per sommare i colori primari, il file RGB é il 25% piú piccolo dello stesso file CMYK
- Il metodo *CMYK* utilizza la ==sintesi sottrattiva== per i colori ed é la migliore soluzione per immagini di qualitá come stampe.

Nel metodo RGB si usano 8 bit per colore per pixel, ovvero 24 bit per pixel (circa 16 milioni di colori)

---

### Palette di colori

Un file RGB occuperebbe molto spazio perció si usa un sottoinsieme di colori rappresentandoli su una tavolozza di colori a cui si assegna un numero per ogni colore. In questo modo si possono usare una quantitá di colori minore (ma comunque sufficienti) utilizzando molto meno spazio

> [!NOTE]
> Piú dettagli a pagina 60 del libro

---

[<<Torna all'indice](obsidian://open?vault=Vault%20di%20denis&file=TPSIT%2FLezioni%202-6%2F0.INDICE)