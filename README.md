# Gemini TTS Generator

Web sederhana untuk generate Text-to-Speech (TTS) dengan Gemini API.

Desain profesional gaya Anthropic / Claude: basis kertas hangat, tinta near-black, satu aksen koral, judul serif besar, label bernomor, kartu tenang dengan hairline, tombol pill — tanpa dekorasi AI-generate.

## Fitur
- Tab **Generator**: tulis teks (maks 3000 karakter + contoh siap pakai), pilih 29 suara Gemini, model TTS, bahasa, dan gaya suara, lalu generate audio yang bisa diputar & diunduh sebagai WAV.
- Model: `gemini-3.8-flash-tts` (default, flagship baru), `gemini-3.8-flash-lite-tts` (tercepat & paling hemat), `gemini-2.5-flash-preview-tts` (lama), `gemini-2.5-pro-preview-tts` (lama, berbayar saja). Model 2.5 / 3.1 preview dijadwalkan pensiun mulai 17 Nov 2026.
- Tab **Admin Panel**: masukkan Gemini API Key (tampilkan/sembunyikan, tempel clipboard, hapus), uji koneksi, status key tersamar, pengaturan model default & awalan nama file, plus panduan 4 langkah mendapatkan API Key gratis dari Google AI Studio.
- Panggilan dilakukan langsung dari browser ke Gemini API (`generativelanguage.googleapis.com`) memakai key pengguna sendiri, audio PCM 24kHz dikonversi ke WAV di browser.

## Catatan penting soal API Key
API Key sengaja hanya disimpan di memori sesi (tidak di localStorage / server) demi keamanan, jadi perlu diisi ulang setelah halaman ditutup / refresh.

## Deploy ke Cloudflare Pages
Repo ini static, tanpa build step:
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git → pilih repo `Digra15/gemini-tts-generator`.
2. Framework preset: **None** / Static HTML.
3. Build command: kosongkan, Build output directory: `/` (root).
4. Deploy. Tidak ada environment variable yang dibutuhkan — API Key dimasukkan lewat Admin Panel di browser.

Dapatkan API Key gratis di: https://aistudio.google.com/apikey
