# 🐮🐷 Moo-Oink: Smart Farm Automation System
### Sistema Integrato di Smistamento Intelligente e Controllo Microclimatico Adattivo

**Moo-Oink** è un progetto sviluppato in **MATLAB/Simulink** che simula un varco di smistamento intelligente per allevamenti 4.0. Il sistema unisce un'automa a stati finiti (FSM) per la gestione logica degli animali e un controllo in retroazione per la gestione del microclima nelle aree di isolamento.

---

## 🚀 Funzionalità Principali

Il progetto si divide in due macro-blocchi logici:

### 1. Smistamento Intelligente (FSM)
Implementato tramite **Stateflow**, gestisce il flusso degli animali attraverso:
- **Riconoscimento:** Identificazione tramite tag RFID (Bovini) o peso (Suini).
- **Decisione:** Smistamento automatico basato su categorie specifiche (es. mucche post-parto, suini sottopeso).
- **Attuazione:** Controllo dei cancelli (Principale vs Deviazione).

### 2. Controllo Microclimatico (Closed-Loop)
Un sottosistema abilitato (**Enabled Subsystem**) che si attiva solo quando un animale è isolato:
- **Regolazione Termica:** Mantiene la temperatura ideale specifica per la specie e la condizione dell'animale.
- **Logica Riscaldamento/Raffreddamento:** Attivazione automatica in base al setpoint (es. 29-32°C per bovini sensibili).
- **Fisica del sistema:** Simulazione dell'inerzia termica tramite integratore.

---

## 🧠 Logica di Controllo

### Categorie di Smistamento (Isolamento)
L'animale viene deviato nell'area di controllo se:
* **Bovini:** Alta produzione, Post-parto, Gravidanza, Vitelli giovani.
* **Suini:** Peso fuori range standard (< 35kg oppure > 80kg).

### Setpoint Temperature
* **Bovini (Caldo):** Target 29°C - 32°C.
* **Bovini (Freddo):** Target -5°C (Refrigerazione controllata).
* **Suini (Caldo):** Target 18°C - 25°C (per animali leggeri).
* **Suini (Freddo):** Target 10°C - 14°C (per animali pesanti).

---

## 🛠️ Requisiti Software

* MATLAB (R2020b o superiore consigliato)
* Simulink
* Stateflow Toolbox

---

## ▶️ Come usare il progetto

1.  Clona la repository:
    ```bash
    git clone [https://github.com/TUO-USERNAME/Moo-Oink.git](https://github.com/TUO-USERNAME/Moo-Oink.git)
    ```
2.  Apri il file `.slx` in MATLAB/Simulink.
3.  Apri il blocco **Signal Editor** per visualizzare o modificare gli scenari di test (es. arrivo animali).
4.  Avvia la simulazione (**Run**).
5.  Osserva i risultati sugli **Scope**:
    * *Cancelli:* Apertura/Chiusura logica.
    * *Temperatura:* Andamento dinamico del microclima.

---

**Autore:** Lucia Brando
