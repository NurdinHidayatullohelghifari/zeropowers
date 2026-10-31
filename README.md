# ⚡ ZeroPowers
> Superpowers untuk AI Coding Assistant Lokal. Mengubah Cline/Roo Code + Ollama menjadi asisten yang efisien, aman, dan 100% offline.

<p align="center">
  <img src="https://img.shields.io/badge/Status-100%25%20Offline-blue?style=for-the-badge" alt="Offline">
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/badge/Engine-Ollama%20%2B%20Qwen2.5-orange?style=for-the-badge" alt="Engine">
</p>

---

## 🎯 Filosofi Desain
- **🛡️ Privasi Pertama:** Tidak ada data kode yang meninggalkan mesin Father.
- **⚡ Efisiensi Kognitif:** Output AI dipangkas menjadi instruksi padat, tanpa halusinasi.
- **🎨 Estetika Fungsional:** Setiap skill memiliki trigger, red flags, dan action plan yang terstruktur rapi.

---

## 🚀 Quick Start (3 Menit)
| Langkah | Perintah / Aksi | Keterangan |
| :--- | :--- | :--- |
| **1. Engine** | `ollama run qwen2.5-coder:7b` | Unduh dan jalankan model lokal. |
| **2. Interface** | Install **Cline** atau **Roo Code** | Ekstensi VS Code untuk AI agent. |
| **3. Konfigurasi** | Settings → Provider: `Ollama` | Arahkan model ke `qwen2.5-coder:7b`. |
| **4. Aktivasi** | Salin folder `skills/` ke project | AI akan otomatis membaca konteks skill. |

---

## 🧩 Skills Matrix (Dashboard Fitur)
| Ikon | Nama Skill | Fungsi Utama | Tool Lokal |
| :---: | :--- | :--- | :--- |
| 🎨 | **Multimodal Gen** | TTS, Gambar, Audio tanpa cloud | `piper`, `stable-diffusion.cpp` |
| 🛠️ | **Local Testing** | Unit test & analisis error | `pytest`, `jest` |
| 🛡️ | **Offline Security** | Scan vulnerability & secrets | `gitleaks`, `semgrep` |
| 🌿 | **Smart Git** | Conventional commits & merge resolve | `git` CLI native |
| 🧹 | **Auto-Refactor** | Bersihkan kode tanpa ubah fungsi | `ruff`, `prettier` |

---

## 📂 Struktur Direktori
```text
zeropowers/
├── 📄 README.md                 # Dokumentasi utama
├── 📄 CONTRIBUTING.md           # Panduan kontribusi
└── 📁 skills/                   # Otak dari ZeroPowers
    ├── multimodal-generation.md
    ├── local-testing-debugging.md
    ├── offline-security-scanner.md
    ├── smart-git-management.md
    └── auto-refactoring-cleanup.md