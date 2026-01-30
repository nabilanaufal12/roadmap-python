# Catatan Belajar Python

## Ikhtisar Python

Python adalah bahasa pemrograman serbaguna yang diciptakan oleh Guido van Rossum di awal tahun 90-an. Python dikenal karena **kejelasan sintaksisnya**, yang membuatnya mudah dibaca dan dipahami, sering disebut sebagai "pseudocode yang dapat dieksekusi".

**Kegunaan Python**:
*   **Pembelajaran Mesin (Machine Learning) & Kecerdasan Buatan (AI)**: Python adalah bahasa nomor satu untuk proyek ML dan ilmu data.
*   **Pengembangan Web**: Digunakan dengan *framework* seperti Django untuk membangun situs web yang kuat. Contoh situs web yang menggunakan Python/Django: YouTube, Instagram, Spotify, Dropbox, dan Pinterest.
*   **Otomatisasi**: Mengotomatiskan tugas-tugas yang berulang untuk menghemat waktu dan meningkatkan produktivitas.
*   **Ilmu Data (Data Science)**.

## Memulai dengan Python

### Instalasi Python dan Lingkungan Pengembangan

1.  **Unduh Python**: Kunjungi [python.org](https://www.python.org/) dan unduh versi terbaru.
2.  **Konfigurasi PATH**: Saat instalasi di Windows, pastikan untuk mencentang opsi "Add Python to PATH" (Tambahkan Python ke PATH). Ini penting agar Python dapat diakses dari *command line*.
3.  **Instal Lingkungan Pengembangan Terpadu (IDE)**: PyCharm adalah editor kode populer untuk Python. Unduh **Community Edition** (gratis dan *open source*) dari [jetbrains.com/pycharm](https://www.jetbrains.com/pycharm/).
    *   Setelah instalasi, buat proyek baru. PyCharm akan membuat *virtual environment* (lingkungan virtual) untuk proyek Anda.
    *   Buat file Python baru (misalnya, `app.py`) dalam proyek Anda.

### Menjalankan Kode Python

Python dapat dijalankan dalam dua mode:

1.  **Mode Interaktif**: Ketik `python3` di terminal untuk masuk ke *Python Command Prompt* (ditandai dengan `>>>`). Anda dapat mengetik dan menjalankan perintah Python satu per satu.
    ```python
    $ python3
    >>> print("Hello, World!")
    Hello, World!
    ```
2.  **Mode Skrip**: Tulis kode Python dalam file teks dengan ekstensi `.py` (misalnya, `test.py`). Jalankan file tersebut dari terminal menggunakan `python3 test.py`.
    ```python
    # test.py
    print("Hello, World!")
    ```
    Untuk membuat skrip dapat dieksekusi langsung (di Linux/macOS), tambahkan `#!/usr/bin/python3` di baris pertama dan berikan izin eksekusi dengan `chmod +x test.py`, lalu jalankan dengan `./test.py`.

## Sintaks Dasar Python

### Komentar

Komentar digunakan untuk menjelaskan kode dan diabaikan oleh *interpreter* Python.
*   **Komentar Satu Baris**: Dimulai dengan tanda pagar (`#`).
    ```python
    # Ini adalah komentar satu baris
    print("Hello") # Komentar di akhir baris
    ```
*   **Komentar Multi-Baris**: Dapat dibuat menggunakan tiga tanda kutip ganda (`"""`) atau tiga tanda kutip tunggal (`'''`). Ini juga sering digunakan sebagai *docstring* (dokumentasi).
    ```python
    """
    Ini adalah komentar multi-baris
    atau docstring.
    """
    ```

### Indentasi

Python menggunakan **indentasi** (spasi) untuk mendefinisikan blok kode, bukan kurung kurawal `{}` seperti bahasa lain.
*   Jumlah spasi untuk indentasi bisa bervariasi, tetapi semua pernyataan dalam satu blok harus memiliki jumlah indentasi yang sama.
*   Konvensi umum adalah menggunakan **empat spasi** untuk setiap tingkat indentasi.

### Pernyataan Multi-Baris

*   Secara *default*, pernyataan Python berakhir dengan baris baru.
*   Karakter *backslash* (`\`) dapat digunakan untuk melanjutkan pernyataan ke baris berikutnya.
    ```python
    total = item_one + \
            item_two + \
            item_three
    ```
*   Pernyataan yang berada di dalam `[]`, `{}`, atau `()` tidak memerlukan karakter `\` untuk melanjutkan baris, {}, or () brackets"].
    ```python
    days = ['Monday', 'Tuesday', 'Wednesday',
            'Thursday', 'Friday']
    ```

### Pernyataan dalam Satu Baris

Beberapa pernyataan dapat ditulis dalam satu baris dengan memisahkannya menggunakan titik koma (`;`), asalkan tidak ada pernyataan yang memulai blok kode baru.
```python
import sys; x = 'foo'; sys.stdout.write(x + '\n')
```

### Identifier dan Kata Kunci (Keywords)

*   **Identifier**: Nama yang digunakan untuk mengidentifikasi variabel, fungsi, kelas, modul, atau objek lain.
    *   Dimulai dengan huruf (A-Z, a-z) atau *underscore* (`_`), diikuti oleh nol atau lebih huruf, *underscore*, dan digit (0-9).
    *   Python **peka huruf besar/kecil** (case-sensitive).
    *   **Konvensi Penamaan**:
        *   Nama kelas dimulai dengan huruf kapital.
        *   Identifier lain (variabel, fungsi) dimulai dengan huruf kecil.
        *   Gunakan `snake_case` (kata-kata dipisahkan oleh *underscore*) untuk nama variabel multi-kata.
        *   Satu *underscore* di awal (`_nama`) menunjukkan identifier privat (internal).
        *   Dua *underscore* di awal (`__nama`) menunjukkan identifier yang sangat privat.
        *   Identifier dengan dua *underscore* di awal dan akhir (`__nama__`) adalah nama khusus yang ditentukan bahasa (*magic/dunder methods*).
*   **Kata Kunci (Reserved Words)**: Kata-kata yang memiliki makna khusus dalam Python dan tidak dapat digunakan sebagai identifier. Semua kata kunci Python menggunakan huruf kecil.
    *   Contoh: `and`, `as`, `assert`, `break`, `class`, `continue`, `def`, `del`, `elif`, `else`, `except`, `False`, `finally`, `for`, `from`, `global`, `if`, `import`, `in`, `is`, `lambda`, `None`, `nonlocal`, `not`, `or`, `pass`, `raise`, `return`, `True`, `try`, `while`, `with`, `yield`.

## Variabel

**Variabel** digunakan untuk menyimpan data sementara di memori komputer.
*   **Deklarasi dan Penugasan**: Cukup berikan nama variabel dan tetapkan nilai menggunakan operator penugasan (`=`).
    ```python
    age = 20
    price = 19.95
    first_name = "Mosh"
    is_online = True
    ```
*   Nilai variabel dapat diubah (ditugaskan kembali) selama eksekusi program.
*   Mengakses variabel yang belum ditugaskan akan menimbulkan `NameError`.

## Tipe Data Primitif

Python memiliki beberapa tipe data dasar (primitif).

### Angka (Numbers)

*   **Integer (int)**: Bilangan bulat (contoh: `10`, `2020`).
*   **Float (floating-point number)**: Bilangan desimal (contoh: `10.1`, `19.95`).

### String

**String** adalah urutan karakter atau data tekstual, selalu diapit oleh tanda kutip tunggal (`'`) atau ganda (`"`).
*   **Kutipan Tiga Kali**: Dapat digunakan untuk string multi-baris.
    ```python
    word = 'word'
    sentence = "This is a sentence."
    paragraph = """This is a paragraph. It is
    made up of multiple lines and sentences."""
    ```
*   **Panjang String**: Gunakan fungsi `len()`.
    ```python
    len("Hello world!") # => 12
    ```
*   **Akses Karakter**: String dapat diperlakukan seperti daftar karakter, diakses dengan indeks.
    ```python
    "Hello world!"[0] # => 'H'
    ```
*   **Penggabungan (Concatenation)**: Menggabungkan dua string atau lebih menggunakan operator `+`.
    ```python
    "Hello " + "world!" # => "Hello world!"
    ```
*   **f-strings (Formatted String Literals)**: Sejak Python 3.6, digunakan untuk menyematkan ekspresi Python di dalam string dengan mudah.
    ```python
    name = "Reiko"
    f"She said her name is {name}." # => "She said her name is Reiko"
    ```
*   **String adalah Objek**: String memiliki metode (fungsi yang melekat pada objek) untuk manipulasi.
    *   `str.upper()`: Mengembalikan string baru dalam huruf kapital.
    *   `str.lower()`: Mengembalikan string baru dalam huruf kecil.
    *   `str.find(substring)`: Mengembalikan indeks kemunculan pertama dari *substring*, atau `-1` jika tidak ditemukan.
    *   `str.replace(old, new)`: Mengembalikan string baru dengan semua kemunculan `old` diganti dengan `new`.
    *   **String bersifat *Immutable***: Metode string tidak mengubah string asli; mereka mengembalikan string baru.
*   **Operator `in`**: Memeriksa apakah suatu *substring* ada dalam string, mengembalikan `True` atau `False`.
    ```python
    "Python" in "Python for Beginners" # => True
    ```

### Boolean

**Boolean** adalah tipe data yang hanya memiliki dua nilai: `True` atau `False`.
*   Perhatikan kapitalisasi `True` dan `False`.
*   Secara numerik, `True` dievaluasi sebagai `1` dan `False` sebagai `0`.
*   Fungsi `bool()` dapat digunakan untuk mengonversi nilai lain ke boolean. Nilai seperti `0`, `None`, dan koleksi kosong (`""`, `[]`, `{}`, `()`, `set()`) dievaluasi sebagai `False`. Semua nilai lainnya adalah `True`.

### None

**None** adalah objek khusus yang mewakili tidak adanya nilai atau nilai nol. Ini adalah objeknya sendiri.
*   Untuk membandingkan dengan `None`, gunakan operator `is` (memeriksa identitas objek), bukan `==` (memeriksa nilai).
    ```python
    "etc" is None # => False
    None is None  # => True
    ```

### Konversi Tipe Data (Type Conversion)

Anda dapat mengonversi nilai dari satu tipe data ke tipe data lain menggunakan fungsi bawaan.
*   `int(value)`: Mengonversi ke integer.
*   `float(value)`: Mengonversi ke float.
*   `str(value)`: Mengonversi ke string.
*   `bool(value)`: Mengonversi ke boolean.

**Penting**: Fungsi `input()` selalu mengembalikan nilai sebagai string, bahkan jika pengguna memasukkan angka. Oleh karena itu, konversi tipe seringkali diperlukan saat memproses input numerik.

## Operator

### Operator Aritmatika

Digunakan untuk melakukan perhitungan matematis.
*   `+`: Penjumlahan
*   `-`: Pengurangan
*   `*`: Perkalian
*   `/`: Pembagian (selalu mengembalikan float)
*   `//`: Pembagian lantai (floor division), membulatkan ke bawah menuju negatif tak terhingga
*   `%`: Modulo (sisa pembagian)
*   `**`: Eksponen (pangkat)

### Operator Penugasan Berimbuh (Augmented Assignment Operators)

Digunakan untuk memperbarui nilai variabel secara ringkas.
*   `x = x + 3` sama dengan `x += 3`
*   Juga ada `-=`, `*=`, `/=`, `//=`, `%=`, `**=`

### Preseden Operator (Operator Precedence)

Menentukan urutan operasi dalam ekspresi.
*   Perkalian (`*`) dan Pembagian (`/`, `//`, `%`) memiliki prioritas lebih tinggi daripada Penjumlahan (`+`) dan Pengurangan (`-`).
*   Tanda kurung `()` dapat digunakan untuk mengubah urutan preseden.

### Operator Perbandingan

Digunakan untuk membandingkan nilai dan mengembalikan nilai boolean (`True` atau `False`).
*   `>`: Lebih besar dari
*   `>=`: Lebih besar dari atau sama dengan
*   `<`: Lebih kecil dari
*   `<=`: Lebih kecil dari atau sama dengan
*   `==`: Sama dengan (jangan bingung dengan operator penugasan `=`)
*   `!=`: Tidak sama dengan
*   **Perbandingan Berantai**: Dapat digabungkan secara berantai, misalnya `1 < 2 < 3`.

### Operator Logika

Digunakan untuk membangun kondisi dan aturan yang kompleks.
*   `and`: Mengembalikan `True` jika **kedua** ekspresi boolean `True`.
*   `or`: Mengembalikan `True` jika **setidaknya satu** ekspresi boolean `True`.
*   `not`: Membalik nilai boolean (misalnya, `not True` menjadi `False`).

### Operator `is` vs `==`

*   `is`: Memeriksa apakah dua variabel merujuk pada **objek yang sama** di memori (identitas objek).
*   `==`: Memeriksa apakah **nilai** dari objek yang ditunjuk sama.

## Input dan Output

*   **`print()`**: Fungsi bawaan untuk menampilkan pesan atau nilai variabel ke terminal.
    *   Secara *default*, `print()` menambahkan baris baru di akhir. Parameter `end` dapat digunakan untuk mengubah karakter akhir.
    ```python
    print("Hello, World", end="!") # => Hello, World!
    ```
*   **`input()`**: Fungsi bawaan untuk membaca input dari pengguna di terminal. Selalu mengembalikan nilai sebagai string.
    ```python
    name = input("What is your name? ")
    ```

## Struktur Kontrol Aliran

### Pernyataan Kondisional (`if`/`elif`/`else`)

Digunakan untuk membuat keputusan dalam program berdasarkan kondisi.
*   `if condition:`: Blok kode dieksekusi jika kondisi `True`.
*   `elif condition:`: (Singkatan dari "else if") Blok kode dieksekusi jika kondisi `if` sebelumnya `False` dan kondisi `elif` ini `True`. Anda dapat memiliki banyak `elif`.
*   `else:`: Blok kode dieksekusi jika semua kondisi `if` dan `elif` sebelumnya `False`.
*   **Penting**: Blok kode didefinisikan oleh indentasi.

### Pernyataan `match`/`case` (Python 3.10+)

Digunakan untuk membandingkan nilai dengan beberapa pola dan mengeksekusi blok kode yang cocok.
*   Mendukung pola `OR` (misalnya, `"speak" | "say_hi"`).
*   Mendukung kondisi (`if`) di dalam `case`.
*   `_` adalah *wildcard* yang selalu cocok (seperti `default` atau `else`).
    ```python
    command = "run"
    match command:
        case "run":
            print("The robot started to run 🏃‍♂️")
        case "speak" | "say_hi":
            print("The robot said hi 🗣️")
        case code if command.isdigit():
            print(f"The robot execute code: {code}")
        case _:
            print("Invalid command ❌")
    # Output: "The robot started to run 🏃‍♂️"
    ```

### Perulangan `while`

Mengulang blok kode berkali-kali selama kondisi tertentu `True`.
*   Penting untuk memperbarui variabel yang memengaruhi kondisi agar perulangan tidak menjadi tak terbatas (infinite loop).
    ```python
    i = 1
    while i <= 5:
        print(i)
        i += 1 # Sama dengan i = i + 1
    ```

### Perulangan `for`

Mengulang melalui item dalam urutan (seperti daftar, string, atau objek *iterable* lainnya).
*   Seringkali lebih ringkas dan mudah dibaca daripada `while` untuk iterasi melalui koleksi.
    ```python
    numbers = [1, 2, 3, 4, 5]
    for item in numbers:
        print(item)
    ```
*   **`range()` Fungsi**: Menghasilkan urutan angka.
    *   `range(stop)`: Menghasilkan angka dari `0` hingga `stop-1`.
    *   `range(start, stop)`: Menghasilkan angka dari `start` hingga `stop-1`.
    *   `range(start, stop, step)`: Menghasilkan angka dari `start` hingga `stop-1` dengan peningkatan `step`.
    *   `range()` mengembalikan objek `range` (sebuah *iterable*), bukan daftar.
    ```python
    for i in range(5): # 0, 1, 2, 3, 4
        print(i)
    for i in range(4, 8): # 4, 5, 6, 7
        print(i)
    for i in range(4, 8, 2): # 4, 6
        print(i)
    ```
*   **`enumerate()` Fungsi**: Digunakan dalam perulangan `for` untuk mendapatkan indeks dan nilai dari setiap item dalam koleksi.
    ```python
    animals = ["dog", "cat", "mouse"]
    for i, value in enumerate(animals):
        print(i, value)
    # Output:
    # 0 dog
    # 1 cat
    # 2 mouse
    ```

### Penanganan Pengecualian (Exception Handling)

Mengelola kesalahan yang terjadi selama eksekusi program menggunakan blok `try`/`except`.
*   `try`: Kode yang mungkin menimbulkan pengecualian ditempatkan di sini.
*   `except ExceptionType as e`: Menangkap pengecualian dari tipe `ExceptionType`. Anda dapat menangkap beberapa tipe pengecualian atau semua pengecualian.
*   `else`: (Opsional) Blok kode yang dieksekusi jika tidak ada pengecualian yang terjadi di blok `try`.
*   `finally`: (Opsional) Blok kode yang selalu dieksekusi, terlepas dari apakah pengecualian terjadi atau tidak. Berguna untuk membersihkan sumber daya.
*   `raise`: Digunakan untuk secara manual menimbulkan pengecualian.
    ```python
    try:
        # Kode yang mungkin menimbulkan kesalahan
        result = 10 / 0
    except ZeroDivisionError:
        print("Tidak bisa membagi dengan nol!")
    except TypeError:
        print("Tipe data salah!")
    else:
        print("Tidak ada kesalahan terjadi.")
    finally:
        print("Eksekusi selesai.")
    ```

### Pernyataan `with`

Menyediakan cara yang bersih untuk mengelola sumber daya (seperti file) yang perlu ditutup setelah digunakan, memastikan sumber daya dilepaskan bahkan jika terjadi kesalahan.
```python
with open("myfile.txt", "w") as f:
    f.write("Hello, world!")
# File f secara otomatis ditutup setelah blok 'with' selesai
```

## Koleksi (Complex Types)

Python memiliki beberapa tipe data kompleks untuk menyimpan koleksi objek.

### Daftar (Lists)

**Daftar** adalah urutan objek yang **terurut** dan **dapat diubah** (mutable). Didefinisikan menggunakan kurung siku `[]`.
*   **Akses Elemen**: Menggunakan indeks (dimulai dari `0`).
*   **Indeks Negatif**: Mengakses elemen dari akhir daftar (`-1` untuk elemen terakhir).
*   **Mengubah Elemen**: Elemen dapat diubah dengan menugaskan nilai baru ke indeks tertentu.
    ```python
    names = ["John", "Bob", "Mosh", "Sam", "Mary"]
    print(names[0]) # => "John"
    print(names[-1]) # => "Mary"
    names[0] = "Jon"
    print(names) # => ["Jon", "Bob", "Mosh", "Sam", "Mary"]
    ```
*   **Slicing**: Mengambil sebagian dari daftar. Sintaks `list[start:end]` (indeks `end` tidak termasuk).
    *   `list[::step]`: Mengambil elemen dengan langkah tertentu.
    *   `list[::-1]`: Membalik daftar.
    *   Slicing mengembalikan daftar baru, tidak mengubah daftar asli.
    ```python
    names[0:3] # => ["Jon", "Bob", "Mosh"]
    ```
*   **Metode Daftar**:
    *   `list.append(item)`: Menambahkan item ke akhir daftar.
    *   `list.insert(index, item)`: Menyisipkan item pada indeks tertentu.
    *   `list.remove(item)`: Menghapus kemunculan pertama dari item.
    *   `list.clear()`: Menghapus semua item dari daftar.
    *   `del list[index]`: Menghapus elemen pada indeks tertentu.
    *   `list.pop()`: Menghapus dan mengembalikan item terakhir.
    *   `list.index(item)`: Mengembalikan indeks kemunculan pertama dari item.
    *   `list.extend(another_list)`: Menambahkan semua item dari daftar lain ke daftar saat ini.
*   **Operator `in`**: Memeriksa apakah item ada dalam daftar, mengembalikan boolean.
*   **`len(list)`**: Fungsi bawaan untuk mendapatkan jumlah item dalam daftar.

### Tuple

**Tuple** mirip dengan daftar, tetapi **tidak dapat diubah** (immutable). Didefinisikan menggunakan tanda kurung `()`.
*   Tidak dapat mengubah, menambahkan, atau menghapus elemen setelah dibuat.
*   Tuple dengan satu elemen memerlukan koma setelah elemen tersebut, misalnya `(1,)`, jika tidak, itu akan dianggap sebagai integer.
*   **Metode Tuple**: Hanya memiliki `count()` (menghitung kemunculan elemen) dan `index()` (mengembalikan indeks elemen).
*   Digunakan ketika Anda ingin memastikan bahwa urutan data tidak akan dimodifikasi secara tidak sengaja.
*   **Unpacking Tuple**: Elemen tuple dapat ditugaskan ke beberapa variabel.
    ```python
    a, b, c = (1, 2, 3) # a=1, b=2, c=3
    d, e = e, d # Cara mudah untuk menukar nilai
    ```

### Kamus (Dictionaries)

**Kamus** menyimpan pemetaan dari **kunci** ke **nilai** (key-value pairs). Didefinisikan menggunakan kurung kurawal `{}`.
*   **Kunci** harus berupa tipe data yang **tidak dapat diubah** (immutable) (misalnya, integer, float, string, tuple).
*   **Nilai** dapat berupa tipe data apa pun.
*   **Akses Nilai**: Menggunakan kunci dalam kurung siku `[]`"].
    *   Mengakses kunci yang tidak ada akan menimbulkan `KeyError`.
    *   Gunakan `dict.get(key, default_value)` untuk menghindari `KeyError` dan memberikan nilai *default* jika kunci tidak ditemukan.
*   **Menambahkan/Memperbarui**: `dict[key] = value` atau `dict.update({key: value})`.
*   **`dict.setdefault(key, default_value)`**: Menyisipkan kunci-nilai hanya jika kunci belum ada.
*   **Menghapus**: `del dict[key]`.
*   **Melihat Kunci/Nilai**:
    *   `dict.keys()`: Mengembalikan objek *iterable* dari semua kunci.
    *   `dict.values()`: Mengembalikan objek *iterable* dari semua nilai.
    *   Urutan kunci dijamin sesuai urutan penyisipan sejak Python 3.7.
*   **Operator `in`**: Memeriksa apakah kunci ada dalam kamus.

### Set

**Set** adalah koleksi item yang **tidak terurut** dan **unik** (tidak ada duplikat). Didefinisikan menggunakan kurung kurawal `{}` atau fungsi `set()`.
*   Elemen set harus berupa tipe data yang **tidak dapat diubah**.
*   **Menambahkan**: `set.add(item)`.
*   **Operasi Set**:
    *   `set1 & set2`: Irisan (intersection).
    *   `set1 | set2`: Gabungan (union).
    *   `set1 - set2`: Selisih (difference).
    *   `set1 ^ set2`: Selisih simetris (symmetric difference).
*   **Operator `in`**: Memeriksa apakah item ada dalam set.
*   `set.copy()`: Membuat salinan dangkal dari set.

## Fungsi

**Fungsi** adalah blok kode yang terorganisir dan dapat digunakan kembali untuk melakukan satu tindakan terkait.

### Mendefinisikan Fungsi

Gunakan kata kunci `def`, diikuti dengan nama fungsi, tanda kurung `()`, dan titik dua `:`.
*   Parameter (argumen) didefinisikan di dalam tanda kurung.
*   Gunakan `return` untuk mengembalikan nilai dari fungsi.
    ```python
    def greet(name):
        return f"Hello, {name}!"
    ```

### Memanggil Fungsi

Panggil fungsi dengan namanya diikuti tanda kurung `()` dan berikan argumen yang diperlukan.
*   **Argumen Kata Kunci (Keyword Arguments)**: Argumen dapat diberikan dengan nama parameter, memungkinkan urutan yang fleksibel.
    ```python
    greet(name="Alice")
    ```

### Argumen Variabel

*   **`*args` (Positional Arguments)**: Mengumpulkan argumen posisi yang tidak ditentukan ke dalam *tuple*.
    ```python
    def varargs(*args):
        return args
    varargs(1, 2, 3) # => (1, 2, 3)
    ```
*   **`**kwargs` (Keyword Arguments)**: Mengumpulkan argumen kata kunci yang tidak ditentukan ke dalam kamus.
    ```python
    def keyword_args(**kwargs):
        return kwargs
    keyword_args(big="foot", loch="ness") # => {"big": "foot", "loch": "ness"}
    ```
*   **Membongkar Argumen (Unpacking Arguments)**: Saat memanggil fungsi, `*` dapat membongkar *tuple* atau daftar menjadi argumen posisi, dan `**` dapat membongkar kamus menjadi argumen kata kunci.

### Mengembalikan Beberapa Nilai

Fungsi dapat mengembalikan beberapa nilai sebagai *tuple*.
```python
def swap(x, y):
    return y, x # Mengembalikan tuple (y, x)
```

### Lingkup Variabel (Variable Scope)

*   **Lingkup Lokal**: Variabel yang didefinisikan di dalam fungsi hanya dapat diakses di dalam fungsi tersebut.
*   **Lingkup Global**: Variabel yang didefinisikan di luar fungsi dapat diakses di mana saja.
*   Kata kunci `global` digunakan untuk secara eksplisit menyatakan bahwa Anda ingin memodifikasi variabel global dari dalam fungsi.
*   Kata kunci `nonlocal` digunakan dalam fungsi bersarang untuk memodifikasi variabel di lingkup penutup (bukan global).

### Fungsi Kelas Satu (First-Class Functions)

Dalam Python, fungsi adalah objek kelas satu, artinya mereka dapat:
*   Ditugaskan ke variabel.
*   Diteruskan sebagai argumen ke fungsi lain.
*   Dikembalikan sebagai nilai dari fungsi lain (membentuk *closure*).

### Fungsi Anonim (`lambda`)

**Fungsi `lambda`** adalah fungsi kecil, anonim, satu baris. Mereka terbatas pada satu ekspresi.
```python
(lambda x: x > 2)(3) # => True
```

### Fungsi Tingkat Tinggi (Higher-Order Functions)

Fungsi yang menerima fungsi lain sebagai argumen atau mengembalikan fungsi sebagai hasilnya.
*   **`map(func, iterable)`**: Menerapkan fungsi ke setiap item dalam *iterable* dan mengembalikan *iterator* dari hasilnya))"].
*   **`filter(func, iterable)`**: Membangun *iterator* dari elemen-elemen *iterable* yang untuknya fungsi mengembalikan `True`))"].

### List Comprehensions

Menyediakan cara ringkas untuk membuat daftar baru dari daftar yang sudah ada. Juga ada *set comprehensions* dan *dictionary comprehensions*.
```python
[x * 2 for x in [1, 2, 3]] # => [2, 4, 6]
{x: x**2 for x in range(5)} # => {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## Modul

**Modul** adalah file Python (`.py`) yang berisi definisi dan pernyataan Python. Mereka memungkinkan Anda untuk mengatur kode secara logis dan menggunakannya kembali.
*   **`import module_name`**: Mengimpor seluruh modul. Anda kemudian mengakses isinya dengan `module_name.item`.
*   **`from module_name import item`**: Mengimpor item tertentu (fungsi, kelas, variabel) dari modul secara langsung.
*   **`import module_name as alias`**: Mengimpor modul dengan nama alias yang lebih pendek.
*   `dir(module_name)`: Menampilkan semua fungsi dan atribut yang didefinisikan dalam modul.

## Kelas (Object-Oriented Programming)

**Kelas** adalah cetak biru untuk membuat objek (instance). Mereka memungkinkan Anda untuk mengelompokkan data (atribut) dan fungsionalitas (metode) bersama.

### Mendefinisikan Kelas

Gunakan kata kunci `class`, diikuti dengan nama kelas (konvensi: huruf kapital awal).
```python
class Human:
    # Atribut kelas, dibagikan oleh semua instance
    species = "H. sapiens"

    # Konstruktor: dipanggil saat objek dibuat
    def __init__(self, name):
        self.name = name # Atribut instance
        self._age = 0    # Konvensi: _ menunjukkan atribut internal

    # Metode instance: mengambil 'self' sebagai argumen pertama
    def say(self, msg):
        print(f"{self.name}: {msg}")

    # Metode kelas: mengambil 'cls' (kelas itu sendiri) sebagai argumen pertama
    @classmethod
    def get_species(cls):
        return cls.species

    # Metode statis: tidak mengambil 'self' atau 'cls'
    @staticmethod
    def grunt():
        return "*grunt*"

    # Properti: mengubah metode menjadi atribut yang dapat diakses
    @property
    def age(self):
        return self._age

    @age.setter
    def age(self, age):
        self._age = age

    @age.deleter
    def age(self):
        del self._age
```

### Membuat dan Menggunakan Objek

*   **Instansiasi**: Membuat objek dari kelas.
    ```python
    i = Human(name="Ian")
    i.say("hi") # => "Ian: hi"
    ```
*   **Atribut Kelas**: Dibagikan oleh semua instance. Dapat diakses melalui kelas atau instance.
*   **Atribut Instance**: Unik untuk setiap objek. Didefinisikan di `__init__` menggunakan `self.attribute_name`.
*   **Metode Instance**: Fungsi yang beroperasi pada instance. Argumen pertama selalu `self` (merujuk pada instance itu sendiri).
*   **Metode Kelas**: Beroperasi pada kelas itu sendiri, bukan instance. Ditandai dengan `@classmethod` dan mengambil `cls` sebagai argumen pertama.
*   **Metode Statis**: Tidak beroperasi pada instance atau kelas. Ditandai dengan `@staticmethod`.
*   **Properti (`@property`)**: Menyediakan cara untuk mengakses metode seolah-olah itu adalah atribut, memungkinkan kontrol atas cara atribut dibaca, ditulis, atau dihapus.

### Pewarisan (Inheritance)

**Pewarisan** memungkinkan kelas baru (kelas anak/turunan) untuk mewarisi atribut dan metode dari kelas yang sudah ada (kelas induk/dasar).
*   Kelas anak didefinisikan dengan kelas induk sebagai parameter: `class Child(Parent):`.
*   **`super().__init__()`**: Digunakan dalam konstruktor kelas anak untuk memanggil konstruktor kelas induk, memastikan atribut induk diinisialisasi.
*   Kelas anak dapat **menimpa (override)** atribut dan metode induk.
*   **Pewarisan Berganda (Multiple Inheritance)**: Kelas dapat mewarisi dari beberapa kelas induk. Urutan Resolusi Metode (Method Resolution Order/MRO) menentukan urutan pencarian atribut/metode.
    *   `ClassName.__mro__` menunjukkan MRO.

### `if __name__ == "__main__":`

Blok kode ini hanya akan dieksekusi ketika skrip dijalankan sebagai program utama, bukan saat diimpor sebagai modul.

## Konsep Lanjutan

### Generator

**Generator** adalah fungsi yang mengembalikan *iterator* yang menghasilkan urutan nilai satu per satu menggunakan kata kunci `yield`. Mereka hemat memori karena menghasilkan nilai sesuai permintaan, bukan membangun seluruh urutan dalam memori sekaligus.
```python
def double_numbers(iterable):
    for i in iterable:
        yield i + i

for i in double_numbers(range(1, 5)): # range() juga generator
    print(i) # => 2, 4, 6, 8
```
*   **Generator Comprehensions**: Sintaks ringkas untuk membuat generator, mirip dengan *list comprehensions* tetapi menggunakan tanda kurung `()`.
    ```python
    values = (-x for x in [1,2,3,4,5])
    ```

### Dekorator (Decorators)

**Dekorator** adalah bentuk "gula sintaksis" yang memungkinkan Anda untuk memodifikasi atau memperluas fungsionalitas fungsi atau metode tanpa mengubah kode aslinya secara langsung.
*   Dekorator adalah fungsi yang mengambil fungsi lain sebagai argumen dan mengembalikan fungsi baru.
*   Sintaks `@decorator_name` ditempatkan di atas definisi fungsi.
    ```python
    def log_function(func):
        def wrapper(*args, **kwargs):
            print(f"Entering function {func.__name__}")
            result = func(*args, **kwargs)
            print(f"Exiting function {func.__name__}")
            return result
        return wrapper

    @log_function
    def my_function(x, y):
        return x + y

    my_function(1, 2)
    # Output:
    # Entering function my_function
    # Exiting function my_function
    ```
*   **`@wraps` dari `functools`**: Penting untuk digunakan dalam dekorator untuk mempertahankan metadata fungsi asli (seperti `__name__` dan `__doc__`).