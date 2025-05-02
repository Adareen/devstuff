
Questa è una delle basi più importanti del framework Spring.
L’iniezione delle dipendenze è un **principio di progettazione** in cui un oggetto **non crea da solo le proprie dipendenze**, ma le **riceve dall’esterno**, tipicamente da un **contenitore**.

> In parole povere: invece di fare `new` dentro la tua classe, qualcuno ti passa l’oggetto già pronto.

### 🎯 Obiettivo della DI

- Separare la **logica del tuo codice** dalla **creazione degli oggetti**.
- Rendere il codice **più riutilizzabile, testabile e flessibile**.

---
### Cos’è il contenitore IoC?

Il **contenitore IoC (Inversion of Control)** è il cuore del framework Spring. È lui che:

- Crea gli oggetti (chiamati [[Beans]]),
- Li **inizializza e configura**,
- E si occupa di **iniettare** le dipendenze dove servono.

“IoC” significa che non sei più tu a controllare il flusso (es. `new`), ma è il framework a **invertire il controllo** e a gestirlo per te.


### 🔧 Esempio pratico senza DI
```java
public class Car {
    private Engine engine = new Engine(); // la dipendenza viene creata direttamente

    public void start() {
        engine.run();
    }
}
```
Questo è **rigido**: non puoi facilmente cambiare il tipo di `Engine`, né testarlo con un finto `Engine`.


### 🔧 Esempio con Spring e DI
```java
@Component
public class Engine {
    public void run() {
        System.out.println("Motore acceso");
    }
}

@Component
public class Car {
    private final Engine engine;

    @Autowired
    public Car(Engine engine) { // l’oggetto Engine viene iniettato
        this.engine = engine;
    }

    public void start() {
        engine.run();
    }
}
```
Spring crea e gestisce sia `Car` che `Engine`, e inietta automaticamente `Engine` nel costruttore di `Car`.


### 🔁 Tipi di iniezione

- **Per costruttore** (preferita, come nell'esempio sopra)
- **Per campo** (`@Autowired` direttamente sul campo, meno testabile)
- **Per metodo setter** (`setEngine(...)` con `@Autowired`)

### ✅ Vantaggi

- Codice più **modulare** e **manutenibile**
- Più facile da **testare** con oggetti simulati (mock)
- Separazione delle responsabilità: le classi non devono sapere come creare le loro dipendenze