---
version: 1.0.0
name: local-testing-debugging
description: Panduan pembuatan unit test, eksekusi test runner, dan analisis error stack trace secara 100% lokal tanpa mengirim kode ke cloud.
---
# Skill: Local Automated Testing & Debugging
## Trigger
Gunakan skill ini ketika mitra manusia meminta pembuatan unit test, debugging error, atau verifikasi fungsionalitas kode, dan menginginkan solusi yang berjalan sepenuhnya di lingkungan lokal tanpa mengandalkan layanan CI/CD cloud atau API eksternal.

## Core Principles
1. **100% Offline Testing**: Gunakan test runner lokal (seperti `pytest`, `jest`, `cargo test`) yang sudah terinstal di mesin pengguna.
2. **Hemat Token & Fokus**: Saat menganalisis stack trace, hanya ekstrak bagian paling relevan (baris error, file, dan fungsi). Jangan output seluruh log mentah.
3. **Reproduktif**: Selalu sertakan langkah untuk mereproduksi error secara lokal sebelum memberikan solusi perbaikan.
4. **Non-Destruktif**: Pastikan kode test yang dihasilkan tidak mengubah atau menghapus data produksi/database lokal pengguna.

## Red Flags 🚩
- Menyarankan penggunaan layanan CI/CD berbayar (GitHub Actions Pro, CircleCI) atau SaaS testing (BrowserStack) sebagai solusi utama.
- Mengoutput log error yang sangat panjang tanpa diringkas (membuang context window).
- Membuat test yang bergantung pada koneksi internet aktif (kecuali secara eksplisit diminta).

## Action Plan
1. **Identifikasi Bahasa & Framework**: Deteksi bahasa pemrograman dan test runner yang umum digunakan (misal: Python -> `pytest`, JS/TS -> `jest`/`vitest`).
2. **Buat Test Minimal**: Tuliskan unit test yang fokus pada fungsi yang bermasalah atau baru dibuat.
3. **Instruksi Eksekusi**: Berikan perintah terminal yang tepat untuk menjalankan test tersebut secara lokal.
4. **Analisis & Perbaikan**: Jika test gagal, analisis output error, berikan penjelasan singkat, dan tawarkan kode perbaikan (diff).

## Panduan Spesifik
- **Python**: Prioritaskan `pytest` dengan `unittest.mock` untuk mocking dependency eksternal.
- **JavaScript/TypeScript**: Prioritaskan `vitest` atau `jest` dengan `msw` (Mock Service Worker) untuk mocking network request secara lokal.
- **Go**: Gunakan `testing` package bawaan dengan `httptest` untuk mocking server.
