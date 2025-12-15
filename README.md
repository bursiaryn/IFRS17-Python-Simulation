# IFRS17-Python-Simulation
"End-to-end IFRS 17 simulation engine in Python. Implements GMM &amp; PAA approaches, CSM amortization logic, and comparative analysis against IFRS 4 standards.

# IFRS 17 (PSAK 74) Actuarial Simulation Engine

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Status](https://img.shields.io/badge/Status-Educational-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Executive Summary

Repository ini berisi *actuarial modeling framework* berbasis Python untuk mensimulasikan perhitungan **IFRS 17 (Insurance Contracts)** atau PSAK 74 di Indonesia.

Proyek ini dibangun untuk mendemonstrasikan transisi dari pendekatan berbasis aturan (IFRS 4) menuju pendekatan berbasis prinsip yang melihat neraca secara ekonomi (*market-consistent*). Model ini mencakup simulasi *end-to-end* mulai dari proyeksi arus kas hingga amortisasi *Contractual Service Margin* (CSM).

## 🚀 Key Features

Model ini menangani komponen kritis dalam pengukuran IFRS 17:

* **Measurement Models:** Implementasi **General Measurement Model (GMM)** dan perbandingan dengan **Premium Allocation Approach (PAA)**.
* **Fulfillment Cash Flows (FCF):** Estimasi arus kas masa depan yang disesuaikan dengan nilai waktu uang (*Time Value of Money*) dan risiko.
* **CSM Engine:** Mekanisme pengakuan, *unlocking*, dan amortisasi CSM berdasarkan *coverage units*.
* **Transition Analysis:** Visualisasi dampak finansial perpindahan dari IFRS 4 ke IFRS 17.
* **Automated Reporting:** Menghasilkan 18+ visualisasi otomatis terkait profitabilitas dan solvabilitas portofolio.

## 📊 Visual Analysis Samples

Berikut adalah hasil simulasi dari model ini:

### 1. IFRS 17 vs IFRS 4 Profit Emergence
Perbandingan pola pengakuan laba. IFRS 17 meratakan laba sepanjang masa kontrak melalui mekanisme CSM, berbeda dengan IFRS 4 yang cenderung *front-loaded*.

![Profit Comparison](output/07_ifrs17_vs_ifrs4.png)

### 2. CSM Amortization Pattern
Visualisasi bagaimana marjin jasa kontraktual dilepaskan ke P&L seiring berjalannya layanan asuransi.

![CSM Amortization](output/05_csm_amortization.png)

*(Catatan: Lihat folder `output/` untuk visualisasi lengkap termasuk Risk Adjustment dan GMM vs PAA)*

## 🛠️ Technical Methodology & Assumptions

This IFRS 17 engine is built on a bottom-up approach, calculating liabilities at the contract level before aggregation. The key actuarial assumptions used in the simulation are:

* **Discount Rates:**
    * **Long-duration (GMM):** 5.0% flat rate (proxy for long-term risk-free rate + illiquidity premium).
    * **Short-duration (PAA):** 3.0% flat rate.
* **Risk Adjustment (RA):**
    * **Methodology:** Cost of Capital (CoC) approach.
    * **CoC Rate:** 6% per annum applied to projected Solvency Capital Requirement (SCR).
    * **Risk Factors:** Product-specific risk weights ranging from 2.0% (Term Life) to 8.0% (Motor) of Sum Assured.
* **Mortality Model:**
    * Deterministic projection using **Makeham's Law** `μ_x = A + B * c^x`.
    * **Base assumption:** `c = 1.085` to model increasing mortality with age.
    * **Cap:** Maximum mortality rate capped at 0.95.
* **Lapse Rates:**
    * Explicit lapse rates modeled per product type:
        * Whole Life: 10%
        * Term Life: 12%
        * Endowment: 8%
        * General Insurance (Motor/Property): 20-25%
* **Expense Inflation:** 3.0% per annum applied to renewal expenses.
* **Measurement Models:**
    * **GMM (Building Block Approach):** Applied to Whole Life, Term Life, and Endowment products.
    * **PAA:** Applied to Motor and Property insurance (coverage period ≤ 1 year).

## 💻 How to Run

1.  Clone repository ini:
    ```bash
    git clone [https://github.com/username/IFRS17-Actuarial-Engine.git](https://github.com/username/IFRS17-Actuarial-Engine.git)
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  Jalankan Jupyter Notebook:
    ```bash
    jupyter notebook notebooks/ifrs17_simulation.ipynb
    ```

## ⚠️ Disclaimer

Proyek ini dibuat untuk tujuan **edukasi dan demonstrasi kapabilitas modeling**. Hasil perhitungan bergantung penuh pada asumsi yang diinput dan penyederhanaan model. Tidak ditujukan untuk penggunaan produksi dalam pelaporan keuangan riil tanpa validasi aktuaria lebih lanjut.

---
*Created by rayan - linkedin.com/in/rosyidroyyan*
