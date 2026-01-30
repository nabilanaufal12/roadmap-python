# Variabel dan Tipe Data di Python

Catatan ini merangkum konsep variabel, tipe data, dan interaksi dengan *shell* Python interaktif (REPL), dengan perbandingan antara Python dan C.

## Variabel dalam Pemrograman

Variabel adalah nama simbolis yang merujuk pada objek atau nilai yang disimpan dalam memori komputer. Variabel memungkinkan Anda menetapkan nama deskriptif pada data, sehingga lebih mudah untuk memanipulasi dan menggunakan kembali nilai-nilai tersebut di seluruh kode Anda.

### Variabel dalam C

Dalam bahasa pemrograman C, sebuah variabel adalah lokasi memori di mana kita dapat menyimpan beberapa nilai. Saat mendeklarasikan variabel di C, Anda harus menentukan tipe datanya terlebih dahulu (misalnya, `int x = 10;`). Memori dialokasikan untuk variabel `x` yang cukup untuk menyimpan nilai integer.

Jika Anda menulis `int y = x;`, memori baru dialokasikan untuk `y`, dan nilai dari `x` (yaitu 10) disalin ke lokasi memori `y`. Ini berarti salinan baru dibuat. Variabel di C bersifat *statis* karena setelah tipe datanya ditentukan, variabel tersebut hanya dapat menyimpan nilai dari tipe tersebut sepanjang masa pakainya. Jika Anda mencoba menetapkan nilai tipe yang berbeda, Anda mungkin mendapatkan kesalahan atau kehilangan presisi.

### Variabel dalam Python

Berbeda dengan C, variabel di Python hanyalah sebuah *label* yang diberikan pada suatu objek. Variabel tidak memiliki informasi tipe sendiri dan tidak memiliki arti tersendiri. Memori dialokasikan untuk *objek*, bukan untuk variabel.

Ketika Anda menulis `x = 10`, Python secara internal mengalokasikan memori untuk objek integer `10`, dan kemudian label `x` ditetapkan ke objek ini. Jika Anda kemudian menulis `y = x`, tidak ada memori baru yang dialokasikan untuk `y`. Sebaliknya, `y` menjadi label lain yang menunjuk ke objek yang sama dengan yang ditunjuk `x`.

Python adalah bahasa yang *dinamis* dalam hal pengetikan (*dynamically typed*). Ini berarti tipe variabel tidak perlu ditentukan di muka dan dapat berubah sepanjang masa pakainya. Tipe variabel akan diketahui saat *runtime* berdasarkan nilai yang ditunjuknya. Misalnya, Anda dapat menetapkan `x = 10` (integer) dan kemudian `x = 4.55` (float) tanpa masalah.

### Objek dalam Python

Setiap item data di Python adalah sebuah *objek*. Sebuah objek adalah entitas yang berisi data beserta properti dan perilakunya. Objek adalah *instance* dari sebuah *class*, yang merupakan cetak biru atau struktur yang harus diikuti oleh setiap objek dari kelas tersebut. Variabel di Python tidak menyimpan objek, melainkan menunjuk atau merujuk ke objek.

Fungsi `id()` bawaan Python mengembalikan pengenal atau identitas objek, yang di CPython (distribusi Python standar) bertepatan dengan alamat memorinya.

Ketika sebuah objek tidak lagi memiliki referensi yang menunjuk kepadanya (misalnya, setelah variabel yang menunjuknya ditetapkan ulang ke objek lain), objek tersebut menjadi "yatim piatu" (*orphaned*) dan tidak dapat diakses lagi. Python kemudian akan mengklaim kembali memori yang dialokasikan untuk objek tersebut melalui proses yang dikenal sebagai *garbage collection*.

### Membuat Variabel

Variabel dibuat di Python dengan menetapkan nilai menggunakan operator penugasan (`=`).

#### Penugasan Berantai (*Chained Assignment*)
Python memungkinkan penugasan berantai, yang membantu menetapkan nilai yang sama ke beberapa variabel dalam satu baris.
Contoh: `x = y = z = 10`

#### Pembongkaran *Iterable* (*Iterable Unpacking*)
Ini adalah fitur Python yang mendistribusikan nilai-nilai dalam sebuah *iterable* (seperti *tuple* atau *list*) ke dalam serangkaian variabel.
Contoh: `name, age, job = ("Jane", 25, "Python Dev")`
Ini juga merupakan cara yang elegan untuk menukar nilai antara dua variabel tanpa variabel sementara: `a, b = b, a`

#### Ekspresi Penugasan (*Assignment Expressions*)
Dikenal juga sebagai operator Walrus (`:=`), ekspresi penugasan memungkinkan Anda menetapkan hasil ekspresi yang digunakan dalam kondisi atau *loop* `while` ke sebuah nama dalam satu langkah.
Contoh: `while (line := input("Type some text: ")) != "stop":`

### Konvensi Penamaan Variabel

Aturan dan praktik terbaik untuk menamai variabel di Python:

#### Aturan Penamaan
*   Dapat berisi huruf (A-Z, a-z), angka (0-9), dan garis bawah (`_`).
*   Tidak boleh dimulai dengan angka.
*   Dapat dimulai dengan huruf atau garis bawah.
*   Tidak boleh ada spasi; gunakan garis bawah untuk memisahkan kata.
*   Nama variabel bersifat *case-sensitive* (huruf besar dan kecil dibedakan), jadi `x` dan `X` adalah variabel yang berbeda.
*   Python memiliki dukungan Unicode penuh, sehingga karakter Unicode dapat digunakan dalam nama variabel.

#### Praktik Terbaik Penamaan
*   **Deskriptif**: Berikan nama yang jelas menjelaskan tujuan variabel.
*   **Singkat**: Meskipun deskriptif, usahakan tetap singkat.
*   **Kata Benda**: Variabel selalu merujuk pada objek konkret, jadi namanya harus berupa kata benda.
*   **Hindari Huruf Tunggal**: Kecuali untuk indeks (`i, j, k`) atau koordinat (`x, y, z`).
*   **Hindari Singkatan**: Gunakan nama lengkap kecuali singkatan tersebut sudah umum diterima (misalnya, `cmd`, `msg`).
*   **Konvensi Multi-kata**:
    *   **Snake Case**: Kata-kata dipisahkan oleh garis bawah, semua huruf kecil (misalnya, `student_name`). Ini adalah rekomendasi PEP 8.
    *   **Camel Case**: Kata kedua dan selanjutnya diawali huruf kapital (misalnya, `studentName`).
    *   **Pascal Case**: Mirip Camel Case, tetapi kata pertama juga diawali huruf kapital (misalnya, `StudentName`).
*   **Kualifikasi Adjektif**: Kombinasikan kata sifat sebagai kualifikasi dengan kata benda (misalnya, `initial_temperature`).
*   **Hindari `my_`**: Bagian `my_` tidak menambah nilai deskriptif.
*   **Bendera Boolean**: Sering menggunakan pola penamaan `is_` atau `has_` (misalnya, `is_adult`).
*   **Koleksi**: Gunakan kata benda jamak untuk *list* dan *dictionary* (misalnya, `fruits`, `colors`), dan kata benda tunggal untuk *tuple* (misalnya, `color`, `row`).

#### Nama Variabel Publik dan Non-Publik
Konvensi penamaan yang umum adalah menggunakan garis bawah di awal (misalnya, `_timeout`) untuk menunjukkan bahwa variabel tersebut bersifat non-publik atau ditujukan untuk penggunaan internal dalam modul.

#### Nama Terlarang dan Tidak Dianjurkan
*   **Kata Kunci (*Keywords*)**: Python memiliki kata kunci yang merupakan bagian dari sintaks bahasa (misalnya, `class`, `if`, `for`). Anda tidak dapat menggunakannya sebagai nama variabel. Jika perlu, tambahkan garis bawah di akhir (misalnya, `class_`).
*   **Kata Kunci Lunak (*Soft Keywords*)**: Kata kunci hanya dalam konteks tertentu (misalnya, `match` dalam pencocokan pola struktural). Ini dapat digunakan sebagai nama variabel di luar konteks tersebut.
*   **Nama Bawaan (*Built-in Names*)**: Hindari menggunakan nama fungsi atau tipe bawaan Python (misalnya, `list`, `str`) sebagai nama variabel, karena ini akan menimpa objek asli dan dapat menyebabkan kesalahan.

### Petunjuk Tipe (*Type Hints*)
Anda dapat menggunakan petunjuk tipe untuk menambahkan informasi tipe eksplisit ke variabel Anda menggunakan sintaks `variable: data_type [= value]`"]. Petunjuk tipe bersifat opsional dan tidak memengaruhi perilaku *runtime*, tetapi membantu alat analisis kode statis dan meningkatkan keterbacaan, terutama untuk tipe koleksi.
Contoh: `language: str = "Python"`, `colors: dict[str, str] = {...}` = {"]

### Lingkup Variabel (*Variable Scopes*)

Konsep lingkup (*scope*) mendefinisikan bagaimana variabel dicari dalam kode Anda dan menentukan visibilitasnya. Python memiliki empat lingkup utama, yang dapat disajikan menggunakan akronim LEGB: *Local*, *Enclosing*, *Global*, dan *Built-in*.

*   **Variabel Global**: Dibuat pada tingkat modul dan terlihat di seluruh modul serta modul lain yang mengimpornya.
*   **Variabel Lokal**: Didefinisikan di dalam sebuah fungsi dan hanya terlihat di dalam fungsi tersebut. Setelah fungsi selesai dieksekusi, variabel lokal akan hilang.
*   **Variabel Non-Lokal**: Dibuat dalam fungsi luar yang mendefinisikan fungsi dalam. Variabel yang lokal untuk fungsi luar bersifat non-lokal untuk fungsi dalam.
*   **Variabel Kelas dan Instans (Atribut)**: Variabel yang dibuat di dalam kelas kustom. Atribut kelas dibuat pada tingkat kelas dan umum untuk semua instans, sedangkan atribut instans melekat pada instans tertentu dari kelas.

### Menghapus Variabel
Anda dapat secara eksplisit menghapus variabel dari lingkupnya menggunakan pernyataan `del`. Ini menghapus referensi ke objek, tetapi memori tidak segera dibebaskan; *garbage collector* Python akan mengklaimnya setelah tidak ada lagi referensi ke objek tersebut.

## Tipe Data Dasar di Python

Tipe data adalah kategori data yang juga menginformasikan operasi apa yang dapat dilakukan pada kumpulan data tertentu. Python memiliki beberapa tipe data bawaan utama:

### Tipe Numerik
Tipe data numerik di Python dapat berupa *integer*, *floating number*, atau *complex numbers*.

*   **Integer (`int`)**: Bilangan bulat positif atau negatif (misalnya, -1, 2, 3000). Tidak memiliki titik desimal dan tidak ada batasan ukuran di Python. Python tidak menggunakan koma sebagai pemisah numerik; gunakan garis bawah (`_`) sebagai gantinya untuk keterbacaan (misalnya, `867_5309`).
    *   **Integer Non-Desimal**: Python juga mendukung representasi bilangan biner, oktal, dan heksadesimal dengan menambahkan awalan:
        *   Biner: `0b` atau `0B` (misalnya, `0b1010`).
        *   Oktal: `0o` atau `0O` (misalnya, `0o72`).
        *   Heksadesimal: `0x` atau `0X` (misalnya, `0xff`).
        *   Secara *default*, saat dicetak, Python akan menampilkan nilai desimal yang setara.
*   **Float (`float`)**: Bilangan riil yang mencakup titik desimal (misalnya, -1.5, 3.14159). Dapat positif atau negatif dan dapat direpresentasikan dalam notasi ilmiah (menggunakan `e` atau `E`, misalnya `1.73E5`). Tipe *float* memiliki ukuran maksimum, yang disebut `inf` (tak terhingga) jika nilainya melebihi batas.
*   **Complex (`complex`)**: Kombinasi bilangan riil dan bilangan imajiner (misalnya, `10+3j`).

### Tipe Boolean (`bool`)
Tipe data Boolean digunakan untuk merepresentasikan salah satu dari dua nilai: `True` atau `False`. Ini adalah hasil dari pemeriksaan kondisi (misalnya, `5 < 10` akan mengembalikan `True`).

### Tipe String (`str`)
*String* adalah urutan karakter. Mereka harus ditulis di dalam tanda kutip tunggal (`'`) atau ganda (`"`). Secara *default*, Python akan menampilkan *string* yang diapit tanda kutip tunggal.

### Tipe Urutan (*Sequence Types*)
Tipe urutan adalah urutan data yang terurut. Ini termasuk:
*   **String**: Seperti dijelaskan di atas.
*   **List**: Kumpulan nilai yang dipisahkan koma, diapit kurung siku (`[]`), dan dapat diubah (*mutable*).
*   **Tuple**: Kumpulan nilai yang dipisahkan koma, diapit kurung biasa (`()`), dan tidak dapat diubah (*immutable*).

### Tipe Set (`set`)
*Set* adalah koleksi data yang tidak terurut, *iterable*, dapat diubah (*mutable*), dan tidak memiliki elemen duplikat. Elemen dipisahkan koma dan diapit kurung kurawal (`{}`). *Set* dapat melakukan operasi *union* dan *intersection*.

### Tipe Dictionary (`dict`)
*Dictionary* adalah tipe data paling fleksibel di Python, digunakan untuk menyimpan data dalam jumlah besar. Ini adalah koleksi nilai data yang tidak terurut yang disimpan dalam pasangan *key-value*. Sintaksnya adalah `{key : value, key : value}`.

## *Shell* Interaktif Python (REPL)

### Apa itu REPL?
REPL adalah singkatan dari *Read Evaluate Print Loop*. Ini adalah *shell* interaktif Python yang memungkinkan Anda mengetik perintah Python, menjalankannya, dan melihat hasilnya secara instan.
*   **Read**: Membaca pernyataan atau perintah yang Anda berikan.
*   **Evaluate**: Mengevaluasi dan memproses perintah tersebut.
*   **Print**: Mencetak hasil di layar.
*   **Loop**: Mengulangi proses yang sama, siap menerima perintah berikutnya.

Untuk mengaktifkan *shell* interaktif Python, ketik `python` (atau `python3`) di *command prompt* dan tekan Enter.

### Menggunakan REPL sebagai Kalkulator
Anda dapat menggunakan REPL untuk melakukan perhitungan dasar seperti penjumlahan, pengurangan, perkalian, dan pembagian.
Contoh: `10 + 5` akan menghasilkan `15`.

### Operator Aritmatika
Python menyediakan berbagai operator aritmatika:
*   Eksponen: `**` (misalnya, `2 ** 2` menghasilkan 4).
*   Modulus (sisa bagi): `%` (misalnya, `2 % 2` menghasilkan 0).
*   Pembagian Lantai (*Floor Division*) / Pembagian Integer: `//` (mengembalikan nilai integer, misalnya `2 // 2` menghasilkan 1).
*   Pembagian: `/` (mengembalikan nilai *floating point*, misalnya `2 / 2` menghasilkan 1.0).
*   Perkalian: `*`.
*   Pengurangan: `-`.
*   Penjumlahan: `+`.

### Presedensi Operator Aritmatika
Presedensi (prioritas) menentukan operasi mana yang akan dilakukan terlebih dahulu dalam ekspresi yang mengandung beberapa operator aritmatika.
*   Operator eksponen (`**`) memiliki prioritas tertinggi.
*   Operator modulus (`%`), pembagian lantai (`//`), pembagian (`/`), dan perkalian (`*`) memiliki prioritas yang sama.
*   Operator pengurangan (`-`) dan penjumlahan (`+`) memiliki prioritas terendah dan sama.
*   Jika operator memiliki prioritas yang sama, evaluasi biasanya dilakukan dari kiri ke kanan.
Contoh: `10 + 5 ** 2 // 5`
1.  `5 ** 2` dievaluasi terlebih dahulu (hasilnya 25).
2.  Kemudian `25 // 5` dievaluasi (hasilnya 5).
3.  Terakhir `10 + 5` dievaluasi (hasilnya 15).