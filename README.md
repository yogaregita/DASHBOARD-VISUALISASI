# Dashboard Emas Insight

## Cara membuka
1. Ekstrak seluruh isi ZIP ke satu folder.
2. Klik dua kali index.html. Dashboard dapat dibuka langsung di browser tanpa instalasi dan tanpa koneksi internet.
3. Pilih menu Permasalahan, Tujuan, Metode, Hasil per Tujuan, atau Kesimpulan.
4. Untuk FEVD: Hasil per Tujuan > Tujuan 2. Grafik menunjukkan batang bertumpuk horizon 1–20. Arahkan penunjuk atau sentuh batang, atau ubah pilihan horizon untuk melihat angka.

## Isi kode
- index.html: struktur dan isi dashboard.
- dashboard.css: gaya visual dan tampilan responsif.
- dashboard.js: navigasi, grafik, filter, evaluasi, dan unduh CSV.
- data.js: data yang langsung dimuat browser, agar pembukaan lokal bekerja.
- data.json: salinan data dalam format JSON.
- favicon.svg: ikon dashboard.

## Mengubah data
Dashboard memuat window.RESEARCH_DATA dari data.js terlebih dahulu. Jika mengedit data.json, sinkronkan data.js dengan menjalankan perintah berikut dari folder ini (memerlukan Python):

python -c "from pathlib import Path; Path('data.js').write_text('window.RESEARCH_DATA = '+Path('data.json').read_text()+';', encoding='utf-8')"

FEVD terdapat pada array fevd, dengan field horizon, gold, ihsg, usd (dalam persen). Grafik menampilkan 20 horizon dari Tabel 9 skripsi. Tinggi segmen dinormalisasi dengan total setiap horizon untuk mempertahankan tinggi batang 100% ketika ada pembulatan; angka yang ditampilkan tetap nilai asli tabel.

## Sumber dan batas interpretasi
Historis: data_emas_updated.xlsx (722 observasi).
Evaluasi: akurasimodel.xlsx (90 pasangan aktual-prediksi).
Metode, Granger, IRF, dan FEVD: Draft sidang_Yoga Regita H.A.pdf.
FEVD adalah kontribusi terhadap varians kesalahan peramalan, bukan persentase pembentuk harga emas. Data FEVD dibulatkan tiga desimal mengikuti tabel skripsi. Dashboard tidak melatih ulang VECM.

Referensi antarmuka: FRED (rentang waktu dan eksplorasi seri); Datawrapper (grafik waktu).

Paket ini tidak memerlukan library JavaScript eksternal, akun hosting, atau kunci API. Link web story dan referensi hanya memerlukan internet jika dibuka.

## Navigasi
Navbar berada di bagian atas pada desktop dan HP. Jika lebar layar terbatas, geser menu atas secara horizontal.
