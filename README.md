# SIG-Teori-Modul9-WorkingwithWMSData

## Data 

1. Kunjungi [Global Grid of Probability of Urban Expansion](https://sedac.ciesin.columbia.edu/data/set/lulc-global-grid-prob-urban-expansion-2030) oleh SEDAC , data ini berisi prakiraan probabilistik perubahan tutupan lahan perkotaan global dari tahun 2000 hingga 2030 dengan resolusi 2,5 menit busur. Klik Layanan Peta .
2. Copy the WMS service URL. This is the URL to the WMS service which hosts the data layer.

## Prosedur

1. Buka QGIS dan klik Buka Pengelola Sumber Data .
2. Di kotak dialog Pengelola Sumber Data alihkan ke WMS/WMTS , klik Baru .
3. Di kotak dialog Buat Koneksi WMS/WMTS Baru di bawah Detail Koneksi , masukkan Nama sebagai SEDAC, dan tempel URL yang disalin di kotak teks URL . Klik Oke . Jika Anda mendapatkan kesalahan dengan URL yang disalin, coba dengan URL alternatif https://sedac.ciesin.columbia.edu/geoserver/ows.

----------------------------------

Catatan :

Anda membuat koneksi baru ke layanan WMS - bukan lapisan tertentu. Layanan tunggal biasanya menawarkan beberapa lapisan yang dapat ditambahkan ke proyek Anda.

---------------------------------

4. Sekarang di kotak dialog Pengelola Sumber Data , klik Sambungkan . Semua lapisan yang tersedia akan dimuat. Anda akan melihat ID berbeda yang tercantum di sebelah lapisan. ID 0berarti Anda mendapatkan peta dari semua lapisan. Jika Anda tidak menginginkan semua lapisan, Anda dapat memperluas daftar dengan mengeklik ikon ▸ dan memilih lapisan yang diinginkan.
5. Untuk tutorial ini, kami tertarik pada lapisan tertentu. Telusuri . Pilih versi default dari lapisan perluasan kota 2030.Probabilities of Urban Expansion to 2030.
6. Di bagian Pengkodean Gambar , Anda harus memilih format gambar. Format gambar itu penting, dan tergantung pada kasus penggunaan. Berdasarkan perspektif pengguna, berikut adalah beberapa petunjuk,

- Kualitas : Kompresi file untuk PNG adalah lossless, untuk JPEG ini adalah kompresi lossy dan TIFF dapat berupa keduanya. Itu berarti kualitas PNG akan lebih baik dibandingkan dengan JPEG. Jika tujuan utama Anda adalah mencetak peta, gunakan PNG.

- Kecepatan : Karena gambar PNG tidak dikompresi dan ukurannya lebih besar, gambar tersebut akan membutuhkan waktu lebih lama untuk dimuat. Jika Anda menggunakan lapisan dalam proyek Anda sebagai lapisan referensi dan perlu sering memperbesar/menggeser, gunakan JPEG.

- Dukungan Klien : QGIS mendukung sebagian besar format, tetapi jika Anda sedang mengembangkan aplikasi web, browser biasanya tidak mendukung TIFF, jadi Anda harus memilih format lain.

- Jenis data : Jika lapisan Anda terutama vektor, PNG akan memberikan hasil yang lebih baik. Untuk lapisan citra, JPEG biasanya merupakan pilihan yang lebih baik.

Untuk tutorial ini, pilih PNG sebagai formatnya. Ubah nama Layer jika Anda mau dan klik Add .

7.Sekarang lapisan Probabilitas Ekspansi Perkotaan hingga 2030 akan dimuat di kanvas. Gunakan alat Zoom/Pan untuk menjelajahi lapisan. Cara kerja layanan WMS adalah setiap kali Anda memperbesar/menggeser, ia mengirimkan koordinat area pandang Anda ke server dan server membuat gambar untuk area pandang tersebut dan mengembalikannya ke klien. Jadi, akan ada beberapa penundaan sebelum Anda melihat gambar untuk area tersebut setelah Anda memperbesar. Oleh karena itu, koneksi internet selalu diperlukan untuk mengakses lapisan ini. 
8. Sekarang, perbesar ke tempat yang diketahui dan klik ikon Identifikasi Fitur di bilah alat.
9. Klik pada piksel apa saja di kanvas, itu akan memunculkan kotak dialog dengan nilai sel. Ini adalah nilai piksel dalam lapisan - yang mewakili kemungkinan bahwa piksel tersebut akan mengalami urbanisasi pada tahun 2030. Karena lapisan tersebut tidak disimpan secara lokal, nilai ini diambil dari penyedia layanan. Anda dapat melihat hasilnya lebih baik dengan memilih Format as HTMLdan View as Tree.

------------------------------

Catatan :

Informasi diambil oleh GetFeatureInfo , ini adalah panggilan standar WMS yang memungkinkan kita untuk mengambil informasi tentang fitur dan cakupan yang ditampilkan di peta. Jika peta terdiri dari berbagai lapisan, dan GetFeatureInfo dapat diinstruksikan untuk mengembalikan beberapa deskripsi fitur, HTML/GeoJSON adalah format file yang biasa digunakan untuk mengambil informasi.

------------------------------

10. Untuk melihat, informasi tambahan tentang layer klik kanan pada layer dan pilih Properties… .
11. Di kotak dialog Properti Lapisan , alihkan ke tab Informasi di sini semua informasi seperti penyedia data , proyeksi , jangkauan dapat ditemukan. Klik OK untuk menutup kotak dialog setelah menjelajah.
12. Di QGIS Browser , cari XYZ Tiles dan klik dan seret OpenStreetMapke kanvas.
13. Klik pada ikon panel Open the Layer Styling dan alihkan ke Transparency .
14. Atur opacity Global ke50 %.
15. Sekarang di kanvas, lapisan Urban dapat dieksplorasi dengan referensi geografis.
16. Untuk mendapatkan lebih banyak akses ke transparansi layer, klik kanan pada layer dan pilih Properties… .
17. Di kotak dialog Properti Lapisan , alihkan ke tab Legenda , di bawah Widget yang tersedia pilih dan klik ikon Tambahkan widget yang dipilih . Klik Oke .Opacity slider.
18. Sekarang widget penggeser akan tersedia untuk mengontrol opacity layer.
19. selesai.
