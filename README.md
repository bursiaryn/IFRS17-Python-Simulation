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

![Profit Comparison](output/ifrs17_visualizations/07_ifrs17_vs_ifrs4.png)

### 2. CSM Amortization Pattern
Visualisasi bagaimana marjin jasa kontraktual dilepaskan ke P&L seiring berjalannya layanan asuransi.

![CSM Amortization](output/ifrs17_visualizations/05_csm_amortization.png)

*(Catatan: Lihat folder `output/` untuk visualisasi lengkap termasuk Risk Adjustment dan GMM vs PAA)*

## 🛠️ Technical Methodology & Assumptions

Untuk menjaga transparansi (*intellectual honesty*), model ini menggunakan asumsi berikut:

* **Discount Rate:** [Jelaskan: Apakah menggunakan Flat yield curve (misal 3%) atau EIOPA/Risk-free rate curve?]
* **Risk Adjustment (RA):** [Jelaskan: Metode apa yang dipakai? Cost of Capital atau VaR confidence level tertentu?]
* **Mortality/Morbidity:** [Jelaskan: Menggunakan tabel standar apa atau asumsi simplifikasi?]
* **Aggregation Level:** Perhitungan dilakukan pada level [Individual Contract / Group of Contracts / Portfolio].

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
