# artex-tunnel

Menjalankan ARTEX di GitHub Actions dan membukanya ke internet lewat
Cloudflare Quick Tunnel, supaya bisa dibuka dari HP tanpa VPS.

## Aman untuk repo public

URL tunnel + setup token **tidak pernah muncul di log**.
Keduanya hanya dikirim ke Telegram kamu via GitHub Secrets.

## Setup sekali saja (5 menit)

1. Di Telegram, cari **@BotFather** → `/newbot` → ikuti sampai dapat token.
   Jangan kirim token itu ke siapa pun / di chat mana pun.
2. Cari bot barumu di Telegram, tap **Start** (kirim `/start`).
3. Cari **@userinfobot** → tap Start → catat `Id` kamu, itu `CHAT_ID`.
4. Di GitHub, buka repo ini → **Settings → Secrets and variables →
   Actions → New repository secret**, buat dua secret ini:
   - `TELEGRAM_BOT_TOKEN` = token dari BotFather
   - `TELEGRAM_CHAT_ID` = Id dari @userinfobot
5. Setelah dua secret itu ada, repo ini aman dijadikan **Public**.

## Cara pakai

1. Buka tab **Actions** di repo ini.
2. Pilih workflow **artex-tunnel** di sidebar kiri.
3. Klik **Run workflow** → **Run workflow**.
4. Tunggu pesan Telegram (build Docker ~3-5 menit). Pesannya berisi:
   URL `https://....trycloudflare.com` + setup token.
5. Buka URL itu dari HP, masukkan setup token di halaman `/setup`,
   lalu buat password admin.

## Catatan

- Satu run tahan sampai **6 jam**, lalu jalankan lagi bila perlu.
- Jangan bagikan URL tunnel ke orang lain, dan segera buat password admin
  di halaman `/setup` setelah pertama kali buka.
- Kalau run gagal dengan pesan soal Secrets, berarti langkah 4 di atas
  belum dilakukan.
