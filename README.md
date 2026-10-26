<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
  <img src="assets/hero-light.svg" width="100%" alt="CosmoSPROUT, il livello diagnostico che rende affidabili le serre chiuse e autonome, anche nello spazio. Nel grafico la misura di una sonda si allontana lentamente dal valore atteso e il sistema la segnala prima che scatti la soglia di allarme.">
</picture>

Siamo CosmoSPROUT, un team di Roma. Lavoriamo su uno dei fitotroni dell'Agri Research and Teaching Center dell'Università Campus Bio-Medico, nel programma V.I.T.A. Open Innovation, e vogliamo che l'impianto capisca da solo quando può fidarsi dei propri sensori.

## Da dove partiamo

In un fitotrone una lettura strana può voler dire cose molto diverse. Il sensore può essersi rotto, oppure una sonda sta derivando piano piano. Può trattarsi di un transitorio dopo un cambio di set point, di un problema vero della pianta o di un dato incoerente. Sul grafico questi casi si assomigliano, ma per ognuno serve altro: cambiare la sonda, ricalibrarla, aspettare, intervenire sulla coltura, scartare il dato.

Gli allarmi a soglia segnalano solo che un valore è uscito dal range. Una sonda che deriva lentamente può non farli scattare mai.

## Come lo facciamo

Costruiamo un Digital Twin del fitotrone, basato sui bilanci di massa ed energia, che stima in ogni momento quanto dovrebbe valere ciascuna grandezza. Poi guardiamo la differenza fra quello che il sensore misura e quello che il modello si aspetta. Il ciclo della luce, la stagione e i cambi di set point li spiega già il modello, quindi nel residuo resta soprattutto il segnale del guasto. Per questo bastano pochi mesi di storico per addestrare il sistema, e le derive lente si vedono anche quando sono ancora dentro le soglie.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/diagnosi-dark.svg">
  <img src="assets/diagnosi-light.svg" width="100%" alt="Schema della diagnosi: la misura dei sensori meno il valore atteso dal Digital Twin dà il residuo. Il residuo passa per rilevazione, isolamento (aiutato dalle telecamere sulla coltura) e prognosi, fino al cockpit. Se l'evidenza non basta, l'isolamento passa il caso all'operatore.">
</picture>

Sui residui il sistema rileva l'anomalia con test statistici sequenziali e cerca di capirne la causa, indicando quanto è probabile. Quando l'evidenza è troppo debole si astiene e chiama l'operatore. Stima anche quanto tempo resta prima di dover intervenire, sul processo o sulla taratura delle sonde. Le telecamere sulla coltura aggiungono un indizio: se le sonde segnalano un problema e la pianta sta bene, il sospetto cade sul sensore.

L'impianto è attivo da pochi mesi e probabilmente nel suo storico non ci sono ancora guasti. Per insegnare al sistema a riconoscerli li provochiamo noi, in modo controllato e reversibile: un canale scollegato, un offset su una sonda, una portata ridotta, un dosaggio sbagliato, una perdita controllata di CO₂.

## Perché anche nello spazio

Le serre per le missioni di lunga durata saranno sistemi chiusi. Verso Marte un messaggio impiega fino a 22 minuti per arrivare e, durante la congiunzione solare, le comunicazioni si interrompono per settimane, mentre un guasto in una serra fuori suolo va gestito nel giro di qualche ora. La diagnosi quindi deve farla la serra. Un fitotrone condotto da remoto per un intero ciclo colturale è un buon banco di prova a terra.

## Chi siamo

- Giorgia Mannarino, Engineer
- Giorgia Pontetti, Engineer
- Simone Saverio Fildi, AI Specialist

Il team è nato nel 2026.

<a href="https://www.linkedin.com/company/coseritylab/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/linkedin-dark.svg">
    <img src="assets/linkedin-light.svg" height="48" alt="Seguici su LinkedIn">
  </picture>
</a>
