# Analisi delle Serie Temporali: Impatto della Qualità dell'Aria sulla Salute

Questo progetto applica tecniche di analisi statistica e modellizzazione predittiva per studiare la relazione temporale tra i livelli di inquinamento atmosferico e i ricoveri ospedalieri per patologie respiratorie.

## 🎯 Obiettivo
L'obiettivo principale è sviluppare un modello di previsione basato su serie temporali che integri variabili ambientali esogene per migliorare l'accuratezza delle stime dei ricoveri su base settimanale.

## 🛠️ Metodologia e Pipeline
Il lavoro segue un approccio rigoroso suddiviso in fasi logiche:

### 1. Pre-processing dei Dati
* **Data Cleaning:** Gestione dei formati temporali e ordinamento cronologico.
* **Resampling:** Aggregazione dei dati giornalieri in frequenza settimanale per ridurre il rumore e catturare trend di medio periodo.
* **Focus Geografico:** Analisi specifica su base regionale (Regione East).

### 2. Analisi Esplorativa (EDA)
* **Analisi di Correlazione Incrociata (CCF):** Identificazione dei ritardi temporali (*lag*) ottimali per comprendere dopo quante settimane l'inquinamento influisce sui ricoveri.
* **Decomposizione Stagionale:** Scomposizione della serie in Trend, Stagionalità e Residuo per isolare i pattern ricorrenti.


### 3. Diagnostica Statistica
* **Test di Stazionarietà:** Utilizzo del test di Augmented Dickey-Fuller (ADF) per determinare la necessità di differenziazione dei dati.
* **Analisi ACF/PACF:** Studio delle funzioni di autocorrelazione per la stima iniziale dei parametri dei modelli.

### 4. Modellizzazione Predittiva
* **SARIMA (Seasonal AutoRegressive Integrated Moving Average):** Implementazione di un modello univariato basato esclusivamente sullo storico dei ricoveri.
* **SARIMAX:** Estensione del modello con l'aggiunta di regressori esogeni (PM2.5 e Temperatura) per valutare l'impatto dei fattori esterni.
* **Auto-Optimization:** Selezione automatica degli iperparametri tramite criteri di informazione (AIC/BIC).

[Image of SARIMAX model architecture]

## 🚀 Requisiti
Per eseguire l'analisi sono necessarie le seguenti librerie Python:
* **pandas** >= 1.5.0 (per la gestione efficiente del `resample`)
* **statsmodels** >= 0.14.0 (fondamentale per i modelli `SARIMAX` e la funzione `ccf`)
* **pmdarima** >= 2.0.0 (per la funzione `auto_arima`)
* **matplotlib** >= 3.6.0
* **seaborn** >= 0.12.0
* **numpy** >= 1.23.0
## 📂 Struttura del Repository
- `serie_temporali_corrected.ipynb`: Notebook principale contenente l'intero flusso di lavoro, dalla pulizia dei dati alla validazione dei modelli.
- `air_quality_health_dataset.csv`: Fonte dati originale con parametri di qualità dell'aria e dati ospedalieri.
