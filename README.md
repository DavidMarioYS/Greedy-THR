# Greedy-THR
## 1. **Metode Konversi Mata Uang**
   - **Fungsi `convert_to_rupiah(amount, exchange_rate)`**:
     - **Cara Kerja**: Fungsi ini mengambil dua parameter: `amount`, yaitu jumlah uang dalam mata uang asing, dan `exchange_rate`, yaitu nilai tukar mata uang asing ke Rupiah. Fungsi mengalikan `amount` dengan `exchange_rate` untuk mendapatkan jumlah dalam Rupiah. Hasilnya kemudian dikonversi ke integer agar menjadi bilangan bulat.
     - **Tujuan**: Mengonversi jumlah uang dalam mata uang asing ke Rupiah.

## 2. **Metode Greedy untuk Pembagian THR**
   - **Fungsi `calculate_change(amount, denominations)`**:
     - **Cara Kerja**: Fungsi ini menggunakan pendekatan **greedy** untuk membagi jumlah uang dalam denominasi tertentu (misalnya pecahan Rp100.000, Rp50.000, dan seterusnya). Fungsi ini bekerja dengan iterasi melalui daftar denominasi dari nilai terbesar ke terkecil, menghitung berapa banyak pecahan dari denominasi tersebut yang bisa digunakan untuk membagi jumlah uang yang tersisa. Setiap kali sebuah denominasi digunakan, jumlah tersebut dikurangi dari `remaining_amount`. Proses ini terus berlanjut hingga uang yang tersisa lebih kecil dari denominasi terkecil atau habis.
     - **Tujuan**: Fungsi ini digunakan untuk membagi jumlah uang ke dalam pecahan tertentu, sehingga memberikan hasil yang efisien dan meminimalkan sisa uang yang tidak terbagi.

## 3. **Proses dalam Fungsi `main()`**
   - **Pilihan Mata Uang**:
     - **Cara Kerja**: Program meminta pengguna untuk memilih salah satu dari beberapa mata uang asing, yang kemudian dikonversi ke Rupiah menggunakan kurs yang telah ditetapkan dalam dictionary `exchange_rates`.
     - **Tujuan**: Memberikan opsi kepada pengguna untuk mengonversi uang dalam berbagai mata uang asing.

   - **Konversi Mata Uang**:
     - **Cara Kerja**: Berdasarkan pilihan mata uang pengguna, program mengonversi jumlah uang yang diinput ke dalam Rupiah menggunakan fungsi `convert_to_rupiah`.
     - **Tujuan**: Mengonversi uang asing ke Rupiah agar dapat digunakan untuk proses pembagian THR.

   - **Pembagian THR untuk Orang Dewasa dan Anak-anak**:
     - **Cara Kerja**: Setelah konversi, program membagi uang yang dihasilkan ke dalam pecahan yang sesuai untuk dua kategori: orang dewasa dan anak-anak. Pembagian dilakukan dalam dua tahap: pertama untuk orang dewasa, dan sisa uang yang tidak dibagikan kepada orang dewasa kemudian dibagikan untuk anak-anak. Hasil pembagian dan sisa uang ditampilkan kepada pengguna.
     - **Tujuan**: Memanfaatkan sisa uang secara efisien setelah pembagian untuk orang dewasa untuk digunakan pada pembagian bagi anak-anak.

## 4. **Pendekatan Greedy**
   - **Cara Kerja**: Pendekatan greedy selalu memilih opsi terbaik yang tersedia pada setiap langkah, dalam hal ini memilih pecahan terbesar yang masih bisa digunakan dari jumlah uang yang tersisa. Ini dilakukan karena tujuan dari pendekatan greedy adalah memaksimalkan efisiensi di setiap langkah, meskipun itu tidak selalu menjamin solusi optimal secara global untuk semua kasus.
   - **Contoh Penerapan dalam Program**: Pada saat pembagian THR, program selalu mulai dari pecahan terbesar (Rp100.000) dan berlanjut ke pecahan yang lebih kecil, memastikan setiap denominasi yang digunakan maksimal sebelum berpindah ke pecahan yang lebih kecil.

## Informasi Penting Lainnya:
- **Validasi Input**: Program melakukan validasi sederhana pada pilihan mata uang yang dipilih pengguna. Jika pengguna memilih mata uang yang tidak ada dalam daftar, program menampilkan pesan error dan menghentikan eksekusi.
- **Penggunaan Integer**: Dalam proses konversi dan pembagian, jumlah uang dalam Rupiah diubah menjadi integer untuk menghindari kesalahan pembulatan.
- **Kemungkinan Peningkatan**: Program dapat ditingkatkan dengan menambahkan lebih banyak mata uang, fitur konversi dua arah (Rupiah ke mata uang asing), dan handling input yang lebih komprehensif untuk memastikan input yang diberikan oleh pengguna valid (misalnya, memastikan input bukanlah nilai negatif atau nol). 

Secara keseluruhan, kode ini menggabungkan konsep-konsep dasar dalam pemrograman seperti kontrol alur (percabangan, pengulangan), operasi aritmatika, manipulasi string, dan penggunaan fungsi untuk mengelola program secara modular. Program ini bermanfaat untuk simulasi pembagian uang dalam berbagai pecahan, yang bisa diterapkan dalam skenario dunia nyata seperti pembagian THR atau manajemen keuangan lainnya.

Tentu, saya akan menjelaskan pola yang digunakan dalam kode tersebut secara detail.

## **Pola yang Digunakan dalam Program**

Program yang kamu berikan mengikuti beberapa pola dan metode dalam prosesnya. Berikut adalah penjelasan lengkap mengenai pola-pola tersebut:

1. **Pola Interaksi Pengguna**
2. **Pola Konversi Mata Uang**
3. **Pola Algoritma Greedy untuk Pembagian THR**
4. **Pola Alur Data dan Pemrosesan**
5. **Pola Validasi dan Penanganan Kesalahan**

Mari kita bahas satu per satu.

---

## **1. Pola Interaksi Pengguna**

**Deskripsi Pola:**
Program ini dirancang untuk berinteraksi dengan pengguna melalui serangkaian input dan output yang terstruktur. Pola interaksi ini memastikan pengguna dapat dengan mudah memahami dan menggunakan program sesuai kebutuhan.

**Langkah-langkah dalam Pola Interaksi:**

1. **Pemilihan Mata Uang Asing:**
   - Program menampilkan daftar opsi mata uang asing yang tersedia (USD, EUR, JPY, GBP, AUD, SGD, MYR, IDR).
   - Pengguna diminta untuk memilih salah satu mata uang dengan memasukkan angka yang sesuai (1-8).

2. **Input Jumlah Uang Asing:**
   - Setelah memilih mata uang, pengguna diminta memasukkan jumlah uang dalam mata uang asing tersebut yang ingin dikonversi ke Rupiah.

3. **Menampilkan Hasil Konversi:**
   - Program menampilkan proses dan hasil konversi dari mata uang asing ke Rupiah berdasarkan kurs yang telah ditentukan.

4. **Input Jumlah Uang untuk Orang Dewasa:**
   - Pengguna diminta memasukkan jumlah uang dalam Rupiah yang akan dibagikan kepada orang dewasa.

5. **Menampilkan Hasil Pembagian untuk Orang Dewasa:**
   - Program menggunakan algoritma greedy untuk membagi jumlah uang tersebut ke dalam pecahan uang Rupiah yang tersedia dan menampilkan hasilnya.

6. **Menampilkan Sisa Uang Setelah Pembagian untuk Orang Dewasa:**
   - Program menghitung dan menampilkan sisa uang yang belum dibagikan setelah pembagian untuk orang dewasa.

7. **Menampilkan Hasil Pembagian untuk Anak-anak:**
   - Sisa uang tersebut kemudian dibagi lagi menggunakan algoritma greedy untuk anak-anak, dan hasilnya ditampilkan.

8. **Menampilkan Sisa Uang Setelah Pembagian untuk Anak-anak:**
   - Program menampilkan sisa uang terakhir yang belum terbagi setelah pembagian untuk anak-anak.

**Tujuan Pola:**
Pola interaksi ini dirancang agar proses penggunaan program menjadi intuitif dan terstruktur, memungkinkan pengguna untuk mengikuti langkah-langkah secara sistematis dan memahami setiap tahap proses yang terjadi.

---

## **2. Pola Konversi Mata Uang**

**Deskripsi Pola:**
Program menggunakan pola konversi mata uang yang sederhana namun efektif, di mana jumlah uang dalam mata uang asing dikonversi ke Rupiah berdasarkan kurs yang telah ditetapkan.

**Langkah-langkah dalam Pola Konversi:**

1. **Pemilihan Kurs yang Sesuai:**
   - Setelah pengguna memilih mata uang, program mengambil nilai kurs yang sesuai dari dictionary `exchange_rates`.

2. **Perhitungan Konversi:**
   - Program mengalikan jumlah uang asing yang diinput oleh pengguna dengan nilai kurs untuk mendapatkan jumlah dalam Rupiah.
   - Hasil perhitungan dikonversi menjadi integer untuk menghilangkan desimal dan memudahkan pembagian selanjutnya.

3. **Menampilkan Proses dan Hasil Konversi:**
   - Program menampilkan proses perhitungan konversi secara detail agar pengguna dapat melihat bagaimana hasil konversi diperoleh.

**Contoh:**
Jika pengguna memasukkan 500 SGD dengan kurs 10,503.11, maka:
```
500 * 10,503.11 = 5,251,555
```

**Tujuan Pola:**
Pola ini memastikan bahwa konversi mata uang dilakukan secara akurat dan transparan, memberikan pengguna pemahaman yang jelas tentang bagaimana jumlah Rupiah diperoleh dari jumlah uang asing yang mereka miliki.

---

## **3. Pola Algoritma Greedy untuk Pembagian THR**

**Deskripsi Pola:**
Program menggunakan **algoritma greedy** untuk membagi jumlah uang Rupiah ke dalam pecahan uang kertas yang tersedia. Algoritma greedy selalu memilih opsi terbaik yang tersedia pada setiap langkah dengan harapan mendapatkan solusi optimal secara keseluruhan.

**Langkah-langkah dalam Pola Algoritma Greedy:**

1. **Menyiapkan Daftar Denominasi:**
   - Program memiliki daftar pecahan uang Rupiah yang tersedia: `[100000, 50000, 20000, 10000, 5000, 2000, 1000]`.

2. **Inisialisasi:**
   - Program memulai dengan jumlah uang yang akan dibagikan (`amount`) dan hasil pembagian yang kosong (`result = {}`).

3. **Iterasi melalui Denominasi:**
   - Program mengiterasi melalui setiap denominasi mulai dari yang terbesar hingga terkecil.

4. **Menghitung Jumlah Pecahan yang Dibutuhkan:**
   - Untuk setiap denominasi, program menghitung berapa banyak pecahan tersebut yang dapat digunakan:
     ```
     count = amount // denom
     ```
   - Jika `count` lebih dari 0, program menambahkan entry ke `result` dan mengurangi `amount` dengan nilai yang telah dibagikan:
     ```
     amount -= count * denom
     ```

5. **Melanjutkan hingga Selesai:**
   - Proses ini dilanjutkan hingga semua denominasi telah diproses atau `amount` menjadi 0.

6. **Mengembalikan Hasil:**
   - Fungsi mengembalikan `result` yang berisi jumlah setiap pecahan yang digunakan dan `remaining_amount` yang merupakan sisa uang yang tidak dapat dibagi lebih lanjut.

**Contoh Proses:**
Misalkan kita ingin membagi Rp3,120,000:
- **Rp100,000**:
  - `count = 3120000 // 100000 = 31`
  - `amount = 3120000 - (31 * 100000) = 120000`
- **Rp50,000**:
  - `count = 120000 // 50000 = 2`
  - `amount = 120000 - (2 * 50000) = 20000`
- **Rp20,000**:
  - `count = 20000 // 20000 = 1`
  - `amount = 20000 - (1 * 20000) = 0`

**Hasil Akhir:**
```
{
  100000: 31,
  50000: 2,
  20000: 1
}
```

**Tujuan Pola:**
Pola algoritma greedy ini digunakan karena efisien dan sederhana, serta memastikan jumlah pecahan yang digunakan seminimal mungkin, yang sangat berguna dalam konteks pembagian uang nyata untuk mengurangi kompleksitas dan jumlah fisik uang kertas yang digunakan.

---

## **4. Pola Alur Data dan Pemrosesan**

**Deskripsi Pola:**
Program mengikuti alur data yang terstruktur dari input hingga output, memastikan setiap tahap pemrosesan data dilakukan secara berurutan dan logis.

**Langkah-langkah dalam Pola Alur Data:**

1. **Input Data dari Pengguna:**
   - Pengguna memasukkan pilihan mata uang dan jumlah uang yang ingin dikonversi.

2. **Pemrosesan Konversi:**
   - Data input diolah melalui fungsi konversi untuk mendapatkan jumlah dalam Rupiah.

3. **Pembagian Uang untuk Orang Dewasa:**
   - Jumlah Rupiah yang telah dikonversi dibagi sesuai permintaan pengguna untuk orang dewasa menggunakan algoritma greedy.

4. **Menghitung Sisa Uang:**
   - Setelah pembagian untuk orang dewasa, program menghitung sisa uang yang tersedia untuk pembagian selanjutnya.

5. **Pembagian Uang untuk Anak-anak:**
   - Sisa uang dibagi lagi menggunakan algoritma greedy untuk anak-anak.

6. **Output Data ke Pengguna:**
   - Hasil dari setiap tahap pembagian dan sisa uang yang tersedia ditampilkan kepada pengguna secara detail.

**Visualisasi Alur Data:**
```
[Input Pengguna] --> [Konversi Mata Uang] --> [Pembagian untuk Dewasa] --> [Sisa Uang] --> [Pembagian untuk Anak-anak] --> [Sisa Uang Akhir] --> [Output]
```

**Tujuan Pola:**
Pola alur data ini memastikan bahwa proses dilakukan secara sistematis dan setiap tahap pemrosesan bergantung pada hasil dari tahap sebelumnya, menjaga konsistensi dan akurasi data sepanjang eksekusi program.

---

## **5. Pola Validasi dan Penanganan Kesalahan**

**Deskripsi Pola:**
Program melakukan validasi terhadap input yang diberikan oleh pengguna dan menangani kesalahan sederhana untuk mencegah terjadinya error selama eksekusi.

**Langkah-langkah dalam Pola Validasi:**

1. **Validasi Pilihan Mata Uang:**
   - Program memeriksa apakah pilihan mata uang yang dimasukkan pengguna berada dalam rentang yang valid (1-8).
   - Jika tidak valid, program menampilkan pesan error dan menghentikan eksekusi.

2. **Validasi Input Jumlah Uang:**
   - Program mengasumsikan bahwa pengguna memasukkan nilai numerik yang valid untuk jumlah uang.
   - **Catatan:** Dalam kode yang ada, validasi untuk memastikan bahwa jumlah uang adalah angka positif belum diterapkan dan dapat menjadi area untuk peningkatan.

3. **Penanganan Kesalahan Potensial:**
   - Program menggunakan struktur try-except (meskipun tidak ditampilkan dalam kode) untuk menangani kemungkinan kesalahan seperti input yang tidak sesuai tipe data yang diharapkan.

**Tujuan Pola:**
Validasi dan penanganan kesalahan ini penting untuk memastikan bahwa program berjalan lancar dan memberikan informasi yang berguna kepada pengguna jika terjadi kesalahan input, meningkatkan robustness dan user experience dari program.

---

## **Ringkasan dan Informasi Penting Lainnya**

- **Efisiensi dan Optimalitas:**
  - Penggunaan algoritma greedy memastikan pembagian uang dilakukan secara efisien dengan menggunakan jumlah pecahan terkecil yang diperlukan.

- **Keterbacaan dan Pemeliharaan Kode:**
  - Kode dibagi menjadi fungsi-fungsi terpisah (`convert_to_rupiah` dan `calculate_change`), meningkatkan modularitas dan memudahkan pemeliharaan serta pengembangan lebih lanjut.

- **Potensi Peningkatan:**
  - **Validasi Input Lebih Lanjut:** Menambahkan validasi untuk memastikan input jumlah uang adalah angka dan positif.
  - **Dukungan Mata Uang Dinamis:** Mengambil nilai kurs secara real-time dari API untuk akurasi yang lebih baik.
  - **Antarmuka Pengguna yang Lebih Baik:** Mengimplementasikan GUI sederhana untuk interaksi yang lebih intuitif.
  - **Penanganan Pecahan Koin:** Menambahkan denominasi untuk pecahan koin (misalnya Rp500, Rp200, Rp100) jika diperlukan.

- **Penggunaan dalam Kehidupan Nyata:**
  - Program ini dapat digunakan oleh individu atau organisasi yang ingin membagi dana dalam mata uang asing ke dalam pecahan Rupiah secara efisien, seperti dalam persiapan pembagian THR, sumbangan, atau keperluan finansial lainnya.

---

**Kesimpulan:**
Program ini menerapkan pola-pola pemrograman yang efektif untuk mencapai tujuan konversi dan pembagian uang secara efisien dan terstruktur. Penggunaan algoritma greedy dan interaksi pengguna yang sistematis membuat program ini mudah digunakan dan diadaptasi untuk berbagai keperluan finansial.
