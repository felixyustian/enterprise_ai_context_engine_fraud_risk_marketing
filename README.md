# Enterprise AI Agentic Workflow: Banking Risk & Compliance Engine

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-Latest-orange)
![LangGraph](https://img.shields.io/badge/LangGraph-Multi--Agent-green)
![RAG](https://img.shields.io/badge/Architecture-RAG%20%2B%20Tabular-red)

Repositori ini berisi prototipe fungsional Enterprise AI Context Engine yang dirancang untuk mengotomatisasi analisis risiko finansial dan strategi operasional menggunakan Agentic Workflow. Sistem ini mengintegrasikan data dinamis melalui Model Context Protocol (MCP) untuk pengambilan keputusan berbasis data secara real-time.

```mermaid
graph TD
    subgraph Client_Interface [Interface Layer]
        User((Analyst / Business Unit)) -- "Natural Language Query" --> Agent[AI Agent Orchestrator]
    end

    subgraph Enterprise_Security_Boundary [Secure Environment - On-Premise/VPC]
        
        subgraph AI_Intelligence_Core [Intelligence Layer]
            Agent -- "Prompt & Schema" --> LLM{LLM Engine<br/>Gemini / LLaMA}
            LLM -- "Data Request via MCP" --> Agent
        end

        subgraph MCP_Infrastructure [Control & Context Layer]
            Agent -- "Standardized Tool Call" --> MCPServer[MCP Context Server]
            
            subgraph Security_Middleware [Security & Governance]
                MCPServer --> PII[PII Masking / Anonymization]
                MCPServer --> Audit[Audit Logging & Compliance]
            end
        end

        subgraph Data_Ecosystem [Data Layer]
            PII -- "Authorized Query" --> Conn[Data Connectors]
            Conn -- "Secure Access" --> DB[(Enterprise Database<br/>Fraud/Risk/Mkt)]
            DB -- "Raw Data" --> Conn
        end

        Conn -- "Encrypted Results" --> PII
        PII -- "Sanitized Context" --> MCPServer
        MCPServer -- "Structured Metadata" --> Agent
        Agent -- "Actionable Insights" --> User
    end

    %% Styling for visual hierarchy
    style Enterprise_Security_Boundary fill:#f4f7f9,stroke:#2c3e50,stroke-width:2px
    style MCP_Infrastructure fill:#e3f2fd,stroke:#1565c0,stroke-width:2px
    style Security_Middleware fill:#ffebee,stroke:#c62828,stroke-dasharray: 5 5
    style AI_Intelligence_Core fill:#fffde7,stroke:#fbc02d
    style DB fill:#e8f5e9,stroke:#2e7d32
```

## 📋 Ringkasan Eksekutif
Proyek ini mendemonstrasikan kemampuan untuk menerjemahkan strategi AI perusahaan ke dalam roadmap yang dapat dieksekusi. Dengan menggabungkan data terstruktur (statistik perbankan) dan data tidak terstruktur (regulasi), sistem ini memberikan wawasan mendalam mengenai Risk Analytics, Marketing Analytics, dan Fraud Analytics.

Solusi ini dikembangkan untuk menjawab tantangan operasional di mana keputusan bisnis strategis sering kali terhambat oleh silo data antara tim pemasaran, risiko, dan kepatuhan (*compliance*).

## 🚀 Fitur Utama
Agentic Orchestration (LangGraph): Menggunakan state machine untuk mengelola alur kerja AI mulai dari ekstraksi data hingga laporan strategis akhir secara siklis dan terstruktur.

* MCP Tool Integration: Implementasi Model Context Protocol sebagai nilai tambah strategis untuk memisahkan logika bisnis dari inti model AI.
* RAG-Powered Insights: Menggunakan Retrieval-Augmented Generation (RAG) dengan Vector Database FAISS untuk analisis kepatuhan regulasi secara otomatis.
* Enterprise-Grade UI: Interface interaktif berbasis Streamlit yang mendukung injeksi API Key secara dinamis, memastikan keamanan data sensitif.

## 🏗️ Arsitektur Sistem
Sistem ini menggunakan alur kerja agen otonom (Agentic Workflow) yang terbagi menjadi tiga spesialisasi:

1.  **Data Analyst Agent:** Bertugas melakukan ekstraksi wawasan dari dataset tabular (menggunakan basis *UCI Bank Marketing Dataset*). Agen ini mengevaluasi metrik kunci seperti *conversion rate* dan profil saldo nasabah.
2.  **Compliance Officer Agent (RAG):** Mengimplementasikan **Retrieval-Augmented Generation (RAG)** menggunakan *Vector Database* **FAISS** dan **Gemini-Embedding-001**. Agen ini secara dinamis mencari aturan dalam regulasi internal atau OJK yang relevan dengan kueri bisnis.
3.  **Executive Manager Agent:** Bertugas sebagai orkestrator akhir yang mensintesis temuan dari kedua agen sebelumnya untuk menghasilkan rekomendasi strategis yang mitigatif terhadap risiko.

## Tech Stack
* Core: Python 3.12+
* AI Orchestration: LangChain & LangGraph
* LLM & Embedding: Google Gemini 2.5 Flash & Gemini-Embedding-001
* Data Science: Pandas, Scikit-Learn (Isolation Forest untuk Fraud Detection)
* Deployment: Streamlit via Google Colab Native Proxy

## 📖 Cara Menjalankan (Google Colab)
Klik tombol di bawah ini untuk menjalankan *pipeline* secara penuh di Google Colab tanpa perlu setup lokal:

1. Buka Notebook di Google Colab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/felixyustian/enterprise_ai_context_engine_fraud_risk_marketing/blob/main/enterprise_ai_context_engine_fraud_risk_marketing.ipynb)

2. Masukkan Gemini API Key Anda.
3. Jalankan semua sel (*Run All*).
4. Akses Dashboard: Gunakan tautan `googleusercontent.com` yang dihasilkan, masukkan API Key Gemini Anda di sidebar, dan mulai analisis.

## 📈 Kasus Bisnis (ROI)
Implementasi sistem ini ditujukan untuk mencapai:
* **Reduksi Risiko:** Deteksi dini potensi pelanggaran regulasi sebelum kampanye dijalankan.
* **Peningkatan ROI Pemasaran:** Memastikan target kampanye sesuai dengan profil risiko perbankan yang sehat.
* **Skalabilitas:** Memungkinkan tim R&D untuk menambah agen baru (misalnya: *Fraud Detection Agent*) tanpa merusak alur kerja utama.

---

## ⚖️ License & Copyright

*   **Implementation Copyright:** © 2026 [Felix Yustian Setiono](https://linkedin.com/in/felixsetiono). The entire system architecture, API source code, and experimental analysis documents within this repository are the original intellectual property of the author.
