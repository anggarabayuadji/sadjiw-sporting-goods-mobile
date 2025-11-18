# sadjiw_sporting_goods

A new Flutter project.

## Tugas 7 (Pertanyaan)

**1.  Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.**

Widget tree adalah struktur yang menggambarkan bagaimana suatu widget tersusun di suatu tampilan aplikasi. Setiap elemen yang akan ditampilkan termasuk ke dalam bagian dari sebuah widget tree. Hubungan parent-child terjadi ketika sebuah widget (parent) memiliki widget lagi di dalamnya (child). Sebuah child widget akan mengikuti aturan yang telah ditentukan dalam parent widgetnya.

**2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.**

| **Widget**     | **Fungsi** |
|----------------|-------------|
| **MaterialApp** | Root aplikasi yang mengatur tema, navigasi, dan settingan awal. |
| **Scaffold** | Menyediakan struktur halaman dengan AppBar, body, dan elemen utama lainnya. |
| **AppBar** | Menampilkan judul di bagian atas. |
| **Padding** | Mengatur jarak di sekitar widget. |
| **Column** | Menyusun widget secara vertikal. |
| **Row** | Menyusun widget secara horizontal. |
| **Card** | Menampilkan informasi dengan bentuk seperti kartu. |
| **Container** | Untuk menyimpan pengaturan ukuran, warna, dan padding sebuah widget. |
| **Text** | Menampilkan teks. |
| **Icon** | Menampilkan ikon yang disediakan oleh Flutter. |
| **InkWell** | Menambahkan efek ketika widget diklik. |
| **Material** | Memberikan tampilan sesuai gaya Material Design. |
| **SnackBar** | Menampilkan pesan sementara di bagian bawah layar ketika ada aksi dari user. |
| **Center** | Meletakkan widget di tengah. |
| **SizedBox** | Memberi jarak konsisten antar widget. |


**3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.**

Berguna sebagai wadah untuk mengatur konfigurasi dasar aplikasi Flutter berbasis Material Design seperti tempa warna, font, navigasi halaman, dll. Widget ini sering digunakan sebagai root karena menyediakan fitur-fitur widget lainnya seperti Scaffold, AppBar, SnackBar. Hal itu memastikan aplikasi yang kita buat bisa memastikan UI aplikasi flutter kita tampil secara konsisten dalam satu sistem desain.

**4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?**

Stateless widget adalah widget yang tidak bergantung pada perubahan data untuk menampilkan sesuatu. Hal itu mengartikan bahwa tampilannya bersifat statis dan tidak akan berganti-ganti lagi. Sedangkan StatefulWdiget adalah kebalikannya, sehingga dapat dibilang bahwa widget ini bergantuk pada perubahan data atau bersifat dinamis.

Stateless widget digunakan ketika kita tidak perlu mengganti-gantinya lagi di masa mendatang. StatefulWidget digunakan ketika perlu ada perubahan tampilan tergantung terhadap interaksi dari user.

**5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?**

BuildContext adalah objek yang menunjukkan posisi suatu widget di dalam widget tree. Hal ini penting karena memungkinkan widget untuk berinteraksi dengan widget lain di atasnya, seperti untuk mengakses tema, navigator, atau menampilkan SnackBar. Dalam metode build, BuildContext digunakan untuk mengetahui hubungan hierarki antar widget dan memastikan tampilan dibangun sesuai struktur yang benar.

**6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".**

Hot reload merupakan fitur yang memnugkinkan perubahan kode terlihat langsung tanpa kehilangan state aplikasi yang berjalan. Hal itu bisa mempercepat proses pengembangan. Sedangkan hot restart akan mengulang seluruh aplikasi dari awal dan menghapus semua state yang sudah ada. 

---
## Tugas 8 (Pertanyaan)

**1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?**

`Navigator.push()` digunakan untuk pindah ke halaman baru tanpa menutup halaman sebelumnya. Hal itu memungkinkan user untuk bisa menekan tombol back. Sedangkan `Navigator.psuhReplacement()` akan menggntikan halaman sekarang dengan halaman baru sehingga user tidak bisa tekan back karena sudah terhapus dari stack. Di aplikasi saya sebaiknya `navigator.push()` digunakan untuk berpindah ke halaman detail produk dan `navigator.pushReplacement()` cocok digunakan untuk pindah dari halaman login ke halaman utama.

**2. Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?**

Saya menggunakan Scaffold untuk kerangka utamanya. AppBar digunakan untuk membuat judulhalaman agar terus konsisten. Drawer digunakan untuk membuat navbar di samping agar user bisa berpindah-pindah halaman. Dengan semua hal itu, tampilan dari aplikasi menjadi lebih stabil, konsisten, dan nyaman dipandang.

**3. Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.**

Padding membuat tampilan lebih rapi dan tidak berdempet. SingleChildScrollView berguna agar form bisa discroll jika isinya banyak, terutama di layar kecil. ListView cocok untuk menampilkan banyak elemen form atau list produk secara vertikal. Di aplikasi saya, halaman form produk menggunakan Padding di tiap input dan diwrap SingleChildScrollView agar bisa digeser ke bawah tanpa overflow.

**4. Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?**

Saya menggunakan colorscheme diparent widget MaterialAppnya, sehingga seluruh halaman bisa konsisten menggunkaan warna yang sama

## Tugas 9 (Pertanyaan)

**1. Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?**

Perlu membuat model Dart saat mengambil atau mengirim data JSON karena model memberikan struktur yang jelas, sehingga setiap field punya tipe data yang pasti dan null-safety. Dengan menggunakan mode, maka kesalahan seperti salah tipe (misal yang seharusnya string jadi integer) bisa terdeteksi lebih awal saat compile, bukan saat runtime. Jika kita langsung bekerja dengan Map<String, dynamic> tanpa model, maka tidak ada validasi tipe, field bisa salah nama tanpa ketahuan, nilai bisa null tanpa disadari, dan kode menjadi lebih sulit dirawat serta mudah menimbulkan bug yang sulit dilacak. Model membuat aplikasi lebih konsisten, aman, mudah dibaca, dan lebih mudah dikembangkan dalam jangka panjang.

**2. Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest. **

Package http berfungsi untuk melakukan permintaan HTTP biasa seperti GET atau POST ke endpoint Django yang tidak memerlukan autentikasi, karena package ini tidak menyimpan cookie atau session.

CookieRequest digunakan untuk kebutuhan autentikasi, seperti login, register, logout, dan akses endpoint yang membutuhkan status pengguna login. CookieRequest secara otomatis menyimpan dan mengirim session cookie Django, sehingga Flutter dapat mempertahankan sesi login di setiap request berikutnya. Sehingga bisa dibilang, http digunakan untuk request publik, sedangkan CookieRequest digunakan untuk request yang memerlukan identitas dan sesi pengguna.

**3. Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.**

Instance CookieRequest perlu dibagikan ke semua komponen Flutter karena objek ini menyimpan informasi sesi login, termasuk session cookie yang dibutuhkan untuk mengakses endpoint Django yang memerlukan autentikasi. Jika setiap halaman membuat instance CookieRequest baru, maka session tidak akan terbawa dan pengguna dianggap selalu “belum login”. Dengan membagikan satu instance yang sama (melalui Provider), seluruh halaman dapat mengakses status login, data pengguna, dan melakukan request terautentikasi secara konsisten.

**4. Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?
**

Agar Flutter dapat berkomunikasi dengan Django, beberapa konfigurasi konektivitas harus disiapkan terlebih dahulu. Menambahkan 10.0.2.2 ke ALLOWED_HOSTS penting karena emulator Android tidak bisa mengakses localhost secara langsung dan membutuhkan alamat khusus itu untuk menjangkau server Django di komputer host. CORS harus diaktifkan, karena Flutter dan Django berada di origin yang berbeda, sehingga Django perlu diberi izin untuk menerima permintaan dari aplikasi Flutter. Selain itu, pengaturan SameSite/cookie perlu disesuaikan agar session cookie dapat ikut terkirim dalam setiap request, terutama untuk fitur login. Di sisi Flutter, kita juga harus menambahkan izin akses internet di AndroidManifest.xml, kalau tidak aplikasi tidak dapat mengirim request apa pun.

Jika konfigurasi-konfigurasi ini tidak dilakukan dengan benar, Flutter akan gagal terhubung dengan Django. Request bisa diblokir oleh Django karena host tidak diizinkan, ditolak oleh CORS, cookie login tidak terkirim sehingga pengguna dianggap tidak autentikasi, atau aplikasi Android tidak bisa mengakses internet sama sekali. Akibatnya, fitur seperti login, fetch data, dan submit form tidak akan berfungsi.

**5. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.**

Mekanisme pengiriman data dari Flutter ke Django dimulai ketika pengguna mengisi input pada Flutter, lalu data tersebut dikemas menjadi JSON dan dikirim melalui request HTTP atau CookieRequest menuju endpoint Django. Django menerima request tersebut, memprosesnya (misalnya menyimpan ke database atau menghasilkan respons), lalu mengembalikan data JSON ke Flutter. Setelah Flutter menerima respons JSON, data tersebut diubah menjadi model Dart agar memiliki struktur dan tipe yang jelas. Model tersebut yang kemudian digunakan oleh widget untuk menampilkan data secara rapi dan aman di antarmuka aplikasi.

**6. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.**

Autentikasi dimulai saat Flutter mengirim data login/registrasi ke Django melalui CookieRequest. Django memverifikasi atau membuat akun, lalu mengembalikan cookie sesi jika berhasil. Cookie ini disimpan oleh Flutter sehingga request selanjutnya dianggap sudah login. Setelah itu Flutter menampilkan menu utama. Saat logout, Flutter memanggil endpoint logout Django, sesi dihapus, dan cookie dibersihkan sehingga pengguna kembali tidak login.

