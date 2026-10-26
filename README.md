<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="logo/cosmosprout-logo-white.svg">
  <img src="logo/cosmosprout-logo.svg" alt="CosmoSPROUT" width="440">
</picture>

### Il livello diagnostico che rende affidabili le serre chiuse e autonome, anche nello spazio

[![V.I.T.A.](https://img.shields.io/badge/V.I.T.A.-Open%20Innovation-3E8A47)](#-il-progetto)
[![Focus](https://img.shields.io/badge/focus-Anomaly%20Detection-C2307A)](#-come-funziona)
[![Digital Twin](https://img.shields.io/badge/Digital%20Twin-bilanci%20di%20massa%20ed%20energia-2F6390)](#-come-funziona)
[![Status](https://img.shields.io/badge/status-pilota%20in%20avvio-1B2A24)](#-il-progetto)
[![Made in](https://img.shields.io/badge/made%20in-Roma%20🇮🇹-008C45)](#-team)

**Capiamo quando fidarsi dei sensori e distinguiamo un guasto da un'anomalia della pianta.**

[Il progetto](#-il-progetto) · [Il problema](#-il-problema) · [Come funziona](#-come-funziona) · [Cosa otteniamo](#-cosa-otteniamo) · [Perché lo spazio](#-perché-lo-spazio) · [Team](#-team) · [Contatti](#-contatti)

</div>

---

## 🌱 Il progetto

Una serra chiusa e autonoma, sulla Terra come in una base lunare, funziona solo se può fidarsi dei propri dati. **CosmoSPROUT** costruisce il livello diagnostico che lo rende possibile, partendo da uno dei fitotroni dell'**Agri Research and Teaching Center** dell'Università Campus Bio-Medico di Roma, nell'ambito del programma **V.I.T.A. Open Innovation**.

---

## 🚨 Il problema

Lo stesso valore anomalo può avere cinque cause diverse. Sul segnale si somigliano tutte, ma ognuna richiede un intervento diverso:

| Causa | Cosa serve |
|---|---|
| 🔧 Guasto del sensore | Riparare o sostituire la sonda |
| 📉 Deriva di taratura | Ricalibrare |
| 🔄 Transitorio di processo | Niente: si riassorbe da solo |
| 🌿 Anomalia della pianta | Un intervento agronomico |
| ❓ Dato incoerente | Escluderlo dall'analisi |

Un allarme a soglia dice solo che un valore è fuori range, non perché. E le derive lente, che fuori range non ci vanno mai, non le vede affatto.

---

## 🧠 Come funziona

**Anomaly detection basata sui residui.** Un Digital Twin basato sui bilanci di massa ed energia calcola in continuo il valore atteso di ogni grandezza. Il sistema non analizza le serie grezze ma lo scarto fra misura e valore atteso: così intercetta anche le derive sotto soglia e si può addestrare con pochi mesi di storico.

```mermaid
flowchart LR
    S["📡 Sensori<br/>misura"] --> R
    DT["🧮 Digital Twin<br/>valore atteso ± incertezza"] --> R
    R["➖ Residuo<br/>misura − atteso"] --> D["🔍 Rilevazione"]
    D --> I["🧭 Isolamento<br/>causa + probabilità"]
    CAM["📷 Telecamere<br/>stato della coltura"] --> I
    I --> P["⏳ Prognosi<br/>tempo per intervenire"]
    P --> C["🖥️ Cockpit<br/>allarme, causa, azione"]
    I -. "evidenza insufficiente" .-> O["🧑‍🔬 Operatore"]

    style S fill:#eef5ee,stroke:#3E8A47
    style DT fill:#e8f0f7,stroke:#2F6390
    style R fill:#fbe9f1,stroke:#C2307A
    style D fill:#fbe9f1,stroke:#C2307A
    style I fill:#fbe9f1,stroke:#C2307A
    style P fill:#fbe9f1,stroke:#C2307A
    style CAM fill:#eef5ee,stroke:#3E8A47
    style C fill:#e8f0f7,stroke:#2F6390
    style O fill:#f4f4f4,stroke:#1B2A24
```

---

## 🎯 Cosa otteniamo

- 🔍 **Rilevazione**: le anomalie emergono prima che il valore esca dalla soglia.
- 🧭 **Isolamento**: per ogni anomalia, la causa probabile con una probabilità calibrata. Se l'evidenza non basta, decide l'operatore.
- 📷 **Canale visuale**: le telecamere sulla coltura separano il guasto del sensore dal problema della pianta.
- ⏳ **Prognosi**: quanto tempo resta prima che serva intervenire.
- 🧪 **Guasti indotti**: per insegnare al sistema a riconoscerli, li provochiamo in modo controllato e reversibile.

---

## 🚀 Perché lo spazio

Verso Marte un messaggio impiega fino a 22 minuti ad arrivare e, durante la congiunzione solare, le comunicazioni si interrompono per settimane. Una serra a ciclo chiuso, invece, va gestita in ore. Deve quindi saper diagnosticare da sola.

Il risultato: un impianto conducibile da remoto per un intero ciclo colturale e un analogo terrestre delle serre per missioni spaziali di lunga durata.

---

## 👥 Team

| | Nome | Ruolo |
|---|---|---|
| 🛠️ | Giorgia Mannarino | Engineer |
| 🛠️ | Giorgia Pontetti | Engineer |
| 🤖 | Simone Saverio Fildi | AI Specialist |

📍 Roma, dal 2026

---

## 📬 Contatti

[![LinkedIn](https://img.shields.io/badge/LinkedIn-seguici-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/company/coseritylab/)

<div align="center">

**CosmoSPROUT**: *dal fitotrone alla base lunare, dati di cui potersi fidare.*

</div>
