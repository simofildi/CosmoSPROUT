<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
  <img src="assets/hero-light.svg" width="100%" alt="CosmoSPROUT, il livello diagnostico che rende affidabili le serre chiuse e autonome, anche nello spazio. Il grafico mostra la misura di una sonda che deriva lentamente rispetto al valore atteso dal Digital Twin: il sistema la segnala prima che scatti la soglia di allarme.">
</picture>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/strip-dark.svg">
    <img src="assets/strip-light.svg" width="440" alt="Anomaly detection, Digital Twin, pilota in avvio, Roma">
  </picture>
</p>

<div align="center">

**Capiamo quando fidarsi dei sensori e distinguiamo un guasto da un'anomalia della pianta.**

[Il progetto](#il-progetto) · [Il problema](#il-problema) · [Come funziona](#come-funziona) · [Dalla correlazione alla causa](#dalla-correlazione-alla-causa) · [Cosa costruiamo](#cosa-costruiamo) · [Cosa otteniamo](#cosa-otteniamo) · [Perché lo spazio](#perché-lo-spazio) · [Team](#team) · [Contatti](#contatti)

</div>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Il progetto

Una serra chiusa e autonoma, sulla Terra come in una base lunare, funziona solo se può fidarsi dei propri dati. **CosmoSPROUT** costruisce il livello diagnostico che le dice quando fidarsi.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Il problema

Lo stesso valore anomalo può avere cinque cause. Sul segnale si somigliano, eppure ognuna chiede un intervento diverso:

| Causa | Cosa serve |
|---|---|
| Guasto del sensore | Riparare o sostituire la sonda |
| Deriva di taratura | Ricalibrare |
| Transitorio di processo | Niente: si riassorbe da solo |
| Anomalia della pianta | Un intervento agronomico |
| Dato incoerente | Escluderlo dall'analisi |

Un allarme a soglia segnala che un valore è fuori range senza indicarne la causa. Le derive lente, che restano sotto soglia, non le vede proprio.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Come funziona

Il progetto si regge sull'anomaly detection basata sui residui. Un Digital Twin costruito sui bilanci di massa ed energia calcola in continuo il valore atteso di ogni grandezza. Il sistema lavora sullo scarto fra misura e valore atteso, da cui il modello fisico ha già tolto le variazioni prevedibili come il ciclo di luce, la stagione e i cambi di set point. Quello che resta è il segnale del guasto: così il sistema intercetta anche le derive sotto soglia e si può addestrare con pochi mesi di storico.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/diagnosi-dark.svg">
  <img src="assets/diagnosi-light.svg" width="100%" alt="Schema della diagnosi: la misura dei sensori meno il valore atteso dal Digital Twin dà il residuo. Il residuo passa per rilevazione, isolamento (aiutato dalle telecamere sulla coltura) e prognosi, fino al cockpit. Se l'evidenza non basta, l'isolamento passa il caso all'operatore.">
</picture>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Dalla correlazione alla causa

Un singolo segnale raramente basta. Uno scostamento che nasce in un sottosistema si manifesta in un altro, con ritardi diversi. Un'occlusione parziale della pompa di ricircolo, per esempio, riduce la portata; poi cala l'ossigeno, sale l'ammoniaca e si sposta il pH. Letti uno per uno, i canali indicano un problema chimico, e una correzione chimica coprirebbe la causa senza risolverla. Letti insieme, il primo scostamento che il modello non sa spiegare è quello della portata, quindi la causa è idraulica.

Il sistema ragiona così su finestre di dati multivariate. Insieme all'allarme restituisce l'ipotesi di causa, la sua probabilità e il tempo utile per intervenire.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Cosa costruiamo

- **Cockpit**: una vista dell'impianto in tempo reale, con i valori collocati nel punto in cui vengono misurati, le tendenze, gli allarmi e le azioni consigliate. Si usa da postazione fissa, da remoto o da mobile.
- **Digital Twin**: un modello basato sui bilanci di massa ed energia, allineato di continuo ai dati di esercizio. Calcola i valori attesi e permette di simulare scenari what-if.
- **Diagnosi con AI**: rilevazione, isolamento e prognosi delle anomalie, con escalation all'operatore quando l'evidenza non basta.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Cosa otteniamo

- **Rilevazione**: il sistema segnala l'anomalia anche quando il valore resta dentro la soglia.
- **Isolamento**: per ogni anomalia propone una causa, con una probabilità calibrata. Se l'evidenza non basta, si astiene e passa il caso all'operatore.
- **Canale visuale**: le telecamere guardano la coltura. Se le sonde vedono uno scostamento e la pianta sta bene, il sospetto cade sul sensore.
- **Prognosi**: stima quanto tempo resta prima che una grandezza esca dai limiti e quando conviene ricalibrare ogni sonda.
- **Guasti indotti**: quando lo storico non contiene ancora guasti, li provochiamo noi, in modo controllato e reversibile, per insegnare al sistema a riconoscerli.
- **Sensori virtuali**: se una misura manca, il Digital Twin la ricostruisce dalle altre con un'incertezza dichiarata, e l'impianto continua a lavorare in modalità degradata entro margini noti.
- **Dati di cui fidarsi**: ogni intervallo dei dataset prodotti esce con un indice di attendibilità.
- **Nessuna finestra scoperta**: notti, fine settimana e chiusure smettono di essere ore senza sorveglianza.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Perché lo spazio

Nelle missioni di lunga durata, verso una base lunare o verso Marte, coltivare piante a bordo fa parte del sistema di supporto alla vita. Riduce i rifornimenti da imbarcare, aiuta a rigenerare l'aria e a riciclare l'acqua, e ha effetti documentati sul benessere dell'equipaggio. Queste serre non si possono collaudare in volo, quindi si provano a terra, in impianti isolati che ne riproducono i vincoli. Il riferimento europeo è EDEN ISS del DLR, in Antartide: nell'inverno 2019 l'equipaggio dedicava alla serra circa 2,6 ore al giorno, e una quota rilevante di quel tempo andava in set-up, manutenzione e correzione dei sistemi di controllo.

Oggi, quando qualcosa non va, la diagnosi si fa da Terra. In EDEN ISS il sistema di monitoraggio manda un avviso via satellite a un gruppo di agronomi a Brema, che discutono e comunicano la contromisura. Verso Marte questo schema si inceppa: un messaggio impiega fino a 22 minuti ad arrivare e, durante la congiunzione solare, le comunicazioni si interrompono per settimane. Un guasto in una serra fuori suolo e a ciclo chiuso va invece gestito in poche ore, quindi il ciclo "rileva, chiedi a Terra, aspetta, intervieni" non sempre si chiude in tempo.

Serve che sia la serra a fare la diagnosi. Nei sistemi spaziali questa capacità si chiama Fault Detection, Isolation and Recovery (FDIR): rilevare un guasto, localizzarlo e avviare il ripristino. Sulle piattaforme robotiche è prassi consolidata. Nelle serre è ancora poco applicata, perché una parte del sistema da diagnosticare è viva e i suoi tempi non sono quelli di un attuatore.

Sulla Terra la stessa capacità si misura con lo stesso metro, le ore di lavoro degli operatori. Un impianto che riconosce da solo le proprie anomalie si può condurre da remoto per un intero ciclo colturale, e diventa un banco di prova a terra per le serre delle missioni future.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Team

| Nome | Ruolo |
|---|---|
| Giorgia Mannarino | Engineer |
| Giorgia Pontetti | Engineer |
| Simone Saverio Fildi | AI Specialist |

Roma, dal 2026

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/divider-dark.svg">
    <img src="assets/divider-light.svg" width="420" alt="">
  </picture>
</p>

## Contatti

<a href="https://www.linkedin.com/company/coseritylab/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/linkedin-dark.svg">
    <img src="assets/linkedin-light.svg" height="48" alt="Seguici su LinkedIn">
  </picture>
</a>

<br><br>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/footer-dark.svg">
    <img src="assets/footer-light.svg" width="560" alt="CosmoSPROUT: dalla Terra alla base lunare, dati di cui potersi fidare.">
  </picture>
</p>
