Questa guida nasce con l’idea di riassumere — in modo semplice e diretto — le migliori pratiche per scrivere codice
pulito, mantenibile e comprensibile. Almeno, per quanto sono riuscito a capirne in questi anni 😄
Molti dei concetti (e anche la struttura del documento) sono ispirati a uno dei libri più utili e iconici per ogni
programmatore, soprattutto per chi sta
iniziando: [Clean Code](https://www.amazon.it/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882), del
mitico [Uncle Bob!](https://it.wikipedia.org/wiki/Robert_Cecil_Martin)

# Come decidere un nome?

Se si parli di una variabile, di una funzione, di una classe, di un semplice parametro o qualunque altra cosa dare il
corretto nome è fondamentale poiché questo ci permetterà di rendere comprensibile a terzi il nostro codice ed anche a
noi stessi in un secondo momento! Vi sono regole base da seguire:

- Dare nomi con un significato

```python
  x = 12  # wrong name, What is it? It doesn't say anything.
months_in_a_year  # good name, we know what it is!
```

- Usare nomi che evitano disinformazione
  ad esempio se si chiama una variabile accountList, ci si aspetta che sia una lista, non un array o altro
- Usare nomi che siano pronunciabili e non codifiche
  ad esempio dare ad una variabile il nome *mIY* è sbagliato, un utente esterno non potrà mai sapere che significa
  *month in a year*
- Preferire nomi che siano facili da ricercare nel codice
  evitare magic number ma preferire enum e simili
- Evitare (questo a mio gusto) di inserire suffissi e prefissi ai nomi delle classi o metodi
  Gli IDE moderni ti permettono di riconoscerli tramite icone e highlighting diversi a seconda del tipo!
- Evitare di usare nomi diversi per la stessa operazione
  ad esempio, *add*, *insert*, *append* per inserire elementi in una lista
- Dare ai metodi come nome un verbo che faccia capire l'utilità, per le classi invece è preferibile evitare verbi!

# Funzioni

Così come il nome lascia comprendere, le *funzioni* sono le azioni che è possibile eseguire nel nostro codice. Più
semplici e chiare sono meglio è. Vi sono linee guida semplici da seguire per poter garantire questa semplicità:

- La funzione deve essere piccola, evitare di creare funzioni enormi e complesse
- Si devono utilizzare altre funzioni se la logica è complessa, è buona norma avere per ogni indentazione 2/3 righe
- Dovrebbe occuparsi di una sola azione (Single Responsability), o in alternativa deve essere composta da N funzioni che
  si occupano di una singola azione
- Cercare di rispettare appunto il principio di SRP e di OCP, ad esempio spesso l'utilizzo di switch le viola entrambi
- Il nome di una funzione deve essere chiaro e descrittivo: meglio lungo e comprensibile che corto e ambiguo. Inoltre è
  preferibile usare VERBI
- Evitare di avere funzioni con più di tre argomenti. Si preferiscono funzioni:
    - **Monadiche:** servono a interrogare o operare su un solo argomento
    - **Diadiche:** vanno usate solo se i due argomenti sono coerenti; altrimenti è meglio trasformarle in monadiche
    - **Triadiche:** vanno evitate: complicano lettura e test del codice, da usare solo in casi eccezionali
- Se vi è estrema necessità di passare più di questo numero di argomenti è preferibile avere un oggetto da passare
- Seguire il principio DRY, l'idea è che ogni conoscenza o comportamento del sistema debba esistere in un solo punto

## Conclusioni

Ogni sistema è costruito a partire da un linguaggio specifico, per un dominio specifico. Il codice è creato dai
programmatori per descriverlo.
Le funzioni sono i suoi verbi e le classi i suoi nomi. Un buon codice deve raccontare una storia chiara, non deve solo
funzionare.
Scrivere funzioni chiare, ben definite e brevi aiuta a costruire un linguaggio che esprima quella storia in modo
preciso.

# Commenti

Niente può fare più danni di commenti scritti male. Essi possono aiutare, ma spesso fanno più danni che bene. La
soluzione? Non leggere mai la documentazione!
Scherzi a parte, un buon codice dovrebbe spiegarsi da solo: ogni commento è una piccola sconfitta nella chiarezza del
codice.
I commenti invecchiano male, diventano falsi o fuorvianti, perché il codice cambia ma loro restano.
Meglio scrivere codice chiaro che doverlo spiegare con un commento.
Anche qui delle semplici linee guida da utilizzare:

- Non scrivere commenti per chiarire un codice scritto male, ma riscrivi il codice!
- Sempre meglio avere commenti all'interno del codice che spiega l'azione e non un unica grande descrizione on top del
  metodo
- Aggiungere commenti per chiarire le scelte, come mai è stata presa una decisione
- Per aggiungere una spiegazione "umana" a del codice difficilmente comprensibile, come ad esempio regex per pattern
  complessi o l'utilizzo di funzioni poco chiare
- Per mettere in risalto pezzi di codice critici, sulla quale bisogna fare accurata attenzione
- TODO comments per modifiche da effettuare in futuro e/o non attuabili attualmente
  Invece è sconsigliato:
- Aggiungere commenti inutili, che sono ripetitivi o peggio ancora che creano ancora più dubbi
- Se si può evitare di aggiungere i commenti, modificare il codice per renderlo parlante
- Non utilizzare commenti troppo lunghi, preferire versioni brevi e concise

# Formattazione

Lato mio questa è una delle cose più importanti e che più mi provoca irritazione, provate a chiedere ai miei colleghi!
Non c'è niente di più brutto di vedere codice non uniforme, che non rispetta nessuna convenzione o che cambia riga per
riga.

La formattazione del codice riveste una grande importanza, avere un codice chiaro e leggibile, ci aiuterà ad applicare
eventuali modifiche più facilmente e capire meglio ciò che è stato già implementato. Vi sono varie regole da prendere in
considerazione, ma oggigiorno tutto è reso semplice e facile dai moderni IDE. Ogni linguaggio ha delle convenzioni e
regole proprie spesso mette a disposizioni come file di formattazione che può essere usato dai vari IDE o tool specifici
per tener sotto controllo il tuo codice e darti indicazioni real time. Tipici esempi sono:

- [scalastyle](https://github.com/scalastyle)
- [PEP8](https://peps.python.org/pep-0008/)
- [switft-format](https://github.com/swiftlang/swift-format)
- [clang-format](ClangFormat)
- e molti altri

Unica cosa da fare dunque è selezionare il proprio linguaggio, settare la convenzione relativa nel proprio IDE e lasciar
far a esso!
# Oggetti (OO) e Strutture Dati (Codice procedurale)
Perchè decidiamo di creare alcune variabili private? Perchè non lasciare tutto pubblico? Il motivo è semplice, vogliamo che queste restino immutabili, non vogliamo che nessuno possa vederle, modificarle o cambiarne il significato.

## Programmazione orientata gli oggetti vs Strutture Dati
Gli **oggetti** nascondono i loro dati dietro astrazioni e mettono a disposizione funzioni che lavorano su quei dati.  
Le **strutture dati**, invece, mostrano apertamente i loro dati e **non** hanno funzioni significative. La differenza può sembrare minima, ma ha conseguenze molto importanti su come progettare un sistema.
### Esempio Oggetti
```java
interface Shape {
    public function area(): double;
}

class Square implements Shape {
    private $side;

    public function __construct(double $side) {
        $this->side = $side;
    }

    public function area(): double {
        return pow($this->side, 2);
    }
}

class Rectangle implements Shape {
    private $height;
    private $width;

    public function __construct(double $height, double $width) {
        $this->height = $height;
        $this->width = $width;
    }

    public function area(): double {
        return $this->height * $this->width;
    }
}

class Circle implements Shape {
    private const PI = 3.141592653589793;
    private $center;
    private $radius;

    public function __construct(double $radius) {
        $this->radius = $radius;
    }

    public function area(): double {
        return pow($this->radius, 2) * self::PI;
    }
}
```

### Esempio Strutture Dati
```java
class Square {
    public $side;
}

class Rectangle {
    public $height;
    public $width;
}

class Circle {
    public $center;
    public $radius;
}

class Geometry {
    private const PI = 3.141592653589793;

    public function area(object $shape): double {
        switch(true) {
            case $shape instanceof Square:
                return pow($shape->side, 2);
            case $shape instanceof Rectangle:
                return $shape->height * $shape->width;
            case $shape instanceof Circle:
                return pow($shape->radius, 2) * self::PI;
            default:
                throw new NoSuchShapeException();
        }
    }
}
```

### Cosa succede, quale scegliere?

Cosa succede dunque in un caso o nell'altro? 
Se si ragiona a **strutture dati** le forme sono solo contenitori di dati, non hanno metodi, abbiamo dunque:
- **PRO**: Facile aggiungere nuove funzioni
- **CONTRO**: Difficile aggiungere nuovi tipi di dati
Se si ragiona ad oggetti invece, ogni classe è responsabile della propria logica. 
- **PRO**: Facile aggiungere nuovi tipi di dati
- **CONTRO**: Difficile aggiungere nuove funzioni

Si capisce subito il problema principale: **procedurale e oo sono l’uno l’opposto dell’altro**, ciò che è facile per uno è difficile per l’altro.
In base al caso d'uso bisogna dunque fare la scelta corretta:
- **Usa l’approccio procedurale** quando il sistema richiede di aggiungere spesso _nuove funzioni_ che lavorano su dati già noti e stabili.
- **Usa l’approccio orientato agli oggetti** quando il sistema deve poter crescere con _nuovi tipi di entità_, cioè nuovi oggetti, mantenendo stabili le funzioni già esistenti.

## Legge di Demetra
La legge di Demetra è un ottima euristica che permette di definire al meglio come gli oggetti interagiscono tra loro.
La Legge di Demetra dice che un oggetto non deve attraversare catene di chiamate per arrivare ai dati: deve chiedere direttamente ciò che gli serve al suo "vicino".

Prendiamo ad esempio:
```scala
case class FuelTank(val level: Double)
case class Engine(val fuelTank: FuelTank)
case class Car(val engine: Engine)

val fuel = car.engine.fuelTank.level

```

Questo pezzo di codice viola la legge di demetra in quanto attravera 3 livelli!

Un modo per rispettarla è quella di modificare le classi facendo in modo che leggano solo dal vicino:

```scala
class FuelTank(private val level: Double) {
  def currentLevel: Double = level
}

class Engine(private val fuelTank: FuelTank) {
  def fuelLevel: Double = fuelTank.currentLevel
}

class Car(private val engine: Engine) {
  def fuelLevel: Double = engine.fuelLevel
}

val fuel = car.fuelLevel
```

Esternamente possiamo usare solo fuelLevel, questo permette che la struttura intera di Car resti nascosta.

**PRO:** codice più sicuro, chiaro e mantenibile.  
**CONTRO:** a volte più verboso e con più metodi di passaggio.

### Train Wrecks
Le catene di chiamate lunghe, dette “*train wreck*", come ad esempio `ctxt.getOptions().getScratchDir().getAbsolutePath(` sono brutte da leggere e mantenere.  
Se `ctxt`, `Options` e `ScratchDir` sono **oggetti**, allora usare catene del genere è una **violazione della Legge di Demetra**, perché il codice conosce troppo della loro struttura interna.  
Se invece sono **semplici strutture dati**, allora è normale accedere ai loro campi e la Legge di Demetra **non si applica**.  I getter e setter confondono la distinzione tra oggetti e strutture, ma la regola resta:  
- catena lunga usate su oggetti = cattivo stile;
- catena lunga + strutture dati = accettabile, anche se da usare con moderazione.

### Ibridi
Una cosa che è assolutamente preferibile evitare sono gli ibridi! Hanno metodi che fanno cose importanti (come gli oggetti), ma allo stesso tempo espongono variabili pubbliche o getter/setter che rendono di fatto pubblici i loro dati (come le strutture).
Questi ibridi sono ereditano i contro di entrambi:
- è **difficile aggiungere nuove funzioni** (come negli oggetti)
- è **difficile aggiungere nuovi tipi di dati** (come nel procedurale)
Sono un segnale di **design confuso**, dove non è chiaro se si vuole proteggere i dati o definire comportamenti.  La regola è: **evitali**, perché portano solo complicazioni e rendono il codice fragile.

---

**Tag Obsidian:** #clean #code #martin 


