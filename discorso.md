1. Titolo, dati anagrafici e relatore
Ciao a tutti, sono Enrico Cotti Cottini e oggi vi racconto il progetto che ho realizzato durante il mio stage in Nuvem, in collaborazione con Starline. 
Si tratta di una piattaforma web per configurare e calcolare i costi dei pannelli che servono ad automatizzare le valvole industriali. 

<!-- 2. Azienda ospitante: Nuvem s.r.l.
Nuvem è la società dove ho svolto lo stage: si occupa di consulenza IT e sviluppo software, soprattutto per aziende che vogliono innovare i loro processi. Ho trovato un ambiente giovane, molto orientato all’innovazione e con tanta voglia di sperimentare. Qui ho potuto lavorare davvero sul campo, mettendo in pratica quello che avevo studiato. -->

3. Azienda cliente: Starline Services S.p.A.
Starline invece è l’azienda cliente: produce valvole a sfera e sistemi di automazione per l’industria. starline automation e' un ramo operativo dell'azienda starline services che fa parte del gruppo starline spa, esso si occupa della progettazione e realizzazione di sistemi per l'automazione industriale, precisamenti si occupano di realizzare dei sistemi di valvole attuatori controllati da pannelli di controllo per la gestione di impianti che lavorano con diversi tipi di fluidi.

4. Il sistema attuale: progettazione pannelli in Excel
Prima del nostro intervento, tutto veniva gestito con fogli Excel. Questo significava tanto lavoro manuale, rischio di errori, tempi lunghi e poca chiarezza. Qui vedete un esempio di come venivano gestiti i componenti: non proprio il massimo per un’azienda che vuole essere competitiva e veloce.

5. Contesto applicativo: valvola e attuatore
Entrando nel vivo, il cuore del sistema sono la valvola a sfera e l’attuatore. La valvola regola il flusso, l’attuatore la apre o la chiude in modo automatico. Sono componenti fondamentali in tanti settori industriali, e devono funzionare sempre in modo impeccabile. esistono piu tipi di valvola per esempio qui o messo una valvola a sfera che funzioina con una sfera in mezzo che ruota e controlla il flusso, ma esistono altri tipo a saracinesca, o a farfalla che sono famosi, e poi gli attuatori devono essere ben accoppiati alla valvola stando attenti ai valori e le forze che sopportano, esso si collega tramite uno stelo, essi possono essere a compressione aria, con una molla, idraulici con motore elettrico

6. Contesto applicativo: pannello di controllo
Il pannello di controllo è l’interfaccia tra l’operatore e l’impianto: da qui si gestiscono valvole e attuatori, personalizzando tutto in base alle esigenze del cliente. Un pannello ben progettato fa davvero la differenza in termini di efficienza e sicurezza.

7. Necessità della soluzione software
Con la crescita della complessità degli impianti, Excel non bastava più. Serviva un sistema che automatizzasse la gestione dei dati, riducesse gli errori e permettesse di lavorare in modo più rapido e sicuro. Da qui nasce l’idea di una piattaforma web dedicata. l'idea iniziale era quella di una piattaforma nella quale fosse possibile gestire la creazione di preventivi su misura per progetti diversi e modulari per aiutare i tecnici che devono fare i preventivi per i clienti.

8. Descrizione dello stage
Il mio stage è durato due e mi ha permesso di seguire le fasi iniziali del progetto dato che la durata di esso era stimata inizialmente sui 6 mesi: dall’analisi dei requisiti allo sviluppo vero e proprio. Ho lavorato con un team conposto da alcuni membri interni della nuvem e alcuni della starline, ho lavorato un po a tutte le parti del progetto toccando frontend backend .

9. Metodologia di sviluppo: Agile e Scrum
Per questo progetto abbiamo scelto la metodologia Agile, utilizzando il framework Scrum. Si tratta di un approccio molto adatto a contesti dove i requisiti cambiano rapidamente e la collaborazione con il cliente è continua.
Tutto parte da un’idea iniziale del cliente, che viene analizzata per definire i requisiti e trasformata in user stories. Queste storie alimentano il product backlog, una lista ordinata delle funzionalità da sviluppare.
Il lavoro viene poi suddiviso in sprint di due settimane. Al termine di ogni sprint ci sono incontri regolari — come le review e le retrospective — per valutare i progressi e raccogliere feedback.
Questo ci permette di restare sempre allineati con le aspettative del cliente e di adattarci velocemente a ogni cambiamento necessario.

10. Scrum applicato al progetto
Nel nostro progetto, Scrum è stato applicato in modo concreto e strutturato.
Abbiamo organizzato il lavoro in sprint bisettimanali. Per la gestione del codice abbiamo utilizzato GitHub, mentre per la comunicazione interna ci siamo affidati a Microsoft Teams.
Per l’ambiente di sviluppo e distribuzione abbiamo adottato Docker, che ci ha aiutati a mantenere coerenza tra i diversi ambienti.
Alla fine di ogni sprint, abbiamo svolto una review con il cliente per mostrare i risultati ottenuti e raccogliere feedback immediato(demo).
Questo processo iterativo ci ha permesso di migliorare costantemente il prodotto e rispondere con agilità alle sue esigenze reali.

11. Analisi dei requisiti
All’inizio abbiamo mappato tutti i casi d’uso: gestione progetti, offerte, anagrafiche dei componenti. Abbiamo distinto tra requisiti funzionali, qualitativi e vincoli tecnici, usando anche diagrammi per avere tutto sotto controllo e non perdere di vista le priorità.

12. Progettazione: architettura esagonale
Per il backend abbiamo scelto un’architettura esagonale: in parole semplici, ci permette di separare la logica di business da tutto il resto, rendendo il sistema più facile da testare, mantenere e aggiornare in futuro.

13. Progettazione: Dependency Injection
Un altro aspetto importante della nostra progettazione è stata l’adozione della Dependency Injection, o iniezione delle dipendenze.
Questo meccanismo permette di gestire automaticamente le dipendenze tra i vari componenti del sistema, evitando di istanziarli manualmente all’interno del codice. In pratica, ogni oggetto riceve ciò di cui ha bisogno dall’esterno, anziché crearselo da solo.
In .NET, la Dependency Injection è supportata nativamente grazie al sistema di configurazione dei servizi tramite l’interfaccia IServiceCollection.
Ad esempio, abbiamo registrato i nostri servizi usando istruzioni come services.AddScoped<IMioServizio, MioServizio>(), che dicono al framework quale implementazione fornire quando viene richiesto un certo tipo.
Questo approccio ha migliorato la modularità, ha reso il codice più riutilizzabile, e ci ha permesso di scrivere test più semplici, grazie alla possibilità di sostituire facilmente i componenti con versioni simulate.
In sintesi, la Dependency Injection ha reso la nostra architettura più pulita, flessibile e manutenibile.

 14. Progettazione e tecnologie (discorso ~1 minuto)
Dal punto di vista tecnologico, abbiamo scelto strumenti moderni e adatti allo sviluppo di applicazioni web modulari e scalabili.
Per il frontend abbiamo utilizzato MudBlazor, una libreria basata su Blazor che ci ha permesso di creare un’interfaccia moderna e reattiva in C#.
Per la documentazione e l’interazione con le API, abbiamo integrato Scalar, uno strumento che ci ha aiutato a visualizzare e testare facilmente le api.
Come database, abbiamo optato per MongoDB, una soluzione NoSQL molto flessibile, adatta a gestire dati dinamici e scalabilita orizzontale.
Per garantire la portabilità e la coerenza degli ambienti di sviluppo e produzione, abbiamo containerizzato l’applicazione usando Docker.
Infine, lo sviluppo è stato gestito con JetBrains Rider, un IDE potente che ha facilitato l’integrazione con .NET e gli strumenti di versionamento.
Grazie a questo stack tecnologico, siamo riusciti a costruire un sistema solido, facilmente manutenibile e pronto per essere distribuito in ambienti reali.

15. Conclusioni e prospettive (circa 1 minuto)
Il progetto ha raggiunto gran parte degli obiettivi: oggi Starline dispone di una piattaforma in grado di semplificare e velocizzare la configurazione dei pannelli, con una maggiore tracciabilità e riduzione degli errori.
Dalla tabella dei requisiti emerge che molte funzionalità chiave sono già operative, come la gestione dei progetti, dei materiali, dei brand e l’interfaccia responsive. Tuttavia, alcuni aspetti sono ancora parziali o mancanti, come l’autenticazione avanzata, l'importazione dati da API e l’esportazione delle offerte.
In prospettiva, sarà importante migliorare l’esperienza utente, completare le funzionalità avanzate e rafforzare la sicurezza e la gestione dei ruoli.
Dal punto di vista personale, è stata un’esperienza molto formativa: mi ha permesso di confrontarmi con un vero contesto aziendale, di capire come adattare le metodologie agili nella pratica e di crescere sia professionalmente che umanamente.
È un’esperienza che mi ha dato strumenti concreti e motivazione per proseguire in questo percorso.

Conclusione e ringraziamenti
Grazie per l’attenzione! Se avete domande o curiosità, sono qui.