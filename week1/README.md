# Writing and Presentation Test Week 1
## Day 1 : Unix Command Line
Command Line Interface(CLI) adalah antarmuka berbasis UI yang digunakan untuk menjalankan program maupun untuk mengelola file komputer.Dengan menerima perintah yang dimasukan ke keyboard dan dijalankan oleh komputer.

Shell adalah antarmuka pengguna yang digunakan untuk memproses semua perintah yang diketik di CLI serta dapat membaca dan menafsirkan perintah dan menginstrusikan ke sistem untuk mengerjakan perintah tersebut.

Shell Windows adalah Command Prompt serta file yang dapat dieksekusi adalah CMD.exe.Dengan command prompt kita dapat melakukan hal berikut:

- Membuat dan memodifikasi direktori
- Membuat dan menghapus file
- Mengganti format file

### Perintah dasar CLI
1. pwd memberikan informasidirektori aktif yang sedang diakses
2. cd (change directory) untuk mengubah atau membuka direktori tertentu
3. mkdir (make directory) untuk membuat folder atau direktori baru
4. rmdir digunakan untuk menghapus direktori
5. rm untuk menghapus file
6. rm -r digunakan untuk menghapus direktori
7. cat (concatenate) berfungsi untuk menggabungkan file
8. ls digunakan jika ingin mengetahui isi didalam direktori
9. touch digunakan untuk membuat file baru dengan berbagai jenis format
10. cp digunakan untuk menyalin file
11. cp -r digunakan untuk menyalin direktori
12. mv digunakan untuk memindahkan atau juga bisa untuk mengganti nama file

## Day 2 : Git dan Github
Git merupakan sebuah version control system yang banyak sekali digunakan karena bersifat open source.Git berfungsi untuk mengatur versi source code program dengan memberikan tanda baris dan nama yang dapat ditambah maupun diganti.

Github adalah aplikasi atau website yang digunakan untuk menyimpan dan mengelola kode suatu project.

### Perintah dasar Git
- git config digunakan untuk mengatur konfigurasi sesuai keinginan pengguna seperti username dan email.
- git init digunakan untuk membuat repositori baru
- git add digunakan untuk menambahkan file ke index
- git clone digunakan untuk checkout repository
- git commit digunakan untuk melakukan commit pada perubahan ke head
- git status untuk menampilkan daftar file
- git push untuk mengirimkan perubahan ke master branch
- git checkout untuk membuat branch atau berpindah diantaranya
- git remote untuk membuat user terhubung ke remote repository

## Day 3 : HTML
HTML adalah singkatan dari Hyper Markup Language yaitu bahasa markup untuk membuat dan menyusun halaman dan aplikasi web.Untuk menggunakan html perlu menuliskan tag dan atribut tertentu yang memiliki tag pembuka dan tag penutup.
### Struktur HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <p>Apa kabar hari ini</p>
    <img src="" alt="">
</head>
<body>
    <h1>HELLO I'M BRIAN</h1>
</body>
</html>
```
Dalam HTML terdapat 2 jenis tag yaitu single tag `<br/>` dan double tag `<h1></h1>`.Menambahkan komentar pada file HTML menggunakan tag `<!-- -->`
### Membuat tabel pada HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table border="1">
        <tr>
            <td>Baris ke 1 - Kolom ke 1</td>
            <td>Baris ke 1 - Kolom ke 2</td>
        </tr>
        <tr>
            <td>Baris ke 2 - Kolom ke 1</td>
            <td>Baris ke 2 - Kolom ke 2</td>
        </tr>
    </table>
</body>
</html>
```
Elemen semantik adalah elemen yang menyatakan tujuan dari elemen itu sendiri. Misalnya tag `<footer>` tag ini digunakan untuk membuat elemen footer atau bagian kaki dari web.
### Membuat struktur form
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table border="0">
    <form action="proses.php" method="POST">
        <tr>
		<td><label>Username: </label></td>
		<td><input type="text" name="nama"><br /></td>
        </tr>
        <tr>
        <td><label>Email: </label></td>
		<td><input type="email" name="email"><br /></td>
        </tr>
		<tr>
        <td><label>Password: </label></td>
		<td><input type="password" name="password"><br /></td>
        </tr>
		
        <tr>
        <td><label>Jenis Kelamin: </label></td>
		<td><input type="radio" name="gender">Pria
		<input type="radio" name="gender">Wanita<br /></td>
        </tr>

		<tr>
        <td><label>Umur: </label></td>
		<td><input type="number" name="usia"><br /></td>
        </tr>
        <tr>
        <td><label>Tanggal lahir: </label></td>
		<td><input type="date" name="tanggal"><br /></td>
        </tr>
        <tr>
        <td><label>Lampiran: </label></td>
		<td><input type="file" name="berkas"><br /></td>
        </tr>
        <tr>
        <td><label>Kirim: </label></td>
		<td><input type="submit" name="simpan"></td>
        </tr>
	</form>
    </table>
</body>
</html>
```
## Day 4 : CSS

CSS adalah singkatann dari cascading style sheets yang merupakan bahasa yang digunakan untuk menentukan atau mengatur tampilan website.

Jenis-jenis CSS dibagi menjadi 3 yaitu:

- Inline CSS adalah kode yang dituliskan didalam tag HTML`<p style="font-size: 12px;color: blueviolet;">apa kabar</p>`
- Internal CSS adalah kode yang dituliskan di bagian header HTML `<style>
Body  { background-color:red;  }
P  { font-size:20px;  color:black;  }
</style>`
- External CSS adalah kode yang dituliskan terpisah dari file HTML namun dikaitkan dengan tag `<link rel="stylesheet" href="style.css">`

### Struktur CSS
```css
 h1{
background-color: aqua;
}
```
Selector – Memberi style CSS pada elemen HTML yang diingikan
Block Declaration memiliki satu atau lebih jenis declaration yang dipisahkan dengan tanda titik koma “;”.Setiap Deklaration memiliki properti dan setiap properti memiliki nilai.
### CSS comment
Berfungsi memberi komentar pada kode sehingga kita bisa tau fungsi dari tag tersebut dengan `/* */`
### CSS Selector
- ID selector menggunakan atribut HTML untuk memilih elemen dengan diawali pagar(#)
- CLASS selector memilih atribut html dengan class tertentu dengan karakter titik(.)
- Gruping selector memilih semua elemen HTML dengan style css yang sama. Untuk Group Selector, pisahkan setiap selector dengan tanda koma.

### CSS Box model
- Content : Konten didalam box, dimana text atau gambar ditampilkan
- Padding : Area kosong yang mengelilingi konten dan bersifat transparan
- Border : Batas yang mengelilingi Padding dan Content
- Margin : Area kosong diluar Border yang bersifat transparan

### CSS Flexbox
mode layout yang ada di CSS3 dan digunakan untuk mengatur elemen di suatu halaman web.Ada dua komponen utama sebuah layout Flexbox yaitu container dan item.

Properti container flexbox

- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

## Day 5 : Algorithm dan Pseudocode
Algoritma adalah urutan langkahlogis yang digunakan untuk menyelesaikan suatu masalah.Fungsi dari algoritma adalah memecahkan masalah atau mengkonversikan sebuah permasalahan ke bahasa pemrograman.

Kriteria algoritma diantaranya adalah:

- Finiteness(keterbatasan)
- Definiteness(kepastian)
- Input(masukan)
- Output(keluaran)
- Effectivenes(keefektivitasan)

Jenis-jenis algoritma

- Sequence adalah intruksi yang dikerjakan secara berurutan
- Selection merupakan intruksi yang dijalankan jika memenuhi suatu kondisi
- Interation interaksi yang berulangkali dijalankan selama memenuhi kondisi tertentu
- Concurrent intruksi yang dijalankan secara bersamaan

Contoh penulisan algoritma

Jika nilai >= 75 maka
keterangan berhasil,tetapi jika =< 75 makaa keterangan  gagal.

### Pseudocode
Pseudocode adalah teknik atau gaya penulisan dalam menulis kode pemrograman secara lebih sederhana agar mudah dibaca dan dipahami serta berfungsi untuk mendokumentasikan pemrograman.

Psuedocode memiliki 3 bagian yaitu:

- Judul merupakan penjelasan dari algoritma
- Deklarasi mendefinisikan data dan variabel yang digunakan
- Deskripsi adalah langkah-langkah penyelesaian masalah

Contoh pseudocode serderhana

- Input(a,b,c)
- Jumlah =a+b+c
- Data = Jml/3
- Output(Data)

### Flowchart
Flowchart atau bagan alur adalah sebuah diagram yang menampilkan langkah-langkah untuk melakukan proses dari suatu program.Fungsi flowchart adalah memberi gambaran jalananya program dapat mudah dipahami.Beberapa strukture flowchart

- Input
- Output
- Proses pengolahan data
- Penyimpanan data

## Javascript
Javascript adalah bahasa pemrograman yang digunakan untuk logic pada sebuah website.Sehingga dapat membuat website lebih interaktif dan dinamis.Untuk mengecek apakah logic berjalan dapat dilihat dengan `console.log()`.Pada javascript kita juga bisa membuat single comment dengan tanda `//` dan multiline comment dengan tanda `/* */`.

Tipe data fundamental pada javascript

- Number terdiri dari angka termasuk angka desimal
- string grup karakter pada keyboard yaitu huruf,angka,spasi dan symbol.
- Boolean memiliki 2 nilai yaitu true dan false
- Null berarti sebuah variable tidah memiliki nilai
- Undefine merupakan tipe data yang mempresentasikan variable atau data
- Object adalah koleksi data yang saling berhubungan

### Variable
Variable adalah wadah atau tempat menyimpan nilai.Terdapat 3 cara untuk menuliskan variable

- Var
```javascript
var nama  = 'brian'
console.log(nama)
//Output: brian
```
- Let
```javascript
let nama = 'brian'
console.log(nama)
//Output: brian
nama = wahyu
console.log(nama)
//Output: wahyu
```
- Const
```javascript
const pi = 3.14
console.log(pi)
//output: 3.14
pi= 10
console.log(pi)
//Output: error
```

Aturan penamaan variable

1. Tidah boleh menggunakan angka pada awalan
2. Gunakan camelcase untuk penamaan lebih dari 1 kata
3. Variable harus mendeskribsikan isinya
### Operator
Operator merupakan intruksi yang digunakan untuk melakukan suatu proses contohnya:

- Assignment (=) digunakan untuk menyimpan nilai variable
- Increment dan Decrement untuk menambah atau mengurangi nilai 
- Arithmetic untuk melibatkan operasi matematika yang terdiri dari (+,-,*,/,%)
- Comparison untuk membandingkan nilaisatu dengan lainya
- Simbol operator(<,>,<=,>=,===,!==)
- Logical operator(&&,||,!)

## Javascript Conditional
Conditional merupakan percabangan yang menggambarkan suatu kondisi yang sebelumnya sudah dicek spesifikasinya sebelum menjalankan perintah.Jika kondisi tersebut benar maka akan dijalankan.

contoh conditional:

- If statement akan mengeksekusi statment jika benar
```javascript
if (true){
    console.log('tampilkan pesan ini')
}
//output: tampilkan pesan ini
```
- If ... Else statement akan mengeksekusi code jika bernilai salah
```javascript
let hujan = false;
if (hujan){
    console.log('tidak pakai payung')
}else{
    console.log('pakai payung')//program yang ditampilkan
}
```
- If...Else if statement digunakan jika ada berbagai kondisi
```javascript
let rambu = 'merah';
if (rambu === 'merah'){
    console.log('berhenti');
}else if(rambu === kuning){
    console.log('hati-hati')
}else if(rambu === hijau){
    console.log('jalan terus');
}else{
    console.log('peringatan')
}
```
- Truthy dan falsy untuk mengecek apakah variable sudah terisi
```javascript
let nama = 'tahuu';
if (nama){
    console.log(nama)
}else{
    console.log('variable kosong')
}
//output:tahuu
```
- Switch case conditional digunakan jika percabangan terlalu banyak
```javascript
switch (new Date().getDay()) {
    case 0:
      day = "Sunday";
      break;
    case 1:
      day = "Monday";
      break;
    case 2:
       day = "Tuesday";
      break;
    case 3:
      day = "Wednesday";
      break;
    case 4:
      day = "Thursday";
      break;
    case 5:
      day = "Friday";
      break;
    case 6:
      day = "Saturday";
  }
  //sunday
```
## Javascript looping
Statement yang mengulang interuksi hingga kondisi terpenuhi

Jenis-jenis loop

- for loop adalah perulangan yang sudah jelas berapa banyak perulangan yang dilakukan
- while loop adalah perulangan yang belum diketahui berapa banyak perulangan yang harus dilakukan
- Do while perulangan yang belum diketahui berapa banyak perulangan yang harus dilakukan.jika memenuhi kondisi maka pengulangan akan dilakukan dan jika tidak memenuhi kondisi maka pengulangan akan berhenti
