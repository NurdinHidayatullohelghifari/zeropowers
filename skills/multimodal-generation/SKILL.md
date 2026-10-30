\---

version: 1.0.0

name: multimodal-generation

description: Panduan generasi media (TTS, Gambar, Audio, Video) 100% lokal, open-source, dan gratis.

\---



\# Skill: Multimodal Generation (Strictly Local \& Free)



\## Trigger

Gunakan skill ini ketika mitra manusia meminta pembuatan konten media dari teks (Text-to-Speech, Text-to-Image, Text-to-Audio, Text-to-Video) dan menginginkan solusi yang \*\*100% gratis, open-source, dan dapat berjalan secara lokal (offline)\*\* tanpa mengandalkan layanan cloud berbayar atau API key.



\## Core Principles

1\. \*\*100% Offline \& Gratis\*\*: Jangan pernah menyarankan layanan cloud berbayar (seperti ElevenLabs, DALL-E, Midjourney, atau RunwayML). Fokus hanya pada alat open-source yang dapat diunduh dan dijalankan di mesin lokal.

2\. \*\*Kesadaran Sumber Daya (Resource Awareness)\*\*: Model lokal membutuhkan RAM/VRAM. Selalu tanyakan atau asumsikan spesifikasi hardware minimal sebelum menyarankan model berat. Berikan alternatif ringan (CPU-friendly) sebagai default.

3\. \*\*Open Source Only\*\*: Hanya rekomendasikan alat dengan lisensi permisif yang dapat diinstal via package manager standar (`pip`, `apt`, `brew`) atau binary langsung.

4\. \*\*Instruksi Instalasi yang Jelas\*\*: Sertakan perintah instalasi yang tepat dan cara verifikasi bahwa alat tersebut berjalan sebelum memberikan kode generasi.



\## Red Flags 🚩

\- Menyarankan alat yang memerlukan pendaftaran akun, API key, atau langganan berbayar.

\- Mengasumsikan pengguna memiliki GPU dengan VRAM besar (8GB+) tanpa memberikan alternatif CPU.

\- Memberikan kode yang gagal jika tidak ada koneksi internet.

\- Tidak memperingatkan tentang waktu pemrosesan yang lama pada hardware spesifikasi rendah.



\## Action Plan

1\. \*\*Identifikasi Modalitas \& Hardware\*\*: Tentukan jenis media dan tanyakan spesifikasi hardware (CPU saja atau ada GPU? Berapa RAM/VRAM?).

2\. \*\*Pilih Alat Lokal\*\*: Berdasarkan hardware, pilih alat dari panduan referensi (`references/tools-guide.md`). Prioritaskan alat yang ringan.

3\. \*\*Berikan Solusi Lengkap\*\*: Sediakan perintah instalasi, kode minimal yang bisa langsung dijalankan, penanganan error lokal (seperti OOM), dan lokasi output file.

4\. \*\*Fallback Lokal\*\*: Jika alat utama terlalu berat, segera tawarkan alternatif yang lebih ringan (misal: dari `coqui-tts` ke `piper`).



\## Panduan Spesifik Modalitas (Lokal Saja)

\- \*\*Text-to-Speech (TTS)\*\*: Rekomendasi utama `piper` (cepat, CPU-friendly). Alternatif: `espeak` (sangat ringan).

\- \*\*Text-to-Image\*\*: Rekomendasi utama `stable-diffusion.cpp` (bisa di CPU). Alternatif GPU: `diffusers` dengan model LCM/Turbo.

\- \*\*Text-to-Audio\*\*: Rekomendasi utama `ffmpeg` (untuk manipulasi dasar). Alternatif advanced: `bark` (butuh GPU 4GB+ atau di-quantize).

\- \*\*Text-to-Video\*\*: Rekomendasi utama `ffmpeg` (membuat slideshow dari gambar). Hindari model video generatif lokal kecuali pengguna memiliki GPU 12GB+ VRAM.

