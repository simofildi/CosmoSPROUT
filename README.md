<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
  <img src="assets/hero-light.svg" width="100%" alt="CosmoSPROUT, il livello diagnostico che rende affidabili le serre chiuse e autonome, anche nello spazio. Nel grafico la misura di una sonda si allontana lentamente dal valore atteso e il sistema la segnala prima che scatti la soglia di allarme.">
</picture>

Una sonda del pH segna un valore più alto del solito. Può darsi che il pH sia salito davvero, oppure che la sonda si sia sporcata e stia derivando. Nel primo caso va corretta la soluzione, nel secondo va ricalibrata la sonda. E se il problema è la sonda, correggere la soluzione sposta il pH vero nella direzione sbagliata.

Con CosmoSPROUT vogliamo che una serra chiusa e autonoma capisca da sola quale dei due casi ha davanti. Partiamo da uno dei fitotroni dell'Università Campus Bio-Medico di Roma, nel programma V.I.T.A. Open Innovation.

## Ha ragione il sensore?

I casi possibili in realtà sono cinque: un guasto del sensore, una deriva di taratura, un transitorio dopo un cambio di set point, un problema vero della pianta, un dato incoerente. Sul grafico si assomigliano. Gli allarmi a soglia dicono solo che un valore è uscito dal range, e una sonda che deriva piano può non farli scattare mai.

## Misura meno atteso

Costruiamo un Digital Twin del fitotrone basato sui bilanci di massa ed energia, che stima in ogni momento quanto dovrebbe valere ciascuna grandezza. Il sistema guarda la differenza fra misura e valore atteso. Luce, stagione e cambi di set point li ha già spiegati il modello, quindi in quella differenza resta soprattutto il guasto. Bastano pochi mesi di storico per addestrare il sistema, e le derive si vedono quando sono ancora sotto soglia.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/diagnosi-dark.svg">
  <img src="assets/diagnosi-light.svg" width="100%" alt="Schema della diagnosi: la misura dei sensori meno il valore atteso dal Digital Twin dà il residuo. Il residuo passa per rilevazione, isolamento (aiutato dalle telecamere sulla coltura) e prognosi, fino al cockpit. Se l'evidenza non basta, l'isolamento passa il caso all'operatore.">
</picture>

Sui residui il sistema rileva l'anomalia, propone una causa con la sua probabilità e stima quanto tempo resta per intervenire. Se l'evidenza è troppo debole si astiene e chiama l'operatore. Le telecamere sulla coltura danno un indizio che non dipende dalle sonde: se le sonde segnalano un problema e la pianta sta bene, il sospetto cade sul sensore.

## Un esempio: la pompa

La pompa di ricircolo si occlude in parte. Cala la portata, poi l'ossigeno disciolto; più tardi sale l'ammoniaca e si sposta il pH. Sono quattro segnali su tre sottosistemi, e si muovono in momenti diversi. Chi li guarda uno per uno vede un problema chimico e lo corregge con la chimica, coprendo la causa senza risolverla. Letti insieme, il primo scostamento che il modello non sa spiegare è quello della portata, quindi il problema è idraulico.

All'operatore vorremmo far arrivare un messaggio come questo (l'esempio è inventato):

```text
Fitotrone 03, ore 14:20
Anomalia       portata di ricircolo sotto l'atteso
Causa          occlusione parziale della pompa (probabilità 0,78)
Da aspettarsi  ossigeno in calo, poi ammoniaca e pH
Intervenire    entro 6-10 ore
```

## Guasti fatti apposta

L'impianto è attivo da pochi mesi e probabilmente nel suo storico non ci sono ancora guasti. Così li provochiamo noi, in modo controllato e reversibile: un canale scollegato, un offset su una sonda, una portata ridotta, un dosaggio sbagliato, una perdita controllata di CO₂. Ogni prova verifica come reagisce il sistema e, insieme, gli dà gli esempi che altrimenti richiederebbero anni di osservazione.

## Fino a Marte

Nella serra antartica EDEN ISS, nell'inverno 2019, l'equipaggio dedicava alla serra circa 2,6 ore al giorno. Su Marte l'aiuto da Terra arriva tardi: un messaggio impiega fino a 22 minuti e durante la congiunzione solare le comunicazioni si fermano per settimane, mentre un guasto in una serra fuori suolo va gestito in qualche ora. La diagnosi, quindi, deve farla la serra.

Sulla Terra il vantaggio è più semplice. Il fitotrone si conduce da remoto per un intero ciclo colturale, e notti, weekend e chiusure smettono di essere ore senza sorveglianza.

## Chi siamo

Giorgia Mannarino e Giorgia Pontetti (Engineer), Simone Saverio Fildi (AI Specialist). Siamo a Roma, il team è nato nel 2026.

<a href="https://www.linkedin.com/company/coseritylab/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/linkedin-dark.svg">
    <img src="assets/linkedin-light.svg" height="48" alt="Seguici su LinkedIn">
  </picture>
</a>
