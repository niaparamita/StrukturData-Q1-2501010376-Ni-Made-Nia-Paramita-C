# StrukturData-Q1-2501010376-Ni-Made-Nia-Paramita-C

jawaban:
Berikut adalah penjelasan komprehensif mengenai struktur data dasar dan analisis efisiensinya:

---

## 1. Karakteristik Memori dan Akses Data

Perbedaan kecepatan akses antara Array dan Singly Linked List ditentukan oleh cara data diletakkan di RAM.

* **Array (Memori Kontinu):** Elemen disimpan dalam blok memori yang berurutan. Karena setiap elemen memiliki ukuran yang sama, komputer dapat menghitung lokasi elemen ke-$i$ secara instan menggunakan rumus: $\text{Alamat}_i = \text{Alamat Dasar} + (i \times \text{Ukuran})$. Inilah mengapa aksesnya **$O(1)$**.
* **Singly Linked List (Memori Non-Kontinu):** Elemen (node) tersebar secara acak. Satu-satunya cara mengetahui lokasi elemen berikutnya adalah dengan membaca *pointer* pada elemen saat ini. Untuk mencapai elemen ke-$n$, Anda harus melewati $n-1$ elemen sebelumnya. Inilah mengapa aksesnya **$O(n)$**.



---

## 2. Analisis Efisiensi Operasi Manipulasi

Linked List lebih unggul daripada Array dalam kondisi **sering terjadi penyisipan atau penghapusan di awal atau tengah data**.

* **Alasan Teoritis:** * Pada **Array**, penyisipan di awal memaksa setiap elemen lainnya bergeser satu posisi ke kanan (**Element Shifting**) yang memakan waktu $O(n)$.
    * Pada **Linked List**, Anda hanya perlu mengubah arah *pointer* pada node terkait tanpa harus memindahkan data lainnya secara fisik. Proses penyambungan kembali ini hanya memakan waktu **$O(1)$** (setelah lokasi ditemukan).

---

## 3. Konsep Doubly Linked List

**Anatomi Node:**
Sebuah node pada Doubly Linked List (DLL) memiliki tiga komponen: **Data**, **Pointer Next** (ke depan), dan **Pointer Prev** (ke belakang).



* **Dampak Memori:** Penggunaan memori meningkat signifikan karena setiap node harus menyimpan dua alamat memori (pointer) alih-alih satu. Pada sistem 64-bit, ini menambah beban sekitar 8 byte per node dibandingkan Singly Linked List.
* **Fleksibilitas:** DLL memungkinkan penelusuran **dua arah** (maju dan mundur). Hal ini mempermudah operasi seperti penghapusan node tertentu karena kita bisa langsung mengetahui node sebelumnya tanpa harus mengulang pencarian dari awal daftar.

---

## 4. Mekanisme Circular Linked List

**Perbedaan Teoritis:**
Pada Linked List biasa, node terakhir menunjuk ke `NULL` (akhir daftar). Pada **Circular Linked List**, node terakhir menunjuk kembali ke **node pertama (Head)**, sehingga membentuk lingkaran tanpa ujung.

* **Skenario Penggunaan (Use Case):** **Penjadwalan CPU Round Robin**.
    * Sistem operasi memberikan jatah waktu pada setiap aplikasi secara bergantian. Dengan struktur melingkar, setelah aplikasi terakhir selesai mendapatkan giliran, CPU secara otomatis kembali ke aplikasi pertama dalam siklus tanpa perlu logika reset yang rumit.



---

## 5. Array Dinamis di Python (List)

Ketika sebuah Python List (Dynamic Array) kehabisan kapasitas saat melakukan `.append()`, terjadi mekanisme otomatis berikut:

1.  **Over-allocation:** Python memesan blok memori baru yang lebih besar (biasanya $\approx 1.125\times$ dari ukuran lama).
2.  **Copying:** Semua elemen dari memori lama disalin ke blok memori yang baru.
3.  **Update:** Pointer list diarahkan ke memori baru, dan memori lama dihapus.

**Analisis Kompleksitas:**
Meskipun proses menyalin data memakan waktu $O(n)$, hal ini jarang terjadi karena kapasitas dilebihkan. Oleh karena itu, biaya operasi `append` secara rata-rata dianggap **Amortized $O(1)$**.
