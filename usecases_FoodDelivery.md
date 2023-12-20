# Casi d’uso Progetto Food Delivery

L’applicazione permette di gestire consegne a domicilio da parte di FoodsProvider.

Un utente si registra con mail e password.

All’applicazione è possibile accedere come utente Cliente, Ristoratore e Fattorino.

Il Cliente può effettuare ordini ai FoodProvider e recensire l’ordine ricevuto.

Il Ristoratore può creare più ristoranti, in cui registrare i propri prodotti. Tramite il ristorante creato potrà gestire gli ordini che riceve. 

Il Fattorino riceve notifiche per ordini da consegnare e li consegna, per ricevere le notifiche deve effettuare la timbratura d’entrata e per non riceverne deve effetturare la timbratura d’uscita.


## D.C.1 - Registrazione

### Attori

- Utente

### Requisiti

Entrare sulla pagina registrazione del sito. Contiene due campi obbligatori: mail e password. 

### Scenario base

1. Utente: accede alla pagina Registrazione.
2. Sistema: renderizza la pagina richiesta.
3. Utente: scrive i propri dati mail e password per creare l’utente.
4. Utente: clicca sul tasto “Iscriviti”.
5. Sistema: valida i dati immessi dall'utente.
6. Sistema: registra le credenziali utente e lo informa che è stato registrato con successo.
7. Utente: può fare login con le credenziali mail e password.

### Variante C.D. 1.1 - Utente clicca “Iscriviti” senza inserire i dati
3. Utente: clicca tasto invio senza inserire alcun dato.
4. Sistema: evidenzia i campi vuoti in rosso
5. Sistema: informa l’utente che non ha inserito dei dati neccessari a finalizzare la registrazione

### Variante C.D. 1.2 - Inserimento mail in formato errato
3. Utente: inserisce mail di formato errato 
4. Sistema: prova a validare la mail e fallisce
5. Sistema: evidenzia il campo mail in rosso
6. Sistema: informa l’Utente che ha inserito una mail incorretta

*Nota: se l'utente inserisce mail che non esiste ma che supera la validazione rientra nello scenario base*

### Variante C.D. 1.3 - Inserimento mail già registrata
3. Utente: inserisce mail già registrata
4. Sistema: prova a validare la mail e rileva la sua esistenza
5. Sistema: evidenzia il campo mail in rosso
6. Sistema: informa l’Utente che ha inserito una mail di un account già esistente

### Variante C.D. 1.4 - Inserimento password in formato errato
3. Utente: inserisce pasword di formato errato 
4. Sistema: prova a validare la password e fallisce
5. Sistema: evidenzia il campo password in rosso
6. Sistema: informa l’Utente che ha inserito una password troppo facile



## D.C.2 - Login

### Attori

- Utente

### Requisiti

Entrare sulla pagina login del sito. Contiene tre campi obbligatori: mail, password e ruolo

### Scenario base

1. Utente: accede alla pagina Login.
2. Sistema: renderizza la pagina richiesta
3. Utente: scrive i propri dati mail, password e ruolo per accedere.
4. Utente: clicca sul tasto Accedi.
5. Sistema: valida i dati immessi dall'utente.
6. Sistema: carica l'homepage.
7. Utente: può navigare nell'app, completare il suo profilo e fare ordini.

### Variante C.D. 1.1 - Utente clicca “Accedi” senza inserire i dati
3. Utente: clicca tasto invio senza inserire alcun dato.
4. Sistema: evidenzia i campi vuoti in rosso
5. Sistema: informa l’utente che non ha inserito dei dati neccessari a finalizzare la registrazione

### Variante C.D. 1.2 - Inserimento mail in formato errato
3. Utente: inserisce mail di formato errato 
4. Sistema: prova a validare la mail e fallisce
5. Sistema: evidenzia il campo mail in rosso
6. Sistema: informa l’Utente che ha inserito una mail incorretta

*Nota: se l'utente inserisce mail che non esiste ma che supera la validazione rientra nello scenario base*

### Variante C.D. 1.2 - Inserimento mail non registrata
3. Utente: inserisce mail non registrata
4. Sistema: prova a validare la mail ma non la trova tra quelle esistenti
5. Sistema: evidenzia il campo mail in rosso
6. Sistema: informa l’Utente che ha inserito una mail di un account non esistente
7. Sistema: carica la pagina Registrazione , con il campo mail precompilato

### Variante C.D. 1.3 - Inserimento password errata
3. Utente: inserisce pasword errata
4. Sistema: prova a validare la password e fallisce
5. Sistema: evidenzia il campo password in rosso
6. Sistema: informa l’Utente che ha inserito una password errata

### Variante C.D. 1.4 - Utente accede per la prima volta con un determinato ruolo
5. Sistema: valida i dati immessi dall'utente
6. Sistema: crea un Profilo associato al ruolo dell'Utente
7. Sistema: carica la pagina Profilo
8. Utente: può modificare i campi del nuovo Profilo.



## D.C.3 - Inserimento dati profilo

### Attori

- Utente

### Requisiti

L'utente deve essere loggato con un ruolo

### Scenario base

1. Utente: accede alla pagina Informazioni Profilo.
2. Sistema: carica la pagina con il form dei dati anagrafici (nome, cognome,data di nascita, telefono)
3. Utente: scrive i propri dati anagrafici.
4. Utente: clicca sul tasto Salva Modifiche.
5. Sistema: valida i dati immessi dall'utente.
6. Sistema: carica la pagina Informazioni Profilo.
7. Utente: può vedere i suoi dati aggiornati.

### Variante C.D. 3.1 - Utente non inserisce alcuni dei dati necessari
3. Utente: clicca tasto invio senza inserire alcun dato.
4. Sistema: evidenzia i campi vuoti in rosso
5. Sistema: informa l’utente che non ha inserito dei dati neccessari a finalizzare la registrazione






## D.C.4 - Timbratura

### Attori

- Fattorino
- Admin

### Requisiti

L'utente deve essere loggato come Fattorino

### Scenario base

1. Fattorino: apre la pagina Timbrature cliccando sul bottone in Homepage
2. Sistema: carica la pagina Timbratura con i bottoni ENTRATA o USCITA.
3. Fattorino: clicca sul bottone opportuno.
4. Sistema: registra la timbratura
5. Sistema: notifica di azione avvenuta con successo

### Postcondizioni

Il fattorino ha timbrato con successo e potrà prendere in carico il prossimo ordine di un ristorante nelle sue vicinanze.

### Variante C.D. 4.1 Pulsante sbagliato

6. Utente: notifica admin dell'errore
7. Admin: aggiusta il record 



## D.C.5 - Ordina Cibo

### Attori

- Cliente

### Premessa

L'ordine da parte del cliente è una delle fasi più complesse per l'applicazione in quanto sono necessari molti dati e interazioni.

Il percorso tra le pagine che dovrebbe fare normalmente l'utente è il seguente: 

Ristorante > Conferma Dati Spedizione (CDS) > Conferma Orario (CO) > Pagamento&RiepilogoOrdine (P&RO) > Ordini [ Help]

eventua

### Requisiti

L'utente deve essere loggato come Cliente

### Scenario base

1. Cliente: apre la pagina del Ristorante
2. Sistema: carica la pagina del ristorante con una foto del ristorante , le info , il menu , l'ordine (carrello)
3. Cliente: legge il menu
4. Cliente: aggiunge uno o più prodotti all'ordine
5. Sistema : stampa il prodotto(i) aggiunto
5. Cliente : sceglie consegna o ritiro in locale
6. Sistema : cambia il tipo di consegna switchando il bottone
7. Cliente : clicca il tasto VAI AL PAGAMENTO
8. Sistema: salva dati ordine (cliente,ristorante,prodotti,tipo di consegna)
9. Sistema: carica la pagina CDS(nome , cognome , cell , indirizzo)
10. Cliente: inserisce i dati opportuni
11. Cliente: clicca sul bottone Continua
12. Sistema: caricamento (salva nell'ordine i dati indirizzo)
13. Sistema:carica pagina CO con il seguente *form*
- menu a tendina di selezione range oppure "Appena possibile"
- campo testo note opzionale (sono utili al corriere)
14. Cliente: compila *form* e clicca bottone continua
15. Sistema: caricamento (salva nell'ordine l'orario e le note)
16. Sistema: carica pagina P&RO con *form* di selezione metodo di pagamento tra: 
- Carta (+ form dati carta)
- PayPal (+ bottone PagaConPayPal)
- Contanti
17. Cliente: rilegge l'ordine e clicca su uno dei metodi di pagamento
18. Sistema: mostra nella pagina P&RO il bottone OEP ed eventuali form / bottoni relativi ai pagamenti
19. Cliente: compila eventuali campi e clicca sul bottone OEP
20. Sistema: caricamento (salva nell'ordine il tipo di pagamento e invia l'ordine al ristorante)
21. Sistema: carica la pagina 




### Postcondizioni

L'utente è stato registrato con successo e può accedere alla piattaforma utilizzando le nuove credenziali.

### Variante C.D. 5.1 Utente non loggato

8. Sistema: salva i dati dell'ordine
9. Sistema: carica la pagina di accesso
10. Utente: inserisce dati e clicca Accedi
11. Sistema: sostituisce il bottone accedi (arancione)con uno di caricamento (grigio)
12. Sistema: carica la pagina di Conferma dati

### Variante C.D. 5.2 Utente aveva già inserito i dati di spedizione
9. Sistema la pagina di Conferma dati precompilata



## D.C.6 - Affida Ordine

### Attori
- Ristoratore

### Requisiti
Il Ristoratore deve essere loggato sulla pagina Ordini  nella sezione dell'ordine specifico

### Scenario base
1. Ristoratore: Il Ristoratore clicca sul bottone "Affida ordine" 
2. Sistema: Invia ad un fattorino una notifica di consegna da effettuare
3. Sistema: INforma che l'azione è stata eseguita con successo




## D.C.7 - Notifica  Ordine Fattorino

### Attori
- Fattorino

### Requisiti
Il Fattorino deve essere loggato sull'applicazione.

### Scenario base
1. Sistema: Invia notifica al fattorino, affidandogli un numero univoco dell'ordine e informazioni base sulla consegna da effettuare 
2. Fattorino: Il Fattorino clicca sul bottone "Notifiche"  
3. Sistema: Indirizza alla pagina notifiche
 


## D.C.8 - Notifica  Ordine Ristoratore 

### Attori
- Ristoratore 

### Requisiti
Il Ristoratore deve essere loggato sull'applicazione.

### Scenario base
1. Sistema: Invia notifica al Ristoratore , affidandogli un numero univoco dell'ordine e informazioni base sulla consegna da effettuare al cliente
2. Ristoratore : Il Ristoratore clicca sul tasto "Notifiche"  
3. Sistema: Indirizza alla pagina notifiche


## D.C.9 - Consegna  Ordine

### Attori
- Fattorino

### Requisiti
Il Fattorino deve essere loggato sull'applicazione sulla pagina "Ordini".

### Scenario base
1. Fattorino: Il Fattorino clicca sul tasto "Consegna effettuata"  dell'ordine specifico
2. Sistema: Comunica che l'azione è stata eseguita correttamente 



## D.C.10 - Creazione Food Provider

### Attori
- Ristoratore

### Requisiti
Il Ristoratore deve essere loggato e accedere alla pagina dell'applicazione "Gestisci Food Provider".

### Scenario base
1. Ristoratore: Il Ristoratore inserisce i dati del nuovo Food Provider che vuole creare  
2. Ristoratore: Il Ristoratore clicca sul tasto Salva  
3. Sistema: Crea un Food Provider a cui potrà accedere per inserire i prodotti.

### Variante C.D. 10.1Utente clicca “Salva” senza inserire 1 o più dati obbligatori
2. Ristoratore: Il Ristoratore clicca sul tasto Salva  senza aver inserito tutti i dati obbligatori necessari alla creazione del Food Provider
3. Sistema: Informa che mancano alcuni dati obbligatori per poter creare il nuovo Food Provider.


## D.C.11 - Creazione Prodotto

### Attori
- Ristoratore

### Requisiti
Il Ristoratore deve essere loggato e avere creato un Food Provider e accedere alla pagina dell'applicazione "Gestisci prodotti" di un specifico Food Provider.

### Scenario base
1. Ristoratore: Il Ristoratore inserisce i dati del prodotto  
2. Ristoratore: Il Ristoratore clicca sul tasto Salva  
3. Sistema: Aggiunge tra i prodotti presenti nel Food Provider il nuovo prodotto.

### Variante C.D. 11.1  Utente clicca “Salva” senza inserire 1 o più dati obbligatori
2. Ristoratore: Il Ristoratore clicca sul tasto Salva  senza aver inserito tutti i dati obbligatori necessari alla creazione del prodotto
3. Sistema: Informa che mancano alcuni dati obbligatori per poter creare il nuovo prodotto.





## D.C.12 - Eliminazione profilo altrui

### Attori
- Admin

### Requisiti
L'Admin deve essere loggato e accedere alla pagina "Visualizza utenti registrati"

### Scenario base
1. Admin: Inserisci i dati per ricercare un utente specifico
2. Admin: Clicca tasto invio
3. Sistema: Mostra l'utente ricercato 
4. Admin: Clicca sul tasto "Banna utente"
5. Sistema: Informa che l'utente è stato bannato correttamente

### Variante C.D. 12.1  Admin inserisce dati che non corrispondono a nessun utente
3. Sistema: Informa che non è stato trovato nessun utente in base alla ricerca effettuata.


## D.C.13 - Scrivi recensione

### Attori
- Cliente

### Requisiti
Il Cliente deve essere loggato,  aver ricevuto un ordine dal Food Provider che vuole recensire ed essere sulla pagina del Food Provider che vuole recensire

### Scenario base
1. Cliente: Il Cliente  inserisce una recensione testuale 
2. Cliente: Il Cliente clicca quante stelle vuole attribuire alla recensione (da 1 a 5)
3. Cliente: Il Cliente  clicca sul tasto salva
4. Sistema: Aggiunge tra le recensioni già esistenti la nuova recensione inserita

 ### Variante C.D. 13.1  Cliente non clicca sul numero di stelle da attribuire
 2. Cliente: Il Cliente  clicca sul tasto salva
 3. Sistema: Informa che non è possibile inserire la nuova recensione perchè non è stato inserito il dato obbligatorio "Numero di stelle"



## D.C.14 - Logout

### Attori
- Cliente
- Ristoratore
- Fattorino
- Admin

### Requisiti
L'utente deve essere loggato in una pagina qualsiasi dell'applicazione

### Scenario base
1. Utente: L'utente clicca sul bottone Profilo 
2. Sistema: Apre un menù a tendina con varie opzioni
3. Utente: L'utente clicca sul bottone Esci 
4. Sistema: Effettua il logout dell'utente dall'applicazione e reindirizza l'utente sulla home con visualizzazione da "Profilo non loggato"
