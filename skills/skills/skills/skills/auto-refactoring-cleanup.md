---
version: 1.0.0
name: auto-refactoring-cleanup
description: Panduan refactoring kode untuk meningkatkan keterbacaan, mengurangi kompleksitas, dan membersihkan dead code tanpa mengubah perilaku fungsional.
---
# Skill: Auto-Refactoring & Code Cleanup
## Trigger
Gunakan skill ini ketika mitra manusia meminta untuk "merapikan kode", "optimasi struktur", "mengurangi kompleksitas", atau "membersihkan dead code" pada sebuah file atau fungsi.

## Core Principles
1. **Zero Behavioral Change**: Refactoring TIDAK BOLEH mengubah output atau perilaku fungsional dari kode. Jika ada perubahan logika, itu bukan refactoring, itu fitur/fix baru.
2. **Incremental & Safe**: Lakukan perubahan dalam langkah-langkah kecil. Jangan merombak seluruh file sekaligus jika tidak diminta, agar mudah di-review.
3. **Idiomatic**: Pastikan kode hasil refactoring mengikuti best practice dan gaya penulisan (style guide) bahasa pemrograman tersebut (misal: PEP 8 untuk Python, ESLint untuk JS).
4. **Jelaskan "Mengapa"**: Selalu berikan alasan singkat mengapa suatu perubahan refactoring dilakukan (misal: "Mengurangi nested loop dari O(n²) ke O(n)").

## Red Flags 🚩
- Mengubah nama variabel publik atau signature fungsi yang digunakan di bagian lain proyek tanpa memperingatkan pengguna.
- Memperkenalkan library/dependensi baru hanya untuk tujuan refactoring sederhana.
- Menghilangkan komentar atau dokumentasi yang sebenarnya penting saat membersihkan "dead code".

## Action Plan
1. **Identifikasi Target**: Tentukan area yang akan di-refactor (fungsi panjang, nested condition, duplikasi kode, atau variabel dengan nama tidak jelas).
2. **Tawarkan Rencana**: Jelaskan secara singkat apa yang akan diubah (misal: "Saya akan mengekstrak blok ini menjadi fungsi terpisah dan mengganti nama variabel X menjadi Y").
3. **Berikan Diff**: Tampilkan kode sebelum dan sesudah (atau unified diff) agar pengguna bisa memverifikasi perubahan dengan mudah.
4. **Validasi**: Ingatkan pengguna untuk menjalankan test lokal (mengacu pada skill `local-testing-debugging`) untuk memastikan tidak ada regresi.

## Panduan Spesifik
- **Python**: Gunakan `ruff` atau `black` untuk formatting, sarankan penggunaan type hints jika belum ada.
- **JavaScript/TypeScript**: Sarankan penggunaan optional chaining (`?.`), nullish coalescing (`??`), dan destrukturisasi untuk merapikan kode.
- **General**: Ekstraksi "Magic Numbers" menjadi konstanta dengan nama yang deskriptif.