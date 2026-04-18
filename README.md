# Enterprise AI Context Engine: Unifying Risk, Fraud, & Marketing Analytics

![Architecture](https://img.shields.io/badge/Architecture-MCP%20%7C%20LLM%20%7C%20MLOps-blue)
![Status](https://img.shields.io/badge/Status-Deployment%20Ready-success)

## Executive Summary
Repositori ini mendemonstrasikan prototipe **Enterprise AI Context Engine**, sebuah sistem cerdas yang dirancang untuk menjembatani kesenjangan antara model Machine Learning tradisional (Fraud Detection, Risk Scoring), data pipeline (Marketing Analytics), dan Large Language Models (LLMs). 

Proyek ini menggunakan arsitektur yang terinspirasi dari **Model Context Protocol (MCP)**, memungkinkan LLM bertindak sebagai agen penalaran otonom yang dapat memanggil analitik bisnis secara *real-time* untuk menghasilkan strategi bisnis yang *actionable* dan berbasis ROI.

## Business Use Case
Dalam ekosistem ritel/fintech, kampanye pemasaran sering kali mendatangkan *traffic* yang tinggi. Namun, tanpa lapisan analitik yang terintegrasi, sulit untuk mengetahui apakah *traffic* tersebut adalah pelanggan potensial (High LTV) atau justru anomali/sindikat (Fraud) dengan risiko gagal bayar yang tinggi (Credit Risk). Sistem ini mengotomatiskan analisis lintas domain tersebut.

## Fitur Utama
1. **Fraud Analytics Module:** Menggunakan `IsolationForest` (Unsupervised Learning) untuk mendeteksi anomali pada transaksi.
2. **Risk Analytics Module:** Mengevaluasi metrik *credit scoring* dan probabilitas gagal bayar berdasarkan data historis pengguna.
3. **Marketing Analytics Module:** Mengkalkulasi metrik *Return on Investment* (ROI) dan *Customer Acquisition Cost* (CAC) per kampanye.
4. **LLM Orchestration (Gemini API):** Mengintegrasikan hasil dari ketiga modul analitik di atas untuk menyusun narasi bisnis dan rekomendasi operasional bagi eksekutif.
5. **Caching System (Redis):** Mengoptimalkan latensi pemanggilan data untuk efisiensi operasional.

## Cara Menjalankan (Google Colab)
Klik tombol di bawah ini untuk menjalankan *pipeline* secara penuh di Google Colab tanpa perlu setup lokal:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1B8i7dGn7UixuSfhZumC8_zMK2v2n8TH3?usp=sharing)

1. Buka Notebook di Google Colab.
2. Masukkan Gemini API Key Anda.
3. Jalankan semua sel (*Run All*).

## Tech Stack
* **Orchestration:** Python, Google Generative AI (Gemini 2.5 Pro)
* **Data Science:** Pandas, NumPy, Scikit-Learn
* **Infrastructure:** Redis (In-memory cache)
