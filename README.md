Berikut draf `README.md` yang disesuaikan secara khusus berdasarkan daftar materi modul/video yang ada pada gambar yang kamu kirim:

# 🚀 Vue Routing Learning

Repositori ini berisi catatan, contoh kode, dan dokumentasi hasil pembelajaran materi **Vue Router** di Vue 3.

---

## 📌 Materi Pembelajaran

Berikut adalah poin-poin materi yang dipelajari dan diimplementasikan dalam proyek ini:

### 1. Defining the Routing Rules
Mendefinisikan aturan navigasi pada aplikasi dengan menentukan pemetaan antara URL (*path*) dan komponen halaman (*views*).
- Konfigurasi `createRouter` dan `createWebHistory`.
- Menentukan daftar `routes` berisi `path`, `name`, dan `component`.

### 2. RouterView (`<RouterView />`)
Komponen bawaan Vue Router yang berfungsi sebagai tempat (*placeholder*) untuk merender halaman/komponen sesuai dengan route yang sedang aktif.

### 3. RouterLink (`<RouterLink />`)
Komponen navigasi deklaratif pengganti tag HTML `<a>`.
- Menggunakan atribut `to` untuk berpindah halaman tanpa memicu *full page reload* (SPA behavior).
- Menggunakan `active-class` untuk styling link yang sedang aktif.

### 4. Dynamic Routing
Menangani route dinamis yang menerima nilai parameter variabel pada URL (misalnya `/car/:id`).
- Mengambil parameter route menggunakan `useRoute().params`.
- Menampilkan data detail secara spesifik berdasarkan parameter ID yang diterima.

### 5. Programmatic Routing
Navigasi antar halaman secara terprogram melalui JavaScript/logic code menggunakan `useRouter()`.
- Menggunakan `router.push('/path')` atau `router.push({ name: 'RouteName' })`.
- Navigasi berdasarkan aksi event, seperti klik tombol atau setelah proses form selesai.

### 6. Catch All Route (404 Not Found)
Menangani URL tidak valid yang dimasukkan oleh pengguna menggunakan *wildcard pattern*.
- Menerapkan route `path: '/:pathMatch(.*)*'`.
- Mengarahkan pengguna ke komponen tampilan **404 Not Found / Page Not Found**.

### 7. Adding Query Params
Mengirim dan membaca data tambahan pada URL melalui *query string* (misalnya `/cars?make=Toyota&sort=asc`).
- Mengirim query via `router.push({ query: { make: 'Toyota' } })` atau `<RouterLink :to="{ query: { ... } }">`.
- Membaca parameter query menggunakan `useRoute().query`.

---

## 🛠️ Modul Tambahan
- **Nested Routes**: Pembagian tampilan layout induk (*parent*) dan anak (*child routes*) menggunakan `<RouterView />` bertingkat.

---