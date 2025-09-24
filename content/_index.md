
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

{{< slide id="toc" >}}

## Scaletta

1. [Introduzione](#intro)
1. [Principali soluzioni tecnologiche](#interfaces)
1. [Principali modalità d'utilizzo di GenAI](#modes)
    1. per [docenti](#academic-use-teachers)
    1. per [studenti](#academic-use-students)
1. [Principali impieghi di GenAI in ambito educativo](#academic-use)
1. [Esempi di tecnologie GenAI per l'educazione](#technologies)
1. [Sfide e criticità dell'applicazione di GenAI all'educazione](#challenges)
1. [Sperimentazioni in corso in UniBo](#unibo-experiments)

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

{{% section %}}

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

{{% /section %}}

---

{{< slide id="modes" >}}

# Principali __modalità d'utilizzo__ _generali_

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

# Principali __impieghi__ di GenAI in ambito educativo

L'utilizzo di strumenti AI varia a seconda del __ruolo__ accademico considerato.

{{% multicol %}}
{{% col %}}

{{% fragment %}}
## Docenti
- __Progettazione__ _curricula_, _sillabi_, struttura delle _lezioni_, etc.
- Supporto alla __creazione__ di _contenuti didattici_
- Supporto alla __valutazione__ e al __feedback__ per gli studenti
- __Supporto__ alle _attività amministrative_
- Creazione di __tutori AI__ personalizzati per gli studenti
{{% /fragment %}}

{{% /col %}}
{{% col %}}

{{% fragment %}}
## Studenti
- __Produzione__ di _contenuti_ per lo studio <!-- (riassunti, appunti, etc.) --> o _elaborati_
- __Ricerca__ e __sintesi__ di informazioni da _fonti varie_
- __Tutoraggio__ _personalizzato_ e pratica
- __Arricchimento__ del _materiale_ di studio <!-- (e.g. sbobinatura, traduzione) -->
<!-- - __Brainstorming__ generazione idee per progetti o ricerche -->
{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

{{< slide id="academic-use-teachers" >}}

# GenAI in ambito educativo: __Docenti__

---

## GenAI in ambito educativo: __Docenti__

<!-- - I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche. -->

### __Progettazione__ di _contenuti didattici_ (Overview)

GenAI utile per _delineare_ i vari aspetti di un __percorso didattico__, tra cui:
+ Definizione degli _obiettivi di apprendimento_
+ Strutturazione di un _sillabo_ coerente e completo
+ Suggerimenti su contenuti e _risorse_ da includere come _approfondimento_
+ Suggerimenti su _compiti_ o _proposte di progetto_ per gli studenti
+ Definizione di una _metodologia di valutazione_ basata su criteri chiari

---

## GenAI in ambito educativo: __Docenti__

### __Progettazione__ di _contenuti didattici_ (Pattern di prompt utili)

- <u>`Progetta`</u>` il sillabo per un corso su X`
    - assume che `X` sia un argomento ben definito

- <u>`Suggerisci`</u>` una diversa struttura per questa dispensa affinché sia più incrementale`
    - \[allegando la dispensa]
    - approccio incrementale spesso più efficace

- <u>`Struttura`</u>` una presentazione per una lezione su questo capitolo del libro X`
    - \[allegando il capitolo/libro]

---

## GenAI in ambito educativo: __Docenti__

### __Progettazione__ di _contenuti didattici_ (Esempio)

- `Struttura una lezione su canto V della Divina Commedia, livello liceo scientifico.`
    + caricando il _testo del canto_, e la _pagina Wikipedia_ corrispondente


<br>

{{< image src="./teaching/divine-comedy-structure.png" max-h="50vh" alt="Esempio di struttura di lezione generata da ChatGPT" >}}

\[conversazione completa: <https://chatgpt.com/share/68c986ed-ab5c-8008-ace0-26f3c6edccc8>]

---

## GenAI in ambito educativo: __Docenti__

### __Progettazione__ di _contenuti didattici_ (Note)

- Meglio seguire un approccio __gerarchico__:
    + prima la struttura generale delle lezioni
        + poi la struttura di ogni lezione
            + poi la struttura di ogni slide
                + ...

- Sempre meglio partire da __materiale pre-esistente__ e _allegarlo_ al prompt
    * attenzione ai diritti d'autore

- Fornire __suggerimenti__ sugli aspetti salienti da considerare _nel prompt_

---

## GenAI in ambito educativo: __Docenti__

<!-- - I __Docenti__ utilizzano AI per semplificare e migliorare vari aspetti della loro attività didattiche. -->

### Supporto alla __creazione__ di _contenuti didattici_ (Overview)
<!-- - I vari strumenti di AI possono essere adoperati per la generazione di vari contenuti -->
<!-- - Slide e quiz interattivi per gli studenti sono gli esempi più comuni...ma non sono i soli: -->

GenAI utile per _generare_ effettivamente i contenuti didattici, tra cui:

+ _Slides_ / presentazioni
+ _Dispense_ / materiale da studiare
+ _Casi di studio_ / __esempi__
+ Esercizi / _quiz_ / _test_ di vario tipo

---

## GenAI in ambito educativo: __Docenti__

### Supporto alla __creazione__ di _contenuti didattici_ (Pattern di prompt utili)

- <u>`Genera`</u> `il sillabo per un corso su X`
    - assume che `X` sia un argomento ben definito

- <u>`Riscrivi`</u> `questa dispensa affinché sia più incrementale`
    - \[allegando la dispensa]
    - approccio incrementale spesso più efficace

- <u>`Genera`</u> `una presentazione per una lezione su questo capitolo del libro X`
    - \[allegando il capitolo/libro]

---

## GenAI in ambito educativo: __Docenti__

### Supporto alla __creazione__ di _contenuti didattici_ (Esempio)

- `Genera le slide di una lezione su canto V della Divina Commedia, livello liceo scientifico`
    + caricando il _testo del canto_, e la _pagina Wikipedia_ corrispondente
    + magari avendo fornito la _struttura generale_ nelle __interazioni precedenti__

<br>

{{< image src="./teaching/divine-comedy-slides.png" max-h="50vh" alt="Esempio di generazioni di slide da ChatGPT" >}}
\[slide generate visibili [qui](https://docs.google.com/presentation/d/1-6cSMomDG--L2GfOJQmAQ9wzNDCm9ng5fJ8czOYuzqY/edit?usp=sharing)]

\[conversazione completa: <https://chatgpt.com/share/68c986ed-ab5c-8008-ace0-26f3c6edccc8>]

---

## GenAI in ambito educativo: __Docenti__

### Supporto alla __creazione__ di _contenuti didattici_ (Note)

- Meglio _progettare la scaletta_ __prima di__ chiedere la _generazione del contenuto_
    * i.e. flusso logico delle slide

- Meglio fornire __materiale pre-esistente__ e _allegarlo_ al prompt
    * attenzione ai diritti d'autore

- Meglio richiedere la generazione di elementi singoli (es. slide) __uno alla volta__
    * e.g., `Genera la slide 1`, `Genera la slide 2`, etc.

---

## GenAI in ambito accademico: __Docenti__

### Supporto alla __valutazione__ degli studenti (Overview)

+ _Valutazione semi-automatica_ delle risposte degli studenti
+ _Feedback personalizzato_ basato sulle risposte degli studenti nei _quiz_ o _compiti_
+ _Identificazione_ di aree di miglioramento/approfondimento
<!-- + _Suggerimenti_ su _risorse_ o _strategie_ di studio personalizzate. -->

---

## GenAI in ambito accademico: __Docenti__

### Supporto alla __valutazione__ degli studenti (Pattern di prompt utili)

- <u>`Valuta`</u> `la risposta X data alla domanda Y secondo questi criteri di valutazione: ...`
    | Tipo                   | Descrizione        | Peso / Valore |
    |------------------------|--------------------|---------------|
    | **Informazioni attese**| informazione $1$     | $p_1$            |
    |                        | informazione $2$     | $p_2$           |
    |                        | informazione $N$     | $p_N$            |
    | **Errori tipici**      | errore tipico $1$    | $-e_1$           |
    |                        | errore tipico $2$    | $-e_2$           |
    |                        | errore tipico $M$    | $-e_M$           |
    | **Fattori bonus/malus**| fattore $1$ (bonus)  | $+b_1$           |
    |                        | fattore $2$ (malus)  | $-b_2$           |
    |                        | fattore $K$ (malus)  | $-b_K$           |


- `... calcola il punteggio totale e fornisci un feedback costruttivo`
    <!-- + La scala di valutazione va da 0 a 30, eventuali mezzi punti sono arrotondati per difetto -->
    + \[opt] `interrompi il ragionamento e chiedimi come procedere se incontri elementi non coperti dalla griglia`

---

## GenAI in ambito accademico: __Docenti__

### Supporto alla __valutazione__ degli studenti (Pattern di prompt utili, cont.)

- `Riposta X alla domanda Y, segue opinione grezza, aiutami a dare un feedback costruttivo`
    + Le opinioni grezze possono essere ad esempio:
        - "La risposta è corretta ma manca di esempi pratici"
        - "La spiegazione è chiara ma alcuni passaggi sono troppo sintetici"
        - "L'argomento è ben coperto ma la struttura del testo è confusa in alcuni punti"

- `Risposta X alla domanda Y, giudizio Z, suggerisci materiali di approfondimento per lo studente`
    + fornire copia dei materiali didattici se si vuole che GenAI attinga da essi
---

## GenAI in ambito accademico: __Docenti__

### Supporto alla __valutazione__ degli studenti (Esempio completo)

- _Domanda_ esempio:
<br/>
<span style="color: grey; font-style: italic;">
    "Nel Canto V dell’Inferno, Dante incontra Paolo e Francesca. Analizza come l’autore intreccia amore e colpa nella rappresentazione dei due personaggi, mettendo in evidenza gli strumenti poetici e retorici utilizzati per suscitare empatia nel lettore, e discuti in che modo questo episodio contribuisce alla visione dantesca della giustizia divina"
</span>

- _Griglia_ di valutazione:

| Tipo                    | Descrizione                                                                                   | Peso / Valore |
| ----------------------- | --------------------------------------------------------------------------------------------- | ------------- |
| **Informazioni attese** | Contestualizzazione del canto V                                                               | 2             |
|                         | Presentazione della pena dei lussuriosi (bufera infernale)                                    | 2             |
|                         | Racconto di Paolo e Francesca: dinamica della vicenda                                         | 2             |
|                         | Analisi dei temi amore/colpa/peccato ed empatia suscitata                                     | 3             |
|                         | Collegamento alla visione della giustizia divina e al progetto etico-teologico di Dante       | 3             |
| **Errori tipici**       | {{% color "red" %}}Riassunto meramente narrativo senza analisi {{% /color %}}                 | -2            |
|                         | Confondere canto o collocazione nell’Inferno                                                  | -1            |
| **Fattori bonus/malus** | Uso di citazioni testuali mirate (anche brevi)                                                | +2            |
|                         | Argomentazione poco coerente o priva di struttura                                             | -2            |
|                         | Approfondimento critico originale (es. riflessione sul rapporto tra eros e logos)             | +2            |

---

## GenAI in ambito accademico: __Docenti__

### Supporto alla __valutazione__ degli studenti

- Risposta esempio _buona_ (voto 26/30):
<br/>
<span style="color: grey; font-style: italic;">
    "Nel canto V Dante colloca i lussuriosi nel secondo cerchio, travolti dalla bufera che simboleggia la passione incontrollata. L’incontro con Paolo e Francesca, introdotto dal giudizio di Minosse, è narrato con forte pathos: Francesca parla per entrambi, presentando l’amore come forza inevitabile, alimentata dalla lettura (“Galeotto fu ’l libro”). Dante utilizza un registro lirico che suscita empatia, ma al tempo stesso mostra come la mancanza di responsabilità trasformi l’amore in colpa. Il canto esprime così la tensione tra pietà umana e giustizia divina."
</span>

<!-- - Risposta esempio {{% color "red" %}} non accurata {{% /color %}} (voto 14/30):
<br/>
<span style="color: grey; font-style: italic;">
    "Nel canto V Dante incontra Paolo e Francesca, uccisi dal marito di lei dopo essersi innamorati leggendo un libro. Dante si commuove e sviene. L’episodio è famoso perché parla di un amore romantico che colpisce ancora oggi."
</span> -->

{{< image src="./teaching/divine-comedy-eval.png" max-h="50vh" alt="Correzione risposte tramite ChatGPT" >}}

---

## GenAI in ambito accademico: __Docenti__

### Caso 4: _Supporto attività amministrative_ (Overview)

<!-- - L'efficacia nell'automatizzazione di compiti ripetitivi rende AI uno strumento utile per la gestione di varie attività amministrative -->
+ Generazione di __comunicazioni__ generali/personalizzate con gli studenti (email, annunci, etc...)
+ Creazione di __documenti__ amministrativi standard (lettere, report, etc...)
+ Analisi dei __questionari della didattica__ per individuare aree di miglioramento
+ Generazione __timesheet__ o _report di avanzamento_ per progetti di ricerca

---

## GenAI in ambito accademico: __Docenti__

### Caso 4: _Supporto attività amministrative_ (Pattern di prompt utili)
<!-- - <u>`Genera`</u> ` una email per informare gli studenti del corso X che la lezione di domani è spostata a data Y` -->

- <u>`Genera`</u> ` una lettera di benvenuto per i nuovi studenti iscritti al corso X`
    + includendo informazioni su:
        * struttura del corso
        * modalità di valutazione
        * risorse disponibili
        * contatti utili

- <u>`Crea`</u> ` una lettera di raccomandazione per lo studente Y basata su queste informazioni: ...`
    + __Privacy-concerning__: informazioni sullo studente (es. voti, progetti, etc...)
    + interazioni passate tra il firmatario e lo studente
    + informazioni sul destinatario (es. università, azienda, etc...)

- `Dato questo questionario di feedback degli studenti,` <u>`genera`</u> ` un report sintetico con i punti chiave e suggerimenti per migliorare il corso`
    + \[allegando esiti del questionario e feedback dello studente]

- `Genera un timesheet mensile per il progetto P, considerando i seguenti vincoli:`
    + `massimo 8 ore al giorno, dal lunedì al venerdì`
    + `faccio 3 ore di lezione il lunedì e 2 ore il mercoledì`
    + __Nota__ LLM non possono inferire il calendarario se non per mezzo di informazioni esplicite e/o tools

<!-- ---

## AI in ambito accademico: __Docenti__

### Caso 4: _Supporto attività amministrative_

- Immaginiamo di voler inviare una email di benvenuto agli studenti iscritti al corso:

- `Generami una lettera sintetica di benvenuto agli studenti del mio corso sull'opera "La divina commedia" di Dante Alighieri. Il corso tratterà del background di Dante e inquadrerà gli aspetti essenziali dei vari canti.`
  + Descrizione del corso: `Il corso tratterà del background di Dante e inquadrerà gli aspetti essenziali dei vari gironi.`
  + Descrizione modalità esame: `L'esame è costituito da una parte scritta più una parte orale (l'ultima accessibile solamente superando quella scritta).`
  + Descrizione risorse: `Le lezioni saranno basate su slide e dispense, con materiale di approfondimento consigliato.`
  + Orario lezioni:
    * Lunedì 9:00 - 11:00
    * Mercoledì 14:00 - 16:00
    * Giovedì 10:00 - 12:00
  + Eventuali contatti: `ugo.rossi@unibo.it` -->

<!-- ---

## AI in ambito accademico: __Docenti__

### Caso 4: _Supporto attività amministrative_

### Risultato generato:
{{< image src="./teaching/welcome-letter-chatgpt.png" max-h="80vh" alt="Welcome letter written with ChatGPT" >}} -->

---

## GenAI in ambito accademico: __Docenti__

### Caso 5: _Creazione di tutor AI personalizzati_

> Tutor AI $\approx$ _Chatbot_ basato su LLM, istruito/informato su materiale specifico del corso/docente

È possibile __creare__ _tutor AI personalizzati_ per _assistere_ gli studenti al di fuori delle ore di lezione in grado di
+ __Rispondere__ a domande _frequenti_ sugli argomenti/logistica del corso
+ Fornire __spiegazioni__ aggiuntive su _argomenti del corso_
+ Fornire __supporto__ personalizzato in base alle _esigenze_ individuali degli studenti

{{% fragment %}}
> Doppia interfaccia:
> 1. Studente $\rightarrow$ interfaccia _conversazionale_ (chat)
> 2. Docente $\rightarrow$ interfaccia semplificata per _caricare_ materiali/istruzioni di riferimento
{{% /fragment %}}

---

## GenAI in ambito accademico: __Docenti__

### Caso 5: _Creazione di tutor AI personalizzati_

- Esistono varie _piattaforme_ che permettono di _creare facilmente_ dei bot personalizzati basati su LLM

- Esempio: [SchoolAI](https://schoolai.com/)
    + Si crea uno __"spazio di lavoro"__, inserendo il nome del corso e una breve descrizione
    + Si __caricano__ i materiali di riferimento (dispense, slide, link a pagine web, etc...)
    + Eventualmente vengono fornite altre _informazioni utili_ (preferenze del docente, orari, convenzioni, etc)

- Una volta creato lo spazio di lavoro, si può _iniziare a chattare_ con il bot, che risponderà in base al materiale caricato

<div style="display:flex; gap:30px; justify-content:center; align-items:flex-start;">
  <figure style="text-align:center;">
    {{< image src="./schoolai/setup.png" max-h="40vh" alt="SchoolAI Setup" >}}
    <figcaption><p style="font-size: 24px; font-style: italic;">Setup dello spazio di lavoro</p></figcaption>
  </figure>

  <figure style="text-align:center;">
    {{< image src="./schoolai/chat.png" max-h="40vh" alt="SchoolAI Chat" >}}
    <figcaption><p style="font-size: 24px; font-style: italic;">Chat con il tutor AI</p></figcaption>
  </figure>
</div>

---

{{< slide id="academic-use-students" >}}

# GenAI in ambito educativo: __Studenti__

---

## GenAI in ambito accademico: __Studenti__

### Caso 1: _Produzione di contenuti_ (Overview)

+ Creazione di __appunti__ di studio _sintetici_ e _organizzati_
+ Generazione di __bozze__ per _progetti_ o _relazioni_
+ Creazione di __presentazioni__ per _progetti accademici_
+ Validazione di __contenuti__ (e.g., controllo grammaticale, coerenza, etc...)

---

## GenAI in ambito accademico: __Studenti__

### Caso 1: _Produzione di contenuti_ (Pattern di prompt utili)

- <u>`Integra`</u>` questi due appunti di lezione in un unico documento coerente e ben strutturato`
    + \[allegando i due appunti]
    + opzionalmente: `Evidenzia le parti ridondanti o contraddittorie`
    + opzionalmente: `Aggiungi un sommario all'inizio`

- `Data questa scaletta, generami una bozza per questo capitolo di tesi`
    + \[allegando la scaletta + riferimenti bibliografici]
    + si può anche chiedere di mantenere uno stile specifico (formale, informale, tecnico, etc...)

- `Dato il documento caricato,` <u>`trova errori `</u> `,` <u>`incongruenze `</u> `,` <u>`punti di attacco `</u> `e` <u>`suggerimenti `</u> `per migliorarlo`
    + \[allegando la bozza]

---

## GenAI in ambito accademico: __Studenti__

### Caso 1: _Produzione di contenuti_ (Esempio)

- `Genera una parafrasi puntuale del canto, riga per riga`
    + \[allegando il testo del canto]

<br>

{{< image src="./student/divine-comedy-chap5-analysis.png" max-h="60vh" alt="Parafrasi (generata) del canto V della Divina Commedia" >}}

---

## GenAI in ambito accademico: __Studenti__

### Caso 1: _Produzione di contenuti_ (Note)

- La produzione di contenuti permette di avere una _base di partenza_ su cui lavorare
    + utile per la prima stesura, non per l'ultima
    + si genera una __bozza__, poi la si _rielabora_ e _migliora_.

- Nella produzione di contenuti con GenAI è importante:
    + fare attenzione {{% color "red" %}}diritti d'autore{{% /color %}} e {{% color "red" %}}plagio{{% /color %}} anche accidentale
    + __verificare sempre__ l'_accuratezza_ e la _correttezza_ delle informazioni generate

- È importante __specificare__ chiaramente il _contesto_, gli _obiettivi_, e _background_ nel prompt
    + è possibile fornire queste informazioni man man che si corregge il tiro
---

## GenAI in ambito accademico: __Studenti__

### Caso 2: _Comprensione_ (Overview)

+ __Spiegazioni__ _semplificate_ di concetti complessi
+ __Risposte__ a domande _specifiche_ su argomenti di studio
+ __Suggerimenti__ per ulteriori _letture_ o _risorse di apprendimento_
+ __Esempi__ pratici per _illustrare_ concetti teorici (codice, esercizi matematici, etc...)
+ __Confronti__ tra concetti simili per chiarirne le differenze

---

## GenAI in ambito accademico: __Studenti__

### Caso 2: _Comprensione_

- `Spiegami in termini semplici il concetto di X`
    + \[fornendo magari materiale didattico]

- `Nel documento allegato cosa si intender per A?`
    + \[allegando il documento]
    + opzionalmente: `Spiegami con un esempio pratico`

- `Quali sono le differenze principali tra i concetti A e B?`
    + Specifica sempre un _contesto_ per i concetti A e B.
    + Ad esempio, "In ambito matematico, quali sono le differenze tra funzione e relazione?"

---

## GenAI in ambito accademico: __Studenti__

### Caso 2: _Comprensione_

- `All'interno del canto V della Divina Commedia, cosa rappresenta la bufera infernale?`
- Risposta generata:
<span style="color: grey; font-style: italic;">
    "La bufera infernale simboleggia la passione amorosa incontrollata dei lussuriosi, che in vita li trascinò senza misura e che ora li tormenta eternamente nel contrappasso."
</span>

{{< image src="./student/bufera-infernale-chatgpt.png" max-h="50vh" alt="Risposta di chat gpt sulla bufera infernale" >}}

---

## GenAI in ambito accademico: __Studenti__

### Caso 3: _Arricchimento materiale prodotto_

<!-- - AI può aiutare a _migliorare_ qualitativamente del materiale prodotto dagli studenti: -->
+ __Correzione__ grammaticale e stilistica di testi
+ __Parafrasi__ o __riformulazione__ di contenuti per maggiore chiarezza
+ __Suggerimenti__ per migliorare la struttura o l'organizzazione del materiale
+ Strutturazione/analisi di __codice__ per progetti di _programmazione_
+ Generazione di __grafici__ o diagrammi per visualizzare dati o concetti

---

## GenAI in ambito accademico: __Studenti__

### Caso 3: _Arricchimento materiale prodotto_

- `Cerca errori o incongruenze nel testo allegato`
    + \[allegando la documento]

- `Trascrivi questa traccia audio`
    + \[allegando la traccia audio]

- `Traduci questo testo in X`
    + \[allegando il testo e specificando la lingua X].
    + opzionalmente è possibile anche chiedere una traduzione con un certo stile (formale, informale, tecnico, etc...).

- `Fai il riassunto di questo video`
  + \[allegando il video]

---

## GenAI in ambito accademico: __Studenti__

### Caso 3: _Arricchimento materiale prodotto_

- `Traduci il testo del canto in inglese cercando di avere anche lì uno stile arcaico ed uno schema metrico`
<br/>

{{< image src="./student/divine-commedy-comment-traduction.png" max-h="50vh" alt="Traduzione commento sulla divina commedia" >}}

---

## GenAI in ambito accademico: __Studenti__

### Caso 3: _Arricchimento materiale prodotto_

- Nel caso della __sbobinatura__, è sempre importante _controllare l'esattezza del testo_ generato
    + spesso vengono commessi {{% color "red" %}}errori di trascrizione{{% /color %}}, specialmente con nomi propri o termini tecnici.
    + è sempre bene _rileggere_ e _correggere_ il testo sbobinato

- Nel caso della __traduzione__, è importante considerare il _contesto_ e il _pubblico_ a cui è destinato il testo tradotto
    + è consigliabile fornire __indicazioni__ chiare sullo _stile_ e sul _tono_ desiderati
    + è sempre bene _rileggere_ e _validare_ la traduzione generata

- Facile incorrere in problematiche relative a problemi di __plagio__ o __diritti d'autore__
    + la traduzione è 'inventata' da GenAI o è una traduzione esistente?
    + avevi il diritto di usare le registrazioni? e di condividerle col provider di GenAI?

---

## GenAI in ambito accademico: __Studenti__

### Caso 4: _Brainstorming_

- Strumenti AI possono essere affiancati agli studenti a __supporto__ del _processo creativo_:
    + __Idee__ per progetti o ricerche
    + __Refactoring__ di codice
    + Cercare __soluzioni__ alternative a problemi complessi
    + __Suggerimenti__ per migliorare l'_efficacia_ di presentazioni o discorsi

---

## GenAI in ambito accademico: __Studenti__

### Caso 4: _Brainstorming_

- `Quali sono i punti chiave di queste slide/appunti/capitolo?`
    + \[allegando il materiale]

- `Fornisci un elenco di problemi aperti su argomento X`
    + \[specificando l'argomento X]

- `Suggerisci idee per un progetto su X`
    + \[specificando l'argomento X, e la natura del progetto]
    <!-- + opzionalmente: `Concentrati su approcci innovativi o interdisciplinari` -->

- `Data questa tesi/articolo, suggerisci 5 idee per estenderla`
    + \[allegando la tesi/articolo]

---


## GenAI in ambito accademico: __Studenti__

### Caso 4: _Brainstorming_

- `Voglio fare una tesina dove metto in relazione l'inferno dantesco alla cultura musulmana, suggerisci idee`

<br/>

{{< image src="./student/divine-commedy-islam.png" max-h="50vh" alt="Suggerimenti per tesina su inferno dantesco e cultura musulmana" >}}

---

{{< slide id="technologies" >}}

# Esempi di __tecnologie__ GenAI per l'educazione

---

## Esempi di __tecnologie__ GenAI per l'educazione

- __Esistono__ vari _strumenti_ basati su GenAI che supportano i casi d'uso discussi
- Segue __panoramica__ delle soluzioni più _comuni_ e _interessanti_
- Alcuni di questi forniti con una modalità __gratuita__ mentre altri richiedono un __abbonamento__ o __pagamento__ per funzionalità avanzate
    + pagamento spesso _necessario_ per usabilità pratica

---

<!--
## Esempi di __tecnologie__ GenAI: _Chat Testuali_
- [ChatGPT](https://chat.openai.com/) - Piattaforma utilizzata per la generazione di contenuti in base alle richieste degli utenti.
  + Supporta conversazioni contestuali e risposte personalizzate.
  + Utilizzata per vari scopi in ambito educativo come spiegazioni, generazione di appunti, risoluzione di esercizi, etc.
- [Claude](https://www.anthropic.com/index/claude-2) - Elabora grandi quantità di informazioni.
  + Elabora una grande quantità di informazioni e contenuti.
  + In grado di generare idee, produrre testi e codice.
- [Microsoft Copilot](https://bard.google.com/) - Strumento LLM di Microsoft
  + Integrato in vari prodotti Microsoft come Word, Excel, PowerPoint, etc.
  + Aiuta a generare contenuti, analizzare dati e automatizzare compiti ripetitivi.
  + Per l'educazione è usato per snellire la pianificazione delle lezioni, le valutazioni del lavoro e la creazione di materiali didattici.
- [Gemini](https://gemini.google.com/?hl=it) - Modello di linguaggio Google:
  + Eccelle in compiti che richiedono analisi dei dati in tempo reale e elaborazione multimodale.
  + Come per le altre alternative, è usato per generare contenuti, rispondere a domande e assistere in vari task.

---

## Esempi di __tecnologie__ GenAI: _Assistenti per la scrittura_
- [Grammarly](https://www.grammarly.com/) - Assistente di scrittura AI:
  + Aiuta a migliorare la grammatica, lo stile e la chiarezza dei testi.
  + Utile per studenti e docenti per la revisione di saggi, email e altri documenti.
- [QuillBot](https://quillbot.com/) - Strumento di parafrasi:
  + Permette di riformulare testi mantenendo il significato originale.
  + Utile per evitare il plagio e migliorare la qualità della scrittura.
- [DeepL](https://www.deepl.com/) - Traduttore e assistente di scrittura:
  + Offre traduzioni di alta qualità e suggerimenti per migliorare la scrittura.
  + Utile per studenti e docenti che lavorano con testi in diverse lingue.

---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

- [TeachMeAI](https://teachmeai.com/) - Piattaforma educativa AI:
  + Offre strumenti per creare lezioni interattive e personalizzate.
  + Dispone di una vasta libreria di strumenti per:
    * Creare risorse didattiche
    * Supporti educativi speciali (BES)
    * Compiti amministrativi
- [Eduaide AI](https://www.eduaide.ai/) - Fornisce una serie di strumenti basati su AI per docenti e studenti
  + Semplifica la pianificazione delle lezioni.
  + Valuta grado padronanza degli studenti.
  + Crea materiali didattici personalizzati.

- [Diffit](https://web.diffit.me/) - Piattaforma per creare risorse educative fatte su misura
  + In base alle esigenze specifiche degli studenti.
  + Crea riassunti, quiz, etc.

- [SchoolAI](https://schoolai.com/) - Presenta diversi strumenti AI per insegnanti e studenti.
    + Possibile creare tutor AI personalizzati basati su materiali di corso specifici.
    + Presente uno strumento chiamato "Dot" per guidare gli studenti attraverso il processo di apprendimento.
       * In base al loro stile di apprendimento e alle loro esigenze.
    + Strumenti appositi per monitorare i progressi degli studenti e adattare le lezioni di conseguenza.

---

## Esempi di __tecnologie__ GenAI: _Valutazione e Feedback_

- [Turnitin](https://www.turnitin.com/) - Strumento di rilevamento del plagio:
  + Utilizzato per verificare l'originalità dei lavori degli studenti.
  + Aiuta a mantenere l'integrità accademica.

- [EssayGrader](https://essaygrader.ai/) - Strumento di valutazione automatica:
  + Fornisce feedback immediato sui saggi degli studenti.
  + Valuta aspetti come grammatica, coerenza e struttura.
  + Ha integrazione con piattaforme LMS come Canvas e Google Classroom.

- [Kahoot](https://kahoot.com/) - Piattaforma di apprendimento basata su giochi:
  + Permette di creare quiz interattivi e giochi educativi.
  + Utilizza AI per analizzare le risposte degli studenti e fornire feedback in tempo reale.

---
-->

## Esempi di __tecnologie__ GenAI: _Chat Testuali_

{{% multicol %}}

{{% col %}}
{{< image src="./interface-conversational.png"  alt="ChatGPT Schermata d'Esempio" >}}
{{% /col %}}

{{% col %}}
- [ChatGPT](https://chat.openai.com/)
    + _Stato dell'arte_ per modelli e interfaccia conversazionale
    + supporto ai __progetti__: gruppi di chat con _istruzioni/file condivisi_
    + supporto ai __GPT__{{% color "red" %}}\*{{% /color %}}: _chat-bot personalizzati_ (da terze parti) con funzionalità/_informazioni_ specifiche
    + modalità __studia e impara__ (per discenti){{% color "red" %}}\*{{% /color %}}: esercizi, quiz, spiegazioni, etc...

- Nella versione a __pagamento__
    + _meno limiti_ di utilizzo{{% color "red" %}}\*{{% /color %}}, _più scelta_ di modelli aggiornati
        * es. numero di messaggi, _upload di file_, etc.
    + modalità __agente__: possibilità per ChatBot di _interfacciarsi_ ad altre applicazioni e servizi

{{% /col %}}

{{% /multicol %}}

{{% color "red" %}}\*{{% /color %}} funzionalità impattanti per l'educazione

---

## Esempi di __tecnologie__ GenAI: _Chat Testuali_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/claude-main-screen.png"  alt="Claude Schermata Principale" width="50vw" >}}
{{% /col %}}

{{% col %}}
- [Claude](https://claude.ai/)
    + importante competitor di ChatGPT
    + supporto ai __progetti__: gruppi di chat con _istruzioni/file condivisi_
    + supporto gli __artefatti__: _chat-bot personalizzati_ (da terze parti) con funzionalità/_informazioni_ specifiche
- Nella versione a __pagamento__
    + _meno limiti_ di utilizzo, _più scelta_ di modelli aggiornati
        * es. numero di messaggi, _upload di file_, etc.
    + possibilità di definire __connettori__: possibilità per ChatBot di _interfacciarsi_ ad altre applicazioni e servizi
{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Chat Testuali_

{{% multicol %}}

{{% col %}}
{{< image src="./interface-powerpoint.png" alt="Copilot Schermata Principale" width="50vw" >}}
{{% /col %}}

{{% col %}}
- [Microsoft Copilot](https://copilot.microsoft.com/)
    + interfaccia _conversazionale_ + _in-app_ integrata in prodotti _Office 365_ (Word, Excel, PowerPoint, etc.)
    + aiuta a generare contenuti _dentro l'app_, o automatizzare compiti ripetitivi
    + utile per la __generazione__ di _slide_ (PowerPoint), _documenti_ (Word) e analisi dati (Excel)
{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Assistenti per la scrittura_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/grammarly-main-screen.png" alt="Grammarly Schermata Principale" width="50vw" >}}
{{% /col %}}

{{% col %}}
- [Grammarly](https://www.grammarly.com/) - Assistente di scrittura AI:
  + aiuta a migliorare la _grammatica_, lo stile e la _chiarezza_ dei testi.
  + utile soprattutto per la _scrittura in lingua_

- Integrazione con __browser__ o _editor di testo_

- Controlli _più fini_ sono possibili solo con la versione __premium__

- Competitor _gratuito_: [LanguageTool](https://languagetool.org/it)
{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Assistenti per la scrittura_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/quillbot-main-screen.png" alt="QuillBot Schermata Principale" width="60vw" >}}
{{% /col %}}

{{% col %}}
- [QuillBot](https://quillbot.com/)
   + correzione grammaticale
   + detettore di _plagio_ o _generazione_{{% color "red" %}}\*{{% /color %}}
   + traduzione
   + gestore di voci bibliografiche
   + sintetizzatore di testi

- Interfaccia _1-size-fits-all_ per comuni operazioni di scrittura

{{% color "red" %}}\*{{% /color %}} dubbi su accuratezza
{{% /col %}}

{{% /multicol %}}

<!-- ---

## Esempi di __tecnologie__ GenAI: _Assistenti per la scrittura_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/deepl-main-screen.png" alt="DeepL Schermata Principale" >}}
{{% /col %}}

{{% col %}}
- [DeepL](https://www.deepl.com/) - Traduttore e assistente di scrittura:
  + Offre traduzioni di alta qualità e suggerimenti per migliorare la scrittura.
  + Utile per studenti e docenti che lavorano con testi in diverse lingue.

- Utilizzabile come applicazione web o desktop.
{{% /col %}}

{{% /multicol %}} -->

<!-- ---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

{{% multicol %}}

{{% col %}}
> Imppossibile navigare al sito
{{% /col %}}

{{% col %}}
- [TeachMeAI](https://teachmeai.com/) - Piattaforma educativa AI:
  + Offre strumenti per creare lezioni interattive e personalizzate.
  + Dispone di una vasta libreria di strumenti per:
    * Creare risorse didattiche
    * Supporti educativi speciali (BES)
    * Compiti amministrativi
{{% /col %}}

{{% /multicol %}} -->

---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/eduaide-main-screen.png" alt="Eduaide.Ai Schermata Principale" width="45vw" >}}
{{% /col %}}

{{% col %}}
- [Eduaide AI](https://www.eduaide.ai/)
    + costruzione _semi-automatica_ di __strumenti didattici interattivi__
    + focus su ordini di _scuola primaria e secondaria_, solo in inglese

- Sistema _GenAI-based_ per la __didattica__:
    + _pianificazione_ e _impostazione_ delle lezioni
    + creazione _esercizi_ e _attività pratiche_, anche di _gruppo_
    + creazione _quiz_ e test di valutazione
    + _feedback_ personalizzato per studenti

- Soluzione _omni-comprensiva_ per docenti
    + versione _premium_ __senza limiti__ di utilizzo + __ChatBot d'aula__

- Molte funzionalità, _difficile valutare efficacia_
    + bisogna comunque fornire _materiale/indicazioni_ di partenza

{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/diffit-main-screen.png" width="50vw" alt="Diffit Schermata Principale" >}}
{{% /col %}}

{{% col %}}
- [Diffit](https://web.diffit.me/)
    + generazione di _materiali didattici_...
    + ... a partire da _libreria di risorse_ (__premium__)
{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/school-ai-chat.png" alt="SchoolAI Schermata Chat con Dot" width="45vw" >}}
{{% /col %}}

{{% col %}}
- [SchoolAI](https://schoolai.com/) - GenAI per insegnanti _e studenti_
    + __tutor AI__ personalizzati (sul corso) che:
        1. _guidano_ lo studente
        2. si _adattano_ al suo stile di apprendimento
    + strumenti per __monitorare i progressi__ degli studenti...
    + ... e _adattare le lezioni_ di conseguenza

- Supporta __"spazi di lavoro"__ personalizzati (per corso)
  + controllo dei _diritti/livelli d'accesso_ (docenti/studenti)
  + condivisione di _materiali_ e _risorse_ all'interno dello spazio

{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Piattaforme Educative_

### Note su [SchoolAI](https://schoolai.com/)


{{% color "red" %}}Non è chiaro...{{% /color %}}

1. cosa significhi _"guidare"_ lo studente
1. cosa significhi _"adattarsi"_ al suo stile di apprendimento
1. cosa significhi __"monitorare i progressi"__
1. quali _informazioni_ il chat-bot _catturi_ e usi per guidare/adattarsi
    + e quali informazioni la piattaforma _conservi_ sugli studenti
1. quanto bene funzionino i chat-bot in situazione di __cold-start__
    + nuova classe, nuovo studente, nuovo corso, etc...
1. come facciano i _tutor AI_ a mantenere l'engagement degli studenti
    + considerato che i chat-bot basati su LLM sono __reattivi__

---

## Esempi di __tecnologie__ GenAI: _Valutazione e Feedback_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/turnitin-home-page.png" width="50vw" alt="Turnitin Schermata Home" max-h="40vh" >}}
{{< image src="./reading/comparison/compilatio.png" width="50vw" alt="Compilatio Schermata Home" max-h="40vh" >}}
{{% /col %}}

{{% col %}}
- Strumenti di rilevamento del __plagio__:
    + [Turnitin](https://www.turnitin.com/)
    + [Compilatio](https://www.compilatio.net/it)

- Tanto più efficaci quanto più ampia la loro biblioteca di _testi di riferimento_
    + importante che questa possa essere _costantemente aggiornata_, _ampia_

- Possibile integrazione con _piattaforme LMS_ (Moodle, Canvas, etc...)
    + es. per controllare i _compiti/esami_ caricati dagli studenti

- I sistemi professionali sono __costosi__
    + meglio appoggiarsi a _licenza istituzionale_ se disponibile

- __Diffidare__ delle funzionalità di _GenAI-detection_

{{% /col %}}

{{% /multicol %}}

---

## Esempi di __tecnologie__ GenAI: _Valutazione e Feedback_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/easygrader-main-screen.png" alt="EasyGrader Schermata Home" width="50vw" >}}
{{% /col %}}

{{% col %}}
- [EssayGrader](https://essaygrader.ai/)
    + valutazione _automatica_ di __saggi__
    + previo _inserimento_ di __griglia di valutazione__ ("rubric") da parte del docente
    + valuta aspetti come grammatica, coerenza, struttura

- Funzionalità __premium__:
    + integrazione con piattaforme _LMS_ come Canvas e __Google Classroom__
    + ridotto limite di _saggi valutabili al mese_
    + analisi della performance a livello di _classe_ o _studente_
    + detection di _testo generato_

{{% /col %}}

{{% /multicol %}}

<!--

## Esempi di __tecnologie__ GenAI: _Valutazione e Feedback_

{{% multicol %}}

{{% col %}}
{{< image src="./tech-example/kahoot-quiz-creation.png" alt="Kahoot Schermata Creazione Quiz" width="50vw" >}}
{{% /col %}}

{{% col %}}
- [Kahoot](https://kahoot.com/)
  + Permette di creare _quiz interattivi_ e _giochi educativi_
  + Utilizza AI per analizzare le risposte degli studenti e fornire feedback in tempo reale.

- Usato in vari corsi per rendere l'apprendimento più coinvolgente e interattivo.
{{% /col %}}

{{% /multicol %}} -->

---

{{< slide id="challenges" >}}

# Sfide e __criticità__ dell'applicazione di GenAI all'educazione

---

## Sfide e __criticità__ dell'applicazione di GenAI all'educazione

<!-- - L'integrazione di AI generativa nell'educazione presenta enormi _opportunità_ sia per __studenti__ che __docenti__  -->
<!-- - Tuttavia è giusto considerare anche varie {{% color "red" %}}criticità{{% /color %}} che possono emergere nell'adozione delle varie soluzioni: -->
+ Possibili __impatti negativi__ sull'apprendimento
    - es. mancato sviluppo di _competenze_, eccessiva _dipendenza_ dagli strumenti
+ Questioni __etiche__, __legali__ e di __privacy__
    - es. è giusto usage GenAI per _correzioni_ e {{% color "red" %}}valutazioni{{% /color %}}?
    - es. problemi legati al _diritto d'autore_ nell'uso di _materiali protetti_ come _input_
    - es. _plagio_ accidentale o volontario
    - es. data _leak_ di informazioni sensibili
+ Facilità di __abuso__ degli strumenti AI da parte di _studenti_
    - es. _frode_ nello svolgimento di compiti, esami, etc.
<!-- - Vi è un dibattito in corso su come bilanciare i vari benefici offerti dall'AI con le potenziali sfide etiche, pedagogiche e pratiche. -->

<!-- Si vuole __evitare__ che l'AI diventi un __ostacolo__ piuttosto che un __supporto__ all'apprendimento. -->

---

## Potenziali abusi degli strumenti GenAI

<!-- - Vi sono preoccupazioni sempre più diffuse riguardo l'utilizzo di strumenti AI nel {{% color "red" %}}compromettere valutazioni date agli studenti e nell'integrità accademica{{% /color %}}. -->
Un __controllo diretto__ su come gli studenti utilizzano GenAI è spesso {{% color "red" %}}impraticabile{{% /color %}}
+ è __possibile__ che gli studenti abusino degli strumenti generativi
+ è __difficile__, per i docenti, _verificare_ le competenze _reali_ degli studenti

{{% fragment %}}

### Al tempo stesso

+ È impratico {{% color "red" %}}vietare completamente{{% /color %}} l'uso di GenAI
+ È importante __educare__ all'uso _corretto_ e _responsabile_ degli strumenti AI

{{% /fragment %}}

<!-- ---

## __Potenziali__ abusi degli strumenti GenAI

- Questo ha comportato la __nascita__ di discussioni sull'effettivo utilizzo di AI in ambito accademico.
- Alcuni sostengono l'uso dell' AI debba essere __rigorosamente limitato__ o __vietato__ in certi contesti educativi.
- Altri, invece, vedono nell'AI un'_opportunità_ per migliorare l'apprendimento e l'insegnamento, a patto che venga utilizzata in maniera __responsabile__. -->

---

## __Prevenire__ abusi degli strumenti GenAI (pt. 1)

<!-- - Una delle soluzioni proposte è l'adozione di __sistemi di rilevamento__ di contenuti generati da AI. Tuttavia, questi presentano varie limitazioni:
    + Non rilevano direttamente il "plagio" ma piuttosto identificano testi che "sembrano" generati da AI (_similarità_).
    + Sono {{% color "red" %}}limitati{{% /color %}} in ciò che possono rilevare (esempio il riscrivere un testo generato da AI con parole proprie).
    + Possono produrre {{% color "red" %}}falsi positivi{{% /color %}}, penalizzando ingiustamente studenti.
    + Possono essere {{% color "red" %}}aggirati{{% /color %}} con tecniche semplici. -->

### Strumenti di rilevamento automatico

- ... della _similarità_ tra elaborati (per evitare che gli studenti si copino a vicenda)
    + e.g., [Turnitin](https://www.turnitin.com/), <https://github.com/DanySK/code-plagiarism-detector>

- ... del _plagio_ (per evitare che gli studenti copino da fonti esterne)
    + e.g., [Compilatio](https://www.compilatio.net/it)

- ... di _errori_ di grammatica e stile (per evitare che gli studenti presentino elaborati con errori banali)
    + e.g., [Grammarly](https://www.grammarly.com/)

- ... di _contenuti generati da AI_ (per evitare che gli studenti usino AI per generare i loro elaborati)
    + e.g., [GPTZero](https://gptzero.me/), [OpenAI AI Text Classifier](https://platform.openai.com/ai-text-classifier)

### Note

- Hanno una funzione di __deterrenza__
- Hanno __margine d'errore__, tanto maggiore quanto più _complessa_ la rilevazione
    + es. rilevazione di testi generati da AI è {{% color "red" %}}molto imprecisa{{% /color %}}
    + $\rightarrow$ dicono dove guardare, __non certificano__ problemi

---

## __Prevenire__ abusi degli strumenti GenAI (pt. 2)

### Suggerimenti su strategie di verifica

- Evitare compiti che possano essere __svolti__ in toto __con GenAI__
    + es. risposte multiple, calcoli di cui si debba riportare solo il risultato, etc.

- Considerare __modalità di verifica__ in cui l'impiego di GenAI è {{% color "red" %}}poco pratico{{% /color %}}
    + es. esami _orali_, scritti su carta, etc.

- Tenere la verifica in __ambienti controllati__ dove l'accesso alla rete sia {{% color "red" %}}limitato{{% /color %}}
    + es. nei laboratori del DISI è prassi limitare i siti Web accessibili durante gli esami al solo [eol.unibo.it](https://eol.unibo.it)

- _Progettare_ compiti che richiedano __competenze specifiche__ difficilmente replicabili con GenAI...
    + es. analisi critica, riflessioni personali, applicazioni pratiche, etc.

- ... da verificare con __modalità orali__ o __pratiche__
    + es. discussioni, presentazioni, progetti, etc.

---

## Protezione dei dati e privacy

- Dati caricati su piattaforme AI possono essere utilizzati per __addestrare modelli futuri__
- Ciò può comportare {{% color "red" %}}rischi per la protezione dei dati{{% /color %}}, specialmente se i dati contengono informazioni __sensibili__ o __personali__
    + es. informazioni _anagrafiche_ sugli _studenti_ e le loro _prestazioni_ accademiche
<!-- - Le istituzioni educative hanno __responsabilità__ che gli strumenti AI _aderiscano_ a normative sulla privacy e protezione dei dati (es. _GDPR_, _FERPA_, _COPPA_).
- Le istituzioni devono decidere se __limitare__ gli strumenti popolari o __investire__ in soluzioni dedicate e conformi. -->

{{% fragment %}}

> Fare attenzione livello di protezione dei dati offerto dagli strumenti GenAI adottati
- in assenza di informazioni chiare, __meglio assumere il peggio__ e __limitare l'uso__ di tali strumenti
    + idem in caso di _non-configurabilità_ delle impostazioni di privacy

{{% /fragment %}}

---

## Problemi di Bias, Disinformazione e Accuratezza

<!-- - I modelli AI possono {{% color "red" %}} riflettere e amplificare errori{{% /color %}} presenti nei dati di addestramento.
- Ciò può portare a {{% color "red" %}}disinformazione{{% /color %}} o {{% color "red" %}} rappresentazioni distorte{{% /color %}} di argomenti.
- Gli studenti potrebbero {{% color "red" %}}accettare informazioni errate{{% /color %}} come verità, {{% color "red" %}}compromettendo{{% /color %}} la qualità dell'apprendimento.
- Risulta __fondamentale__ _accrescere una capacità di utilizzo responsabile e critica_ degli strumenti AI. -->

- GenAI può generare informazioni incomplete, imprecise, __sbagliate__, o incoerenti

- Occorre rivedere sempre il materiale generato, sia lato docenti che lato studenti

- Per mitigare l'<u>imprecisione</u>, è utile _fornire_ __contesto__ e __dettagli__ nei prompt, e allegare __fonti__ di riferimento
    + contesto $\approx$ chi sei, cosa stai facendo
    + dettagli $\approx$ cosa ti serve, come lo vuoi
    + fonti $\approx$ materiale di riferimento, esempi

- Per mitigare l'<u>incompletezza</u>, è utile:
    1. sfruttare la generazione _poco alla volta_, __gerarchicamente__, e ricorsivamente
        + es. prima i capitoli, poi le sezioni di ogni capitolo, poi i paragrafi di ogni sezione, etc.
    2. chiedere __esplicitamente__ di includere certi aspetti
        + es. fornendo una scaletta di cose da includere, esempi, etc.


<!-- ## Problemi di Bias, Disinformazione e Accuratezza


- Studenti e docenti devono essere _consapevoli_ dei limiti e potenziali errori degli strumenti AI.
- È importante _insegnare_ a _valutare criticamente_ le informazioni generate da AI e a verificare le fonti ed eventuali bias.
- Gli educatori devono __progettare__ compiti che richiedano un'_analisi critica_ degli output dell'IA, promuovendo competenze che vanno oltre la semplice ricerca di informazioni.
- IA da strumento che fornisce risposte a strumento che _supporta il pensiero critico_ e la _risoluzione di problemi_. -->

---

## Impatto sul Pensiero Critico e sull'Eccessiva Dipendenza

Ci sono __preoccupazioni__ riguardo all'effetto su larga scala di una _eccessiva dipendenza_ dagli strumenti di GenAI
+ {{% color "red" %}}riduzione{{% /color %}} della capacità di __ricerca indipendente__
+ {{% color "red" %}}diminuzione{{% /color %}} della capacità di __analisi critica__ delle informazioni
+ {{% color "red" %}}minore sviluppo{{% /color %}} di competenze di __risoluzione dei problemi__

---

## Impatto sul Pensiero Critico e sull'Eccessiva Dipendenza

### Consigli non richiesti (Opinionated)

- Tener presente il _bias cognitivo_ WYSIATI ("__What You See Is All There Is__", Kahneman 2011)
    + si tende a fidarsi di ciò che GenAI fornisce, pensando che sia _tutto ciò che c'è da sapere_
    + {{% color "red" %}}ma GenAI non è sempre <u>esaustiva</u>{{% /color %}}
        * meglio assumere che non lo sia __mai__ (aka: _GenAI <u>non</u> è un motore di ricerca_)

- Importante __educare__ certe competenze <u>anche</u> in assenza di GenAI (es. _ricerca_ di informazioni in testo/tomo/rete)
    + importante _allenare_ queste competenze nei _corsi di base_ (es. con compiti/esami che _impediscano_ l'uso di GenAI)
        * solo dopo, in _corsi avanzati_, istruire all'uso degli strumenti di GenAI per __aumentare__ tali competenze (es. con compiti/esami che _richiedano_ l'uso di GenAI)
    + {{% color "red" %}}perché GenAI <u>non</u> è sempre <u>accurata</u>{{% /color %}}
        * meglio potersi accorgere degli errori e poterne fare a meno quando sbaglia

- Affinchè GenAI abbia un _impatto positivo_ sull'apprendimento sarà importante un _grande sforzo_ (ri-)organizzativo
    + es. ripensare __metodi di insegnamento__, __tipi di compiti__ e __modalità di verifica__

<!-- - Abbiamo visto come __potenzialmente__ strumenti AI siano in grado:
  + Di fornire _facilmente_ accesso a risposte rapide.
  + Generare _immediatamente_ contenuti su richiesta.

- Tale facilità può portare a una {{% color "red" %}}dipendenza{{% /color %}} eccessiva dagli strumenti AI
- Diversi ostacoli all'apprendimento e allo sviluppo del pensiero critico:
  + {{% color "red" %}}Riduzione{{% /color %}} della capacità di ricerca indipendente.
  + {{% color "red" %}}Diminuzione{{% /color %}} della capacità di analisi critica delle informazioni.
  + {{% color "red" %}}Minore sviluppo{{% /color %}} di competenze di risoluzione dei problemi. -->

<!-- ---

## Impatto sul Pensiero Critico e sull'Eccessiva Dipendenza

- Ricerche evidenziano come però, l'uso di AI generativa:
  + Possano _incrementare la creatività_,
  + _Facilitare_ un apprendimento più profondo se usata per _aumentare la conoscenza e la costruzione di idee_.

- A livello educativo è necessario progettare attività che __incoraggino__ l'uso critico e riflessivo degli strumenti AI, __promuovendo__ un equilibrio tra l'uso di AI e lo sviluppo di competenze umane fondamentali. -->

---

## Sull'adozione di soluzioni GenAI in ambito educativo

In questo momento proliferano _strumenti roboanti_ la cui __efficacia__ ed __usabilità__ pratica sono tutte da dimostrare

- Non farsi abbindolare dal marketing:
    1. le soluzioni offrono __molte funzionalità__...
    2. la cui __efficacia__ è vincolata
        + alla _qualità_ del _materiale di partenza_ (fornito dall'utilizzatore)
        + alla _pazienza_ del docente di fornire _istruzioni chiare_ e dettagliate
        + alla _motivazione_ degli studenti a fruire attivamente degli strumenti

- Soluzioni _special-purpose_ (es. Eduaide AI) <u>non necessariamente offrono LLM migliori</u>, rispetto a soluzioni general-purpose (es. ChatGPT)
    + spesso il valore aggiunto sta _nell'interoperabilità_ con altri strumenti (es. LMS, gestione classe, etc.)
        * l'acquisto ha senso se c'è interoperabilità con _sistemi pre-esistenti_ (es. __Moodle__)
    + a volte il valore aggiunto sta _nella UI_ che guida maggiormente l'utente

- Rischio di __lock-in__ con soluzioni proprietarie
    + es. dipendenza da _licenze_, _formati chiusi_, _vendor-specific features_, etc.
        * una volta che si sceglie un provider non è facile cambiare
    + i vendor principali sono visibilmente in una fase di _accumulo di utenti_

---

{{< slide id="unibo-experiments" >}}

# Sperimentazioni in corso in UniBo

(__DISCLAIMER__: Seguono opinioni personali dello speaker)

---

## AI-Assisted Programming

Sperimentazione di *AI-assisted programming* nel primo anno del corso di _laurea triennale in Scienze Statistiche_
- __Obiettivo__: supportare l’insegnamento dell’informatica tramite strumenti di IA generativa
- Esperienza ispirata al quadro metodologico di _Porter e Zingaro (Manning Publications, 2024)_
- Focus su aspetti *cognitivi*, *metacognitivi* e *motivazionali* dell’__apprendimento della programmazione__
- Integrazione di IA per:
    - assistenza alla _scrittura del codice_
    - _analisi automatica_ delle soluzioni
    - _personalizzazione del feedback_ agli studenti
- Discussione di *vantaggi* e *criticità* emersi durante la sperimentazione

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
- Sarebbe forse critico se fosse un corso di base in un CdL di Informatica
{{% /fragment %}}

<!-- ---

## Personalizzazione e conoscenza del profilo d’aula con l’IA

- __Obiettivo__: _personalizzazione dei contenuti didattici_ e la _creazione di profili d’aula_ basati sui dati
- Applicazione di *tecniche di clusterizzazione* ai background e ai comportamenti degli studenti universitari per individuare pattern ricorrenti
    + _stili di apprendimento_
    + grado di _familiarità con le tecnologie_
    + progressione nei corsi
- Implicazioni operative per il *supporto alla progettazione didattica*
- Potenzialità dell’IA come strumento di supporto alla *governance* e al miglioramento continuo dell’offerta formativa

{{% fragment %}}
### Commenti
- __attenzione__: all'uso che si fa di dati sensibili 
{{% /fragment %}} -->

---

## Sperimentazioni di GenAI in Giurisprudenza (pt. 1)

Nel Dipartimento di Scienze Giuridiche (DSG) sono state integrate 4 modalità innovative di GenIA nella didattica:
- _Analisi critica_ in aula delle risposte di ChatGPT su _temi giuridici_, per promuovere un uso consapevole
- _Storytelling giuridico_: trasformazione di casi tecnici in racconti narrativi tramite GenIA, per facilitare la comprensione
- _Confronto tra pari_ sull’uso di GenIA nello studio del diritto
- _Simulazioni di role-play_ con GenIA nel corso di negoziazione internazionale, per esplorare dinamiche di trattativa e asimmetrie informative

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
{{% /fragment %}}

---

## Sperimentazioni di GenAI in Giurisprudenza (pt. 2)

CdLM in Informatica Giuridica, Sperimentazione su LLM in task giuridiche

* **Obiettivo**: sperimentare LLM locali in task giuridiche
* **Attività**:
  * Estrazione di definizioni normative e riferimenti giuridici
  * Identificazione di elementi qualificanti (es. titolare trattamento dati)
  * Generazione di definizioni giuridiche
* **Metodologia didattica**:
  * Introduzione teorica + esercitazioni in piccoli gruppi
  * Scelte tecniche su parametri (temperatura, top-k, top-p), system prompt, contesto.
* **Output atteso**: valutazione critica dei risultati, analisi dell’impatto delle scelte tecniche, riflessione etica.

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
- __Attenzione__ alla generazione di definizioni giuridiche
{{% /fragment %}}

---

## Sperimentazioni di GenAI in Giurisprudenza (pt. 3)

CdLM in Informatica Giuridica, Sperimentazione su KNIME e ipotesi giuridiche

* **Obiettivo**: laboratorio su KNIME, strumento di coding visuale per data processing finalizzato alla verifica di un’ipotesi giuridica
* **Attività**:
  * Presentazione e giustificazione del caso e dei dati
  * Pulizia, elaborazione e commento dei dataset
  * Esposizione metodologia + visualizzazione grafica
* **Aspetti critici**:
  * Questioni giuridiche (es. privacy)
  * Questioni etiche (es. bias di genere)
* **Output atteso**: valutazione dei risultati con strumenti di argomentazione e interpretazione giuridica.

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
{{% /fragment %}}

---

## Sperimentazioni di GenAI in Giurisprudenza (pt. 4)

Sperimentazione nel corso “Didattica del diritto” (CdL Giurisprudenza): progettare UDA con supporto generativo
- Utilizzo di GenAI per _progettare Unità di Apprendimento_ (UDA) rivolte a studenti delle scuole superiori
- _Attività di gruppo_: generazione idee, strutturazione attività inclusive per BES, esplorazione metodologie innovative (flipped classroom, simulazioni di processo), connessioni interdisciplinari
- _Obbligo di trasparenza_ sull’origine delle idee generate
- Presentazione finale dei progetti, _riflessione sui limiti_ e _valore_ dell’AI, _feedback_ della docente

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
{{% /fragment %}}

---

## Laboratorio su Bias e GenAI: sceneggiature inclusive

CdL in Scienze della Comunicazione e DAMS:
- Sperimentazione didattica: uso critico di GenAI (ChatGPT, Bard) per scrivere _sceneggiature originali_
- Focus su _progettazione di prompt_ e _riconoscimento/discussione di bias_ (genere, etnia, abilismo, rappresentazione sociale) nei testi generati
- Approccio interdisciplinare: integrazione tra pedagogia e informatica per _analisi critica delle sceneggiature_
- __Obiettivo__: promuovere media education, pensiero critico e data literacy, riflettendo sui rischi dei pregiudizi sistemici nei dati di addestramento

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy
{{% /fragment %}}

---

## Didattica delle lingue e GenAI

- __Attività 1__ — Scrittura in L2 con _feedback IA_ (inglese B2)
    - Blog di classe; uso strategico del feedback di ChatGPT
    - Focus progressivo: morfosintassi → lessico → stile

- __Attività 2__ — _Prompting_ per interazione orale (italiano L2)
    - Sviluppo dell’arte del prompting per “conversare con la macchina”
    - Obiettivo: pratica autonoma della produzione orale fuori aula

- __Attività 3__ — Progettazione UDA con GenAI (formazione docenti)
    - Uso di più strumenti GenAI per progettare unità didattiche
    - Valutazione: UDA = 40% del voto finale; restante via colloquio orale

{{% fragment %}}
### Commenti

- _Nessuna criticità_ dal punto di vista delle policy per attività 1 e 2
- __Attenzione__ all'attività 3: richiede analisi dell'efficacia di GenAI nella progettazione didattica
{{% /fragment %}}

---

![The end](./end.webp)

[torna a scaletta](#toc)
