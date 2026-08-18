# 📊 Corporate Financial Benchmark & Solvency Analysis: Leonardo S.p.A. vs Airbus SE (2021–2024)

**Author:** Marco Iaccarino  
**Domain:** Corporate Finance, Financial Statement Analysis & Credit Risk  
**Time Horizon:** Fiscal Years 2021–2024 (4-Year Consolidated Data)  
**Tech Stack:** Python (pandas, numpy, plotly, yfinance)  
**Methodology:** Standard Italian Economia Aziendale 2 Academic Accounting Framework  

---

## 📌 Executive Summary & Business Problem

Questo progetto analizza l'andamento economico-finanziario e la solvibilità quadriennale (FY 2021–2024) di **Leonardo S.p.A.** a confronto con il benchmark europeo **Airbus SE**, applicando il modello formale di **Economia Aziendale 2**:
* **Conto Economico a Valore Aggiunto** (con scomposizione in aree di gestione: VP, VA, MOL, ROGC, ROA, RC, RAI, RN).
* **Stato Patrimoniale Finanziario a 5 Aree** (criterio di liquidità ed esigibilità decrescente).
* **Set Essenziale di 12 Indici di Bilancio** (Redditività con DuPont Analysis, Solidità e Copertura, Liquidità e CCN).
* **Modello Altman Z-Score (Manufacturing)** per la stima del rischio di insolvenza e default.

### 🔍 Key Findings
* **Redditività Operativa:** Leonardo mostra un recupero costante: il ROS sale dal 6,44% (2021) al 7,47% (2024) e il ROE raggiunge il 10,59% nel 2024, agganciando la marginalità operativa di Airbus (ROS 7,44%).
* **Solidità e Deleveraging:** Leonardo dimezza il debito finanziario su mezzi propri (DF/MP da 0,76 a 0,43) e riduce l'incidenza PFN/EBITDA da 1,39 a 0,48 anni (debito netto a 900 M€). Airbus conferma una cassa netta positiva (PFN -3.200 M€).
* **Copertura degli Investimenti:** Entrambi i player mantengono la Copertura dell'Attivo Fisso di 2° Livello ampiamente > 1,0 (1,33 per Leonardo e 1,20 per Airbus nel 2024), garantendo equilibrio tra immobilizzazioni e fonti a M/L termine.
* **Altman Z-Score:** Leonardo compie una transizione virtuosa passando dalla Distress Zone iniziale (1,51) alla Grey Zone superiore (2,76 nel 2024), trainata dalla crescita dei margini e dalla rivalutazione della capitalizzazione di mercato.

---

## 📁 Repository Structure

corporate-financial-health-leonardo-analysis/
│
├── data/
│   ├── raw/                 # Dati IFRS grezzi di bilancio (2021-2024)
│   └── processed/           # Matrici riclassificate e tabelle indici
│
├── notebooks/
│   └── financial_analysis.ipynb   # Pipeline completa in Python (dati, calcoli e grafici)
│
├── screenshots/             # Output documentati del progetto
│   ├── 01_leonardo_ifrs_statements.png
│   ├── 01_bis_airbus_ifrs_statements.png
│   ├── 02_leonardo_reclassified_statements.png
│   ├── 02_bis_airbus_reclassified_statements.png
│   ├── 03_leonardo_financial_ratios.png
│   ├── 03_bis_airbus_financial_ratios.png
│   ├── 04_altman_z_score_analysis.png
│   └── 05_financial_benchmark_dashboard.png
│
├── README.md                # Reportistica del progetto
└── requirements.txt         # Dipendenze Python

---

## 🛠️ Accounting Framework, Formulas & Project Deliverables

### 1. Bilanci Consolidati Ufficiali IFRS (FY 2021–2024)
Verifica dell'identità contabile: Totale Attivo = Totale Passivo + Patrimonio Netto.

| Leonardo S.p.A. (IFRS Grezzo) | Airbus SE (IFRS Grezzo) |
| :---: | :---: |
| ![Leonardo IFRS](screenshots/01_leonardo_ifrs_statements.png) | ![Airbus IFRS](screenshots/01_bis_airbus_ifrs_statements.png) |

---

### 2. Riclassificazioni Accademiche (Economia Aziendale 2)

* **Conto Economico a Valore Aggiunto:**
  * VP (Valore Produzione) - CE (Costi Esterni) = VA (Valore Aggiunto)
  * VA - L (Costo Lavoro) = MOL (EBITDA)
  * MOL - AA (Ammortamenti/Accantonamenti) = ROGC (Redd. Op. Caratteristico)
  * ROGC + RGCA (Gestione Accessoria) = ROA (Redd. Op. Aziendale / EBIT)
  * ROA - OF (Oneri Finanziari) = RC (Reddito di Competenza)
  * RC +/- CS (Componenti Straordinari) = RAI (Reddito Ante Imposte)
  * RAI - I (Imposte) = RN (Reddito Netto)
* **Stato Patrimoniale Finanziario (5 Aree):**
  * Impieghi: Capitale Investito (CI) = Attivo a Breve (AB) + Attivo Fisso Netto (AFN)
  * Fonti: Fonti Finanziamento (FF) = Passivo Breve (PB) + Passivo M/L (PML) + Mezzi Propri (MP)
  * Mezzi di Terzi: MT = PB + PML

| Leonardo S.p.A. (CE & SP Riclassificati) | Airbus SE (CE & SP Riclassificati) |
| :---: | :---: |
| ![Leonardo Riclassificato](screenshots/02_leonardo_reclassified_statements.png) | ![Airbus Riclassificato](screenshots/02_bis_airbus_reclassified_statements.png) |

---

### 3. Sistema Essenziale di Indici di Bilancio

* **1. REDDITIVITÀ (PROFITABILITY)**
  * ROE (%) = (RN / MP) * 100
  * ROI (%) = (ROGC / CI) * 100
  * ROA (%) = (EBIT / CI) * 100
  * ROS (%) = (EBIT / Ricavi) * 100
  * Rotazione CI (Turnover) = Ricavi / CI
* **2. SOLIDITÀ PATRIMONIALE (SOLVENCY)**
  * Rapp. Indebitamento Complessivo = MT / MP
  * Rapp. Indebitamento Finanziario = Debiti Finanziari Totali / MP
  * Copertura Attivo Fisso 2° Livello = (MP + PML) / AFN  [Target > 1.0]
  * Incidenza PFN / EBITDA = Posizione Finanziaria Netta / EBITDA [Anni]
* **3. LIQUIDITÀ & CIRCOLANTE (LIQUIDITY)**
  * Indice Liquidità Primaria (Cash Ratio) = Cassa / PB
  * Indice di Tesoreria (Quick Ratio) = (Cassa + Crediti) / PB
  * Indice Liquidità Secondaria (Current Ratio) = AB / PB  [Target >= 1.0]
  * Capitale Circolante Netto (CCN) = AB - PB [€M]

| Leonardo S.p.A. (Indici) | Airbus SE (Indici) |
| :---: | :---: |
| ![Leonardo Indici](screenshots/03_leonardo_financial_ratios.png) | ![Airbus Indici](screenshots/03_bis_airbus_financial_ratios.png) |

---

### 4. Altman Z-Score Model & Dashboard Plotly

* **Formula Z-Score (Manufacturing):**  
  Z = 1.2*X1 + 1.4*X2 + 3.3*X3 + 0.6*X4 + 0.999*X5  
  * X1 = CCN / Totale Attivo
  * X2 = Retained Earnings / Totale Attivo
  * X3 = EBIT / Totale Attivo
  * X4 = Market Cap / MT
  * X5 = Ricavi / Totale Attivo
* **Soglie:** Z > 2.99 (Safe Zone 🟢), 1.81 <= Z <= 2.99 (Grey Zone 🟡), Z < 1.81 (Distress Zone 🔴).

| Altman Z-Score Analysis | Corporate Benchmark Dashboard (Plotly) |
| :---: | :---: |
| ![Altman Z-Score](screenshots/04_altman_z_score_analysis.png) | ![Dashboard Plotly](screenshots/05_financial_benchmark_dashboard.png) |

---

💻 Quickstart & Run Locally
```bash
git clone https://github.com/tuo-username/corporate-financial-health-leonardo-analysis.git
cd corporate-financial-health-leonardo-analysis
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/financial_analysis.ipynb
```

⚖️ Academic Case Study & Data Integrity Disclaimer
Finalità Didattica: Case study accademico indipendente sviluppato a scopi di portfolio e ricerca. Non costituisce consulenza finanziaria né credit rating formale.

Fonti: Dati ricavati da bilanci consolidati pubblici (IFRS). Per cifre certificate fare riferimento esclusivo alle Relazioni Finanziarie annuali ufficiali di Leonardo S.p.A. e Airbus SE.
