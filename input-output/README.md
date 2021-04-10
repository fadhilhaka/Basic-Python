# Input/Output 

## Output

### Print

~~~
print("Hello, World!")
~~~

Output:

~~~
Hello, World!
~~~

### Memasukkan nilai variabel pada string

Untuk memasukkan nilai variabel pada string, Python memiliki dua cara. Cara yang pertama adalah langsung menggabungkan variabel pada statement print().

~~~
x = 100
print('Nilai x adalah', x)
~~~

Output:

~~~
Nilai x adalah 100
~~~

Untuk menampilkan text (string), bisa menggunakan mekanisme string format. Misalnya yang pertama:

~~~
print('hai {}'.format('bro'))
~~~

Cara yang kedua mirip dengan sintaks C/C++, yakni menggunakan operator “%” yang ditambahkan dengan "argument specifiers", misalnya "%s" and "%d". Contohnya saat kita ingin menambahkan nama kita pada string hello:

~~~
nama = "Dicoding"
umur = 5
print("Umur %s adalah %d tahun." % (nama, umur))
~~~

Output:

~~~
Umur Dicoding adalah 5 tahun.
~~~

Contoh menambahkan objek selain string (otomatis dikonversi):

Beberapa argument specifier yang umum digunakan:

* %s - String
* %d - Integers
* %f - Bilangan Desimal
* %.<digit>f - Bilangan desimal dengan sejumlah digit angka dibelakang koma.
* %x/%X - Bilangan bulat dalam representasi Hexa (huruf kecil/huruf besar)

Contoh mencetak representasi Hexa (bilangan basis 16):

~~~
a, b = 10, 11
a, b
print('a: %x and b: %X' % (a, b))
~~~

Output:

~~~
(10, 11)
a: a and b: B
~~~

[String format](https://docs.python.org/id/3.8/library/string.html#format-specification-mini-language)

## Input

~~~
nilai = input('Masukkan angka : ')
~~~

Output:

~~~
Masukkan angka : 90
~~~

~~~
print(nilai)
~~~

Output:

~~~
'90'
~~~

Jika input merupakan string berisi ekspresi matematika, maka konversi dengan int() atau float() akan menghasilkan error. Anda dapat menggunakan fungsi eval() yang sekaligus juga berfungsi menyelesaikan ekspresi matematika.

## Command-line arguments

Python memungkinkan Anda untuk membuat sebuah "skrip" berupa deretan kode program kemudian disimpan dalam sebuah berkas dengan nama akhiran .py (misal: skrip.py).

Berkas ini dapat dipanggil sebagai skrip di konsol atau command prompt, serta dapat ditambahkan parameter tambahan saat memanggil skrip tersebut.

~~~
$ python test.py arg1 arg2 arg3
~~~

Hal ini difasilitasi oleh module sys yang telah dibawa secara default pada Python. Untuk menggunakannya, jangan lupa lakukan import terlebih dahulu:

~~~
import sys
~~~

Utamanya fungsi yang akan digunakan adalah sys.argv yang memuat seluruh argumen yang diterima. Anda juga dapat menggunakan len(sys.argv) untuk mengetahui banyaknya argumen yang ditampung.

Contoh, sebuah berkas test.py yang akan menambahkan tiga argumen:

~~~
import sys
print('Jumlah arguments:', len(sys.argv), 'arguments.')
print('Argument List:', str(sys.argv))
print(sys.argv[1])
~~~

Jalankan pada konsol/terminal/command prompt:

~~~
$ python test.py arg1 arg2 arg3
~~~

Output:

~~~
Jumlah arguments: 4 arguments.
Argument List: ['test.py', 'arg1', 'arg2', 'arg3']
arg1
~~~

## Dynamic Typing

Python dikenal sebagai salah satu bahasa yang menerapkan dynamic typing, yakni bahasa pemrograman yang hanya mengetahui tipe variabel saat program berjalan dan dilakukan assignment. Tentu saja, pada Python juga umumnya tidak ada deklarasi variabel, hanya berupa assignment statement. Cara ini adalah salah satu bentuk simplifikasi alokasi memori dalam bahasa Python. Anda dapat selalu memeriksa tipe variabel yang digunakan dengan fungsi type() dan memastikan tipe variabel yang tepat dengan metode isinstance(). Anda akan mempelajari lebih jauh mengenai fungsi pada modul Fungsi dan mengenai class pada modul Pemrograman Berorientasi Objek.

Contoh:

~~~
# Ketika kita memberikan nilai 6 pada variabel x
x = 6  
print(type(x))
# Kemudian Berikan string “hello” pada variabel x di baris selanjutnya
x = 'hello'
print(type(x))
~~~

Output:

~~~
<class 'int'>
<class 'str'>
~~~

## Duck Typing

Duck typing adalah sebuah konsep, tipe atau kelas dari sebuah objek tidak lebih penting daripada metode yang menjadi perilakunya. Duck typing ini tidak terkait langsung dengan dynamic typing atau static typing, ini hanya memberikan keleluasaan pada developer untuk tidak perlu mencemaskan tentang tipe atau kelas dari sebuah objek, yang lebih penting adalah kemampuan melakukan operasinya. Sehingga untuk memeriksa dan mengetahui tipe sebuah objek, Anda cukup memastikan metode/fungsi/behavior dari objek tersebut. Misalnya fungsi len() untuk mengetahui panjang string, yang tidak berlaku pada variabel numerik (misalnya integer).

## Transformasi Karakter dan String 

### upper()

~~~
kata = 'dicoding'
kata = kata.upper()
print(kata)
~~~

Output:

~~~
DICODING
~~~

### lower()

~~~
kata = ‘DICODING’
kata = kata.lower()
print(kata)
~~~

Output:

~~~
dicoding
~~~

### rstrip()

~~~
print('Dicoding    '.rstrip())
~~~

Output:

~~~
Dicoding
~~~

### lstrip()

~~~
print('    Dicoding'.lstrip())
~~~

Output:

~~~
Dicoding
~~~

### strip()

~~~
print('    Dicoding    '.strip())
~~~

Output:

~~~
Dicoding
~~~

Anda juga bisa menentukan mana karakter atau bagian yang ingin dihilangkan, misalnya:

~~~
kata = 'CodeCodeDicodingCodeCode'
print(kata.strip('Code'))
~~~

Output:

~~~
Dicoding
~~~

### startswith()

Metode startswith() akan mengembalikan nilai True jika string diawali dengan kata awalan tertentu yang kita inginkan, jika tidak maka akan mengembalikan nilai False.

~~~
print('Dicoding Indonesia'.startswith('Dicoding'))
~~~

Output:

~~~
True
~~~

### endswith()

Metode endswith() ini kebalikannya dari metode startswith(), metode ini akan mengembalikan nilai True jika string diakhiri dengan kata akhiran tertentu yang kita inginkan, jika tidak maka akan mengembalikan nilai False. 

~~~
print('Dicoding Indonesia'.endswith('Indonesia'))
~~~

Output:

~~~
True
~~~

## Memisah dan Menggabung String

### join()

Metode join() adalah metode yang dipakai untuk menggabungkan sejumlah string. 

~~~
print(' '.join(['Dicoding', 'Indonesia', '!']))
~~~

Output:

~~~
Dicoding Indonesia !
~~~

### split()

Metode split() adalah metode yang memisahkan substring berdasarkan delimiter tertentu (defaultnya adalah whitespace, tab, atau newline).

~~~
print('Dicoding123Indonesia123!'.split('123'))
~~~

Output:

~~~
['Dicoding', 'Indonesia', '!']
~~~

## Mengganti Elemen String

### replace()
Metode replace() dapat mengembalikan string baru dalam kondisi substring telah tergantikan dengan parameter yang dimasukkan. Berikut contoh kodenya.

~~~
string = "Ayo belajar Coding di Dicoding"
print(string.replace("Coding", "Pemrograman"))
~~~

Output:

~~~
Ayo belajar Pemrograman di Dicoding
~~~

## Pengecekan String

### isupper()

Metode isupper() akan mengembalikan nilai True jika semua huruf dalam string adalah huruf besar, dan akan mengembalikan nilai False jika terdapat satu saja huruf kecil di dalam string tersebut.

~~~
kata = ‘DICODING’
kata.isupper()
~~~

Output:

~~~
True
~~~

### islower()

Metode islower()  adalah kebalikan dari metode isupper(), metode ini akan mengembalikan nilai True jika semua huruf dalam string adalah huruf kecil, dan akan mengembalikan nilai False jika terdapat satu saja huruf besar di dalam string tersebut.

~~~
kata = ‘dicoding’
kata.islower()
~~~

Output:

~~~
True
~~~

### isalpha()

Metode ini akan mengembalikan nilai True jika semua karakter dalam string adalah huruf alfabet, jika tidak maka akan mengembalikan nilai False.

~~~
‘dicoding’.isalpha()
~~~

Output :

~~~
True
~~~

### isalnum() 

Metode ini akan mengembalikan nilai True jika karakter dalam string adalah alfanumerik yaitu hanya huruf atau hanya angka atau berisi keduanya, jika tidak maka akan mengembalikan nilai False.

~~~
‘dicoding123’.isalnum()
~~~

Output :

~~~
True
~~~

### isdecimal() 

Metode ini akan mengembalikan nilai True jika karakter dalam string berisi hanya angka/numerik, jika tidak maka akan mengembalikan nilai False.

~~~
‘12345’.isdecimal()
~~~

Output :

~~~
True
~~~

### isspace()

Metode ini akan mengembalikan nilai True jika string berisi hanya karakter whitespace, seperti spasi, tab, newline, atau karakter whitespaces lainnya, jika tidak maka akan mengembalikan nilai False.

~~~
‘    ’.isspace()
~~~

Output :

~~~
True
~~~

### istitle()

Metode ini akan mengembalikan True jika string berisi huruf kapital di setiap kata dan dilanjutkan dengan huruf kecil seterusnya, jika tidak maka akan mengembalikan nilai False.

~~~
‘Dicoding Indonesia’.istitle()
~~~

Output :

~~~
True
~~~

## Formatting pada String

### zfill()

Metode yang dapat menambahkan nilai numerik berupa 0 di sebelah kiri sebuah angka atau string. Penggunaan metode zfill() ini bisa diterapkan untuk nomor nota atau nomor antrian. Anda akan menemui kebutuhan untuk menambahkan awalan 0 misalnya seperti, 0001 untuk angka awalan 1, 0101 untuk angka awalan 101, dan sebagainya. 

Nilai kembalian yang dihasilkan oleh zfill jumlah karakternya kurang dari atau sama dengan value yang kita masukkan pada metode zfill. Misalnya jika kita memberi value 10, maka nanti akan ditulis zfill(10) yang berarti nilai numerik berupa 0 dan angka atau string yang ada, jumlah karakternya harus kurang dari atau sama dengan value zfill tersebut.

Jika kita ingin menerapkan zfill pada data berupa angka, maka kita harus mengonversinya terlebih dahulu ke dalam bentuk string menggunakan str() seperti di bawah ini:

~~~
# Contoh 1: Penggunaan zfill 5 pada angka satuan
angka = 5
print (str(angka).zfill(5));
# Contoh 2: Penggunaan zfill 5 pada angka ratusan
angka = 300
print (str(angka).zfill(5));
# Contoh 3: Penggunaan zfill 5 pada angka desimal negatif (memiliki koma)
angka = -0.45
print (str(angka).zfill(5));
# Contoh 4: Penggunaan zfill 7 pada angka desimal negatif (memiliki koma)
angka = -0.45
print (str(angka).zfill(7));
~~~

Output:

~~~
00005

00300

-0.45

-000.45
~~~

Pada contoh ketiga yang memiliki angka -0.45 dengan zfill(5) menghasilkan output yang sama yaitu -0.45. Mengapa bisa demikian? Hal tersebut dikarenakan jumlah karakter yang ada sudah berjumlah 5 yang di mana karakter koma (“,”) dan negatif (“-”) juga dihitung. Sehingga tidak ada nilai 0 yang ditambahkan pada sebelah kiri dari data angka.

Namun, bagaimana jika pada contoh ketiga nilai zfill kita ubah menjadi 7 sehingga tertulis zfill(7). Maka semuanya akan terjawab di contoh keempat yang menghasilkan -000.45 yang menambahkan dua nilai ‘nol’ pada sebelah kiri data angka. Zfill otomatis mendeteksi tanda negatif (“-”) pada sebuah nilai sehingga otomatis nilai ‘nol’ ditempatkan setelah tanda negatif.

Lain halnya ketika data yang ingin kita tambahkan nilai 0 berupa string. Kita tidak perlu mengonversi data tersebut ke dalam bentuk string karena memang asalnya sudah dalam bentuk string. Untuk memperjelas pernyataan tersebut perhatikan contoh di bawah ini.

~~~
# Contoh 1
kata = 'aku'
print (kata.zfill(5));
# Contoh 2
kata = 'kamu'
print (kata.zfill(5));
# Contoh 3
kata = 'dirinya'
print (kata.zfill(5));
~~~

Output:

~~~
00aku

0kamu

dirinya
~~~

Pada contoh ketiga menghasilkan output string yang sama dengan aslinya yaitu string “dirinya” menghasilkan output “dirinya” juga. Mengapa bisa demikian? Hal tersebut karena jumlah karakter pada kata “dirinya” lebih dari nilai zfill(5). Sehingga nilai string yang dikembalikan utuh seperti aslinya (tanpa dikurangi atau ditambahkan 0).

### rjust()

~~~
'Dicoding'.rjust(20)
~~~

Output:

~~~
'            Dicoding'
~~~

### ljust()

~~~
'Dicoding'.ljust(20, '!')
~~~

Output:

~~~
'Dicoding!!!!!!!!!!!!'
~~~
 
### center()

~~~
'Dicoding'.center(20)
~~~

Output:

~~~
'      Dicoding      '
~~~

## String Literals

Umumnya, string ditulis dengan mudah di Python, diapit oleh tanda petik tunggal. Tetapi, dalam kondisi tertentu, dibutuhkan petik tunggal di tengah string (misalnya struktur kepemilikan dalam Bahasa Inggris - Dicoding’s Cat atau penyebutan Jum’at pada hari dalam bahasa Indonesia).

Apabila kita menuliskannya sebagai berikut,

~~~
st1 = ‘Jum’at’
~~~

Maka Python akan salah mengira bahwa string berakhir setelah huruf m dan selebihnya merupakan kode yang invalid. Namun Python memperbolehkan Anda menggunakan petik dua seperti Anda menggunakan petik tunggal. Dalam kasus sebelumnya, Anda cukup mengetikkan:

~~~
st1 = "Jum’at"
~~~

Dan dalam contoh tersebut, Python mengenali bahwa petik tunggal adalah bagian tidak terpisahkan dari string tersebut. Bagaimana jika kita memerlukan kedua jenis petik dalam string tunggal? Python menyediakan escape character.

Escape Character memungkinkan Anda untuk menggunakan karakter yang sebelumnya tidak bisa dimasukkan dalam string. Umumnya diawali dengan backslash (\) dan diikuti karakter tertentu yang diinginkan. Contohnya, untuk petik tunggal Anda dapat menambahkan seperti: \'.

Cara ini merupakan cara paling aman untuk melakukan penambahan atau penyuntingan dalam variabel. Contohnya sebagai berikut:

~~~
st1 = 'Jum\'at'
~~~

Python mengetahui bahwa pada Jum\’at, sebelum petik terdapat backslash (\) yang menandakan petik tunggal merupakan bagian dari string dan bukan merupakan akhir dari string. Escape character \' dan \" memungkinkan Anda untuk memasukkan karakter ' dan '' dalam bagian string. Beberapa contoh Escape Character

~~~
\' Single quote
\" Double quote
\t Tab
\n Newline (line break)
\\ Backslash
~~~

## Raw Strings

Python juga menyediakan cara untuk mencetak string sesuai dengan apa pun input atau teks yang diberikan. Metode ini dinamakan Raw Strings. Umumnya digunakan untuk regex atau beberapa implementasi lain yang sangat bergantung pada keberadaan backslash. Untuk mengimplementasikan raw strings, sisipkan huruf r sebelum pembuka string:

~~~
print(r'Dicoding\tIndonesia')
~~~

Output:

~~~
Dicoding\tIndonesia
~~~

Seharusnya, perintah \t akan membuat tab dan menghasilkan Dicoding    Indonesia, tapi karena kita menggunakan raw strings, maka kalimat tersebut secara mentah tercetak apa adanya.

## Sort()

~~~
angka = [100, 1000, 500, 200, 5]
angka.sort()
print(angka)
~~~

Output:

~~~
[5, 100, 200, 500, 1000]
~~~

Beberapa hal yang perlu Anda ketahui: 

1. Metode sort langsung melakukan pengurutan pada variabel yang dioperasikannya, sehingga Anda tidak perlu melakukan operasi assignment (=).
2. Metode sort tidak dapat mengurutkan list yang memiliki angka dan string sekaligus di dalamnya.
3. Metode sort menggunakan urutan ASCII, sehingga nilai huruf kapital (uppercase) akan lebih dahulu dibandingkan huruf kecil (lowercase).

Untuk mengatasi kendala ini, Anda dapat memasukkan keyword str.lower pada parameter. Hal ini akan membuat metode sort menganggap semua objek menggunakan huruf kecil, tanpa mengubah kondisi asli dari objek tersebut.

~~~
kendaraan = ['Motor', 'Mobil', 'helikopter', 'pesawat']
kendaraan.sort(key=str.lower)
print(kendaraan)
~~~

Output:

~~~
['helikopter', 'Mobil', 'Motor', 'pesawat']
~~~

## Jenis-jenis operator Matematika dan string

### + (tambah)

Menambahkan dua objek.
3 + 5 menghasilkan 8
'a' + 'b' menghasilkan 'ab'.

### - (kurang)

Mengurangkan operand kedua dari operand pertama. Jika hanya satu operand, diasumsikan nilai operand pertama adalah 0.
-5.2 adalah expression yang sama dengan 0 - 5.2 menghasilkan -5.2.
50 - 24 menghasilkan 26.
Tidak berlaku untuk string, akan menghasilkan error unsupported operand.

### * (perkalian)

Mengembalikan hasil perkalian angka atau mengembalikan string yang diulang sejumlah tertentu.
2 * 3 menghasilkan 6.
'la' * 3 menghasilkan 'lalala'.

### ** (pangkat)

Mengembalikan operand pertama pangkat operand kedua.
3 ** 4 menghasilkan 81 (sama dengan 3 * 3 * 3 * 3).
| Tips: untuk akar dua, gunakan pangkat 0.5.

### / (pembagian)

Mengembalikan hasil pembagian operand pertama dengan operand kedua (float).
13 / 3 menghasilkan 4.333333333333333.

### // (pembagian habis dibagi / div)

Mengembalikan hasil pembagian operand pertama dengan operand kedua (bilangan bulat), kecuali jika salah satu operand adalah float, akan menghasilkan float.
13 // 3 menghasilkan 4.
-13 // 3 menghasilkan -5.
9//1.81 menghasilkan 4.0.

### % (modulo)

Mengembalikan sisa bagi.
13 % 3 menghasilkan 1.
-25.5 % 2.25 menghasilkan 1.5.

[Expression Documentation](https://docs.python.org/id/3.8/reference/expressions.html#operator-precedence)