# Function

Di matematika, fungsi adalah proses yang merelasikan antara sebuah masukan (input) dan keluaran (output). Pada Python, selain fungsi relasi tersebut, fungsi juga adalah salah satu cara untuk mengorganisasikan kode - dengan tujuan akhir kode dapat digunakan kembali (reusability).

Beberapa syarat umum fungsi adalah modularisasi dan fungsionalitasnya. Jadi sebaiknya fungsi hanya memiliki satu kegunaan spesifik namun dapat digunakan kembali. Fungsi-fungsi umum telah disediakan oleh Python misalnya print(). Namun Anda dapat selalu mendefinisikan fungsi Anda sendiri.

## Return

Pernyataan return [expression] akan membuat eksekusi program keluar dari fungsi saat itu, sekaligus mengembalikan nilai tertentu. Nilai return yang tidak mengembalikan (ekspresi) nilai bersifat sama dengan contoh di bawah ini. 

~~~
return None
~~~

Contoh fungsi dengan return:

~~~
def kali(angka1, angka2):
    # Kalikan kedua parameter
    hasil = angka1 * angka2
    print('Dicetak dari dalam fungsi: {}'.format(hasil))
    return hasil
 
# Panggil fungsi kali
keluaran = kali(10, 20);
print('Dicetak sebagai kembalian: {}'.format(keluaran))
~~~

Saat dipanggil:

~~~
Dicetak dari dalam fungsi: 200

Dicetak sebagai kembalian: 200
~~~

## Pass by reference vs value

Seluruh parameter (argumen) pada bahasa Python bersifat “passed by reference”. Artinya saat Anda mengubah sebuah variabel, maka data yang mereferensi padanya juga akan berubah, baik di dalam fungsi, maupun di luar fungsi pemanggil. Kecuali jika anda melakukan operasi assignment yang akan mengubah reference parameter.

Contohnya:

~~~
def ubah(list_saya):
    list_saya.append([1, 2, 3, 4])
    print('Nilai di dalam fungsi: {}'.format(list_saya))
 
# Panggil fungsi ubah
list_saya = [10, 20, 30]
ubah(list_saya)
print('Nilai di luar fungsi: {}'.format(list_saya))
~~~

Dapat dilihat dalam kode diatas, objek mylist yang direferensi adalah sama. Sehingga saat melakukan perubahan, maka perubahannya terjadi pada mylist baik didalam maupun diluar fungsi ubah:

~~~
Nilai di dalam fungsi:  [10, 20, 30, [1, 2, 3, 4]]
Nilai di luar fungsi:  [10, 20, 30, [1, 2, 3, 4]]
~~~

Namun Anda harus berhati-hati karena assignment variabel bernama sama dengan parameter, berarti membuat variabel baru dalam scope lokal dan tidak terkait dengan variabel global.

~~~
def ubah(list_saya):
    "Deklarasi Variabel list_saya berikut hanya dikenali (berlaku) di dalam fungsi ubah"
    list_saya = [1, 2, 3, 4] 
    print ('Nilai di dalam fungsi: {}'.format(list_saya))
 
# Panggil fungsi ubah
list_saya = [10, 20, 30]
ubah(list_saya)
print('Nilai di luar fungsi: {}'.format(list_saya))
~~~

Variabel mylist dibuat kembali versi localnya dalam fungsi ubah dengan operator assignment (sama dengan), sehingga nilai mylist akan berbeda karena bersifat lokal dalam fungsi ubah saja. Hasilnya akan sebagai berikut:

~~~
Nilai di dalam fungsi:  [1, 2, 3, 4]
Nilai di luar fungsi: [10, 20, 30]
~~~

## Argumen dan Parameter Fungsi

Apa perbedaan Argumen dan Parameter fungsi? Menurut [FAQ Programming di dokumentasi Python](https://docs.python.org/3/faq/programming.html#what-is-the-difference-between-arguments-and-parameters), adalah sebagai berikut:

>Parameters are defined by the names that appear in a function definition, whereas arguments are the values actually passed to a function when calling it. Parameters define what types of arguments a function can accept.

## Argumen yang dapat dikirimkan pada fungsi

Sebagai nilai yang akan dimasukkan pada saat fungsi dipanggil, ada dua jenis argumen:

* Keyword Argument, yakni argumen yang disertai identifier atau nama parameter yang secara eksplisit disebutkan. Hal ini termasuk jika kita mengirimkan nilai melalui dictionary yang diawali dua tanda * (**). 
* Positional Argument, yakni argumen selain keyword argument. Jika kita mengirimkan variabel bersifat iterable, maka harus diawali tanda *

Contoh:

~~~
#Keyword Argument

daftar(tanggal=1, bulan='Januari', tahun=2020)
daftar(**{'tanggal': 1, 'bulan': 'Januari', 'tahun'=2020})

#Positional Argument


daftar(1,'Januari',2020)
daftar(*(1, 'Januari, 2020))
~~~

Sintaksis prefix * digunakan sebagai penanda iterable di Python, sedangkan prefix ** digunakan sebagai penanda kontainer/dictionary.

Kontainer (Dictionary) ini bisa bersifat opsional, artinya tidak wajib diisi (boleh kosong), jika memang tidak ada argumen yang perlu ditambahkan. Pada saat diisi, seperti layaknya Dictionary dapat memiliki jumlah/panjang yang dinamis, dengan pasangan kunci-nilai (key-value) yang bervariasi. 

## Susunan/Urutan Parameter Fungsi

Terdapat 5 kemungkinan susunan/urutan parameter fungsi menurut dokumentasi Python:

* positional-or-keyword: Anda bisa menuliskan argumen sebagai keyword argument atau positional argument.

~~~
def kali(nilai1, nilai2=None, nilai3): ...
~~~

* positional-only: Anda menentukan bahwa argumen tertentu hanya dapat diletakkan di posisi tertentu. Hal ini dilakukan dengan cara mendeklarasi posisi utama kemudian diikuti tanda /. Seperti pada contoh berikut, nilai1 dan nilai2 merupakan positional only (harus diletakkan pada posisi tersebut):

~~~
def (nilai1, nilai2, /, nilai3): ...
~~~

* keyword-only: Anda menentukan bahwa argumen tertentu harus disupply dalam bentuk keyword argument. specifies an argument that can be supplied only by keyword. Hal ini dilakukan dengan cara mendeklarasi satu buah var-positional argument diikuti tanda *. Seperti pada contoh berikut, nilai2 dan nilai3 merupakan keyword-only (harus dikirim dengan keyword):

~~~
def func(arg, *, kw_only1, kw_only2): ...
~~~

* var-positional dan var-keyword: Anda menentukan bahwa ada beberapa positional argument dan ada beberapa keyword argument yang akan Anda proses. var-positional ditandai dengan awalan * (iterable) dan var-keyword ditandai dengan awalan ** (dictionary). Contohnya dengan *args yang bersifat var-positional dan **kwargs yang berupa var-keyword.

~~~
def func(*args, **kwargs): ...
~~~

Jika ada argumen posisi dinamis dan argumen kata kunci (keyword) dinamis, maka urutannya adalah argumen posisi dahulu, baru argumen kata kunci. Contoh penggunaan var-positional dan var-keyword pada sebuah berkas python adalah sebagai berikut:

~~~
def printinfo(*args, **kwargs):
    for a in args:
        print('argumen posisi {}'.format(a))
    for key, value in kwargs.items():
        print('argumen kata kunci {}:{}'.format(key, value))
 
 
# Panggil printinfo
printinfo()
printinfo(1, 2, 3)
printinfo(i=7, j=8, k=9)
printinfo(1, 2, j=8, k=9)
printinfo(*(2, 3), **{'i':7, 'j':8})
~~~

Output:

~~~
# printinfo() --> kosong

argumen posisi 1
argumen posisi 2
argumen posisi 3

argumen kata kunci i:7
argumen kata kunci j:8
argumen kata kunci k:9

argumen posisi 1
argumen posisi 2
argumen kata kunci j:8
argumen kata kunci k:9

argumen posisi 2
argumen posisi 3
argumen kata kunci i:7
argumen kata kunci j:8
~~~

## Fungsi Anonim

Fungsi Anonim (anonymous) tidak dideklarasikan seperti halnya fungsi pada umumnya dengan kata kunci def, melainkan menggunakan kata kunci (keyword) lambda. Sebuah fungsi lambda dapat menerima argumen dalam jumlah berapa pun, namun hanya mengembalikan satu nilai expression. Fungsi Lambda tidak dapat memuat perintah atau ekspresi lainnya, misalnya tidak bisa melakukan print.

Fungsi lambda bersifat mandiri, memiliki namespace-nya sendiri, dan tidak dapat mengakses nilai apapun selain yang berada dalam parameter list dan variabel global. Meskipun mirip, Lambda tidak dapat disamakan dengan inline statement pada bahasa C/C++.

Sintaks:

~~~
lambda [arg1 [,arg2,.....argn]]:expression
~~~

Contoh penggunaannya jika kita bandingkan dengan fungsi kali yang berada di modul sebelumnya

~~~
kali = lambda nilai1, nilai2: nilai1 * nilai2;
print ("Hasil : ", kali( 11, 21 ))
print ("Hasil : ", kali( 2, 2 ))
~~~

Hasilnya

~~~
Hasil : 231
Hasil : 4
~~~

## Menulis Modul

Menuliskan modul pada bahasa Python dapat dimulai dengan menuliskan definisi fungsi, kelas, dan variabel yang dapat digunakan kembali pada program lainnya. Misalkan saja kita membuat berkas hello.py yang akan kita panggil di berkas lain.

~~~
# hello.py

# Define a function
def world():
    print("Hello, World!")
~~~

Jika hello.py dijalankan, maka program tidak akan menjalankan apapun karena world() hanya berupa definisi fungsi, kita belum memanggilnya. Jika kita biasanya memanggil sebuah fungsi dari berkas yang sama di bagian main, kali ini kita akan membuat berkas lain main.py yang seolah mengimpor hello.py. Pastikan hello.py dan main.py berada dalam satu direktori agar dapat diimpor dan dipanggil.

~~~
#main.py

#impor
import hello
#panggil
hello.world()
~~~

Saat memanggil sebuah fungsi dari modul yang kita impor, jangan lupa untuk menambahkan nama modulnya diikuti tanda titik, baru fungsi yang akan kita panggil. Dalam hal ini karena kita mengimpor hello.py, maka cukup kita tulis import hello, dan saat memanggilnya dengan hello.world(). Selain itu, kita juga dapat menggunakan from ... import ..., dalam hal ini adalah from hello import world dan memanggil fungsinya langsung yakni world().

Sekarang, saat memanggil main.py, maka akan menghasilkan:

~~~
Hello, World!
~~~

## Menambahkan variabel

Menambahkan variabel pada modul hello, tambahkan variabel nama, misalnya Dicoding.

~~~
#hello.py

def world():
    print("Hello, World!")
nama = "Dicoding"
~~~

Berikutnya, kita coba cetak variabel nama.

~~~
#main.py

#impor
import hello
 
#panggil
hello.world()
#cetak
print(hello.nama)
~~~

Saat Dijalankan:

~~~
Hello, World!
Dicoding
~~~

## Menambahkan kelas

Contoh yang lain, mari tambahkan kelas di modul hello. Kita akan membuat kelas Reviewer dengan atribut nama dan kelas, serta fungsi review() yang akan mencetak atribut yang telah didefinisikan.

~~~
#hello.py

def world():
    print("Hello, World!")
nama = "Dicoding"
class Reviewer:
    def __init__(self, nama, kelas):
        self.nama = nama
        self.kelas = kelas
    def review(self):
        print("Reviewer " + self.nama + " bertanggung jawab di kelas " + self.kelas)
~~~

Tambahkan kelas pada main.py.

~~~
#main.py

#impor
import hello
#panggil
hello.world()
#cetak
print(hello.nama)
#review
diko = hello.Reviewer("Diko", "Python")
diko.review()
~~~

Seperti umumnya kelas pada bahasa pemrograman lainnya, Fungsi dan Atributnya dapat diakses setelah kita melakukan instansiasi. Fungsi Review adalah fungsi yang melekat pada kelas Reviewer. Kita juga dapat memanggil diko.Nama atau diko.Kelas sebagai atribut yang melekat di kelas tersebut.

Output:

~~~
Hello, World!
Dicoding
Reviewer Diko bertanggung jawab di kelas Python
~~~

Lihat kedua variabel "nama" yang dapat menghasilkan dua nilai berbeda, karena nama yang pertama (hello.nama) melekat pada modul, sementara diko. Nama adalah atribut nama pada kelas Reviewer.

## Mengakses Modul dari Folder Lain

### Menambahkan path folder

Opsi ini dipilih umumnya di tahap awal pengembangan, sebagai solusi temporer. Untuk mengetahui path pemanggilan utama, Anda perlu bantuan dari modul sys yang sudah tersedia. Impor modul sys di main program dan gunakan fungsi sys.path.append. Misalnya berkas hello.py kita berada di direktori /home/dicoding/ dan main.py di direktori lainnya. Anda cukup menambahkan path /home/dicoding pada main.py seperti di bawah:

~~~
import sys
sys.path.append('/home/dicoding')
import hello
…
~~~

### Menambahkan modul pada Python Path

Alternatif ini dapat dipilih saat Anda melakukan pemanggilan modul >1x. Pada intinya pilihan ini akan menambahkan modul yang Anda buat pada Path yang diperiksa oleh Python sebagai modul dan paket-paket bawaan. Anda dapat memanfaatkan sys.path kembali untuk mengetahui posisi Anda saat ini.

~~~
print(sys.path)
~~~

Anda mungkin akan menerima output seperti berikut, sangat bergantung dengan jenis environment Anda, tapi pilihlah (atau cobalah satu per satu) jika ada beberapa output.

~~~
'/home/dicoding/my_env/lib/python3.5/site-packages'
~~~

Pindahkan hello.py pada direktori di atas. Maka Ia akan dikenali sebagai sebuah modul yang dapat diimpor oleh siapa saja dalam environment tersebut.

Pada main_program.py cukup impor.

~~~
import hello
~~~

Pastikan path yang Anda assign tepat untuk menghasilkan pemanggilan yang tepat. Modul yang tersebar pada beberapa folder mungkin akan menghasilkan galat. Usahakan peletakan yang se-sederhana mungkin.