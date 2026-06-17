<div align="center">

# 🤖 Minecraft Bot by NazamaBot & Nazama Tools

**Make your server online 24/7 with Minecraft Bot by NazamaBot & Nazama Tools**

[![Version](https://img.shields.io/badge/version-1.0.3-brightgreen?style=for-the-badge)](https://github.com/nazama-tools/minecraft-bot/releases)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)
[![Mineflayer](https://img.shields.io/badge/mineflayer-4.15.0-orange?style=for-the-badge)](https://github.com/PrismarineJS/mineflayer)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20VPS%20%7C%20Termux%20%7C%20Replit-lightgrey?style=for-the-badge)]()

<br/>

> 🎮 Bot Minecraft AFK sederhana yang bisa menjaga koneksi server tetap aktif 24/7.  
> Tersedia dalam dua versi — dengan atau tanpa sistem Login/Register.

<br/>

[📦 Download Release](#-download) • [🚀 Cara Pakai](#-cara-pakai) • [⚙️ Konfigurasi](#-konfigurasi) • [📋 Platform](#-platform-yang-didukung)

</div>

---

## 📌 Tentang Project

**Minecraft Bot** adalah bot AFK berbasis [Mineflayer](https://github.com/PrismarineJS/mineflayer) yang dirancang untuk bergabung ke server Minecraft secara otomatis dan menjaga server tetap aktif. Bot ini:

- 🔌 Menghubungkan **1 bot** ke server Minecraft target
- 🔁 Auto-reconnect jika bot terputus atau di-kick
- 🌐 Menyediakan web server ringan sebagai health check (untuk Replit / UptimeRobot)
- ✅ Support Minecraft versi **1.20.1** (offline mode)

---

## 🗂️ Versi Tersedia

Project ini hadir dalam **dua versi** — pilih sesuai kebutuhan server kamu:

| Fitur | 🔐 LR Version | 🚫 NLR Version |
|---|---|---|
| Auto `/register` | ✅ | ❌ |
| Auto `/login` | ✅ | ❌ |
| Auto-reconnect | ✅ | ✅ |
| Cocok untuk server tanpa auth | ❌ | ✅ |
| Cocok untuk server dengan auth | ✅ | ❌ |

### 🔐 LR Version (Login/Register)
Gunakan versi ini jika server Minecraft yang ingin kamu masuki **menggunakan sistem autentikasi** seperti perintah `/login` dan `/register` (contoh: plugin AuthMe, nLogin, dll).

Bot akan otomatis mengirim `/register` dan `/login` beberapa detik setelah bergabung ke server.

### 🚫 NLR Version (No Login/Register)
Gunakan versi ini jika server **tidak menggunakan sistem login/register** sama sekali. Bot akan langsung aktif setelah berhasil join server.

---

## 📦 Download

Unduh versi terbaru di halaman **[Releases](https://github.com/nazama-tools/minecraft-bot/releases)**:

```
https://github.com/nazama-tools/minecraft-bot/releases
```

Tersedia dua file:
- `bot_Minecraft_LR_V1_0_3.zip` — versi dengan Login/Register
- `bot_Minecraft_NLR_V1_0_3.zip` — versi tanpa Login/Register

---

## ⚙️ Konfigurasi

Sebelum menjalankan bot, buka file `index.js` dan ubah bagian berikut sesuai server kamu:

```js
const bot = mineflayer.createBot({
  host: "IP_SERVER",   // ← Ganti dengan IP / domain server Minecraft
  port: PORT_SERVER,   // ← Ganti dengan port server (default: 25565)
  version: "1.20.1",  // ← Sesuaikan dengan versi server jika perlu
});
```

**Khusus LR Version** — kamu juga bisa mengubah password default bot:

```js
bot.chat("/register bot123 bot123"); // Ganti "bot123" dengan password pilihanmu
bot.chat("/login bot123");           // Sesuaikan dengan password di atas
```

---

## 🚀 Cara Pakai

### 🔷 Pterodactyl Panel (direkomendasikan untuk VPS/hosting)

1. Buat egg baru dengan **runtime Node.js**
2. Upload file `index.js` dan `package.json` ke panel
3. Set **Startup Command** menjadi:
   ```
   npm start
   ```
4. Jalankan server — bot akan otomatis install dependencies dan mulai berjalan

---

### 🔷 Replit

1. Buka [replit.com](https://replit.com) dan buat project baru dengan template **Node.js**
2. Upload atau paste isi file `index.js` dan `package.json`
3. Klik tombol **Run** — Replit akan otomatis menjalankan `npm start`
4. Gunakan **UptimeRobot** untuk ping endpoint `/` agar bot tetap online 24/7

---

### 🔷 Linux / Ubuntu / Kali Linux / VPS

```bash
# 1. Install Node.js jika belum ada
sudo apt update && sudo apt install nodejs npm -y

# 2. Masuk ke folder project
cd minecraft-bot

# 3. Install dependencies
npm install

# 4. Jalankan bot
npm start
```

---

### 🔷 Termux (Android)

```bash
# 1. Install Node.js
pkg update && pkg install nodejs -y

# 2. Masuk ke folder project
cd minecraft-bot

# 3. Install dependencies
npm install

# 4. Jalankan bot
npm start
```

---

### 🔷 Hosting Lainnya (yang Support Node.js)

Untuk platform hosting Node.js lainnya (Railway, Fl0, Render, dll), langkah umumnya:

1. Upload file `index.js` dan `package.json`
2. Set startup command ke `npm start`
3. Pastikan platform mendukung koneksi TCP keluar (untuk koneksi ke server Minecraft)

---

## 📋 Platform yang Didukung

| Platform | Status |
|---|---|
| 🖥️ Linux (Ubuntu, Debian, Kali) | ✅ Didukung |
| ☁️ VPS / Cloud Server | ✅ Didukung |
| 🦜 Pterodactyl Panel | ✅ Didukung |
| 🔁 Replit | ✅ Didukung |
| 📱 Termux (Android) | ✅ Didukung |
| 🚂 Railway / Render / Fl0 | ✅ Didukung |
| 🪟 Windows (via Node.js) | ✅ Didukung |

---

## 📦 Dependencies

| Package | Versi | Fungsi |
|---|---|---|
| [mineflayer](https://github.com/PrismarineJS/mineflayer) | `^4.15.0` | Library untuk membuat bot Minecraft |
| [express](https://expressjs.com) | `^4.18.2` | Web server ringan untuk health check |

---

## 🔄 Changelog

### v1.0.3 — Latest
- ✅ Auto-reconnect saat bot di-kick atau disconnect
- ✅ Delay auto-login yang lebih stabil (LR Version)
- ✅ Random username agar tidak konflik
- ✅ Web server health check endpoint (`/`)

---

## ❓ FAQ

**Q: Bot tidak bisa konek ke server?**  
A: Pastikan IP dan port di `index.js` sudah benar. Cek juga apakah server menggunakan online-mode (bot ini menggunakan offline auth).

**Q: Bot langsung disconnect setelah join?**  
A: Kemungkinan server menggunakan sistem login. Pastikan kamu menggunakan **LR Version** dan password sudah dikonfigurasi dengan benar.

**Q: Bisa tambah lebih dari 1 bot?**  
A: Versi ini dirancang untuk 1 bot per instansi. Untuk multi-bot, jalankan beberapa instance secara terpisah.

**Q: Versi Minecraft apa yang didukung?**  
A: Default menggunakan `1.20.1`. Ubah nilai `version` di `index.js` sesuai versi server kamu.

---

## 🤝 Kontribusi

Kontribusi, issue, dan pull request sangat diterima!  
Silakan buka [Issues](https://github.com/nazama-tools/minecraft-bot/issues) jika menemukan bug atau ingin request fitur.

---

## 👤 Developer

<div align="center">

**NazamaBot & Nazama Tools**

[![GitHub](https://img.shields.io/badge/GitHub-nazama--tools-181717?style=for-the-badge&logo=github)](https://github.com/nazama-tools)

*Make your server online 24/7 with Minecraft Bot by NazamaBot & Nazama Tools* 🚀

</div>

---

<div align="center">

⭐ Jika project ini membantumu, jangan lupa beri **star** di repositori ini!

</div>
