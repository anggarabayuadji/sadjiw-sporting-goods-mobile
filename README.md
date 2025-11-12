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
