# Python Basic dan Style Guide

## Mode

Pada Python dikenal beberapa mode operasi: Interactive, Script (scripting), dan Notebook.

### Interactive

Berbeda dengan bahasa pemrograman lainnya, bahasa Python yang berbasis interpreter memungkinkan kita untuk menjalankan perintah secara interaktif. Mode ini dapat diakses di bagian bawah PyCharm atau dengan memanggil perintah python di command prompt/terminal.

Seluruh kode python dapat Anda jalankan secara berurutan pada sesi interaktif ini. Variabel juga akan tetap disimpan. Anda juga dapat memanggil (import) library. Sehingga salah satu penggunaan utama pada sesi interaktif ini adalah untuk rapid-prototyping.

### Script

Mode yang lain dan sering dipergunakan pada python adalah script (scripting). Pada mode ini kita menggunakan sebuah berkas teks (umumnya berekstensi .py) dan kemudian akan dieksekusi oleh compiler/interpreter.

### Notebook

Contoh: Jupyter.

### Alternatif

Ada beberapa tools online untuk menjalankan kode-kode Python. beberapa yang umum digunakan di industri antara lain IBM Watson Studio, Google Colab, glot.io, REPL.it, dan ideone.com.

## Style Guide

Berikut adalah beberapa style guide menulis kode Python dengan baik dan benar. Panduan gaya penulisan kode ini mengacu pada [PEP-008](https://www.python.org/dev/peps/pep-0008/). Beberapa proyek mungkin memiliki style guide tersendiri. Sejumlah contoh kode yang ditulis di halaman ini berupa pseudocode, bertujuan hanya untuk memberikan gambaran tentang panduan gaya penulisan kode saja.

Guido, pembuat bahasa Python, merasakan bahwa kode lebih sering dibaca dibandingkan ditulis. Oleh sebab itu, panduan ini lebih ditekankan untuk kemudahan membaca kode dan membuatnya konsisten pada (hampir) setiap proyek Python yang ada.

Namun demikian pada kasus-kasus tertentu, keputusan adanya modifikasi tetap pada penulis kodenya. Mungkin sebuah kode dapat terbaca lebih jelas walaupun tidak mengikuti satu atau lebih panduan dalam modul ini.

### Indentasi

Gunakan 4 spasi pada setiap tingkatan indentasi.

Python menggunakan indentasi untuk menulis kode bertingkat. Bahasa lain mungkin menggunakan statement tertentu (Begin, end - pascal), perbedaan baris atau kurung kurawal. Statement yang memiliki indentasi yang sama dan diletakkan secara berurutan dikenali sebagai blok statement oleh Python dan akan dijalankan secara berurutan.

### Baris Lanjutan

Seringkali, saat menulis kode, kita harus menggunakan baris lanjutan karena kode tidak cukup dituliskan dalam satu baris. Umumnya, kita dapat menggunakan tanda hubung, kurung, kurawal, atau seperti disarankan pada PEP-008, gunakan hanging indent. Beberapa panduan dalam menggunakan hanging indent dalam penulisan kode python adalah sebagai berikut:

~~~
# Opsi 1
# Rata kiri dengan kurung atau pemisah dengan argumen utama
foo = long_function_name(var_one, var_two,
                         var_three, var_four)
 
# Opsi 2
# Tambahkan indentasi ekstra - (level indentasi baru) untuk memisahkan parameter/argument dari bagian lainnya
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
 
# Opsi 3
# Hanging indents dengan penambahan level indentasi saja
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
~~~

### Kondisional (If)

Saat menulis pernyataan kondisional, misalnya IF, kita juga menemukan penulisan yang terkadang tidak cukup dituliskan dalam satu baris, atau menggunakan beberapa operand yang akan menyulitkan apabila digabung berturut-turut.

~~~
# Contoh kondisi visual yang tidak diubah/tanpa indentasi
if (sebuah kondisi dan
    kondisi yang lain):
    lakukanSesuatu()
 
# Tambahkan komentar
if (sebuah kondisi dan
    kondisi yang lain):
    #Mengingat Keduanya Benar, lakukan hal berikut
    lakukanSesuatu()
 
# Tambahkan ekstra indentasi pada baris lanjutan
if (sebuah kondisi dan
        kondisi yang lain):
    lakukanSesuatu()
~~~

### Kurung/siku penutup

Penempatan kurung atau siku penutup juga dapat diletakkan pada baris lanjutan, dengan mengikuti posisi karakter pertama yang bukan whitespace (non-whitespace character) pada baris sebelumnya:

~~~
my_list = [
    1, 2, 3,
    4, 5, 6,
    ]

result = some_function_that_takes_arguments(
    'a', 'b', 'c',
    'd', 'e', 'f',
)
~~~

### Tab atau spasi

Spasi adalah model yang disarankan PEP-008. Pengecualian pada kode yang sudah menggunakan tab/tabulasi sebelumnya. Python sejak versi 3 tidak memperbolehkan pencampuran antara Tab dan Spasi untuk indentasi. Anda disarankan untuk melakukan konversi kode untuk menggunakan spasi sepenuhnya.

Anda dapat menggunakan find-replace untuk mengganti tab, atau memanggil kode Anda yang berbasis Python 2 dengan opsi -t (warning) atau -tt (error) untuk mengetahui titik penggunaan tab dan spasi yang bercampur.

### Panjang baris maksimum

Batasi panjang kode setiap baris hingga 79 karakter. Untuk komentar atau dokumentasi, usahakan untuk tidak melebihi 72 karakter.

Dengan membatasi panjang baris maksimum, Anda akan memudahkan pengguna lain membuka >1 window editor secara berdampingan, misalnya untuk melakukan review atau perbandingan. Panjang kode setiap baris yang dibatasi akan memudahkan Anda jika menggunakan code review tools yang menunjukkan dua versi berbeda secara berdampingan.

Mengapa 79? Hal ini dicontohkan pada editor-editor dengan window-width yang terset pada 80 karakter. 1 karakter tersisa bisa berupa marker glyph atau whitespace. Pembatasan 79 karakter ini membuat editor terkecil sekalipun tidak akan merusak struktur dan keterbacaan kode Anda. Jika Anda atau tim mengalami kesulitan (misalnya karena struktur penamaan variabel) yang telah disepakati, cenderung melebihi batasan panjang karakter, Anda dapat melakukan kesepakatan atau konvensi yang berlaku pada kode Anda sendiri. Umumnya hingga 99 karakter per baris.

>Catatan
>>Python Standard Library selalu dikembangkan secara konservatif dan mempertahankan standar 79 karakter pada kode, dan 72 pada komentar/dokumentasi.

Beberapa dari Anda mungkin mengenal pemisahan menggunakan backslash (\), namun tidak disarankan untuk digunakan, kecuali memang diharuskan. Contohnya adalah penggunaan backslash pada statement with atau assert yang tidak dapat menggunakan implicit continuation.

~~~
with open('/path/to/some/file/you/want/to/read') as file_1, \
     open('/path/to/some/file/being/written', 'w') as file_2:
    file_2.write(file_1.read())
~~~

### Mengganti baris

Penggantian baris setelah operator binary memang pernah menjadi rekomendasi. Namun ternyata penggunaan metode ini membuat mata cepat lelah dan Anda perlu melakukan pengecekan ulang pada baris berbeda.

Untuk menyelesaikan masalah ini, dipilih pendekatan baris baru sebelum operator binary. Hal ini untuk mempermudah pembaca kode mengerti operasi yang dilakukan terhadap variabel berikutnya.

### Baris kosong

Anda disarankan untuk menambahkan dua baris kosong pada top level function dan class definitions. Kemudian untuk setiap deklarasi method, dipisahkan dengan satu baris kosong.

Anda juga dapat menambahkan baris kosong ini apabila dibutuhkan, misalnya untuk memisahkan gabungan beberapa fungsi yang memiliki fungsi terkait atau untuk meningkatkan keterbacaan kode. Pemisahan baris kosong tidak diperlukan jika deklarasi fungsi/method Anda bersifat satu baris (one-liner), umumnya untuk fungsi/method yang belum diimplementasikan secara penuh.

### File Encoding

Kode dalam inti Python, selalu menggunakan [encoding](https://id.wikipedia.org/wiki/Pengodean_karakter) UTF-8 (Python 3) atau ASCII (Python 2). Dalam hal ini, apabila dalam sebuah berkas tidak ditulis deklarasi encoding, maka berkas tersebut menggunakan encoding ASCII (Python 2) atau UTF-8 (Python 3). Dalam standard library, non-default encoding hanya digunakan untuk pengujian atau memberikan komentar/dokumentasi, misalnya nama penulis yang tidak menggunakan karakter ASCII.

Untuk Python 3 dan seterusnya, pada standard library hanya menggunakan karakter ASCII dan sebisa mungkin menggunakan kata-kata dalam Bahasa Inggris. Proyek yang menggunakan python 3 didorong untuk menggunakan standar yang sama. Lihat [PEP 3131](https://www.python.org/dev/peps/pep-3131).

### Saat melakukan import library, lakukan import setiap library pada baris berbeda.

~~~
Yes: import os
     import sys
 
No:  import sys, os
~~~

Kecuali, jika anda memerlukan lebih dari satu sub-library dari library yang sama.

~~~
from subprocess import Popen, PIPE
~~~

Import umumnya diletakkan pada bagian awal berkas. Setelah komentar dan dokumentasi tentang berkas tersebut (misalnya definisi kelas, dll), sebelum variabel global dan konstanta. Jika memungkinkan, kelompokkan import dalam urutan berikut:

1. Standard Library
2. Library Pihak Ketiga
3. Local/Library spesifik

### Tanda Petik

Petik tunggal (‘) dan petik ganda (“) dianggap sama oleh Python, dan tidak memiliki preferensi khusus untuk penggunaannya. Hal ini dikarenakan ada kemungkinan string yang memuat salah satunya. Anda disarankan untuk menggunakan salah satunya secara konsisten.

Docstring (dokumentasi kode/fungsi/method) pada Python didefinisikan dengan tiga tanda petik, disarankan tanda petik ganda (”””) pada awal dan akhir statement docstring.

### Whitespace pada Expressions dan Statements

Wajib dihindari penambahan whitespace yang tidak perlu.

Antara kurung, kurawal, kurung siku.

~~~
Yes: spam(ham[1], {eggs: 2})
No:  spam( ham[ 1 ], { eggs: 2 } )
~~~

Setelah koma, tanpa argumen lain setelahnya.

~~~
Yes: foo = (0,)
No:  bar = (0, )
~~~

Sebelum koma, titik dua, atau titik koma.

~~~
Yes: if x == 4: print x, y; x, y = y, x
No:  if x == 4 : print x , y ; x , y = y , x
~~~

Namun, jika Anda menggunakan titik dua/colon sebagai slice (sub-list), pastikan ia memiliki spasi/whitespace yang sama pada kedua sisinya.

~~~
Yes:
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
 
No:
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : upper]
ham[ : upper]
~~~

Saat memberikan parameter pada fungsi, sebelum kurung tidak boleh ada spasi.

~~~
Yes: spam(1)
No:  spam (1)
~~~

Saat memberikan parameter/index pada list, sebelum kurung siku tidak boleh ada spasi.

~~~
Yes: dct['key'] = lst[index]
No:  dct ['key'] = lst [index]
~~~

Saat membuat assignment pada variabel, sebaiknya tidak menambahkan whitespace yang tidak perlu.

~~~
Yes:
x = 1
y = 2
long_variable = 3
 
No:
x             = 1
y             = 2
long_variable = 3
~~~

### Rekomendasi lainnya

Hindari menambahkan whitespace di belakang statement apapun, utamanya di statement akhir dalam sebuah baris, karena whitespace tersebut tidak mudah dilihat.

Biasakan untuk menambahkan satu spasi baik di kiri maupun kanan untuk operasi berikut:

* Assignment (=),
* Augmented assignment (+=, -=etc.),
* Comparisons (==, <, >, !=, <>, <=, >=, in, not in, is, is not),
* Booleans (and, or, not).

Jika operator dengan berbagai tingkatan prioritas digunakan, letakkan whitespace pada operator-operator dengan prioritas terendah. Namun Anda juga dapat menyesuaikannya sendiri. 

>Catatan
>>Jangan pernah menggunakan >1 spasi dan gunakan spasi yang sama baik di sebelah kiri maupun kanan dari operator-operator binary Anda.

~~~
Yes:
i = i + 1
submitted += 1
x = x*2 - 1
hypot2 = x*x + y*y
c = (a+b) * (a-b)
 
No:
i=i+1
submitted +=1
x = x * 2 - 1
hypot2 = x * x + y * y
c = (a + b) * (a - b)
~~~

### Komentar

Dalam sebuah kode Python, Anda diajak untuk memastikan kode Anda terbaca oleh programmer lain. Salah satu caranya adalah dengan menggunakan fitur komentar untuk memberitahu fungsi atau informasi lain terkait kode Anda. Pastikan komentar Anda ter-update dan tidak mengalami kontradiksi dengan kode yang ada.

Umumnya, komentar dituliskan dalam kalimat utuh dengan memperhatikan penulisan (huruf besar di awal kalimat, huruf kecil saat diawali dengan identifier atau variabel, dan diakhiri titik di akhir kalimat). Anda juga bisa menggabungkan beberapa kalimat menjadi blok komentar dengan menambah dua spasi saat berganti kalimat dalam satu paragraf, kecuali pada kalimat terakhir.

Jika memungkinkan, tuliskan komentar dalam bahasa Inggris, kecuali Anda yakin bahwa pembaca komentar ini dipastikan mengerti bahasa Anda.

### Blok komentar

Blok komentar umumnya digunakan untuk menjelaskan fungsi utuh atau sub-fungsi yang mengikuti/berada di bawahnya. Blok komentar diindentasi setara dengan kode yang dijelaskan. Setiap barisnya diawali dengan # dan sebuah spasi serta setiap paragrafnya dimulai pada baris baru.

### Komentar Inline
Komentar Inline pada Python umumnya diletakkan pada baris yang sama dengan kode. Umumnya dipisahkan dan dirapikan dengan jarak dua spasi dari kode yang dimaksud, diawali # dan sebuah spasi. Komentar inline dapat juga digunakan di atas baris yang ingin diberikan komentar, agar tidak mengurangi jumlah karakter yang dapat dituliskan dalam sebuah baris. Untuk semua jenis komentar, jangan menuliskan komentar untuk hal yang sudah langsung dapat dibaca dari kodenya, seperti contoh berikut:

Tidak disarankan:

~~~
x = x + 1                 # Tambahkan x
~~~

Disarankan (kontekstual):

~~~
x = x + 1                 # Mengakomodasi layar ukuran Z
~~~

### Dokumentasi

Guideline untuk menuliskan dokumentasi (docstring) yang baik tersedia di [PEP 257](https://www.python.org/dev/peps/pep-0257). Kuncinya:

* Buatlah dokumentasi untuk semua modul, fungsi, kelas, dan method yang bersifat public atau akan diakses publik.
* Docstring tidak diwajibkan pada method yang tidak bersifat public, namun Anda disarankan menambahkan komentar tentang Apa saja yang dilakukan fungsi/modul ini beserta informasi lainnya yang mungkin diperlukan. Komentar ini diletakkan setelah baris def.

PEP 257 memberikan panduan detil yang dapat digunakan. Seperti yang sudah-sudah, Anda disarankan untuk menutup sebuah docstring yang lebih dari satu baris, pada baris baru berikutnya:

~~~
"""Return a foobang
Optional plotz says to frobnicate the bizbaz first.
"""
~~~

Untuk docstring satu baris, Anda disarankan untuk meletakkan penutup """ - nya pada baris yang sama.

Meskipun secara sintaksis Anda dapat menggantikan 3-tanda-kutip-dua """ dengan 3-tanda-kutip-satu ''', untuk penulisan komentar multi-baris, tetapi PEP 257 memberikan panduan gunakan 3-tanda-kutip-dua untuk dokumentasi (docstring).

