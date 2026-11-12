# Design Guideline — SOM Lab

Panduan ini mendokumentasikan arah visual dan aturan antarmuka untuk SOM Lab, modul pembelajaran interaktif Self-Organizing Maps (SOM) berbahasa Indonesia. Gunakan sebagai acuan saat menambah atau mengubah halaman, komponen, ilustrasi, dan visualisasi.

## 1. Model desain

**Model: editorial learning lab** — perpaduan antara keterbacaan modul akademik dan eksplorasi laboratorium interaktif.

- **Editorial** untuk materi, penjelasan, rumus, studi kasus, dan sumber: tenang, terstruktur, nyaman dibaca.
- **Laboratorium** untuk simulasi dan peta SOM: kontrol terlihat jelas, hasil dapat dibandingkan, dan data dapat dieksplorasi langsung.
- **Karakter:** akademik, ramah, presisi, dan tidak terasa seperti dasbor bisnis.
- **Prioritas:** pemahaman materi dan interpretasi yang benar lebih penting daripada dekorasi. Hindari ornamen yang bersaing dengan data.

## 2. Palet warna

Gunakan warna melalui token berikut. Palet ini diambil dari identitas visual antarmuka saat ini.

| Token | Nilai | Peran |
|---|---|---|
| `ink` | `#182645` | Warna utama teks, navigasi, tombol primer, dan panel kontras tinggi |
| `muted` | `#53627A` | Teks sekunder, keterangan, label, dan sumbu |
| `paper` | `#F5F7FB` | Latar utama halaman |
| `line` | `#DCE3EF` | Garis pemisah dan batas komponen |
| `teal` | `#087F83` | Aksen utama, tautan penting, progres, dan tindakan edukatif |
| `pale` | `#E7F5F2` | Latar lembut untuk sorotan dan keadaan terpilih |
| `indigo` | `#4A50B2` | Aksen sekunder, gunakan seperlunya |
| `focus` | `#B16914` | Cincin fokus keyboard dan penanda fokus yang perlu terlihat |
| `white` | `#FFFFFF` | Panel, kartu, dan kontrol di atas latar utama |

### Aturan penggunaan warna

- Jaga `ink` sebagai warna teks utama dan `muted` untuk informasi sekunder; jangan gunakan warna pucat untuk teks isi.
- Gunakan `teal` secara konsisten sebagai aksen, bukan sebagai warna latar besar yang dominan.
- Gunakan `pale` untuk membedakan keadaan aktif atau informasi terkait tanpa menghilangkan keterbacaan.
- Gunakan warna status tambahan secara semantik: hijau untuk benar/selesai, merah lembut untuk jawaban keliru, dan amber untuk fokus atau peringatan.
- Jangan mengandalkan warna saja untuk menyampaikan makna. Sertakan label, ikon, bentuk, atau teks status.
- Untuk peta nilai, pertahankan skala berurutan yang jelas dan sediakan legenda serta nilai teks. Pastikan teks di atas sel tetap terbaca pada nilai terang maupun gelap.

## 3. Tipografi

- **Teks antarmuka dan isi:** Inter bila tersedia, dengan fallback `ui-sans-serif`, system-ui, dan sans-serif.
- **Judul utama:** Georgia atau serif sistem, berukuran responsif, dengan bobot normal agar terasa editorial.
- **Judul bagian dan kartu:** sans-serif tebal dengan hierarki ukuran yang jelas.
- **Rumus dan kode:** font monospace seperti `ui-monospace` atau Consolas; tampilkan sebagai blok yang dapat digulir bila terlalu lebar.
- Gunakan kapitalisasi kalimat dalam bahasa Indonesia. Huruf kapital semua hanya untuk label pendek seperti eyebrow atau metadata.
- Jaga isi utama sekitar 14–16 px atau lebih; teks kecil untuk metadata saja dan tetap mudah dibaca.
- Gunakan tinggi baris yang lapang untuk isi (sekitar 1,6–1,7) dan hindari paragraf yang terlalu lebar.

## 4. Tata letak dan responsivitas

- **Desktop:** navigasi bab tetap di sisi kiri; konten berada di kanan dalam kolom terpusat dengan lebar maksimum sekitar 1160 px.
- **Tablet:** kurangi lebar/padding navigasi dan susun ulang area simulasi atau visualisasi jika dua kolom tidak lagi nyaman.
- **Ponsel (≤760 px):** navigasi menjadi menu yang dapat dibuka; konten satu kolom; kontrol dan tombol tetap mudah disentuh.
- **Breakpoint tambahan:** sekitar 950 px untuk menyusun ulang panel kode, dan 1100 px untuk merapatkan tata letak sebelum mode ponsel.
- Gunakan grid dua kolom hanya bila isi tiap kolom tetap terbaca. Tumpuk panel, grafik, dan keterangan ketika ruang menyempit.
- Beri jarak antarbagian yang konsisten; kurangi jarak pada ponsel tanpa membuat konten terasa padat.
- Hindari scroll horizontal pada halaman. Tabel dan blok kode boleh memiliki area gulir horizontal yang terlokalisasi.
- Pastikan navigasi tetap terlihat saat berpindah bagian dan target tautan tidak tertutup header tetap.

## 5. Komponen dan pola visual

- **Navigasi bab:** latar `ink`, label sekunder berkontras cukup, keadaan aktif dibedakan oleh latar/batas, dan progres menggunakan teks serta indikator visual.
- **Hero:** judul editorial, ringkasan singkat, tindakan utama dan sekunder, serta visual peta yang mendukung materi.
- **Kartu/panel:** latar putih, batas `line`, sudut membulat moderat (sekitar 8–13 px), dan padding lapang. Gunakan bayangan secara hemat.
- **Tombol:** tinggi minimum sekitar 44 px, label tindakan spesifik, dan gaya konsisten untuk primer, sekunder, serta aksen.
- **Tab:** keadaan terpilih terlihat jelas dan konten aktif tetap terhubung secara semantik dengan tab.
- **Callout:** latar `pale` dan garis aksen di sisi; gunakan untuk penjelasan penting, bukan untuk setiap paragraf.
- **Accordion:** judul harus menjelaskan isi yang dibuka; pertahankan indikator keadaan dan perilaku keyboard bawaan.
- **Tabel:** gunakan header yang jelas, pemisah baris tipis, angka rata/berformat konsisten, dan caption bila diperlukan.
- **Status dan progres:** tampilkan status dalam teks, bukan hanya melalui perubahan warna.
- **Sudut dan ornamen:** utamakan garis sederhana dan radius kecil-menengah. Hindari efek kaca, gradien dekoratif besar, atau bayangan berat.

## 6. Interaksi dan umpan balik

- Setiap kontrol harus menjelaskan hasil atau konsekuensi tindakannya melalui label, petunjuk, atau umpan balik.
- Beri keadaan interaktif yang berbeda dan konsisten: default, hover, fokus, terpilih, dinonaktifkan, berhasil, dan keliru.
- Perubahan parameter simulasi harus tercermin pada nilai yang terlihat; bedakan hasil sebelum dan sesudah tindakan hitung.
- Saat aktivitas selesai, berikan konfirmasi yang ringkas dan perbarui indikator progres secara transparan.
- Simpan progres lokal hanya bila perilaku itu dijelaskan kepada pengguna; sediakan cara yang jelas untuk mengulang aktivitas bila sesuai.
- Animasi hanya untuk membantu orientasi atau menjelaskan perubahan. Hormati `prefers-reduced-motion` dan jangan menjadikan animasi prasyarat pemahaman.
- Jangan mengganti konten secara diam-diam: perubahan tampilan peta, fitur, atau hasil harus memiliki keterangan yang dapat dipahami.

## 7. Aksesibilitas

- Gunakan elemen HTML semantik, urutan heading yang logis, nama label yang deskriptif, dan teks alternatif/deskripsi untuk visualisasi.
- Semua tindakan harus dapat dilakukan dengan keyboard. Sediakan indikator `:focus-visible` yang jelas dan tidak tertutup.
- Jaga kontras teks sesuai WCAG 2.1 AA sebagai sasaran (4,5:1 untuk teks normal; 3:1 untuk teks besar dan elemen non-teks penting).
- Beri nama aksesibel pada kontrol, tab, tombol peta, grafik, serta indikator progres; gunakan ARIA hanya jika semantik HTML belum cukup.
- Umumkan hasil dinamis atau status simulasi melalui area live yang sesuai, tanpa membanjiri pembaca layar.
- Ukuran target sentuh minimal sekitar 44 × 44 px bila memungkinkan.
- Sediakan tautan lewati navigasi, dukung zoom, dan uji tampilan pada layar kecil.
- Jangan menyampaikan status hanya melalui warna; sertakan teks seperti “BMU”, “jawaban benar”, atau “belum dijalankan”.

## 8. Visualisasi dan materi ilmiah

- Pisahkan dengan tegas **ruang fitur** (kemiripan input/bobot) dan **ruang peta** (jarak topologis neuron); label sumbu dan penjelasan harus menyebut ruang yang sedang ditampilkan.
- Untuk hit map, U-matrix, dan component plane, tampilkan nama tampilan, legenda/skala, satuan atau makna nilai, serta detail sel terpilih.
- Gunakan label yang konsisten untuk BMU, neuron, baris/kolom, fitur, QE, dan TE. Jelaskan singkatan pada pemakaian pertama.
- Bedakan data contoh, hasil simulasi, dan interpretasi. Jangan menyebut klaster sebagai kelas yang diketahui tanpa bukti/validasi.
- Jika grafik memiliki angka penting, sediakan tabel atau teks alternatif agar hasil tidak hanya bergantung pada gambar.
- Gunakan data warna berurutan untuk besaran numerik kontinu dan palet kualitatif hanya untuk kategori.

## 9. Bahasa dan konten

- Gunakan bahasa Indonesia yang lugas, suportif, dan akurat secara teknis.
- Satu komponen atau bagian sebaiknya memiliki satu tujuan belajar yang jelas.
- Jelaskan istilah teknis pada konteksnya; pertahankan notasi matematika secara konsisten.
- Tombol menggunakan kata kerja, misalnya “Jalankan update”, “Buka penjelasan”, atau “Ulangi kuis”.
- Hindari klaim berlebihan, instruksi yang ambigu, dan teks placeholder pada antarmuka final.
- Cantumkan sumber untuk materi, angka, atau contoh yang perlu diverifikasi.

## 10. Checklist sebelum rilis

- [ ] Palet, tipografi, jarak, dan gaya komponen konsisten dengan panduan ini.
- [ ] Tata letak diuji pada desktop, tablet, dan ponsel; tidak ada overflow halaman.
- [ ] Navigasi dan seluruh kontrol dapat digunakan dengan keyboard serta memiliki fokus yang terlihat.
- [ ] Kontras, label aksesibel, status dinamis, dan deskripsi visualisasi sudah diperiksa.
- [ ] Setiap grafik memiliki legenda dan interpretasi; warna bukan satu-satunya pembawa makna.
- [ ] Simulasi, status aktivitas, dan progres memberi umpan balik yang jelas.
- [ ] Gerakan dikurangi bila pengguna memilih `prefers-reduced-motion`.
- [ ] Istilah, notasi, bahasa, dan sumber materi konsisten.
