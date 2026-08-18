# 📊 Corporate Financial Health & Bankruptcy Risk Analysis
### Case Study: Leonardo S.p.A. (LDO.MI) vs Airbus SE (AIR.PA)
**Author:** Marco Iaccarino  
**Domain:** Corporate Finance, Financial Accounting & Credit Risk  
**Time Horizon:** Fiscal Years 2021–2024 (4-Year Annual Data)  
**Tech Stack:** Python (`pandas`, `numpy`, `plotly`, `yfinance`)

---

## 📌 Executive Summary
Valutare lo stato di salute economico-finanziario e la solvibilità di un'impresa manifatturiera ad alta complessità è fondamentale per monitorare la gestione operativa, l'autonomia patrimoniale e la solidità del capitale. 
Questo progetto rappresenta un **Case Study didattico e analitico** che esamina l'andamento storico quadriennale (**2021–2024**) di **Leonardo S.p.A.** a confronto con il benchmark europeo **Airbus SE**, integrando:
1. **Riclassificazione di Bilancio** (Conto Economico a Valore Aggiunto e Stato Patrimoniale Finanziario).
2. **Sistema di Indici di Bilancio** (Redditività, Liquidità, Solidità Patrimoniale e Copertura).
3. **Credit Risk Scoring** (Modello Altman Z-Score per imprese manifatturiere).
4. **Metriche ESG di Base** (Intensità emissiva Scope 1-2 e impatto sui costi di finanziamento).

* **Key Finding:** L'analisi evidenzia una progressiva ripresa della redditività operativa (ROS ed EBITDA margin in crescita costante) e un graduale rafforzamento della solidità patrimoniale, con il rapporto di indebitamento e la PFN/EBITDA che migliorano verso livelli di equilibrio. L'Altman Z-Score mostra la tenuta della solvibilità a fronte di un ciclo produttivo capital-intensive caratterizzato da commesse pluriennali.

---

## 🎯 Business Problem
Un neolaureato o junior financial analyst deve supportare il management o un istituto di credito nella valutazione di un'azienda industriale. Le domande pratiche a cui il progetto risponde sono:
* **Marginalità:** Come sono evoluti i margini aziendali (Valore Aggiunto, EBITDA, EBIT) lungo il quadriennio 2021–2024 attraverso la riclassificazione del Conto Economico?
* **Solidità e Liquidità:** La struttura patrimoniale è equilibrata? Gli indici di liquidità (Current/Quick Ratio) e gli indici di solidità (Autonomia Finanziaria, Leverage) garantiscono sostenibilità nel medio-lungo termine?
* **Rischio di Default:** Qual è il posizionamento di solvibilità secondo l'Altman Z-Score (*Safe*, *Grey*, *Distress*)?
* **Sostenibilità:** Come si posiziona l'azienda rispetto ai target di riduzione delle emissioni (Carbon Intensity)?

---

## 📁 Repository Structure

    corporate-financial-health-leonardo-analysis/
    │
    ├── data/
    │   ├── raw/                 # Raw financial statements from yfinance (FY 2021-2024)
    │   └── processed/           # Reclassified balance sheets, income statements and KPIs
    │
    ├── notebooks/
    │   └── financial_analysis.ipynb   # Main end-to-end Python notebook
    │
    ├── README.md                # Project documentation and executive summary
    └── requirements.txt         # Python dependencies

---

## 🛠️ Methodology & Accounting Framework

### 1. Financial Statement Reclassification (FY 2021–2024)
* **Conto Economico a Valore Aggiunto:**
  $$\text{Ricavi delle Vendite} - \text{Costi Operativi Esterni} = \text{Valore Aggiunto}$$
  $$\text{Valore Aggiunto} - \text{Costo del Personale} = \text{EBITDA (MOL)}$$
  $$\text{EBITDA} - \text{Ammortamenti e Svalutazioni} = \text{EBIT (Reddito Operativo)}$$
  $$\text{EBIT} \pm \text{Proventi/Oneri Finanziari} = \text{EBT (Risultato Ante Imposte)}$$
  $$\text{EBT} - \text{Imposte} = \text{Utile Netto}$$

* **Stato Patrimoniale Finanziario (Criterio di Liquidità ed Esigibilità):**
  * **Attivo:** Attivo Circolante (Liquidità Immediate, Differite, Rimanenze) vs Attivo Fisso Netto (Immobilizzazioni).
  * **Passivo:** Passivo Corrente (a breve termine), Passivo Consolidato (a medio-lungo termine) e Patrimonio Netto.

### 2. Comprehensive Ratio Analysis & Risk Scoring
* **Redditività:**
  $$\text{ROE} = \frac{\text{Utile Netto}}{\text{Patrimonio Netto}}, \quad \text{ROI} = \frac{\text{EBIT}}{\text{Totale Attivo}}, \quad \text{ROS} = \frac{\text{EBIT}}{\text{Ricavi}}$$
  
* **Liquidità:**
  $$\text{Current Ratio} = \frac{\text{Attivo Circolante}}{\text{Passivo Corrente}}, \quad \text{Quick Ratio} = \frac{\text{Attivo Circolante} - \text{Rimanenze}}{\text{Passivo Corrente}}$$
  
* **Solidità Patrimoniale e Struttura:**
  $$\text{Rapporto di Indebitamento (Leverage)} = \frac{\text{Totale Debiti}}{\text{Patrimonio Netto}}$$
  $$\text{Grado di Autonomia Finanziaria} = \frac{\text{Patrimonio Netto}}{\text{Totale Attivo}}$$
  $$\text{Copertura delle Immobilizzazioni} = \frac{\text{Patrimonio Netto} + \text{Passività Consolidate}}{\text{Attivo Fisso Netto}}$$
  
* **Altman Z-Score (Manufacturing Model):**
  $$Z = 1.2 X_1 + 1.4 X_2 + 3.3 X_3 + 0.6 X_4 + 0.999 X_5$$
  * *Dove:* $X_1 = \frac{\text{CCN}}{\text{Totale Attivo}}$, $X_2 = \frac{\text{Utili Reinvestiti}}{\text{Totale Attivo}}$, $X_3 = \frac{\text{EBIT}}{\text{Totale Attivo}}$, $X_4 = \frac{\text{Valore di Mercato PN}}{\text{Totale Passivo}}$, $X_5 = \frac{\text{Ricavi}}{\text{Totale Attivo}}$.
  * *Soglie di Rischio:* $Z > 2.99$ (Safe Zone), $1.81 \le Z \le 2.99$ (Grey Zone), $Z < 1.81$ (Distress Zone).

---

## ⚖️ Academic Case Study & Data Integrity Disclaimer
* **Didactic Purpose:** This repository is an independent academic case study developed solely for educational, portfolio demonstration, and research purposes. It does not constitute financial advice, investment recommendation, or an official credit rating.
* **Data Sourcing & Limitations:** Financial data and historical records (FY 2021–2024) are retrieved via public APIs (`yfinance`). While data integrity checks and accounting reconciliations ($\text{Total Assets} = \text{Total Liabilities} + \text{Equity}$) have been implemented in the pipeline, users and reviewers must refer exclusively to the official audited Annual Reports (Relazioni Finanziarie di Bilancio) published by Leonardo S.p.A. and Airbus SE for official figures.
* **Intellectual Property:** All corporate names, trademarks, and financial disclosures remain the intellectual property of their respective owners.
