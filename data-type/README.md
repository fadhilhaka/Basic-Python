# Tipe Data

Dasar dari mempelajari Bahasa Pemrograman yang baru adalah pemahaman terhadap tipe data. Di sini Anda akan diajarkan tentang tipe data bawaan yang ada di Python 3 beserta contoh penggunaannya.

## Numbers

Tipe numerik pada Python dibagi menjadi 3: int, float, complex. 

~~~
a = 10
print(a, "bertipe", type(a))
b = 1.7
print(a, "bertipe", type(b))
c = 1+3j
print(c, " Bertipe bilangan kompleks? ", isinstance(1+3j,complex))
~~~

Output:

~~~
10 bertipe <class 'int'>
1.7 bertipe <class 'float'>
(1+2j) Bertipe bilangan kompleks? True
~~~

Integer tidak dibatasi oleh angka atau panjang tertentu, namun dibatasi oleh memori yang tersedia. Sehingga Anda tidak perlu menggunakan variabel yang menampung big number misalnya long long (C/C++), biginteger, atau sejenisnya. Contoh kode untuk menunjukkan bahwa Python tidak membatasi output integer adalah pencarian bilangan ke-10.000 pada deret fibonacci (catatan: bilangan ke-10.000 pada deret fibonacci memiliki panjang 2.090 digit) sebagai berikut:

~~~
x=[0]*10005;              #inisialisasi array 0 sebanyak 10005; x[0]=0
x[1]=1;                   #x[1]=1
 
for j in range(2,10001):
      x[j]=x[j-1]+x[j-2]  # Fibonacci
print(x[10000])
~~~

Output:

~~~
33644764876431783266621612005107543310302148460680063906564769974680081442166662368155595513633734025582065332680836159373734790483865268263040892463056431887354544369559827491606602099884183933864652731300088830269235673613135117579297437854413752130520504347701602264758318906527890855154366159582987279682987510631200575428783453215515103870818298969791613127856265033195487140214287532698187962046936097879900350962302291026368131493195275630227837628441540360584402572114334961180023091208287046088923962328835461505776583271252546093591128203925285393434620904245248929403901706233888991085841065183173360437470737908552631764325733993712871937587746897479926305837065742830161637408969178426378624212835258112820516370298089332099905707920064367426202389783111470054074998459250360633560933883831923386783056136435351892133279732908133732642652633989763922723407882928177953580570993691049175470808931841056146322338217465637321248226383092103297701648054726243842374862411453093812206564914032751086643394517512161526545361333111314042436854805106765843493523836959653428071768775328348234345557366719731392746273629108210679280784718035329131176778924659089938635459327894523777674406192240337638674004021330343297496902028328145933418826817683893072003634795623117103101291953169794607632737589253530772552375943788434504067715555779056450443016640119462580972216729758615026968443146952034614932291105970676243268515992834709891284706740862008587135016260312071903172086094081298321581077282076353186624611278245537208532365305775956430072517744315051539600905168603220349163222640885248852433158051534849622434848299380905070483482449327453732624567755879089187190803662058009594743150052402532709746995318770724376825907419939632265984147498193609285223945039707165443156421328157688908058783183404917434556270520223564846495196112460268313970975069382648706613264507665074611512677522748621598642530711298441182622661057163515069260029861704945425047491378115154139941550671256271197133252763631939606902895650288268608362241082050562430701794976171121233066073310059947366875
~~~

### Batasan akurasi variabel bertipe float

Python melakukan pemotongan pada digit ke 16 pada variabel float. Float atau bilangan pecahan dibatasi akurasinya pada 15 desimal. Yang membedakan Integer dan Float adalah titik (decimal points). Misalnya dalam penulisan angka 1 jenisnya Integer, tapi jika dituliskan sebagai 1.0 artinya berjenis Float atau pecahan.

### Bilangan Kompleks

Karena Python banyak digunakan juga oleh matematikawan, tipe bilangan di Python juga mendukung bilangan imajiner dan bilangan kompleks. Nilai bilangan kompleks (complex) dituliskan dalam formulasi x + yj, yakni bagian x adalah bilangan real dan y adalah bilangan imajiner. Contohnya adalah sebagai berikut:

~~~
c = 1+5j
print(c)
~~~

Output:
~~~
(1+5j)
~~~

## Strings

String adalah urutan dari karakter unicode yang dideklarasikan dengan petik tunggal atau ganda. String >1baris dapat ditandai dengan tiga petik tunggal atau ganda ''' atau """.

~~~
s = "Ini adalah string baris tunggal"

s = '''Ini adalah string
yang memiliki baris pertama
dan selanjutnya baris kedua'''
~~~

## Bool/Boolean

Tipe data bool atau Boolean merupakan turunan dari bilangan bulat (integer atau int) yang hanya punya dua nilai konstanta: True dan False.

### Nilai Boolean

Nilai konstanta False dan True merepresentasikan nilai kebenaran (truth values), meskipun ada nilai-nilai lain yang juga dianggap benar atau salah. Di dalam konteks angka, misalnya digunakan sebagai argumen dari operator matematika aritmatika, kedua nilai ini berlaku seperti halnya bilangan bulat 0 dan 1, sesuai False dan True.

Ada fungsi bawaan bool() yang dapat mengubah nilai menjadi nilai Boolean, apabila nilai tersebut dapat direpresentasikan sebagai nilai kebenaran (truth values). 

Nilai kebenaran adalah sebuah nilai yang dapat diuji sebagai benar atau salah, untuk digunakan di sintaksis kondisi if atau while atau sebagai operan dari operasi Boolean.

Berikut adalah objek bawaan yang didefinisikan bernilai salah dalam pengujian nilai kebenaran:

* Konstanta yang sudah didefinisikan bernilai salah: None dan False.
* Angka nol dari semua tipe numeric: 0, 0.0, 0j, Decimal(0), Fraction(0, 1).
* Urutan (sequence) dan koleksi (collection) yang kosong: '', (), {}, set(), range(0).

Untuk objek yang didefinisikan sendiri, representasi nilai Boolean akan bergantung dari definisi metode (method) khusus bernama __bool__(self). Jika metode ini mengembalikan True maka interpretasi nilai dari objeknya akan True, demikian juga sebaliknya.

### Operasi Boolean

Operasi dan fungsi bawaan yang memiliki hasil Boolean akan selalu mengembalikan 0 atau False untuk yang bernilai salah, serta 1 atau True untuk yang bernilai benar, kecuali dinyatakan berbeda dalam dokumentasi.

## List 

List adalah jenis kumpulan data terurut (ordered sequence), dan merupakan salah satu variabel yang sering digunakan pada Python. Serupa, namun tak sama dengan array pada bahasa pemrograman lainnya. Bedanya, elemen List pada Python tidak harus memiliki tipe data yang sama. Mendeklarasikan List cukup mudah dengan kurung siku dan elemen yang dipisahkan dengan koma. 

~~~
a = [1, 2.2, 'python']
~~~

Python mengenal slicing operator [] yang dapat melakukan ekstraksi sebuah item atau beberapa item yang berada dalam range tertentu pada tipe data urutan (sequences), misalnya list, string dan tuple. Beberapa tipe urutan juga mendukung "extended slicing" dengan parameter ketiga berupa "step".

* x[0] artinya mengambil elemen paling awal, dengan index 0 dari List x.
* x[5] artinya mengambil elemen dengan index 5 dari List x.
* x[-1] artinya mengambil elemen dengan index paling belakang ke-1 dari List x.
* x[3:5] artinya membuat list dari anggota elemen List x dengan index 3 hingga sebelum index 5 (tidak termasuk elemen dengan index 5, dalam hal ini hanya index 3-4).
* x[:5] artinya membuat list dari anggota elemen List x paling awal hingga sebelum index 5 (tidak termasuk elemen dengan index 5, dalam hal ini hanya index 0-4).
* x[-3:] artinya membuat list dari anggota elemen List x mulai index ke-3 dari belakang hingga paling belakang.
* x[1:7:2] artinya membuat list dari anggota elemen List x dengan index 1 hingga sebelum index 7, dengan "step" 2 (dalam hal ini hanya index 1, 3, 5).

~~~
x = [5,10,15,20,25,30,35,40]
print(x[5])
print(x[-1])
print(x[3:5])
print(x[:5])
print(x[-3:])
print(x[1:7:2])
~~~

Output:
~~~
30
40
[20, 25]
[5, 10, 15, 20, 25]
[30, 35, 40]
[10, 20, 30]
~~~

Elemen pada list dapat diubah atau ditambahkan. Misalnya untuk melakukan perubahan kemudian penambahan:

~~~
x = [1,2,3]
x[2]=4
x.append(5)
print(x)
~~~

Output:
~~~
[1, 2, 4, 5]
~~~

Untuk menghapus item pada list, gunakan fungsi del. Ingat bahwa Indeks Python dimulai dari 0:

~~~
binatang = ['kucing', 'rusa', 'badak', 'gajah']
del binatang[2]
print(binatang)
~~~

Output:
~~~
['kucing', 'rusa', 'gajah']
~~~

### Slicing pada String

Karena string mirip dengan list, maka slicing operator [ ]  juga dapat digunakan pada string untuk mengambil isinya atau bahkan substring. Sebuah string utuh bersifat mutable (bisa diubah), namun elemennya bersifat immutable (tidak bisa diubah).

~~~
s = "Hello World!"
print(s[4]) 		#ambil karakter kelima dari string s
print(s[6:11]) 		#ambil karakter ketujuh hingga sebelas dari string s
s[5]="d" 		    #ubah karakter keenam dari string s menjadi "d", seharusnya gagal karena immutable
s = "Halo Dunia!"	#ubah isi string s menjadi "Halo Dunia!", seharusnya berhasil karena mutable
print (s)
~~~

Output:
~~~
'o'
'World'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
'Halo Dunia!'
~~~

## Tuple

Tuple adalah jenis dari list yang tidak dapat diubah elemennya. Umumnya tuple digunakan untuk data yang bersifat sekali tulis, dan dapat dieksekusi lebih cepat. Tuple didefinisikan dengan kurung dan elemen yang dipisahkan dengan koma.

~~~
t = (5,'program', 1+3j)
~~~

Seperti list, kita dapat melakukan slicing, namun pada tuple kita tidak dapat melakukan perubahan:

~~~
t = (5,'program', 1+3j)
print(t[1])
print(t[0:3])
print(t[0]=10)
~~~

Output:
~~~
'program'
(5, 'program', (1+3j))
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
~~~

### Set

Set adalah kumpulan item bersifat unik dan tanpa urutan (unordered collection). Didefinisikan dengan kurawal dan elemennya dipisahkan dengan koma. Pada Set kita dapat melakukan union dan intersection, sekaligus otomatis melakukan penghapusan data duplikat.

~~~
a = {1,2,2,3,3,3}
print(a)
~~~

Output:
~~~
{1, 2, 3}
~~~

Karena set bersifat unordered, maka kita tidak bisa mengambil sebagian data / elemen datanya menggunakan proses slicing.

~~~
a = {1,2,3}
print(a[1])
~~~

Output:
~~~
Traceback (most recent call last):
File "<string>", line 301, in runcode
File "<interactive input>", line 1, in <module>
TypeError: 'set' object does not support indexing
~~~

## Dictionary

Dictionary pada Python adalah kumpulan pasangan kunci-nilai (pair of key-value) yang bersifat tidak berurutan. Dictionary dapat digunakan untuk menyimpan data kecil hingga besar. Untuk mengakses datanya, kita harus mengetahui kuncinya (key). Pada Python, dictionary didefinisikan dengan kurawal dan tambahan definisi berikut:

* Setiap elemen pair key-value dipisahkan dengan koma (,).
* Key dan Value dipisahkan dengan titik dua (:).
* Key dan Value dapat berupa tipe variabel/obyek apapun.

Dictionary bukan termasuk dalam implementasi urutan (sequences), sehingga tidak bisa dipanggil dengan urutan indeks. Misalnya dalam contoh berikut dicoba dengan indeks 2, tetapi menghasilkan error (KeyError) karena tidak ada kunci (key) 2:

~~~
d = {1:'value','key':2}
print(type(d))
print("d[1] = ", d[1]);
print("d['key'] = ", d['key']);
 
# Generates error
print("d[2] = ", d[2]);
~~~

Output:
~~~
<class 'dict'>
d[1] = value
d['key'] = 2

---------------------------------------------------------------------------
KeyError Traceback (most recent call last)
<ipython-input-7-4b566e677ca2> in <module>()
1 d = {1:'value','key':2}
----> 2 print("d[2] = ", d[2]);

KeyError: 2
~~~

## Konversi (conversion, cast) antar tipe data

Kita dapat melakukan konversi tipe data bawaan dengan menggunakan fungsi konversi tipe bawaan (standard type) misalnya: int(), float(), str(), dll.

Konversi float ke int akan bersifat floor/truncating atau menghilangkan nilai di belakang koma.

~~~
print(int(10.6))
~~~

Output:
~~~
10
~~~

Anda juga dapat melakukan konversi kumpulan data (set, list, tuple).

~~~
print(set([1,2,3]))
print(list('hello'))
~~~

Output:
~~~
{1, 2, 3}
['h', 'e', 'l', 'l', 'o']
~~~

Untuk konversi ke dictionary, data harus memenuhi persyaratan key-value. Berikut adalah dua contoh konversi:

List dari beberapa List yang isinya pasangan nilai menjadi Dictionary. 

Serta konversi List dari beberapa Tuple yang isinya pasangan nilai menjadi Dictionary.

~~~
print(dict([[1,2],[3,4]]))
print(dict([(3,26),(4,44)]))
~~~

Output:
~~~
{1: 2, 3: 4}
{3: 26, 4: 44}
~~~
