# Popular Library

## String 

Dokumentasi: https://docs.python.org/3/library/string.html.

String merupakan salah satu modul bawaan Python yang tidak perlu dideklarasikan. Modul yang sudah bawaan dari Python disebut [modul built-in](https://docs.python.org/3/library/stdtypes.html). Termasuk di dalam modul built in antara lain adalah string, list, range, boolean operator, dan sebagainya. Pada modul string terdapat fungsi-fungsi yang dapat dioperasikan pada variabel bertipe string seperti di bawah. 

* upper(): Ubah setiap huruf dalam string menjadi huruf kapital. 
* lower(): Ubah setiap huruf dalam string menjadi huruf kecil.
* split(): Pisahkan teks berdasarkan delimiter(karakter pemisah).
* title(): Jadikan setiap awal kata kapital.
* zfill(): Tambahkan nol di awal string sebanyak nilai yang ada pada parameter.

## OS

Dokumentasi: https://docs.python.org/3/library/os.html

Modul OS pada Python merupakan modul untuk fungsi-fungsi yang berkaitan dengan sistem operasi, misalnya open(), path(), getcwd(), dan fungsi lainnya. Modul ini memungkinkan Anda untuk memanfaatkan fungsi yang sama dan mengeksekusi fungsi terkait OS yang mungkin berbeda di setiap sistem operasi. Terdapat beberapa fitur yang hanya bekerja pada sistem operasi tertentu.

Contoh kode di bawah menunjukkan fungsi os.getcwd(). Fungsi ini akan mengembalikan string representasi dari Current Working Directory yaitu direktori di mana program Python kita berada. Fungsi ini berlaku di semua OS.

~~~
import os
print(os.getcwd())
~~~

## File Input/Output

Dokumentasi: https://docs.python.org/3/tutorial/inputoutput.html.

Modul Input/Output adalah modul yang berkaitan untuk fungsi yang mengurus masukan dan keluaran pada Python. Contoh fungsi yang ada pada modul ini adalah fungsi untuk menampilkan hasil dari program Python ke layar dan membaca teks yang kita ketik di keyboard.

Kode di bawah menunjukkan 2 contoh fungsi yang ada pada modul Input/Output yaitu membaca teks yang kita ketik di keyboard dan menampilkan teks tersebut.

~~~
string = raw_input("Masukkan sesuatu: ")
print "Input yang masuk adalah : ",  string
~~~

## Pickle

Dokumentasi: https://docs.python.org/3/library/pickle.html.

Jika Anda memiliki sebuah list yang ingin disimpan atau ditransmisikan tanpa khawatir bentuknya akan rusak atau kacau, Anda dapat memanfaatkan fungsi dari library pickle. Pickle merupakan fungsi Object Serialization pada Python. Pickling adalah istilah untuk mengubah objek menjadi byte stream, sedangkan Unpickling adalah perlakuan sebaliknya. 

Kode berikut adalah contoh bagaimana melakukan proses pickle pada sebuah object dictionary dan menyimpannya pada sebuah file.

~~~
import pickle
contoh_dictionary = {1:"6", 2:"2", 3:"f"}
pickle_keluar = open("dict.pickle","wb")
pickle.dump(contoh_dictionary, pickle_keluar)
pickle_keluar.close()
~~~

Kode berikut adalah contoh untuk mengekstraksi berkas pickle dan menaruhnya pada sebuah variabel.

~~~
pickle_masuk = open("dict.pickle","rb")
contoh_dictionary = pickle.load(pickle_masuk)
~~~

## JSON

Dokumentasi: https://docs.python.org/3/library/json.html.

Untuk serialization dengan bahasa lain, umumnya kita menggunakan JSON (JavaScript Object Notation) yang memiliki beberapa perbedaan karakteristik dengan pickle, yakni:

* JSON adalah format text-serialization dan umumnya menggunakan Unicode atau UTF-8. Sementara pickle bersifat binary serialization.
* JSON dapat dibaca dengan mudah oleh manusia, sementara pickle tidak.
* JSON dapat dioperasikan dan digunakan di luar ekosistem Python. Pickle adalah Python-specific.
* JSON secara default hanya dapat merepresentasikan subset dari built-in type pada Python.
* Pickle dapat merepresentasikan hampir (jika tidak seluruh) tipe Python dan secara default melakukan kompresi data.

Seperti yang telah disebutkan sebelumnya, JSON adalah format text yang ditujukan untuk serialization. Agar data dapat dengan mudah ditransmisikan antar berbagai sumber tanpa khawatir bentuknya kacau, menggunakan JSON adalah salah satu pilihan yang tepat.

JSON memiliki format yang hampir mirip dengan dictionary di mana data disimpan dengan format key & value pair. Namun tentunya JSON jauh lebih kompleks dari dictionary. Dapat dilihat dari contoh JSON untuk data pembelian di bawah. Dengan JSON kita dapat menyimpan data dengan lebih terorganisir. Sebuah key seperti children di bawah dapat memiliki sebuah dictionary baru yang berisi informasi terkait objek children tersebut tersebut.

Untuk membuat JSON sederhana ketik seperti kode di bawah.

~~~
import json
 
# contoh JSON:
x = '{ "nama":"Buchori", 
       "umur":22, 
       "Kota":"New York"}'
 
# parse  x:
y = json.loads(x)
 
print(y["umur"])
~~~

## Scrapper 

Dokumentasi urllib: https://docs.python.org/3/library/urllib.html

Dokumentasi beautifulsoup4: https://www.crummy.com/software/BeautifulSoup/bs4/doc/

Web scrapping adalah sebuah proses terotomasi untuk mendapatkan dan parsing data dari web. Disiplin seperti data science, business intelligence, dan lainnya mendapatkan banyak manfaat dari menganalisis data pada situs-situs yang ada di internet. Ada 2 buah library yang terkenal untuk web scraping yaitu urrlib dan beautifulsoup.

* Urrlibadalah library bawaan dari Python. Kode di bawah adalah contoh untuk memulai proses scraping pada situs dengan domain python.orgdan menampilkan isi dari tag title dari situs tersebut.

~~~
url = "http://python.org/"
page = urlopen(url)
html = page.read().decode("utf-8")
start_index = html.find("<title>") + len("<title>")
end_index = html.find("</title>")
title = html[start_index:end_index]
title
~~~

* Beautifulsoup adalah library yang penggunaanya lebih sederhana dari urrlib. Untuk menggunakan beautifulsoup Anda harus menginstalnya terlebih dahulu. Berikut adalah contoh penulisan kode beautifulsoup.

~~~
url = "http://python.org/"
page = urlopen(url)
html = page.read().decode("utf-8")
soup = BeautifulSoup(html, "html.parser")
soup.title
~~~

## Regex

Dokumentasi: https://docs.python.org/3/library/re.html

Regex atau regular expression adalah sebuah cara untuk mencari teks berdasarkan pola tertentu. Ketika kita ingin mencari sebuah kata dalam kamus, misalnya arti dari kata parsing, kita akan mencari kata tersebut di halaman yang yang memiliki kata dengan awalan p, atau pa. Regex bekerja dengan konsep yang sama. Pada regex, kita mencari sebuah kata atau kumpulan kata dengan memberikan pola yang kita inginkan. Contoh umum regex adalah pada email di mana kita dapat menggunakan regex untuk mengecek apakah karakter @ ada pada email atau tidak.

Contoh di bawah menunjukkan penggunaan regex. Pada variabel pattern di bawah, ^a berarti kita ingin mencari teks dengan awalan 'a', dan s$ berarti kita ingin mencari string berakhiran 's'.

~~~
import re
 
pola= '^a...s$'
string_tes= 'abyss'
hasil= re.match(pola, string_tes)
 
if hasil:
    print("Pencarian berhasil.")
else:
    print("Pencarian gagal.") 
~~~

## Argument Parser

Dokumentasi Getopt: https://docs.python.org/3.8/library/getopt.html

Dokumentasi ArgParse: https://docs.python.org/3.8/library/argparse.html

Argument parser bermanfaat jika kita ingin membuat program atau skrip kecil yang langsung menerima parameter pada saat pemanggilan program. Hal ini biasa digunakan dalam pemanggilan aplikasi atau skrip di CLI/terminal *nix-based misalnya linux dan MacOS. Contoh perintah dimaksud adalah:

~~~
python panggildicoding.py -o
~~~

Contoh dengan menggunakan ArgParse untuk menambahkan Argument yang bersifat opsional / tidak wajib:

~~~
#file: panggildicoding.py

import argparse
 
parser = argparse.ArgumentParser()
parser.add_argument('-o', '--output', action='store_true', help="tampilkan output")
args = parser.parse_args()
 
if args.output:
    print("Halo, ini merupakan sebuah output dari panggildicoding.py")
~~~

Maka pada saat dijalankan, terdapat beberapa hal yaitu:

* Berkas panggildicoding.py dapat menerima parameter -o atau --output.
* Jika kita memanggil berkas tanpa parameter -o maka berkas tidak akan menampilkan apapun.
* Jika kita memanggil dengan -o atau --output maka berkas akan menampilkan Halo, ini merupakan sebuah output dari panggildicoding.py.
* Jika kita memanggil --help, maka akan tampil help dengan penjelasan "tampilkan output".

Kita juga bisa membuat argumennya bersifat wajib. Modifikasi berkas panggildicoding.py menjadi seperti berikut:

~~~
import argparse
 
parser = argparse.ArgumentParser()
parser.add_argument('-n', '--nama', required=True, help="Masukkan Nama Anda")
args = parser.parse_args()
 
print("Terima kasih telah menggunakan panggildicoding.py, "+args.nama)
~~~

Maka pada saat dijalankan, terdapat beberapa hal yaitu:

* Berkas panggildicoding.py harus dipanggil dengan parameter -n atau --nama.
* Jika kita memanggil berkas tanpa parameter -n maka berkas akan meminta parameter n atau nama.
* Jika kita memanggil dengan -n NAMAKITA atau --nama NAMAKITA maka berkas akan menampilkan Terima kasih telah menggunakan panggildicoding.py NAMAKITA.
* Jika kita memanggil --help, maka akan tampil help dengan penjelasan "Masukkan Nama Anda".

Anda dapat mensuplai lebih dari satu argumen, dengan menambahkan parser.add_argument sejumlah yang Anda inginkan.