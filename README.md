# Messanger (TBC)

App di messagistica in tempo reale sviluppato con tools come Flutter e Android Studio.

Supporta Android, iOS, Windows, MacOS, Linux ed è utilizzabile anche sul web. (IN TEORIA, stiamo ancora lavorando a quella per android, QUINDI CALMA)

Server hostato su docker in questa [REPO](https://github.com/BPUP-Suite/Messanger_API)

# INDICE

 - [Timeline](#Timeline)
 - Abbiamo solo queste per ora,non rompere :/

# Timeline:

Attenzione, non è una timeline seria, quella seria seria, è in un project dell'organizzazione insieme alla roadmap [PUBBLICA](https://github.com/orgs/BPUP-Suite/projects/4) (ovviamente molto più sintetica, qua ci aggiungo qualsiasi piccola cosa insieme ad altre stupidate)

25/09/2024

- Creazione della repository
- Creazione progetto su Android Studio e aggiunta del plugin di Flutter (dopo 15 crash da parte dell'IDE e 3 errori da parte mia {SOD} )
- Creazione repo dell`API utilizzata come server database e accesso dei dati
- Capito (in parte, piccolissima parte) come funziona postgresql (anche se non so quanto sia performante un relazionare in un`applicazione del genere, ma va bene lo stesso per sto progettino stupido) e implementato (almeno l'init del database) all'interno di una classe python
- Utilizzo di uno strumento semplice per hostare le API (FastAPI su python), per ora c'é solo il main con le due righe default ma va bene lo stesso
- {MM} che si guarda 3^4535 tutorial diversi perchè non capisce come *acciderbolina* si fa la qualsiasi cosa su Flutter
- Sistemazione del progetto in diverse folder all`interno della cartella lib/ per iniziare a capirci qualcosa e renderlo quanto più possibile comprensibile e scalabile, riducendo anche la possibile necessità di fare un refactor dell'intera pagine che mi farebbe diventare estremamente triste

26/09/2024

- Continui lavori di sviluppo al database che è *quasi* completamente sviluppato, e intanto mi meraviglio alla complessità del database di telegram, mentre piango :D
- {MM} continua a guardare altri 23^54 tutorial
- {MM} riesce a fare qualcosa di funzionante che ti porta dalla pagina principale a una dove ti chiede il numero di telefono (peccato che abbia messo un text field e niente form quindi non va niente)
- Mi ha dato il rimborso di star citizen, posso comprare la Mustang
- Fanculo sto progetto (per ora) si deve conquistare lo spazio
- {MM} scopre la possibilità di poter debuggare il progetto da un suo *PERSONAL* device, ed è estremamente contento 

27/09/2024 - 29/09/2024

- Tryhard su Star Citizen con rari casi di modifica al progetto

30/09/2024

- Me so rotto il cazo di SC, refund e continuo progetto
- Database migliorato, aggiunta la possibilità di far partire il progetto tramite Docker (necessario per hostare database, proxy, dbadmin, api facilmente)
- {MM} Migliora la grafica tantizzimo aggiungendo chat, bottoncini maaaagici, lista di chat figa, un menu ad hambuger (o 3 linee in alto a sinistra)
- {MM} ha iniziato a fare troppi bambini e non si capisc nu caz, quindi si sistema l`intero tree delle directory dandogli un po' di senso (sia per l'API, che per il client)
- Primi test di build android + windows + web (e funzionano abbastanza bene) {MM} contento (MacOS e iOS no perchè {EB} è strunz :D)
- TODO: usare telegram come storage dei file più grossi (da pensare un file system per collegare ad ogni file un file_id di telegram, tramite un bot + una local api)

01/10/2024

- Nuovo mese, inizia l'università e piango
- Ho finalmente {SOD} finito l'API per la sezione login,signup e access con hash della password, generazione di un API key utilizzata per l'accesso alle proprie risorse e tante belle cosine
- Ho configurato anche Nginx Proxy Manager e Cloudflare DNS insieme ad un serverino di Oracle Cloud (sia lodato il cielo e il tuo indirizzo IPv4 statico che io banana gigantesca son sotto CG-NAT, grazie Virgin Fibra(e no, non me lo danno l'IPv6 e col caxo che pago 4 euro al mese per avere un indirizzo inutile))
- L'API (dopo tanti fix perchè non so scrivere Dockerfile in modo consistente :( ) funziona ed è operativa :D
- {MM} e io {SOD} abbiamo finalmente iniziato a collaborare (urlando uno addosso all'altro :D) ma abbiamo collegato il client al server permettendo l'access (in pratica il processo che indentifica se un determinato utente è già registrato o meno portandoti alla specifica pagina), il signup e il login (che da come errore UNPROCESSABLE ENTITY dal server nei log, AIUTO COSA VUOL DIRE, però almeno sappiamo che errore è solo che ormai sono le 00:48 del 02/10/2024 e non ho voglia, sia lodato io che ho pensato di fare un logger di tutte le query e richieste API :D)
- Buonanotte 😴

02/10/2024

- Io {SOD} fatto niente / {MM} fatto niente (ah no giusto, riconoscimento biometrico, cosa easy da due secondi [{MM} mi ammazza per codesta affermazione :D] )

03/10/2024

- Io {SOD} fatto niente (fatta un minimo di documentazione per la sezione API) / {MM} inizia a fare la vera e propria chat, con i messaggini e cose tattiche nucleari

05/10/2024

- {MM} sto scrivendo qualcosa, assurdo. Implementato l'invio dei messaggi: quando un messaggio viene inviato (per ora testato solo localmente e con solo del testo + emoji) viene in tempo reale visualizzato correttamente a dx/sx in base al mittente e formattato abbastanza bene.
- Per rispondere a {SOD} il riconoscimento biometrico non è stato facile perchè nessuno giustamente ha fatto qualcosa simile al nostro, OVVIO, quindi ho incastrato 87 cose insieme meglio delle fatine che hanno pure la bacchetta.

13/10/2024

- {SOD} me son dimenticato di fare update su sto readme quindi tutte le seguenti informazioni sono relative a (circa) una settimana di lavoro
- {SOD} implementazione di nuovi metodi per permettere il send dei messaggi che vengono distinti in base al tipo di destinatario (utente,gruppo,canale). Il focus attuale è solo per l`utente (i metodi per canale/gruppo non esistono) e permette solo l'invio di messaggi a una specifica chat privata, è inoltre possibile creare una chat con un'altra persona tramite l'invio del primo messaggio (solo lato server, lato client verrà implementato successivamente)
- Aggiunti anche dei metodi sperimentali relativi al download e all'upload dei file e l'implementazione di WebSocket per ricevere i vari messaggi (da capire se conviene usare un WebSocket per il send dei messaggi o semplicemente usare la chiamata all'API)
- {MM} si diverte con flutter, non ho idea di cosa abbia fatto, sinceramente. L'ultima cosa che ha fatto è relativa alla registrazione con la sistemazione del validator anche con il check tramite api per verificare la disponibilitá dell'handle scelto

15/10/2024

- Sto perdendo il conto delle feature aggiunte (soprattutto quelle di {MM} visto che ci sentiamo poco in sto periodo :( )
- {SOD} DOPO TANTE ORE (VIVA I CIELI) sono riuscito a capire come funzionano le WebSocket (e anche se ancora con tanti bug, tipo le websocket che rimangono nell'array anche dopo la disconnessione) e siamo riusciti ad implementarla nell'applicazione (sia per ricevere i messaggi che per il send di ACK)
- Quindi a livello teorico, il send e il receive dei messaggi sarebbe fattibile (per ora solo su API, visto che su client manca tutta la questione del database dei messaggi locali, la gestione delle credenziali [api_key] e dell'identitá della persona [user_id] e la gestione CORRETTA delle websocket)

21/10/2024

- E dopo quasi una settimana tempo di aggiornare questa fantastica timeline
- Il client ora è super aggiornatissimo con tantissime nuove funzioni, principalmente adesso presenta un database funzione (basato su array e oggetti) che permette lo storage (teoricamente non permanente, ma questo è da capire) dei messaggi e delle chat che sono anche automaticamente visualizzare a schermo con anche la possibilità di entrarci dentro e aggiungere messaggi all'array
- Di conseguenza {SOD} ho sviluppato la sezione relativa all'ottenimento di tutti i dati dell'utente in seguito al login, richiesta e risposta fatte entrambe tramite websocket che permettono di ottenere in qualunque dispositivo le proprie chat/messaggi e dati basi relative all'utente locale

12/11/2024

 - Mamamiaquanto tempo essele pasato, ma tante belle cosine essere state fate in questo arco di tempoz
 - Creazione e sperimentazione di vari Project (su github) per la gestione del lavoro e varia documentazione (tipo il database, anche se devo trovare un modo migliore {anzi probabilmente mi conviene farlo da capo, fa schifo, tanto}):
   1) Lista completa della feature che verranno aggiunte (almeno speriamo, alcune sono particolarmente complesse)
   2) Timeline (a partire da qualche giorno fa) di tutto quello che facciamo lato client/server/documentazione ecc. (ci servirà nel futuro lo so)
   3) Creazione di un gruppo Telegram (ci tocca ancora usarlo, finchè BPUP Messanger non sarà operativo) per il salvataggio di file VIDEO e FOTO (che verrano poi usati per fare un fantastico trailer di presentazione o anche solo per ricordo di quanto eravamo stupidi)
- La parte server del send e receive dei messaggi è FUNZIONANTE (finalmente) ma non completa (più che altro servirebbe far funzionare la parte client per aggiungere le parti di informazioni mancanti e ottimizzare il codice qua e la)
- OTTIMIZZAZIONE del codice relativo a log, authentication, encrypter e jsonparser (quest'ultimo ora usa i dict e le liste [prima usava le stringe -_-] )
- Aggiornamento del file docker-compose.yml perchè mi sono dimenticato (ERRORE GRAVISSIMO) di salvare il SALT in locale (che quindi al riavvio del container veniva eliminato :/ con conseguente perdita di tutte le pass nel db)
- Ora passo al lato client di {MM} anche se, visto che non faccio nulla di là, non ricordo molto:
  1) Aggiunto database locale tramite sqlite per il salvataggio delle informazioni di base dell'utente + tutte le chat e messaggi
  2) Inizio piccolo rework della gestione delle websocket (cosi oggi SPERO riusciamo a mandare un piccolissimo messaggio tra di noi in chat private)
  3) Bho, sinceramente nun so :(
 
  Ah giusto, fantastico sc btw

19/11/2024

 - Me sa che da adesso in poi l'aggiornamento a sta timeline sarà settimanale (anche perchè mi ritrovo sempre il martedì ad aggiornarla)
 - IO {SOD} non sto più lavorando da qualche giorno, ho un esamettino stupido di Analisi e mi voglio concentrare su quello
 - Nelle giornate precedenti però ho continuato a fare mini bug fix e ottimizzazioni del codice qua e là e iniziato a predisporre nuovi metodi per poi sistemare definitivamente il send e receive dei messaggi (e speriamo, riuscir a far un video dove comunichiamo tra di noi da APK)
 - {MM} nel frattempo fa robe strane grafiche di cui non conosco le origini:
   1) pallini che girano per il caricamento
   2) animazioni per il validator (che adesso funziona e controlla effettivamente i valori)
   3) restyle delle chat list (con tutti i valori che necessitano [nome_chat,immagine,ultimo msg,data ultimo msg e messaggi non letti])
 - Infine sistemata TEMPORANEAMENTE (anche se sappiano tutti sarà semi permanente) delle websocket per ottenere tutti i dati INIZIALI (ancora il send_message, l'ack e in generale l'update del database locale non esistono)

03/12/2024

 - Aiutooooooooooooooooooooooooooooooooo
 - Ho fatto il parziale di analisi, 2/2 volo
 - Si ritorna a sviluppare questa fantastica applicazione
 - Nuove modifiche lato server con dei piccoli aggiustamenti ai metodi già esistenti tipo un limite di caratteri di 2056 (numero random, dopo capirò il vero limite del database), ottimizzato il metodo init che prima faceva cose strane per ottenere lo user_id (tipo tramite api_key che veniva trasformata in handle e dopo in user_id?? non so cosa stessi facendo)
 - Aggiunta una fantastica nuova pagine solo per noi fantastici admin (aggiunti più che altro per {MM} che ogni volta mi chiedeva i log del server a cui potevi accedere solo tramite ssh a oracle e leggendo il file fantastico nei data) che permette la visualizzazione dei log da pagina web
 - Lato client, ora i messaggini workano meglio ma manca ancora la parte fondamentale live
 - Inoltre ho trovato un fantastico buggettino con il biometric access che {MM} ha prontamente provveduto a fixare (grande efficenza questo lavoratore) 
