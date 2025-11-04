## Penerapan Sistem CRUD dengan Pemanfaatan CSV dan Konsep Persistence
Pada praktikum ke 11 ini merupakan penerapan sistem CRUD berbasis Java yang memanfaatkan konsep persistence dan file CSV sebagai sumber data. Praktikum ini bertujuan untuk memahami cara pengelolaan data secara berkelanjutan menggunakan Java Persistence API (JPA) tanpa bergantung pada database eksternal. Melalui antarmuka Java Swing, pengguna dapat menambah, mengubah, dan menghapus data yang diimpor dari file CSV serta menyimpannya secara persisten menggunakan Entity dan EntityManager.

## Persistence
Persistence adalah kemampuan suatu aplikasi untuk menyimpan data secara berkelanjutan (permanent storage) agar data tidak hilang ketika program dihentikan atau dijalankan kembali. Konsep ini berfungsi sebagai penghubung antara objek di memori dan penyimpanan permanen, sehingga data tidak hanya bersifat sementara di RAM. Penerapan persistence memungkinkan program menyimpan data secara otomatis, mengurangi kesalahan manual, dan mempermudah pengambilan data di kemudian hari.

## Java Persistence API (JPA)
Java Persistence API (JPA) adalah standar API yang disediakan oleh Java untuk mengatur proses penyimpanan, pengambilan, dan pengelolaan data secara object-relational mapping (ORM). Dengan JPA, pengembang dapat menyimpan dan memanipulasi data tanpa perlu menulis SQL secara manual. Didukung oleh provider seperti Hibernate atau EclipseLink, JPA menawarkan kemudahan dalam pengelolaan data, relasi antar objek, serta transaksi yang aman melalui komponen utama seperti EntityManager dan persistence unit.

## Entity dan Anotasi dalam JPA
Entity merupakan class Java yang berfungsi mewakili suatu tabel penyimpanan data. Setiap objek dari class entity merepresentasikan satu baris data dalam tabel tersebut. Agar class dikenali sebagai entity oleh JPA, class tersebut harus diberi anotasi @Entity.
Beberapa anotasi penting yang digunakan dalam entity, yaitu :

@Entity → Menandakan bahwa class merupakan entity yang akan dikelola oleh JPA.
@Table(name = "nama_tabel") → Menentukan nama tabel penyimpanan data.
@Id → Menunjukkan atribut yang menjadi primary key atau identitas unik data.
@Column(name = "nama_kolom") → Menentukan nama kolom yang sesuai di tabel penyimpanan.
@NamedQuery → Mendefinisikan query tetap (predefined query) agar mudah dipanggil kembali.
Penggunaan anotasi tersebut, membuat pengelolaan data lebih mudah dan terstruktur karena setiap atribut class terhubung langsung dengan kolom penyimpanan.

## Entity Manager dan Persistence Unit
EntityManager adalah komponen inti JPA yang bertugas mengelola siklus hidup objek entity, termasuk menyimpan, memperbarui, mencari, dan menghapus data. EntityManager bekerja berdasarkan konfigurasi yang didefinisikan dalam persistence.xml, yaitu file yang berisi informasi persistence unit (nama unit, provider JPA, dan konfigurasi koneksi).
Beberapa fungsi utama EntityManager, antara lain:

persist() → Menyimpan data baru ke dalam penyimpanan.
find() → Mengambil data berdasarkan primary key.
merge() → Memperbarui data yang sudah ada.
remove() → Menghapus data dari penyimpanan.
createQuery() / createNamedQuery() → Menjalankan query berbasis JPQL (Java Persistence Query Language).
Persistence unit berfungsi sebagai wadah konfigurasi yang memungkinkan EntityManager mengenali media penyimpanan yang digunakan. Dalam praktikum ini, meskipun tidak menggunakan MySQL, konsep persistence tetap diterapkan untuk menyimpan data secara terstruktur melalui file atau memori lokal.
