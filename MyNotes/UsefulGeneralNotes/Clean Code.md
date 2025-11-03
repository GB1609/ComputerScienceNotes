This guide aims to briefly summarise all the best practices for clean, maintainable and understandable code. At least as far as I have understood it over the years :D
Many of the key concepts, as well as the structure of the document itself, are taken from one of the most useful and most recommended books for a programmer, especially a novice: [Clean Code](https://www.amazon.it/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882), by our beloved [Uncle Bob!](https://it.wikipedia.org/wiki/Robert_Cecil_Martin)
# How give a name?
Se si parli di una variabile, di una funzione, di una classe, di un semplice parametro o qualunque altra cosa dare il corretto nome è fondamentale poiché questo ci permetterà di rendere comprensibile a terzi il nostro codice ed anche a noi stessi in un secondo momento! Vi sono regole base da seguire:
- Dare nomi con un significato
```python
  x=12 # wrong name, What is it? It doesn't say anything.
  months_in_a_year # good name, we know what it is!
```

- Usare nomi che evitano disinformazione
  ad esempio se si chiama una variabile accountList, ci si aspetta che sia una lista, non un array o altro
- Usare nomi che siano pronunciabili e non codifiche
  ad esempio dare ad una variabile il nome *mIY* è sbagliato, un utente esterno non potrà mai sapere che significa *month in a year*
- Preferire nomi che siano facili da ricercare nel codice
  evitare magic number ma preferire enum e simili
- Evitare (questo a mio gusto) di inserire suffissi e prefissi ai nomi delle classi o metodi
  Gli IDE moderni ti permettono di riconoscerli tramite icone e highlighting diversi a seconda del tipo!
- Evitare di usare nomi diversi per la stessa operazione
  ad esempio, *add*, *insert*, *append* per inserire elementi in una lista
- Dare ai metodi come nome un verbo che faccia capire l'utilità, per le classi invece è preferibile evitare verbi!

# Functions
Così come il nome lascia comprendere, le *funzioni* sono le azioni che è possibile eseguire nel nostro codice. Più semplici e chiare sono meglio è. Vi sono linee guida semplici da seguire per poter garantire questa semplicità:
- La funzione deve essere piccola, evitare di creare funzioni enormi e complesse
- Si devono utilizzare altre funzioni se la logica è complessa, è buona norma avere per ogni indentazione 2/3 righe
- Dovrebbe occuparsi di una sola azione (Single Responsability), o in alternativa deve essere composta da N funzioni che si occupano di una singola azione
- Cercare di rispettare appunto il principio di SRP e di OCP, ad esempio spesso l'utilizzo di switch le viola entrambi
- Il nome di una funzione deve essere chiaro e descrittivo: meglio lungo e comprensibile che corto e ambiguo
- Evitare di avere funzioni con più di tre argomenti. Si preferiscono funzioni:
	- **Monadiche:** servono a interrogare o operare su un solo argomento
	- **Diadiche:** vanno usate solo se i due argomenti sono coerenti; altrimenti è meglio trasformarle in monadiche
	- **Triadiche:** vanno evitate: complicano lettura e test del codice, da usare solo in casi eccezionali
- Se vi è estrema necessità di passare più di questo numero di argomenti è preferibile avere un oggetto da passare
- Seguire il principio DRY, l'idea è che ogni conoscenza o comportamento del sistema debba esistere in un solo punto
