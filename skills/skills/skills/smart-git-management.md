---
version: 1.0.0
name: smart-git-management
description: Panduan manajemen repositori Git, generasi commit message yang standar, dan resolusi merge conflict secara lokal dan efisien.
---
# Skill: Smart Git & Repo Management (Offline-First)
## Trigger
Gunakan skill ini ketika mitra manusia meminta bantuan untuk membuat commit message, merapikan riwayat Git (rebase/squash), atau menyelesaikan merge conflict tanpa mengandalkan plugin VS Code berbayar atau layanan remote.

## Core Principles
1. **Conventional Commits**: Selalu format commit message menggunakan standar Conventional Commits (misal: `feat:`, `fix:`, `refactor:`) agar riwayat mudah dibaca dan bisa di-generate changelog-nya.
2. **Kontekstual & Ringkas**: Commit message harus menjelaskan *apa* yang diubah dan *mengapa* (jika tidak jelas dari kode), maksimal 72 karakter untuk baris pertama.
3. **Aman & Reversibel**: Sebelum menyarankan perintah Git yang destruktif (seperti `git reset --hard` atau `git rebase`), selalu ingatkan pengguna untuk mem-backup branch atau buat branch cadangan.
4. **Offline-First**: Asumsikan operasi Git dilakukan secara lokal. Perintah `git push` hanya disarankan sebagai langkah terakhir setelah lokal bersih.

## Red Flags 🚩
- Menghasilkan commit message yang generik seperti "update code" atau "fix bug" tanpa detail.
- Menyarankan perintah Git yang berisiko kehilangan data tanpa peringatan (warning) yang jelas.
- Mengasumsikan pengguna memiliki akses ke remote repository tertentu tanpa memverifikasi terlebih dahulu.

## Action Plan
1. **Analisis Perubahan**: Gunakan `git diff` atau minta pengguna memberikan daftar file yang diubah untuk memahami konteks.
2. **Generate Commit Message**: Buat 1-3 opsi commit message yang sesuai standar Conventional Commits berdasarkan perubahan.
3. **Resolusi Conflict (Jika ada)**: Jelaskan bagian mana yang conflict, tawarkan solusi penggabungan kode yang logis, dan berikan perintah `git add` + `git commit` untuk menyelesaikan.
4. **Cleanup**: Sarankan perintah untuk merapikan branch lokal yang sudah tidak terpakai (`git branch -d`).

## Panduan Spesifik
- **Prefix Standar**: `feat` (fitur baru), `fix` (perbaikan bug), `docs` (dokumentasi), `style` (formatting), `refactor` (ubah struktur tanpa ubah fungsi), `test` (tambah test), `chore` (pemeliharaan).
- **Amend**: Jika pengguna baru saja commit dan ada typo, sarankan `git commit --amend --no-edit` atau `--amend -m "pesan baru"`.