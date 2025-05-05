Il **Pattern Singleton** in Java è un design pattern che garantisce che una classe abbia una sola istanza e fornisca un punto di accesso globale a quella istanza. Viene utilizzato quando si ha bisogno di un oggetto che deve essere condiviso in tutta l'applicazione, come per esempio nelle connessioni a un database, nella gestione dei log, o in altre risorse che devono essere condivise e non è conveniente crearne più istanze.

### Punti Chiave:

1. **Costruttore Privato**: La classe ha un costruttore privato per impedire la creazione di istanze dall'esterno.
2. **Istanza Statica**: Una variabile statica mantiene l'unica istanza della classe.
3. **Punto di Accesso Globale**: Un metodo pubblico statico (solitamente chiamato `getInstance()`) fornisce il punto di accesso globale all'istanza.
4. **Sicurezza nei Thread**: È importante che l'istanza del singleton sia thread-safe, soprattutto in ambienti multi-thread.