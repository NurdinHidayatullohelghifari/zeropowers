---
version: 1.0.0
name: offline-security-scanner
description: Panduan deteksi kerentanan keamanan, hardcoded secrets, dan kode berbahaya menggunakan tools scanner open-source yang berjalan lokal.
---
# Skill: Offline Security & Vulnerability Scanner
## Trigger
Gunakan skill ini ketika mitra manusia meminta review keamanan, pengecekan vulnerability, atau pembersihan hardcoded secrets (API key, password) sebelum kode di-commit atau di-deploy.

## Core Principles
1. **Local-First Scanning**: Gunakan tools CLI open-source yang diinstal di mesin lokal. Jangan pernah menyarankan upload kode ke scanner web berbasis cloud.
2. **Zero False Positive Tolerance**: Saat melaporkan vulnerability, jelaskan *mengapa* itu berbahaya dan berikan kode perbaikan yang spesifik.
3. **Secret Management**: Jangan pernah output secret yang terdeteksi dalam log. Sarankan penggunaan `.env` atau secret manager lokal.
4. **Ringan & Cepat**: Prioritaskan tools yang tidak memakan RAM besar dan bisa berjalan cepat di background.

## Red Flags 🚩
- Menyarankan layanan SaaS scanning seperti Snyk Cloud, SonarQube Cloud, atau GitHub Secret Scanning sebagai satu-satunya solusi.
- Membiarkan hardcoded credentials (API keys, private keys) tetap ada di kode tanpa peringatan keras.
- Mengusulkan perubahan arsitektur besar hanya untuk masalah keamanan minor yang bisa diperbaiki dengan satu baris kode.

## Action Plan
1. **Identifikasi Bahasa**: Pilih tool scanner lokal yang sesuai dengan stack bahasa pemrograman.
2. **Simulasikan Perintah**: Berikan perintah CLI untuk menjalankan scanner di direktori proyek.
3. **Analisis Hasil**: Jika ditemukan isu, kategorikan menjadi: Critical, High, Medium, Low.
4. **Berikan Patch**: Tawarkan kode perbaikan (diff) langsung untuk isu Critical dan High.

## Panduan Spesifik
- **Multi-language / Secrets**: `gitleaks` (deteksi hardcoded secrets, sangat cepat, ringan).
- **Python**: `bandit` (static analysis untuk kerentanan Python umum).
- **JavaScript/Node.js**: `npm audit` (bawaan) atau `retire.js` (deteksi library rentan).
- **General SAST**: `semgrep` (bisa dijalankan offline dengan rule set komunitas, sangat efisien).