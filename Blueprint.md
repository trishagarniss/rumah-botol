**📘 BLUEPRINT DESAIN UI FINAL: RUMAH BOTOL RT 03**

**Versi: 1.4** 

**Target: Android Native (XML Layout), Offline-First + Firestore Sync**



**Latar Belakang:**

**Sampah botol plastik sulit terurai dan mencemari lingkungan, namun memiliki nilai ekonomis jika dikelola. Karang Taruna memfasilitasi pengumpulan dan pengelolaan botol untuk memberdayakan masyarakat dan pemuda.**



**Tujuan:**

**Mengurangi sampah botol plastik.**

**Meningkatkan kesadaran pengelolaan sampah.**

**Memberdayakan pemuda Karang Taruna.**

**Menambah kas Karang Taruna dan tabungan warga.**

**Mendorong ekonomi kreatif berbasis lingkungan.**



**Sasaran:**

**Warga desa/kelurahan, anggota Karang Taruna, anak-anak dan remaja.**



**Bentuk Kegiatan:**

**Pengumpulan botol plastik bekas.**

**Penimbangan dan pencatatan botol.**

**Penukaran botol menjadi uang, tabungan, atau poin hadiah.**

**Penjualan botol ke pengepul atau untuk daur ulang.**



**Mekanisme Pelaksanaan:**

**Warga mengumpulkan botol di rumah masing-masing.**

**Botol disetor ke Bank Botol sesuai jadwal.**

**Petugas Karang Taruna menimbang dan mencatat botol.**

**Botol disimpan sementara, kemudian dijual ke pengepul.**

**Hasil penjualan: sebagian untuk tabungan warga, sebagian untuk kas Karang Taruna.**



**Waktu \& Tempat:**

**1–2 kali dalam sebulan**

**Sekretariat Karang Taruna**



**Output yang Diharapkan:**

**Lingkungan lebih bersih dan berkurangnya sampah plastik.**

**Bertambahnya kas Karang Taruna.**

**Terbentuknya kebiasaan memilah sampah di masyarakat.**





**1. 🎨 DESIGN SYSTEM \& STYLE GUIDE**

A. Palet Warna Utama (Brand Identity)

* Primary Color (#2E7D32 - Hijau Botol): Warna identitas utama. Digunakan untuk Toolbar (Header), Tombol Utama (Simpan/Login), dan Checkbox aktif.
* Primary Variant (#1B5E20 - Hijau Gelap): Khusus untuk warna Status Bar HP (area sinyal/baterai) agar terlihat kontras dan rapi.
* Secondary Color (#F9A825 - Kuning Emas): Warna aksen untuk menarik perhatian. Digunakan pada Floating Action Button (FAB), Highlight Angka Saldo, dan Ikon Uang.
* On Primary (#FFFFFF - Putih): Warna khusus untuk Teks atau Ikon yang berada di atas tombol hijau atau toolbar hijau agar terbaca jelas.



B. Warna Latar \& Permukaan (Backgrounds)

* Background Page (#F5F5F5 - Abu Sangat Muda): Latar belakang layar utama (di belakang kartu) supaya mata tidak cepat lelah menatap layar putih penuh.
* Surface Card (#FFFFFF - Putih Bersih): Warna dasar untuk komponen CardView, Dialog Pop-up, dan Bottom Sheet.
* Surface Highlight (#E8F5E9 - Hijau Pudar): Background dekoratif untuk item list yang sedang dipilih atau bagian header profil.



C. Warna Teks (Typography)

* Text Primary (#212121 - Abu Gelap PeKAT): Digunakan untuk informasi paling penting seperti Judul Halaman, Nama Warga, dan Angka Saldo Besar.
* Text Secondary (#757575 - Abu Sedang): Digunakan untuk informasi pendukung seperti Label Form, Tanggal, Sub-judul ("Halo, Admin"), dan Nomor Rumah.
* Text Hint (#BDBDBD - Abu Terang): Digunakan untuk placeholder input (bayangan teks sebelum diketik, misal: "Masukkan berat...").



D. Warna Status (Logic \& Feedback)

* Status Success (#43A047 - Hijau Cerah): Menandakan kondisi positif, seperti status "Sudah Cair", "Harga Deal", atau Ikon Ceklis.
* Status Pending (#FF9800 - Oranye): Menandakan proses menunggu, seperti status "Menunggu Harga", "Belum Dijual", atau Badge Pending.
* Status Error (#D32F2F - Merah): Menandakan bahaya atau aksi destruktif, seperti Validasi Error, Tombol Hapus/Logout, dan Status Gagal.
* Status Locked (#9E9E9E - Abu Mati): Menandakan elemen non-aktif, seperti tombol "Cairkan" yang belum waktunya terbuka (Disable) atau ikon Gembok.



E. Styling Komponen (Bentuk \& Ukuran)

* CardView (Kartu Data): Menggunakan sudut melengkung (Corner Radius 12dp) dan bayangan tipis (Elevation 2dp). Jarak antar kartu (Margin 8dp) dan jarak teks ke tepi kartu (Padding 16dp).
* Tombol (Button): Tinggi tombol standar 48dp (aman untuk sentuhan jempol), dengan sudut sedikit melengkung (Radius 8dp).
* Input Form (EditText): Menggunakan gaya OutlinedBox (kotak bergaris tepi). Garis berwarna abu-abu saat diam, dan berubah menjadi Hijau Primary saat diketik.
* Typography (Font Roboto):

&nbsp;- Headline (24sp Bold): Angka Saldo Besar.

&nbsp;- Title (20sp Medium): Judul Halaman / Toolbar.

&nbsp;- Subtitle (16sp Medium): Nama Warga di List.

&nbsp;- Body (14sp Regular): Teks isi standar.

&nbsp;- Caption (12sp Regular): Tanggal atau label kecil.



**2. 🧭 STRUKTUR NAVIGASI**

🟢 Role PJ (Petugas Lapangan)

Format: Bottom Navigation + Docked FAB

Menu:

* 🏠 Beranda (Dashboard)
* 📋 Riwayat (List input)
* ➕ Input Trashbag (FAB Tengah)
* 💸 Pencairan (Tabungan \& Serah Terima, Multiple Select)
* 👤 Profil (Akun PJ)



🔴 Role Admin

Format: Navigation Drawer (Side Bar)

Menu:

* 📊 Dashboard
* ⚖️ Kelola Penjualan (Input Harga Asongan)
* 💰 Monitoring Pencairan
* 🏘️ Data Warga
* 👮 Data Petugas
* ⚙️ Pengaturan
* 🚪 Logout





3\. 📐 UI DETAIL PER LAYAR

A. PJ – Petugas Lapangan

1\. 🏠 Dashboard PJ

* Header: "Halo, \[Nama PJ]" + Tanggal.
* Card Status Gudang: Total Kg Bulan Ini. Badge Status: Pending (Kuning) atau Terjual (Hijau).
* List Terakhir: 3 input terakhir (Nama - Berat).



2\. ➕ Input Trashbag

* Metode Input:

&nbsp;- Dropdown Manual: Cari "A1 - Pak Budi".

&nbsp;- Tombol Scan QR: Scan QR Code di trashbag warga (Solusi Gap UX).

* Input Berat: EditText (Kg).
* ✨ Logika "Upsert" (Anti-Double Input):

&nbsp;- Saat PJ pilih warga, sistem cek lokal: "Apakah hari ini rumah ini sudah diinput?"

&nbsp;- Jika Ya: Muncul Dialog ⚠️ "Data 3kg sudah ada hari ini. Timpa data lama?"

&nbsp;- Pilihan: "Batal" atau "Timpa Baru". (Data hari yang sama dilarang dijumlah/increment, harus ditimpa/update).



3\. 📋 Riwayat Input

* List Card: Tanggal | Nama | Berat | Status.
* ✨ Logika Lock Edit (Integritas Data):

&nbsp;- Tombol Edit/Hapus (ikon pensil/sampah) HANYA MUNCUL jika status = Pending.

&nbsp;- Jika Admin sudah input harga (Status = Terjual/Rp), tombol Edit HILANG/MATI. PJ dilarang ubah data yang sudah jadi uang.



4\. 💸 Fragment Pencairan PJ – Dynamic Unlock

* List Warga: Checkbox (Multiple Select) | Nama \& Saldo | Tombol Cair (Satuan).
* Bottom Selection Bar: Muncul saat checkbox dicentang -> Tombol "Cairkan Sekaligus".
* Logika Unlock Dinamis:

&nbsp;- Tombol "Cairkan" hanya aktif (Hijau) jika: Hari Ini >= Tanggal Periode Admin ATAU Force Open = True.



5\. 👤 Profil PJ

Header hijau: avatar, nama, role, UID/Email

Menu pengaturan: ganti password, panduan aplikasi

Tombol Logout: hapus sesi login, kembali ke halaman login



B. Admin

1\. 📊 Dashboard Admin

* Card Gudang: Stok Kg belum dijual (Realtime dari input PJ).
* Card Keuangan: Kas RT \& Dana Warga (Akumulasi).
* Grafik Tren.



2\. ⚖️ Kelola Penjualan 

* Filter Transaksi: Bukan lagi "Pilih Bulan", tapi "Pilih Rentang Tanggal" (Start Date - End Date) atau tombol praktis "Pilih Semua Stok Pending".
* Info Box:

"Total Berat Terpilih: 540 Kg" (Akumulasi dari input berbulan-bulan).

"Periode Input: 1 Jan 2026 - 15 Apr 2026".

* Input Harga: Harga Deal Asongan (Rp).
* Tombol Proses: Kunci data \& bagikan saldo.



3\. 💰 Monitoring Pencairan (✨ FITUR UPDATE: Laporan Fisik \& Bendahara)

A. Header Info (Dashboard Keuangan)

* Card Besar: "Total Dana Siap Cair: Rp \[Total]".

&nbsp;- Fungsi: Angka acuan bagi Admin untuk lapor dan mengajukan pengambilan uang tunai kepada Bendahara Karang Taruna.

* List Status: Rekap status per warga (Hijau: Sudah Cair, Merah: Belum).



B. ✨ Fitur Export Laporan (Dual Format - Gap Administrasi) Saat tombol "📄 EXPORT PDF" ditekan, muncul pilihan 2 Format Laporan:

1. Format Ringkasan Kinerja (Untuk Dibacakan di Rapat Karang Taruna/RT)

* Tujuan: Bahan presentasi kinerja Bank Sampah oleh Pengurus Karang Taruna ke warga atau Pembina.
* Isi Laporan:

1. Total Sampah Terkumpul (Kg).
2. Total Uang Penjualan/Omset (Rp).
3. Pemasukan Kas Karang Taruna (10%) -> Highlight Utama (Dana Operasional KT).
4. Total Tabungan yang Dibagikan ke Warga.
5. Top 3 Warga Teladan (Opsional).

* Output: 1 Halaman surat resmi, font besar, mudah dibaca.

2\. Format Lampiran Tanda Terima (Untuk Bendahara KT \& PJ)

* Tujuan: Bukti fisik pengeluaran uang kas Karang Taruna (SPJ) dan arsip tanda tangan.
* Isi Laporan: Tabel detail dengan kolom:

1. No. Rumah (Diurutkan sesuai Rute Jalan Kaki / Letter O).
2. Nama Kepala Keluarga (KK).
3. Jumlah Saldo Diterima (Rp).
4. Kolom tanda Tangan (Kosong, siap diisi).

* Output: Tabel data lengkap, disertai kolom tanda tangan Bendahara Karang Taruna \& PJ di bawahnya.



4\. 🏘️ Data Warga (per KK)

Konsep Data:

* Lingkup: Satu entitas data mewakili Satu Rumah / Satu Kepala Keluarga (KK).
* Identifikasi: Nomor Rumah.



List Warga (UI):

* Tampilan: Nomor Rumah (Besar/Jelas), Nama KK, Saldo Terkini.
* Urutan List: Disusun urut dari Start Point (Awal Gang) -> Memutar (Loop) -> End Point.
* Implementasi: Saat input data warga pertama kali (Create), Admin sebaiknya menginput urut sesuai rumah yang jejer. Atau, penomoran rumah di database (ID) disesuaikan dengan urutan jalan (misal: Rumah\_01 adalah rumah pertama di rute, bukan rumah nomor 1 jika posisinya di tengah).



Detail Warga:

* Info lengkap riwayat transaksi.
* ✨ Tombol Baru: "🔲 LIHAT QR CODE".
* Fungsi: Menampilkan QR Code house\_id. Admin print \& tempel di trashbag. Ini sangat membantu di layout Letter O agar PJ tidak bingung membedakan trashbag rumah "depan" vs "belakang" yang posisinya berdekatan.



5\. Data Petugas

List petugas dengan: foto, nama, email, switch aktif/nonaktif

Menu opsi tiap petugas: edit profil, reset password, hapus akun

FAB untuk tambah PJ baru

Visualisasi switch: hijau = aktif, abu = nonaktif



6\. ⚙️ Pengaturan (Logika Dinamis \& Aman)

Konfigurasi Keuangan:

* Input: Persentase Kas Kartar (Slider / Input Number, misal: 10%).
* Input: Bulan Pencairan (Multi-select / Spinner, misal: Juni \& Desember).

Logika "Apply" (PENTING - Sesuai Gap Integritas Data):

* Tombol Simpan: Saat Admin mengubah persentase kas (misal dari 10% ke 15%), perubahan ini HANYA BERLAKU untuk:

&nbsp;  1. Transaksi baru di masa depan.

&nbsp;  2. Transaksi yang masih berstatus Pending (Belum dijual ke asongan).

* Snapshot Historis: Data riwayat yang sudah berstatus "Terjual" atau "Sudah Cair" (masa lalu) TIDAK AKAN BERUBAH. Ini menjaga agar laporan keuangan tahun lalu tetap akurat sesuai aturan saat itu.

Info Card:

* "Perubahan persentase hanya berlaku untuk penjualan berikutnya. Data historis aman."
* "Tombol Pencairan di HP PJ akan aktif otomatis pada bulan yang dipilih."



7\. Visualisasi Tambahan

Gunakan warna kontras untuk highlight: hijau, kuning, abu

Gunakan ikon sederhana untuk status / info

Semua angka penting dibuat besar agar langsung terlihat

LineChart untuk tren 6 bulan, Card/Box untuk status \& saldo, progress bar atau chip untuk status cepat

catatan dan fitur tambahan:
QR Scan Trashbag → auto load rumah (backup dropdown manual)

Offline-first, auto sync Firestore saat online

CRUD Data: Admin full, PJ terbatas input sendiri

1\. "Zero State" (Tampilan Kosong)

Masalah: Saat aplikasi baru diinstall, halaman Riwayat dan Dashboard akan kosong melompong (putih). Ini terlihat seperti "Error" atau "Bug".

Saran: Tambahkan tampilan jika data kosong.

Contoh: Gambar vektor kardus kosong + Teks: "Belum ada sampah yang disetor. Yuk input sekarang!"



2\. Indikator Sync (Offline ke Online)

Masalah: Karena ini Offline-first, PJ perlu tahu apakah datanya sudah aman terkirim ke server atau masih di HP doang.

Saran: Tambahkan ikon kecil di pojok atas (Toolbar).

☁️ Awan Ceklis: Data aman (Synced).

🔄 Putar-putar: Sedang mengirim.

⚠️ Awan Silang: Offline (Data tersimpan di HP).



3\. Input Keyboard (Desimal)

Masalah: Sering lupa setting tipe keyboard, jadi pas PJ mau input "2.5 Kg", keyboard yang muncul huruf (abc), harus ganti angka dulu. Ribet.

Saran: Di XML EditText berat, pastikan pakai android:inputType="numberDecimal". Biar begitu diklik, langsung muncul angka dan titik.



💡 MEKANISME PERHITUNGAN DINAMIS (REVISI FLEKSIBEL)

1\. Fase Pengumpulan (Durasi Bebas)

* PJ terus input berat botol hari demi hari.
* Status semua transaksi: PENDING (Weight Only).
* Rupiah: 0 / Hidden.
* Tidak peduli ini bulan Januari, Maret, atau Desember, datanya numpuk terus di "Gudang Digital" (Pending).



2\. Fase Penjualan (Saat Asongan Datang)

* Misal: Setelah 4 bulan (Jan-April) numpuk, akhirnya dijual.
* Admin buka menu Kelola Penjualan.
* Filter Tanggal: Admin pilih rentang transaksi yang mau dijual.
* Contoh: "Ambil semua data Pending dari 1 Jan s/d 30 April".
* Input Harga: Masukkan harga deal hari itu (misal Rp 4.000).
* Eksekusi: Klik "PROSES".
* Hasil: Semua data dari Jan-April berubah status jadi TERJUAL, dan saldonya masuk ke warga. Data setelah tanggal 30 April (kalau ada) tetap Pending.



3\. Input Selanjutnya

* Besoknya PJ input lagi.
* Status kembali ke PENDING.
* Menunggu sesi penjualan asongan berikutnya (entah kapan, terserah Admin).
  



Tambahan fitur:
1. Fitur "Batal Cair" (Undo Withdrawal) - Khusus Admin

Masalah: Bagaimana jika PJ jempolnya kepeleset? Niatnya mau mencairkan dana Pak Budi (No. 05), tapi malah kepencet Pak Badu (No. 06).

Di HP PJ, status Pak Badu langsung berubah jadi "Hijau/Sudah Cair". PJ panik karena uangnya belum dikasih, tapi di sistem sudah lunas.

Solusi: Di menu Monitoring Pencairan (Admin), saat Admin klik detail warga yang sudah cair, beri tombol kecil "BATALKAN STATUS CAIR".

Logic: Mengubah status kembali menjadi "Belum Cair" agar muncul lagi di list tagihan PJ.



2\. Log Riwayat Penjualan (History Log)

Masalah: Warga bertanya, "Pak Admin, penjualan bulan Maret lalu itu harganya deal berapa ya? Kok saya dapat segini?"

Solusi: Di menu Kelola Penjualan, tambahkan tab/tombol "Riwayat Penjualan".

Isi: List sederhana berisi: \[Tanggal Proses | Periode Data | Harga Deal | Total Berat Terjual].

Fungsi: Transparansi jika ada audit atau pertanyaan warga di kemudian hari.


