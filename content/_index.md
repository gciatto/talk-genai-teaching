
+++

title = "GenAI: Tecnologie ed Esempi di Utilizzo Per La Didattica"
description = "Formazione su IA generativa"
outputs = ["Reveal"]

+++

{{% section %}}

# GenAI: Tecnologie ed Esempi di Utilizzo Per La Didattica – In relazione alle linee guida di ateneo

[Giovanni Ciatto](mailto:giovanni.ciatto@unibo.it) & [Giovanni Antonioni](mailto:giovanni.antonioni2@studio.unibo.it)
<br> Dipartimento di Informatica — Scienza e Ingegneria (DISI), Sede di Cesena,
<br> Alma Mater Studiorum—Università di Bologna

{{< image src="./front.png" max-h="50vh" >}}

<span class="hint">(versione presentazione: {{< today >}})</span>


---

## Link a queste slide

<{{< slides-url >}}>

{{< qrcode >}}

[<i class="fa fa-print" aria-hidden="true"></i> versione stampabile](?print-pdf&pdfSeparateFragments=false)

---

## Scaletta

1. [Introduzione](#intro)
2. [Principali soluzioni tecnologiche](#interfaces)
3. [Principali modalità d'utilizzo di GenAI](#modes)
4. [Principalità impieghi di GenAI in ambito educativo](#academic-use)

{{% /section %}}

---

{{< slide id="intro" >}}

## __GenAI__: Intelligenza Artificiale _Generativa_

<!-- > [Sistemi basati su] <br> -->
Algoritmi di _IA_ in grado di __generare automaticamente__ _contenuti_, e.g.:
- _testo_
- immagini
- audio e/o video
- codice [di programmazione]
- ...

(cf. [Policy per un uso etico e responsabile dell’Intelligenza Artificiale Generativa nelle attività di didattica e ricerca](https://www.unibo.it/it/allegati/policy-per-un-uso-etico-e-responsabile-dell2019intelligenza-artificiale-generativa-nelle-attivita-di-didattica-e-ricerca/@@download/file/Policy-Generative-AI.pdf))

---

## GenAI mediante _Modelli Fondazionali_ (FM)

+ Grosse _reti neurali_ che imparano ad _elaborare_, _"capire"_, e _produrre_ __dati non__ [necessariamente] __strutturati__
+ __allenati__ su _grandi_ quantità di dati, e con _grandi_ risorse computazionali, a __fare un po' tutto__
    - con l'idea di poterli poi __specializzare__ per _compiti specifici_

<br>
{{< image src="./foundation-models.png" max-h="60vh" alt="Concept dei modelli fondazionali">}}

---

## __Terminologia__: Modelli Fondazionali vs. _Large Language Models_

{{< image src="./fm-vs-llm.webp" width="80%" max-h="70vh" alt="Diagramma di Venn che spiega come gli LLM siano un caso particolare di modelli fondazionali " link="https://thebabar.medium.com/essential-guide-to-foundation-models-and-large-language-models-27dab58f7404" >}}

---

{{% section %}}

## GenAI con modello di consumo _as-a-Service_

{{< image src="./llm-concept.svg" width="100%" max-h="70vh" alt="Modello di consumo 'as a Service' per i modelli fondazionali" >}}

---

## GenAI con modello di consumo _as-a-Service_

- Modelli di __costo__:
    + ad __abbonamento__: si paga un _canone_ fisso mensile/annuale per avere accesso al servizio
        * spesso contiene comunque _limiti_ di consumo
    + a __consumo__: si paga in _proporzione_ all'uso effettivo del servizio

- __Consumo__ è misurato in base allo _sforzo computazionale_ necessario per servire la richiesta:
    + _token_ processati (per testo)
    + quantità di _richieste_ effettuate per unità di tempo (minto, ore, giorno, mese)
    + _dimensione_ dei dati processati (per immagini, audio, video)
    + _complessità_ dello specifico _modello_ impiegato per per servire la richiesta

- La __generazione__ da considerarsi un processo _stocastico_, per costruzione

{{% fragment %}}
> - La __qualità__ del servizio è soggetta a casualità e a _fluttuazioni_ dovute a:
>    + _carico_ del servizio
>    + scelta del modello, e relativo _aggiornamento_
>    + _limiti_ di servizio eventualumente raggiunti nel _quanto di tempo_ corrente
>    + caso
{{% /fragment %}}

{{% /section %}}

---

{{% section %}}

## Ciclo di _apprendimento_ di GenAI

{{< image src="./dataflow.svg" width="100%" max-h="70vh" alt="Ciclo di apprendimento di GenAI" >}}

---

## Ciclo di _apprendimento_ di GenAI — __Conseguenze__ (pt. 1)

- __Bias__ di __campionamento__: GenAI conosce _solo_ ciò su cui è stato _allenato_ + pia speranza che impari a _generalizzare_

- L'apprendimento usa dati presi __dal Web__ + eventuali __dati aziendali__ del fornitore del servizio
    + comprovato impiego delle _interazioni_ degli utenti precedenti come _feedback_ per allenamenti successivi

{{% fragment %}}
##

> - Informazioni di __nicchia__ possono <u>non</u> essere apprese correttamente (o affatto)
> - Fondamentale __evitare di convididere__ informazioni _sensibili_, _confidenziali_, o protette da _diritti d'autore_
{{% /fragment %}}

---

## Ciclo di _apprendimento_ di GenAI — __Conseguenze__ (pt. 2)

- Cicli di apprendimento estramente __costosi__ in termini di _denaro_ e _risorse computazionali_...

- ... eseguiti __periodicamente__ (settimane? mesi?) per migliorare la _qualità_ del servizio
    + il modello di consumo _as-a-Service_ permette all'utente di avere accesso traspente al servizio _aggiornato_


{{% fragment %}}
##

> - Informazioni __recenti__ potrebbero <u>non</u> essere state (ancora) _apprese_
> - Rischio di ricevere risposte __datate__ o _manchevoli_ da GenAI
> - GenAI dà l'_impressione_ di star imparando __durante la conversazione__, ma in realtà lo fa _offline_
{{% /fragment %}}

{{% /section %}}

---

{{< slide id="interfaces" >}}

# Principali soluzioni __tecnologiche__

## Categorizzate per tipo di __interfaccia__

- _Conversazionali_: e.g. [ChatGPT](https://chatgpt.com/), [Claude](https://claude.ai/login?returnTo=%2F%3F), [Scite](https://scite.ai)
- _Auto-completamento_: e.g. [GitHub Copilot](https://github.com/features/copilot)
- _Programmatiche_: e.g. [OpenAI Platform](https://openai.com/api/), [Hugging Face](https://huggingface.co/)
- _In-App_: e.g. [Microsoft 365 Copilot](https://www.microsoft.com/it-it/microsoft-365/copilot?market=it)
- _Editing di audio-visivi_: e.g. [Suno](https://suno.com/), [Runway](https://runwayml.com/)
<!-- - _Ispezione di materiale generato_: e.g. [GPTZero](https://gptzero.me/), [ZeroGPT](https://www.zerogpt.com/) -->

{{% color "red" %}}Lista non esaustiva!{{% /color %}}

---

## Interfaccia __conversazionale__

{{% multicol %}}
{{% col %}}
{{< image src="./logo-chatgpt.svg" height="2em" >}}
{{< image src="./interface-conversational.png" width="100%" link="https://chatgpt.com/share/6798dd04-8a98-8008-a751-bc374318bd9e" >}}
{{% /col %}}
{{% col %}}
<br>

- Interazione _testuale_ che mima una _corrispondenza_ (__chat__)
    + l'utente chiede, l'IA risponde _reattivamente_
- L'interfaccia permette l'inserimento di un __prompt__
    + opzionalmente contenente _allegati_ (e.g. immagini, documenti)
- Le risposte sono __contestuali__
    + i.e., lo _storico_ della conversazione impatta le risposte _future_
- La risposta contiene __testo__ (spesso _formattato_)
    + opzionalmente: _immagini_, URL, codice

{{% fragment %}}

### Talvolta...

- ... prima di rispondere, l'IA fa una __ricerca__ su _Web_
- importante per avere risultati _aggiornati_

{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

## Interfaccia basata su __auto-completamento__

{{% multicol %}}
{{% col %}}
{{< image src="./logo-copilot.svg" height="2em" >}}
{{< image src="./interface-autocompletion.gif" width="100%" >}}
{{% /col %}}
{{% col %}}
<br>

- L'IA _suggerisce_ un __completamento__ per il testo inserito
    + e.g., codice, testo, URL
- L'utente __accetta__ (anche in parte) o _ignora_ il suggerimento
- Usato anche e soprattutto per __codice__ di _programmazione_

{{% fragment %}}

### Attenzione...
- ... modello di costo ad __abbonamento__ (vedi [qui](https://github.com/features/copilot/plans))
- ... potenziali __leak__ di informazioni _sensibili_
- ... rischio di __lock-in__ non trascurabile

{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

## Interfaccia __programmatica__

{{% multicol %}}
{{% col class="col-6" %}}
{{< image src="./logo-openai.svg" height="2em" >}}
```python
import asyncio
from openai import AsyncOpenAI

client = AsyncOpenAI(api_key="sk-1234567890abcdef1234567890abcdef")

async def main():
    stream = await client.chat.completions.create(
        model="gpt-4",
        messages=[
            dict(role="user",
                 content="European countries, one by line")
        ],
        stream=True,
    )
    async for chunk in stream:
        print(chunk.choices[0].delta.content or "", end=", ")

asyncio.run(main())
```

Output:
```plaintext
Albania, Andorra, Austria, Belarus, Belgium, Bosnia and Herzegovina, Bulgaria, Croatia, Cyprus, Czech Republic, Denmark, Estonia, Finland, France, Germany, Greece, Hungary, Iceland, Ireland, Italy, Kosovo, Latvia, Liechtenstein, Lithuania, Luxembourg, Malta, Moldova, Monaco, Montenegro, Netherlands, North Macedonia, Norway, Poland, Portugal, Romania, Russia, San Marino, Serbia, Slovakia, Slovenia, Spain, Sweden, Switzerland, Turkey, Ukraine, United Kingdom, Vatican City (Holy See),
```
{{% /col %}}
{{% col %}}

- __Linguaggio di programmazione__ che interagisce con IA
    + e.g., _Python_, JavaScript

- L'interazione rimane di tipo _richiesta-risposta_
    + il __programma__ invia una _richiesta_, l'IA _risponde_

{{% fragment %}}

### Abilitante per

- Prompt __parametrici__, risposte processate _automaticamente_
    + es. `list of LOCALITIES in AREA, one by line`
        + dove `LOCALITIES` $\in$ {`cities`, `regions`, `states`}
        + e `AREA` $\in$ {`Europe`, `Asia`, `Africa`, `America`, `Oceania`}
        + risultati _ordinati alfabeticamente_

- Scrittura __software__ che usa l'IA come __servizio__
    + utile in _industria_ come in _ricerca_

{{% /fragment %}}

{{% fragment %}}

### Attenzione...
- ... modello di costo __a consumo__ (vedi [qui](https://openai.com/api/pricing/))
    + proporzionale al numero di _token_ processati
    + prezzi variabili _per modello_

{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

## Interfaccia __in-app__

{{% multicol %}}
{{% col %}}
{{< image src="./logo-copilot-office.svg" height="2em" >}}
{{< image src="./interface-inapp.gif" width="100%" >}}
{{% /col %}}
{{% col %}}
<br>

- GenAI integrata in __applicazioni__ _desktop_ o _web_
    + e.g., _Microsoft Office_ (Word, Excel, Outlook)

- supporto per interfaccia __conversazionale__ _interna_
    + conversazione intrinsecamente _contestualizzata_

- IA __automatizza__ _operazioni complesse_ (interne all'app)
    + e.g., _scrittura_ di bozze
    + e.g., _generazione_ di formule, grafici

{{% fragment %}}

### Attenzione...
- ... modello di costo ad __abbonamento__ (vedi [qui](https://www.microsoft.com/it-it/microsoft-365/copilot?market=it#plans))
- ... potenziali __leak__ di informazioni _sensibili_
- ... rischio di __lock-in__ non trascurabile

{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

## Interfaccia per __editing__ di audio-visivi (e.g. _musica_)

{{% multicol %}}
{{% col %}}
{{< image src="./logo-suno.svg" height="2em" >}}
{{< image src="./suno/generate-song-1.png" width="100%" >}}
{{% /col %}}
{{% col %}}
- Interazione __one-shot__ per generare il contenuto
    + _input_: descrizione testuale del contenuto
    + _output_: contenuto

- L'interfaccia permette poi
    + _riproduzione_ del contenuto
    + __modifica__ del contenuto
        + e.g., _taglio_ di parti, _modifica_ di tonalità

{{% fragment %}}

### Esempio

- ["Canzona di Bacco" (Lorenzo il Magnifico, 1490)](https://it.wikipedia.org/wiki/Il_trionfo_di_Bacco_e_Arianna_(poesia)), rock
    + <https://suno.com/song/cce33ee7-a581-47ae-b9d1-806902e88e47>

{{% /fragment %}}
{{% /col %}}
{{% /multicol %}}

---

{{< slide id="modes" >}}

# Principali __modalità d'utilizzo__

## Categorizzate per __ruolo di GenAI__

### GenAI come...

* ... _motore di ricerca_: uso GenAI per __ricercare__ informazioni
* ... _assistente di (ri)scrittura_: uso GenAI per __(ri)scrivere__ documenti
* ... _assistente di lettura_: uso GenAI per __acquisire informazioni__ da documenti
* ... _assistente per l'elaborazione dei dati_: uso GenAI per __elaborare__ dati
* ... _generatore di contenuti_: uso GenAI per __creare__ contenuti

{{% color "red" %}}Lista non esaustiva!{{% /color %}}

---

{{< slide id="academic-use" >}}

## AI in ambito accademico.

- Abbiamo visto vari esempi di __impiego__ generico di GenAI a supporto di attività generiche
    + _generazione contenuti_, _supporto alla scrittura_, _assistenza nella ricerca_, _analisi dei dati_, _etc...

- Con i _progressi ottenuti_, l’AI è oggi sempre più __integrata__ in ambiti diversi.

- Anche il __mondo accademico__ si inserisce in questa tendenza, con GenAI a _supporto_ delle varie attività.

---

## AI in ambito accademico.

L'utilizzo di strumenti AI varia a seconda del __ruolo__ accademico considerato.

{{% multicol %}}
{{% col %}}

{{% fragment %}}
### Docenti
- __Supporto__ alla creazione di contenuti didattici
- __Sviluppo__ curriculum e __strutturazione__ delle lezioni
- __Valutazione__ e __feedback__ sull'andamento del corso
- __Supporto__ alle attività __amministrative__
- __Creazione__ di tutoring AI personalizzato
{{% /fragment %}}

{{% /col %}}
{{% col %}}

{{% fragment %}}
### Studenti
- __Produzione__ contenuti per progetti o appunti
- __Comprensione__ concettuale di argomenti complessi
- __Arricchimento__ del materiale prodotto o studiato
- __Brainstorming__ generazione idee per progetti o ricerche
{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---
## AI in ambito accademico: __Docenti__

- I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 1: _Creazione di contenuti didattici_
- I vari strumenti di AI possono essere adoperati per la generazione di vari contenuti
- Slide e quiz interattivi per gli studenti sono gli esempi più comuni...ma non sono i soli:
    + Possibile definire anche casi d'uso appositi per argomentare discussioni in classe
    + Creazione di guide di studio per gli studenti.
    + Generazione di esempi pratici per illustrare concetti teorici (codice, esercizi matematici, etc...).

---

## AI in ambito accademico: __Docenti__

- I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 2: _Delineazione corsi e pianificazione lezioni_

- Diversi strumenti AI possono essere usati come supporto per la delineazione dei vari aspetti di un corso:
    + Definizione degli obiettivi di apprendimento.
    + Strutturazionedi un curriculum coerente e completo.
    + Suggerimenti su contenuti e risorse da includere come approfondimento.
    + Suggerimenti su compiti o progetti per valutare gli studenti.
    + Definizione di una metodologia di valutazione basata su competenze acquisite. 
---

## AI in ambito accademico: __Docenti__

- I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 3: _Valutazione e feedback_

- AI trova impiego anche nel _monitoraggio_ e _valutazione_ del progresso degli studenti, con suggerimenti personalizzati per migliorare l'apprendimento
    + Analisi delle prestazioni degli studenti attraverso dati e metriche.
    + Feedback personalizzato basato sulle risposte degli studenti nei quiz o compiti.
    + Identificazione di aree di miglioramento
    + Suggerimenti su risorse o strategie di studio personalizzate.
  
---

## AI in ambito accademico: __Docenti__

- I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 4: _Supporto attività amministrative_

- L'efficacia nell'automatizzazione di compiti ripetitivi rende AI uno strumento utile per la gestione di varie attività amministrative
    + Gestione delle comunicazioni con gli studenti (email, annunci, etc...).
    + Gestione delle iscrizioni e registrazioni degli studenti.
    + Monitoraggio delle scadenze accademiche e amministrative.
  
---

## AI in ambito accademico: __Docenti__

- I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 5: _Creazione di tutor AI personalizzati_

- È possibile creare tutor AI personalizzati per assistere gli studenti al di fuori delle ore di lezione in grado di:
    + Rispondere a domande frequenti sugli argomenti del corso.
    + Fornire spiegazioni aggiuntive su concetti complessi.
    + Fornire supporto personalizzato in base alle esigenze individuali degli studenti.
  
---

## AI in ambito accademico: __Studenti__

- Gli __Studenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.


### Caso 1: _Produzione di contenuti_
- Gli studenti possono utilizzare AI per la generazione di vari contenuti:
    + Creazione di appunti di studio sintetici e organizzati.
    + Generazione di bozze per progetti o relazioni.
    + Creazione di presentazioni per progetti accademici.

---

## AI in ambito accademico: __Studenti__

- Gli __Studenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.


### Caso 2: _Comprensione_
- Diverse soluzioni AI sono in grado di aiutare gli studenti nello studio:
    + Spiegazioni semplificate di concetti complessi.
    + Risposte a domande specifiche su argomenti di studio.
    + Suggerimenti per ulteriori letture o risorse di apprendimento.
    + Esempi pratici per illustrare concetti teorici (codice, esercizi matematici, etc...).
  
---

## AI in ambito accademico: __Studenti__

- Gli __Studenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 3: _Arricchimento materiale prodotto_

- AI può aiutare a migliorare qualitativamente del materiale prodotto dagli studenti:
    + Correzione grammaticale e stilistica di testi.
    + Parafrasi o riformulazione di contenuti per maggiore chiarezza.
    + Suggerimenti per migliorare la struttura o l'organizzazione del materiale.
    + Strutturazione di codice per progetti di programmazione.
    + Generazione di grafici o diagrammi per visualizzare dati o concetti.

---

## AI in ambito accademico: __Studenti__

- Gli __Studenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche.

### Caso 4: _Brainstorming_

- Strumenti AI possono essere affiancati agli studenti a supporto del processo creativo:
    + Idee per progetti o ricerche.
    + Refactoring di codice.
    + Trovare soluzioni alternative a problemi complessi.
    + Suggerimenti per migliorare l'efficacia di presentazioni o discorsi.
---
{{< slide id="challenges" >}}

## Sfide e criticità dell'applicazione di GenAI all'educazione

- L'integrazione di AI generativa nell'educazione presenta enormi _opportunità_ sia per __studenti__ che __docenti__ 
- Tuttavia è giusto considerare anche varie {{% color "red" %}}criticità{{% /color %}} che possono emergere nell'adozione delle varie soluzioni:
  + Possibili __impatti negativi__ sull'apprendimento
  + Questioni __etiche__ e di __privacy__
  + Facilità di __abuso__ degli strumenti AI
- Vi è un dibattito in corso su come bilanciare i vari benefici offerti dall'AI con le potenziali sfide etiche, pedagogiche e pratiche.

Si vuole __evitare__ che l'AI diventi un __ostacolo__ piuttosto che un __supporto__ all'apprendimento.
  
---

## Integrità Accademica e Preoccupazioni per la Frode

- Vi sono preoccupazioni sempre più diffuse riguardo l'utilizzo di strumenti AI nel {{% color "red" %}}compromettere valutazioni date agli studenti e nell'integrità accademica{{% /color %}}.
- Non vi è un __controllo diretto__ su come gli studenti utilizzano questi strumenti, e ciò può portare a:
  + {{% color "red" %}}Plagio{{% /color %}} o presentazione di lavoro non originale.
  + {{% color "red" %}}Difficoltà {{% /color %}}nel valutare le competenze reali degli studenti.
  + Erosione della fiducia tra studenti e docenti.
---

## Integrità Accademica e Preoccupazioni per la Frode

- Questo ha comportato la __nascita__ di discussioni sull'effettivo utilizzo di AI in ambito accademico.
- Alcuni sostengono l'uso dell' AI debba essere __rigorosamente limitato__ o __vietato__ in certi contesti educativi.
- Altri, invece, vedono nell'AI un'_opportunità_ per migliorare l'apprendimento e l'insegnamento, a patto che venga utilizzata in maniera __responsabile__.
---

## Integrità Accademica e Preoccupazioni per la Frode

- Una delle soluzioni proposte è l'adozione di __sistemi di rilevamento__ di contenuti generati da AI. Tuttavia, questi presentano varie limitazioni:
    + Non rilevano direttamente il "plagio" ma piuttosto identificano testi che "sembrano" generati da AI (_similarità_).
    + Sono {{% color "red" %}}limitati{{% /color %}} in ciò che possono rilevare (esempio il riscrivere un testo generato da AI con parole proprie).
    + Possono produrre {{% color "red" %}}falsi positivi{{% /color %}}, penalizzando ingiustamente studenti.
    + Possono essere {{% color "red" %}}aggirati{{% /color %}} con tecniche semplici.

---

## Rischi per la Privacy dei Dati e la Sicurezza

- Dati caricati su piattaforme AI possono essere utilizzati per __addestrare modelli futuri__
- Ciò può comportare {{% color "red" %}}rischi per la privacy{{% /color %}}, specialmente se i dati contengono informazioni __sensibili__ o __personali__.
- Le istituzioni educative hanno __responsabilità__ che gli strumenti AI _aderiscano_ a normative sulla privacy e protezione dei dati (es. _GDPR_, _FERPA_, _COPPA_).
- Le istituzioni devono decidere se __limitare__ gli strumenti popolari o __investire__ in soluzioni dedicate e conformi.

---

## Problemi di Bias, Disinformazione e Accuratezza

- I modelli AI possono {{% color "red" %}} riflettere e amplificare errori{{% /color %}} presenti nei dati di addestramento.
- Ciò può portare a {{% color "red" %}}disinformazione{{% /color %}} o {{% color "red" %}} rappresentazioni distorte{{% /color %}} di argomenti.
- Gli studenti potrebbero {{% color "red" %}}accettare informazioni errate{{% /color %}} come verità, {{% color "red" %}}compromettendo{{% /color %}} la qualità dell'apprendimento.
- Risulta __fondamentale__ _accrescere una capacità di utilizzo responsabile e critica_ degli strumenti AI.

---

## Problemi di Bias, Disinformazione e Accuratezza


- Studenti e docenti devono essere _consapevoli_ dei limiti e potenziali errori degli strumenti AI.
- È importante _insegnare_ a _valutare criticamente_ le informazioni generate da AI e a verificare le fonti ed eventuali bias.
- Gli educatori devono __progettare__ compiti che richiedano un'_analisi critica_ degli output dell'IA, promuovendo competenze che vanno oltre la semplice ricerca di informazioni. 
- IA da strumento che fornisce risposte a strumento che _supporta il pensiero critico_ e la _risoluzione di problemi_.
  
---

## Impatto sul Pensiero Critico e sull'Eccessiva Dipendenza

- Abbiamo visto come __potenzialmente__ strumenti AI siano in grado:
  + Di fornire _facilmente_ accesso a risposte rapide.
  + Generare _immediatamente_ contenuti su richiesta.

- Tale facilità può portare a una {{% color "red" %}}dipendenza{{% /color %}} eccessiva dagli strumenti AI
- Diversi ostacoli all'apprendimento e allo sviluppo del pensiero critico:
  + {{% color "red" %}}Riduzione{{% /color %}} della capacità di ricerca indipendente.
  + {{% color "red" %}}Diminuzione{{% /color %}} della capacità di analisi critica delle informazioni.
  + {{% color "red" %}}Minore sviluppo{{% /color %}} di competenze di risoluzione dei problemi.
  
---

## Impatto sul Pensiero Critico e sull'Eccessiva Dipendenza

- Ricerche evidenziano come però, l'uso di AI generativa:
  + Possano _incrementare la creatività_,
  + _Facilitare_ un apprendimento più profondo se usata per _aumentare la conoscenza e la costruzione di idee_.

- A livello educativo è necessario progettare attività che __incoraggino__ l'uso critico e riflessivo degli strumenti AI, __promuovendo__ un equilibrio tra l'uso di AI e lo sviluppo di competenze umane fondamentali.
  
---

## Necessità di Sviluppo Professionale e Alfabetizzazione sull'IA

- Molti docenti {{% color "red" %}}non hanno ancora ricevuto{{% /color %}} una formazione adeguata sull’uso dell’IA, nonostante la sua diffusione crescente.
- I distretti scolastici stanno iniziando a introdurre _linee guida_ e programmi di _formazione_ per docenti e studenti.
- È stato suggerito che un modulo o un corso dedicato ai __chatbot IA__ dovrebbe diventare una componente __obbligatoria__ dei corsi di laurea per garantire che gli studenti siano _informati sull'uso di tali strumenti_.

---


![The end](./end.webp)