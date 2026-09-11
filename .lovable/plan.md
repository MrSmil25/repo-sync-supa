# Performa Konten

## Ringkasan
Menambahkan modul analitik performa konten yang membaca tabel dan view Supabase yang sudah tersedia. Tidak ada perubahan skema, penghapusan halaman, atau penulisan ulang sidebar/routing.

## Yang Akan Dibangun
- Tambahkan menu **Performa Konten** setelah **Content Planner** pada bagian MARKETING.
- Tambahkan halaman `/content-performance` dengan dua tab:
  - **Dashboard Pola**: filter 90 hari dan multi-platform, insight otomatis, grafik format/pilar/hari/tren bulanan, tabel pendamping, dan daftar konten terbaik.
  - **Catatan**: pengingat konten yang belum dicatat, pencarian/filter, tabel catatan, serta aksi edit dan arsip.
- Tambahkan modal **Catat Performa** bertahap:
  - Pilih konten kalender atau konten lain.
  - Isi tanggal dan tautan.
  - Isi metrik yang tersedia dalam kelompok yang jelas.
  - Tambahkan catatan kualitatif.
- Tambahkan kartu dashboard utama untuk KRD, HMS, dan BPH saat masih ada konten yang belum dicatat.

## Perilaku Data
- Gunakan Supabase JS dan RLS yang sudah ada; `recorded_by` diambil dari pengguna aktif.
- Filter dashboard dihitung dari catatan mentah agar rentang tanggal dan pilihan platform berlaku konsisten pada semua visual.
- Data view siap pakai tetap dipakai sebagai sumber pola bawaan dan pengingat.
- Urutan hari grafik selalu Senin–Minggu; angka memakai format Indonesia dan engagement rate dua desimal.
- Arsip dilakukan dengan mengubah `is_archived`, bukan menghapus catatan.

## Teknis
- Tambahkan pustaka query/helper khusus performa, komponen modal input, komponen kartu dashboard, dan satu route baru.
- Gunakan Recharts yang sudah terpasang untuk grafik, serta komponen tombol/dialog/tabel yang sudah tersedia.
- Pertahankan seluruh halaman, menu, dan alur lama; perubahan pada sidebar dan dashboard hanya berupa sisipan baru.

## Verifikasi
- Periksa typecheck dan hasil build otomatis.
- Uji tampilan halaman, tab, filter, modal, serta keadaan kosong melalui browser pada desktop dan mobile.
