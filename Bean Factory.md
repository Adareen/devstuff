`BeanFactory` è **l’interfaccia più semplice e fondamentale** nel framework Spring per la **gestione dei bean**.

> In parole semplici: è un **contenitore IoC (Inversion of Control)** che si occupa di **creare, configurare e fornire oggetti**, chiamati _bean_.

### **Cosa fa la `BeanFactory`?**

- Carica le definizioni dei bean da file XML o altre fonti.
    
- Crea i bean **su richiesta** (lazy loading).
    
- Gestisce l’iniezione delle dipendenze



Differenza tra `BeanFactory` e `ApplicationContext`

| **BeanFactory**                              | **ApplicationContext**                                          |
| -------------------------------------------- | --------------------------------------------------------------- |
| Interfaccia base per contenitori IoC         | Estende `BeanFactory` con funzionalità extra                    |
| Lazy loading (crea bean solo quando servono) | Eager loading (crea tutti i bean subito all’avvio)              |
| Meno funzionalità                            | Aggiunge supporto per i18n, eventi, AOP, ecc.                   |
| Più leggera, ma meno usata oggi              | Standard in Spring Boot e nella maggior parte delle app moderne |

### In Spring moderno (Spring Boot)

In pratica, **non usi mai direttamente `BeanFactory`**. Usi `ApplicationContext`, che **la estende** e aggiunge molte più funzionalità.
