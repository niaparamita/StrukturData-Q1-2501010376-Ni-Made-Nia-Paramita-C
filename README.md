# StrukturData-Q1-2501010376-Ni-Made-Nia-Paramita-C

jawaban:
1. Karena Akses Array memiliki kecepatan  sangat cepat ($O(1)$) karena sifat memorinya yang terprediksi/sudah ditentukan, sehingga cukup satu kali hitung untuk sampai ke tujuan. Sedangkan Linked List membutuhkan waktu $O(n)$ karena memorinya bersifat dinamis dan tidak terprediksi, karena itu sistem harus menelusuri rantai data.
2. Masalah Array: Jika memori memiliki banyak celah kecil (fragmentasi), sistem mungkin gagal mengalokasikan Array yang besar meskipun total memori bebas mencukupi. Selain itu, jika Array penuh, harus melakukan resizing (membuat array baru yang lebih besar dan menyalin semua data lama), yang sangat mahal secara komputasi.

Keunggulan Linked List: Karena bersifat non-kontinu, Linked List dapat memanfaatkan celah-celah memori yang tersebar. Ia tumbuh secara dinamis selama masih ada sisa memori di sistem.

Alasan Teoritis: Alokasi memori dinamis memungkinkan penggunaan ruang yang lebih efisien tanpa perlu memesan blok besar di muka.

3. Array adalah pilihan terbaik untuk kecepatan akses data secara acak karena alamat memorinya kontinu dan dapat dihitung langsung ($O(1)$), namun sangat lambat dan kaku untuk manipulasi (tambah/hapus) di tengah karena harus menggeser elemen lain.Singly Linked List unggul dalam fleksibilitas manipulasi data secara dinamis pada memori yang non-kontinu, namun memiliki akses data yang lambat ($O(n)$) karena harus menelusuri rantai pointer satu arah dari awal.Doubly Linked List menawarkan fleksibilitas navigasi maksimal (bisa maju dan mundur) serta mempermudah operasi penghapusan, tetapi harus dibayar dengan penggunaan memori yang lebih boros karena adanya pointer tambahan (Prev) pada setiap node.

4. Perbedaan Teoritis Utama
Singly/Doubly Linked List: Node terakhir (Tail) menunjuk ke NULL. Ini menandakan akhir dari daftar, sehingga iterasi akan berhenti saat mencapai nilai kosong tersebut.

Circular Linked List: Node terakhir tidak menunjuk ke NULL, melainkan menunjuk kembali ke Node Pertama (Head). Hal ini menciptakan sebuah lingkaran (loop) tanpa akhir yang memungkinkan sistem terus berputar melalui elemen-elemennya tanpa perlu melakukan reset manual ke posisi awal.
contoh: Skenario paling efektif untuk struktur ini adalah Penjadwalan CPU (Round Robin Scheduling) pada Sistem Operasi.

Alasan Efektifitas:
Dalam penjadwalan Round Robin, sistem operasi memberikan jatah waktu (time quantum) yang sama kepada setiap proses yang sedang berjalan.

OS menaruh semua proses dalam sebuah Circular Linked List.

CPU mengeksekusi proses A, lalu pindah ke proses B, lalu C.

Setelah proses terakhir selesai mendapatkan jatah waktunya, CPU secara otomatis kembali ke proses A karena pointer terakhir merujuk kembali ke awal.

Struktur melingkar ini memastikan bahwa tidak ada proses yang terlewat dan siklus pembagian sumber daya berjalan terus-menerus dengan overhead manajemen yang minimal.

5.
Alokasi Baru: Python memesan blok memori baru yang lebih besar (biasanya sekitar $1.125\times$ ukuran lama) di lokasi lain.Penyalinan (Copying): Semua elemen dari array lama disalin ke array baru satu per satu.Penyisipan: Elemen baru yang di-append dimasukkan ke slot kosong pertama di memori baru.Penghapusan: Blok memori lama dihancurkan (dealokasi).Intinya: Meskipun proses penyalinan memakan waktu $O(n)$, hal ini jarang terjadi karena Python melebihkan kapasitas (over-allocation), sehingga secara rata-rata (Amortized), operasi append tetap dianggap $O(1)$.
