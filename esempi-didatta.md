### Docenti
* __Progettazione__ _curricula_, _sillabi_, struttura delle _lezioni_, etc
    + Pattern:
        - A-priori: `Progetta il sillabo per un corso su ...`
        - Variazione: `Riorganizza questo sillabo perchè sia più incrementale ...`
        - A partire da un contenuto: `Struttura una presentazione per una lezione su questo capitolo del libro ...` (fornendo il capitolo/libro)
    + Esempio:
        - Struttura Lezione su canto V della Divina Commedia
    + Note:
        - Meglio seguire un approccio gerarchico
        - Sempre meglio partire da materiale pre-esistente e allegarlo al prompt
            * attenzione ai diritti d'autore
        - Fornire suggerimenti sugli aspetti salienti
* Supporto alla __creazione__ di __contenuti didattici__ (slide, dispense, quiz, esercizi)
    + Pattern:
        - Fondamentalmente analogo alla progettazione con in più l'effettiva generazione del contenuto
    + Esempio:
        - Slide/Dispense/Parafrasi per Lezione su canto V della Divina Commedia
        - Domande a risposta aperta/multipla/etc su canto V della Divina Commedia
        - Esercizi per problemi di matematica su teorema di Pitagora
    + Note:
        - Meglio progettare prima la scaletta e poi chiedere la generazione del contenuto
* Supporto alla __valutazione__ degli studenti
    + Note:
        - Critico se si delega la quantificazione del voto o il giudizio alla AI
        - Accettabile se si usa l'AI per implementare una griglia di valutazione
    + Pattern:
        1. Per la domanda aperta `DDD` mi aspetto che la risposta corretta contenga
            1. `informazione 1` (con peso `p1`)
            1. ...
            1. `informazione N` (con peso `pN`)
        2. errori comuni sono
            1. `errore tipoco 1` (con penalità `-e1`)
            1. ...
            1. `errore tipoco M` (con penalità `-eM`)
        3. altri fattori bonus/malus sono
            1. `fattore 1` (con bonus `b1`)
            1. ...
            1. `fattore K` (con malus `-bK`)
        4. data la risposta `RRR` calcola il punteggio totale e fornisci un feedback costruttivo
            + interrompi il ragionamento e chiedimi come procedere se incontri elementi non coperti dalla griglia
        5. ri-proporziona il punteggio rispetto al peso della domanda nel quiz
    + Esempio:
        - Farei anche qui un esempio con la divina commedia, generando la griglia di valutazione + una risposta buona e una meno buona
  
* Supporto alla creazione di __feedback__ personalizzati
    + Come sopra ma senza specificare i punteggi
    + Oppure: data la domanda `DDD`, la risposta `RRR`, e la lista di mie opinioni grezze `OOO` formula un feedback costruttivo
* __Supporto__ alle _attività amministrative_ (lettere di raccomandazione, email, etc)
    + Esempi:
        - Lettera di raccomandazione per studente a partire da lista grezza di informazioni sullo studente
        - Estrazione di highlight da survey di fine corso
* Creazione di __tutori AI__ personalizzati per gli studenti
    + Qui non so bene che cazzo fare, ma immagino che l'idea sia fornire il materiale didattico pre-esistente e creare un chatbot fine-tuned su quell'arogmento
        + in tal caso: il consiglio è di fornire materiale vario (libri, appunti, slide, esercizi, etc) e di fare attenzione ai diritti d'autore
    + Esempio su divina commedia:
        - Fornire testo del canto, informazioni varie sulla cantica, su Dante, paragrasi varie, traduzioni varie, domande tipiche sull'argomento, etc
