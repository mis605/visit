# Visit Management

Aplikasi web untuk Project Coordinator mengajukan **Rencana Kunjungan** ke Klien dan mencatat **Realisasinya** (foto selfie dengan klien).

## Fitur

- 🔐 Login dengan Google Account (SSO)
- 📝 Ajukan rencana kunjungan — pilih proyek & beberapa tanggal sekaligus
- 📧 Notifikasi email otomatis ke atasan + CC
- 📍 Catat realisasi kunjungan dengan foto selfie
- 📷 Live camera preview dengan timestamp otomatis
- ☁️ Foto tersimpan langsung ke Google Drive
- 📊 Semua data tersimpan di Google Sheets

## Arsitektur

```
Frontend (GitHub Pages)   →   fetch() POST   →   Backend (Google Apps Script)
     index.html                                      visit.gs
```

## Setup

Baca **[SETUP.md](SETUP.md)** untuk panduan lengkap.

Singkatnya:
1. Siapkan Google Spreadsheet (4 sheets: Pengguna, Proyek, Kunjungan, Konfigurasi)
2. Deploy `visit.gs` + `appsscript.json` ke [Google Apps Script](https://script.google.com)
3. Buat OAuth Client ID di [Google Cloud Console](https://console.cloud.google.com)
4. Isi 2 konstanta di `index.html`, lalu upload ke GitHub Pages

## File

| File | Keterangan |
|---|---|
| `index.html` | Frontend — upload ke GitHub Pages |
| `visit.gs` | Backend — upload ke Google Apps Script |
| `appsscript.json` | Konfigurasi GAS — upload ke Google Apps Script |
| `SETUP.md` | Panduan setup lengkap |

## Tech Stack

- **Frontend**: Vanilla HTML + CSS + JS (tanpa framework)
- **Backend**: Google Apps Script (gratis)
- **Database**: Google Sheets
- **Storage**: Google Drive
- **Auth**: Google Sign-In (OAuth 2.0)
- **Email**: Gmail via GAS `GmailApp`
- **Hosting**: GitHub Pages (gratis)
