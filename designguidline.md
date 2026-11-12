# Design Guideline — SOM Lab

Panduan ini mendokumentasikan arah visual dan aturan antarmuka untuk SOM Lab, modul pembelajaran interaktif Self-Organizing Maps (SOM) berbahasa Indonesia. Gunakan sebagai acuan saat menambah atau mengubah halaman, komponen, ilustrasi, dan visualisasi.

## 1. Model desain

**Model: editorial learning lab** — perpaduan antara keterbacaan modul akademik dan eksplorasi laboratorium interaktif.

- **Editorial** untuk materi, penjelasan, rumus, studi kasus, dan sumber: tenang, terstruktur, nyaman dibaca.
- **Laboratorium** untuk simulasi dan peta SOM: kontrol terlihat jelas, hasil dapat dibandingkan, dan data dapat dieksplorasi langsung.
- **Karakter:** akademik, ramah, presisi, dan tidak terasa seperti dasbor bisnis.
- **Prioritas:** pemahaman materi dan interpretasi yang benar lebih penting daripada dekorasi. Hindari ornamen yang bersaing dengan data.

## 2. Tema dan palet warna

SOM Lab menyediakan dropdown **Tema** di header halaman dengan pilihan **Terang** dan **Gelap**. Pengguna dapat mengubah pilihan kapan saja; perubahan langsung diterapkan ke seluruh permukaan, kontrol, dan visualisasi. Sebelum pengguna memilih, tema awal mengikuti preferensi sistem (`prefers-color-scheme`). Setelah dipilih, pilihan pengguna menggantikan preferensi sistem dan disimpan di browser agar tetap berlaku pada kunjungan berikutnya. Gunakan elemen `select` native agar dropdown dapat dioperasikan dengan keyboard dan teknologi bantu. Tetapkan `color-scheme` sesuai tema aktif agar kontrol native browser menyesuaikan tampilan. Jika penyimpanan pilihan gagal, tema tetap berubah untuk sesi saat ini dan tampilkan umpan balik.

Gunakan token semantik berikut, bukan menyalin warna literal ke komponen. Nilai tema gelap di bawah adalah sasaran untuk permukaan utama; pengecualian semantik seperti status dan visualisasi dapat memiliki warna khusus.

| Token | Terang | Gelap | Peran |
|---|---|---|---|
| `ink` | `#182645` | `#E7EDF7` | Teks utama |
| `muted` | `#53627A` | `#AAB8CD` | Teks sekunder, keterangan, label, dan sumbu |
| `paper` | `#F5F7FB` | `#101827` | Latar halaman |
| `line` | `#DCE3EF` | `#2C3A50` | Garis pemisah dan batas |
| `teal` | `#087F83` | `#69D6C6` | Aksen utama, tautan penting, progres |
| `pale` | `#E7F5F2` | `#173A3D` | Sorotan lembut dan keadaan terpilih |
| `indigo` | `#4A50B2` | `#A5A9FF` | Aksen sekunder, gunakan seperlunya |
| `focus` | `#B16914` | `#F4BD68` | Cincin fokus keyboard |
| `surface` | `#FFFFFF` | `#182438` | Kartu, panel, dan kontrol |
| `surface-raised` | `#F7F9FC` | `#202D42` | Header tabel, kontrol sekunder, permukaan bertingkat |

Sidebar mempertahankan permukaan navy gelap pada kedua tema agar identitas navigasi stabil. Sesuaikan warna teks di dalamnya secara terpisah dan jaga kontrasnya.

### Aturan penggunaan warna

- Jaga `ink` sebagai warna teks utama dan `muted` untuk informasi sekunder; cek keterbacaan pada kedua tema.
- Gunakan `teal` secara konsisten sebagai aksen. Pada tema gelap, gunakan teal terang untuk teks aksen agar kontrasnya cukup.
- Gunakan `paper`, `surface`, dan `surface-raised` untuk membentuk hierarki latar; jangan memakai putih tetap sebagai latar komponen di tema gelap.
- Gunakan `pale` untuk keadaan aktif dengan warna teks/batas yang juga disesuaikan untuk tema terkait.
- Gunakan warna status tambahan secara semantik: hijau untuk benar/selesai, merah lembut untuk jawaban keliru, dan amber untuk fokus atau peringatan. Definisikan pasangan latar dan teks untuk kedua tema.
- Jangan mengandalkan warna saja untuk menyampaikan makna. Sertakan label, ikon, bentuk, atau teks status.
- Untuk peta nilai, pertahankan skala berurutan yang jelas dan sediakan legenda serta nilai teks. Pastikan teks di atas sel tetap terbaca pada kedua tema.
- Gunakan `prefers-color-scheme` hanya untuk menentukan tema awal sebelum ada pilihan tersimpan. Gunakan atribut tema pada root halaman untuk menerapkan pilihan pengguna secara eksplisit.
- Simpan pilihan tema pengguna secara lokal; jika penyimpanan gagal, tema tetap berubah untuk sesi saat ini dan tampilkan umpan balik yang jelas.

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
- **Dropdown tema:** tempatkan kontrol berlabel “Tema” di header; sediakan opsi “Terang” dan “Gelap” dengan pilihan aktif yang selalu mencerminkan tema halaman.
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
- Pilihan tema harus langsung mengubah keseluruhan halaman, termasuk peta dan kontrol; simpan pilihan secara lokal dan umumkan kegagalan penyimpanan dengan jelas.
- Perubahan parameter simulasi harus tercermin pada nilai yang terlihat; bedakan hasil sebelum dan sesudah tindakan hitung.
- Saat aktivitas selesai, berikan konfirmasi yang ringkas dan perbarui indikator progres secara transparan.
- Simpan progres lokal hanya bila perilaku itu dijelaskan kepada pengguna; sediakan cara yang jelas untuk mengulang aktivitas bila sesuai.
- Animasi hanya untuk membantu orientasi atau menjelaskan perubahan. Hormati `prefers-reduced-motion` dan jangan menjadikan animasi prasyarat pemahaman.
- Jangan mengganti konten secara diam-diam: perubahan tampilan peta, fitur, atau hasil harus memiliki keterangan yang dapat dipahami.

## 7. Aksesibilitas

- Gunakan elemen HTML semantik, urutan heading yang logis, nama label yang deskriptif, dan teks alternatif/deskripsi untuk visualisasi.
- Semua tindakan harus dapat dilakukan dengan keyboard. Sediakan indikator `:focus-visible` yang jelas dan tidak tertutup.
- Jaga kontras teks sesuai WCAG 2.1 AA sebagai sasaran pada **kedua** tema (4,5:1 untuk teks normal; 3:1 untuk teks besar dan elemen non-teks penting).
- Beri nama aksesibel pada kontrol, tab, tombol peta, grafik, serta indikator progres; gunakan ARIA hanya jika semantik HTML belum cukup.
- Beri label yang terhubung ke dropdown tema, pertahankan dukungan keyboard dari elemen `select`, dan tampilkan pesan status bila preferensi tema tidak dapat disimpan.
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
- [ ] Dropdown tema Terang/Gelap dapat digunakan dengan keyboard dan teknologi bantu serta menampilkan pilihan aktif.
- [ ] Tema sistem dipakai sebagai nilai awal; pilihan eksplisit pengguna tersimpan dan tetap berlaku saat halaman dibuka lagi.
- [ ] Latar, teks, batas, grafik, kontrol, dan status terbaca pada kedua tema.
- [ ] Tata letak diuji pada desktop, tablet, dan ponsel; tidak ada overflow halaman.
- [ ] Navigasi dan seluruh kontrol dapat digunakan dengan keyboard serta memiliki fokus yang terlihat.
- [ ] Kontras, label aksesibel, status dinamis, dan deskripsi visualisasi sudah diperiksa.
- [ ] Setiap grafik memiliki legenda dan interpretasi; warna bukan satu-satunya pembawa makna.
- [ ] Simulasi, status aktivitas, dan progres memberi umpan balik yang jelas.
- [ ] Gerakan dikurangi bila pengguna memilih `prefers-reduced-motion`.
- [ ] Istilah, notasi, bahasa, dan sumber materi konsisten.
