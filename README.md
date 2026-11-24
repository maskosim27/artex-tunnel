# artex-tunnel

Menjalankan ARTEX di GitHub Actions dan membukanya ke internet lewat
Cloudflare Quick Tunnel, supaya bisa dibuka dari HP tanpa VPS.

## Cara pakai

1. Buka tab **Actions** di repo ini.
2. Pilih workflow **artex-tunnel** di sidebar kiri.
3. Klik **Run workflow** -> **Run workflow**.
4. Tunggu sampai step `Start ARTEX` selesai (build Docker ~3-5 menit).
   Di log-nya ada **setup token** (dibutuhkan di halaman `/setup`).
5. Di step `Open public tunnel`, cari baris URL `https://....trycloudflare.com`.
   Buka URL itu dari HP, masukkan setup token di halaman `/setup`,
   lalu buat password admin.

## Catatan

- Repo ini harus tetap **privat**: log berisi URL tunnel + setup token.
- Satu run tahan sampai **6 jam**, lalu jalankan lagi bila perlu.
- Jangan bagikan URL tunnel ke orang lain, dan segera buat password admin
  di halaman `/setup` setelah pertama kali buka.
