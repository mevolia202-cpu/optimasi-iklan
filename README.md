# Kalkulator Budget & ROAS Iklan Shopee

Aplikasi web statis (satu file HTML) berisi kalkulator margin/ROAS, alokasi budget marketing, dan tracker iklan harian. Data disimpan di Supabase (per akun) dan di-cache di localStorage.

## 1. Siapkan Supabase
1. Buat project di https://supabase.com.
2. Buka **SQL Editor**, tempel isi `supabase.sql`, klik **Run**.
3. Buka **Project Settings → API**, salin **Project URL** dan **anon/publishable key**.
4. (Opsional) **Authentication → Providers → Email**: matikan "Confirm email" bila ingin langsung bisa masuk setelah daftar.
5. Setelah GitHub Pages aktif, tambahkan alamat situsnya di **Authentication → URL Configuration → Site URL**.

## 2. Konfigurasi (sudah terisi)
Project Supabase `optimasi shopee` (Singapore) sudah dibuat dan tabelnya sudah terpasang; `SB_URL` dan `SB_KEY` di `index.html` sudah terisi. Bagian ini hanya perlu diubah bila kamu pindah project:
Di `index.html`, ganti dua nilai ini:
```js
const SB_URL="https://XXXX.supabase.co";
const SB_KEY="anon-key-kamu";
```
Gunakan hanya anon/publishable key. Jangan pernah memakai `service_role` key. Anon key aman berada di kode publik karena akses dibatasi Row Level Security (tiap akun hanya bisa membaca/mengubah datanya sendiri).

## 3. Deploy ke GitHub Pages
1. Upload `index.html`, `supabase.sql`, `README.md` ke repository.
2. **Settings → Pages → Deploy from a branch → main / (root) → Save**.
3. Buka `https://USERNAME.github.io/NAMA-REPO/`, daftar, lalu masuk.

Data lokal yang sudah ada otomatis diunggah saat pertama kali masuk dengan akun yang belum punya data di cloud.
