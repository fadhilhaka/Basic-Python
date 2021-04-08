# Introduction

## Pengenalan Python

Python adalah bahasa pemrograman multifungsi yang dibuat oleh **Guido van Rossum** dan dirilis pada tahun **1991**. GvR, begitu ia biasa disebut di komunitas Python, menciptakan Python untuk menjadi **interpreter** yang memiliki kemampuan penanganan kesalahan (**exception handling**) dan mengutamakan sintaksis yang mudah dibaca serta dimengerti (**readability**). Didesain untuk memudahkan dalam prototyping, Python menjadi bahasa yang sangat mudah dipahami dan fleksibel.

Python juga memilih untuk menggunakan **indentasi untuk mengelompokkan blok kode**, berbeda dengan beberapa bahasa lain yang menggunakan simbol tertentu, misalnya kurung kurawal, atau sintaksis begin-end. Sehingga secara visual pun, blok kode Python didesain untuk mudah dipahami. Salah satu yang paling dikenal adalah, penggunaan titik koma atau semicolon (;) tidak wajib di Python dan penggunaan semicolon cenderung dianggap bukan cara khas Python (non-pythonic way), meskipun ia tetap dapat digunakan, misalnya untuk memisahkan dua statement dalam baris yang sama.

~~~
print("Hello World"); print("Welcome to Python")
~~~

Python juga memilih untuk mengadopsi dynamic typing secara opsional, yakni variabel yang dibuat tidak akan diketahui tipenya hingga ia dipanggil pertama kali atau dieksekusi, tidak perlu deklarasi variabel (meskipun dimungkinkan), dan memungkinkan tipe data berubah dalam proses eksekusi program. Sejak Python versi 3.6, sudah tersedia pilihan untuk static typing.

Python pun terus berkembang dalam penggunaannya, sehingga fitur-fitur baru dibutuhkan untuk dikembangkan. Versi 2.0 dirilis Oktober 2000 dengan beberapa pengembangan fitur termasuk Garbage Collector dan Memory Management yang juga menjadi fitur pada beberapa bahasa pemrograman modern lainnya, di antaranya Java dan C#.

[Python 3.0](https://docs.python.org/release/3.0.1/whatsnew/3.0.html) adalah versi perubahan mayor yang dirilis pada Desember 2008, yang didesain sebagai versi yang **tidak backward-compatible** dengan versi-versi sebelumnya. Beberapa sintaksis/statement yang sebelumnya berjalan di versi 2.x, kini tidak lagi berjalan. Semua hal ini didasarkan pada keinginan bahasa Python yang kembali ke “inti”, yakni readable, consistent & explicit. Contohnya, fungsi print yang sebelumnya adalah statement di python 2.x, menjadi function di python 3.x.

## Sejarah / Overview

Saat ini, Python dikelola oleh lembaga non-komersial Python Software Foundation (PSF). Namun sebelumnya, GvR dijuluki sebagai Benevolent dictator for life (BDFL) karena hampir semua keputusan pengembangan Python diambil oleh GvR, berbeda dengan bahasa lain yang misalnya menggunakan voting dan semacamnya. Pasca tahun 2000, dibentuklah beberapa sistem yang memungkinkan Python menjadi lebih sustain, misalnya Python Enhancement Proposals (PEP) untuk pengembangan Python dan tentunya Python Software Foundation (PSF).

Jika PSF menjadi lembaga yang mengelola dan mengadvokasi Python, PEP menjadi panduan dalam pengembangan Python. Beberapa PEP memuat misalnya bagaimana sintaksis dan bagaimana Bahasa Python akan berevolusi, bagaimana modul akan dinyatakan usang (deprecated), dan sebagainya. Setelah kurang lebih 30 tahun dalam pengembangan Python, GvR memutuskan untuk tidak lagi menjabat BDFL pada 12 Juli 2018.

Salah satu patokan dalam pengembangan Python adalah PEP 20 yang berjudul Zen of Python.

[Zen of Python](https://www.python.org/dev/peps/pep-0020/)

~~~
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
~~~

Jika ada pengembangan fitur Python, maka PEP 20 inilah yang menjadi dasar/akar dalam mengambil keputusan.

## Mengapa Python?

Efektivitas Python cukup terbukti dengan banyaknya jumlah pengguna Bahasa Pemrograman ini. Berbagai survei memasukkan Python dalam top-3 sebagai bahasa dengan penggunaan terbanyak, bersaing dengan Java dan PHP. Python dapat digunakan dalam mengakomodasi berbagai gaya pemrograman, termasuk structured, prosedural, berorientasi-objek, maupun fungsional. Python juga dapat berjalan pada berbagai sistem operasi yang tersedia. Beberapa pemanfaatan bahasa Python di antaranya:

* Web development (server-side)
* Software development
* Mathematics & data science
* Machine learning
* System scripting
* Internet of Things (IoT) development
* etc.

## Python Package Index

Dengan dukungan komunitas, Python juga memiliki repository library dan modul yang memungkinkan siapa saja berkontribusi dan menggunakannya. Python menyediakan library yang meliputi regular expressions, documentation generation, unit testing, threading, databases, web browsers, koneksi ke berbagai protokol, cryptography, GUI (graphical user interfaces), dan lain-lain.

[Python Package Index](https://pypi.org/) menyediakan lebih dari 209.000 modul (*Desember 2019) dan skrip yang dapat diinstal dan digunakan secara mudah dalam proyek Python Anda.

Saat ini, Python juga menjadi salah satu bahasa pilihan untuk masuk ke dunia Data Science. Tiga hal utama pada Data Science -  machine learning, data analysis, dan data visualization  banyak disediakan berbasis Python. Sejumlah pustaka paling banyak digunakan dalam machine learning berbasis Python, misalnya: Scikit-Learn, Tensorflow, dan PyTorch.

## Persiapan

Untuk langkah-langkah update Python pada sistem operasi Mac dapat mengunjungi referensi berikut ini:

http://osxdaily.com/2018/06/13/how-install-update-python-3x-mac/

https://wsvincent.com/install-python3-mac/

[Installation Guide](https://docs.python.org/id/3.8/installing/index.html)

## IDE

Integrated Development Environment (IDE) lebih dari sekedar text editor untuk membuat kode, di dalamnya tergabung juga berbagai fasilitas development misalnya Code Versioning, Interpreter, Visualization, dan lain sebagainya.

Untuk menulis program pada bahasa Python, Anda dapat menggunakan teks editor apapun, misalnya Notepad++ atau sejenisnya (Windows), Nano, Vim, Gedit (Linux), atau Visual Studio Code/Atom/Sublime (semua platform). Anda juga bisa menggunakan IDLE dalam bundel package python atau IDE lain yang khusus dibuat untuk Python, misal PyCharm dari JetBrains. Pastikan menyimpan file menggunakan ekstensi yang tepat (umumnya .py untuk kode Python atau .pyc untuk kode yang sudah dikompilasi).

### PyCharm

1. [Unduh PyCharm Community - Free (opsional)](https://www.jetbrains.com/pycharm/)
2. Tampilan PyCharm pada Project Baru.
![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20190711155735bbc74204f703637ec1e6aa24aa3a5c9c.png)
3. Create new Python file.
![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/201907111558160d2f3134305280e404eb7bda8e6c4b4b.png)
![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/201907111558434eeeac415e58795774ed8e2207b0d55f.png)

### [Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)

### [IBM Watson Studio](https://www.ibm.com/my-en/cloud/watson-studio?p1=Search&p4=43700060371516948&p5=b&gclid=Cj0KCQjwsLWDBhCmARIsAPSL3_3QIaJ-bUgsIY0LfzmCt2FoyAinPgizWoFqu0FjQ0JsS2ySfxlopQEaAqnEEALw_wcB&gclsrc=aw.ds)

IBM Watson Studio adalah salah satu layanan dari IBM yang banyak digunakan oleh analis data dan Data Scientist. Anda juga dapat menjalankan kode secara online pada layanan seperti IBM Watson Studio tanpa perlu meng-install perangkat lunak apapun pada komputer Anda. Berikut adalah tutorial bagaimana menggunakan Notebook pada Watson Studio untuk menulis dan menjalankan kode Python.

Sebelum menggunakan IBM Watson Studio, buatlah [akun IBM Cloud](https://cloud.ibm.com/registration?cm_sp=Cloud-Home-_-LeadspaceReg-IBMCloud_CloudHome-_-LSReg) terlebih dahulu. Akun IBM Cloud dapat dipakai untuk mengakses IBM Watson Studio, IBM Watson Machine Learning, dan IBM Cloud.

1. Pada dashboard IBM Cloud cari search bar ketiklah **Object Storage** lalu pilih item tersebut.
2. Kemudian pada halaman Object Storage pilih Lite pada bagan Plan. Perhatikan bahwa satu akun hanya dapat memiliki 1 Object Storage bertipe Lite. Jika Anda telah membuat object storage bertipe Lite sebelumnya, Anda harus menghapus dahulu object storage tersebut untuk bisa membuat object storage lite baru. Untuk Service Name dan Resource Group Anda tidak perlu merubah isinya. Setelah itu klik tombol **Create** yang ada di sidebar sebelah kanan.
3. Login ke [Watson Studio](https://dataplatform.cloud.ibm.com/login?context=cpdaas) menggunakan akun IBM Cloud Anda.
4. Klik tombol **Go To IBM Cloud Pak for Data**.
5. Website IBM Cloud Pak memuat layanan Watson Studios, Watson Machine Learning, dan beberapa layanan IBM lainnya. Untuk mulai mengembangkan proyek ML Anda di Watson Studio, klik tombol **New Project**.
6. Pada laman Create a project pilih **Create an empty project**.
7. Pada halaman New project, isi nama proyek Anda beserta deskripsinya. Storage akan secara otomatis memilih storage yang Anda buat di IBM Cloud. Setelah seluruh kolom Anda isi, klik tombol **Create**.
8. Untuk membuat Notebook pada Watson Studio klik tombol Add to Project lalu pilih **Notebook**.
9. Di halaman New notebook isi nama notebook yang Anda inginkan lalu klik **Create**.
10. Untuk menyimpan pekerjaan Anda, klik tombol File dan pilih **Save**.
11. Pekerjaan yang telah Anda simpan dapat Anda lihat pada menu **Assets** di bagian **Notebooks**.

### [Google Colab](https://colab.research.google.com/notebooks/)
