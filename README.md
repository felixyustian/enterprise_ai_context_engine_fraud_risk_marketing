# Enterprise AI Agentic Workflow: Banking Risk & Compliance Engine

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-Latest-orange)
![LangGraph](https://img.shields.io/badge/LangGraph-Multi--Agent-green)
![RAG](https://img.shields.io/badge/Architecture-RAG%20%2B%20Tabular-red)

## 📋 Ringkasan Eksekutif
Repositori ini mendemonstrasikan prototipe sistem AI tingkat *Enterprise* yang dirancang untuk sektor perbankan dan finansial. Sistem ini mengintegrasikan data terstruktur (statistik perbankan) dengan data tidak terstruktur (regulasi kepatuhan) melalui arsitektur **Multi-Agent** yang dikelola oleh **LangGraph**.

[cite_start]Solusi ini dikembangkan untuk menjawab tantangan operasional di mana keputusan bisnis strategis sering kali terhambat oleh silo data antara tim pemasaran, risiko, dan kepatuhan (*compliance*).

## 🏗️ Arsitektur Sistem
Sistem ini menggunakan alur kerja agen otonom (Agentic Workflow) yang terbagi menjadi tiga spesialisasi:

1.  **Data Analyst Agent:** Bertugas melakukan ekstraksi wawasan dari dataset tabular (menggunakan basis *UCI Bank Marketing Dataset*). Agen ini mengevaluasi metrik kunci seperti *conversion rate* dan profil saldo nasabah.
2.  **Compliance Officer Agent (RAG):** Mengimplementasikan **Retrieval-Augmented Generation (RAG)** menggunakan *Vector Database* **FAISS** dan **Gemini-Embedding-001**. Agen ini secara dinamis mencari aturan dalam regulasi internal atau OJK yang relevan dengan kueri bisnis.
3.  **Executive Manager Agent:** Bertugas sebagai orkestrator akhir yang mensintesis temuan dari kedua agen sebelumnya untuk menghasilkan rekomendasi strategis yang mitigatif terhadap risiko.

## 🚀 Fitur Utama & Keunggulan Teknis
* [cite_start]**Decision-Making Berbasis Konteks:** Menggabungkan logika ML tradisional dengan penalaran LLM melalui *Model Context Protocol* (MCP) yang diimplementasikan dalam struktur LangGraph.
* **Arsitektur RAG Stabil:** Menggunakan model embedding terbaru (`gemini-embedding-001`) untuk akurasi semantik yang lebih tinggi pada dokumen teknis/regulasi.
* **Resiliensi Data:** Memiliki mekanisme *fallback* otomatis untuk memastikan pipeline tetap berjalan meskipun koneksi data eksternal terputus.
* **Efisiensi Operasional:** Mengurangi waktu audit kepatuhan manual dengan integrasi pencarian regulasi secara *real-time*.

## 🛠️ Tech Stack
* **Orchestration:** LangChain, LangGraph
* **LLM & Embedding:** Google Gemini 1.5 Flash, Gemini-Embedding-001
* **Vector Store:** FAISS (Facebook AI Similarity Search)
* **Data Analysis:** Pandas, Scikit-Learn
* **Deployment:** Google Colab / Jupyter Notebook

## 📖 Cara Menjalankan (Google Colab)
1.  Buka file `Enterprise_AI_Context_Engine.ipynb` di Google Colab.
2.  Masukkan `GOOGLE_API_KEY` Anda pada sel konfigurasi.
3.  Jalankan semua sel (*Run All*). 
4.  Sistem akan secara otomatis membangun *knowledge base* regulasi dan menganalisis dataset sebelum memberikan laporan eksekutif.

## 📈 Kasus Bisnis (ROI)
Implementasi sistem ini ditujukan untuk mencapai:
* **Reduksi Risiko:** Deteksi dini potensi pelanggaran regulasi sebelum kampanye dijalankan.
* [cite_start]**Peningkatan ROI Pemasaran:** Memastikan target kampanye sesuai dengan profil risiko perbankan yang sehat.
* **Skalabilitas:** Memungkinkan tim R&D untuk menambah agen baru (misalnya: *Fraud Detection Agent*) tanpa merusak alur kerja utama.

---
**Kontak Pengembang:** [Felix Yustian Setiono](https://linkedin.com/in/felixsetiono)
