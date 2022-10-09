# Writing And Presentation Test Week 3
# Javascript Itermediate
## Array

Array merupakan variabel khusus yang dapat menampung variabel lebih dari satu nilai salam satu waktu.Membuat array dapat menggunakan array literal.Pada javascript array dapat menyimpan fungsi,object , dan array lainya.Setiap data dalam array memiliki nomor index sehingga akan dengan mudah memanggilnya dengan index tersebut.Array juga memiliki method

Array memiliki 5 properti yang sering digunakan yaitu

- constructor
- length
- index
- input
- prototype

Cara penulisan array
```javascript
let arr = ["hsllo", 1, true]

console.log(arr);
console.log(arr.length)
console.log(arr[1])
console.log(arr[2])
```
```javascript
let arrbuah = ["jeruk", "semangka", "pepaya","rambutan"]
```
- Menambahkan baris terakhir pada array dengan ``push``
```javascript
arrbuah.push("duku")
```
- Menambahkan baris pertama dengan ``unshift``
```javascript
arrbuah.unshift("anggur")
```
- Menghapus baris terakhir dengan ``pop``
```javascript
arrbuah.pop()
```
- Menghapus baris pertama dengan ``shift''
```javascript
arrbuah.shift()
```
- Menghapus dan menambahkan data ditengah dengan ``splice``
```javascript
arrbuah.splice(2,1, "buah aga")
```
- Mengambil data dan mengcopy nya ke variabel baru
```javascript
let slice = arrbuah.slice(2,4)
console.log(arrbuah)
console.log(slice)
```
- menganti data awal dengan index dan menampilkanya
```javascript
let hewan = ["kelinci", "kambing"]
hewan[0] = "kucing"
console.log(hewan)
console.log(hewan.length)
```
### Array looping
```javascript
console.log(arrbuah)
for (let i = 0;i < arrbuah.length;i++){
    console.log(arrbuah[i])
}

for(let i= arrbuah.length -1;i>= 0;i--){
    console.log(arrbuah[i])
}

for (let buah of arrbuah){
    console.log(buah)
}
```
Perulangan dan mengembalikan nilai

- menggunakan ``map``
```javascript
arrbuah.map((item,index) => {
    console.log(item)
})

let buahSegar = arrbuah.map((item) =>{
    return item + " " + "segar"
})
console.log(buahSegar)
```
- Menggunakan ``foreach``
```javascript
let angkaPersenForEach = []
angkaDes.forEach((item) =>{
    angkaPersenForEach.push(item * 100 + "%")
})
console.log(angkaPersenForEach)
```
Perbedaan kedua method diatas adalah ``forEach`` tidak dapat membuat array baru dari hasil operasi yang ada didalam looping.Dalam penggunaanya gunakan ``forEach`` jika hanya memerlukan looping untuk menampilkan saja kemudian gunakan ``map`` jika ingin mengubah nilai array sebelumnya.

### Multidimensional array 
Dapat diartikan dengan array didalam array yang dapat menggunakan property dan method built-in array.Kemudian juga dapat melakukan perulangan didalamnya

```javascript
let arrmulti= [
    ["nama", "alpha"],
    ["umur", 17],
    ["kelas", "JS"]
]
console.log(arrmulti[2][1])
arrmulti[2][1] ="CSS"
console.log(arrmulti)
```
## Javascript Object

Object pada javascript merupakan sebuah variabel yang menyimpan nilai (properti) dan fungsi (method).Properti adalah ciri khas dari objek (variabel). Sedangkan method adalah perilaku dari objek (fungsi).Method dapat dibuat dengan cara mengisi nilai dengan sebuah fungsi.

Sama seperti array object juga dapat menyimpan data dengan tipe yang berbeda.

Contoh object
```javascript
let nama_obj = {
    key1: "value",
    key2: "value2",
};
console.log(nama_obj);
```
Cara mengakses properti object 
```javascript
let siswa = {
    nama: "Brian",
    umur: "21",
    hobi: "futsal",
    "nomor handphone": 0999999999
}
console.log(siswa);
```
- Menggunakan dot notation
```javascript
console.log(siswa.nama)
```
- Menggunakan bracket notation
```javascript
console.log(siswa['nomor handphone']);
```
- Memanggil nama object dengan namaa variabel
```javascript
let properti = "umur"
console.log(siswa[properti]);
```
- Menambahkan properti baru ke object
```javascript
let buku = {
    judul: "kancil suka",
    penulis: "hikayat",
    "jumlah halaman": 340,
};
console.log(buku);
//cara pertamas
buku.tahun= 2022;
buku.terjual= 3000;
console.log(buku);
//cara kedua
buku['penerbit'] = 'mediakita'
console.log(buku);
```
- Assignment menggunakan dot notation dan braket notation
```javascript
let hewan = {
    nama: "kucing",
    kaki: 4,
    warna :"putih",
}
console.log(hewan);
//cara pertama
hewan.nama = 'kelinci'
hewan.warna = 'kuning'
console.log(hewan);
//cara kedua
hewan["kaki"] = 2
console.log(hewan);
```
- Cara menghapus object
```javascript
delete hewan.warna;
console.log(hewan);
```
Method pada object adalah nilai yang kita masukan dalam properti berupa function.Contoh Method:
```javascript
const greeting ={
    welcome: function (){
        return "selamat datang"
    },
    afterPay: function(){
        return 'terima kasih sudah membeli'
    }
}
console.log(greeting.welcome());
console.log(greeting.afterPay());
```
- Looping pada object
```javascript
let murid = {
    nama: "brian",
    umur: 17,
    hobi: "membaca",
    asal: "jakarta"
};
console.log(murid);
for (let key in murid){
    console.log(murid[key]);
}
//[nama,umur,hobi]
console.log(Object.keys(murid));
console.log(Object.values(murid));
```
### Nested object
Merupakan data object yang kompleks yang terdiri dari turunan object lainnya.
```javascript
let novel = {
    judul: 'tips javascript',
    tahun: 2022,
    penulis: {
        penulis1: {
            nama: 'brian',
            umur: 21,
            kota: 'Sleman'
        },
        penulis2:{
            nama: 'wahyu',
            umur: 20,
            kota: 'minggir'
        }
    }
}
console.log(novel);
```
Cara akses properti object pada nested
```javascript
console.log(novel.penulis.penulis1.nama);
console.log(novel.penulis.penulis2.umur);
```
Looping nested
```javascript
for (let key in novel.penulis.penulis1){
    console.log(novel.penulis.penulis1[key]);
}
```
Array Object
Kita juga dapat menyimpad array didalam object tersebut.
```javascript
let users = [
    {
        nama: "dila",
        umur: 17,
        alamat: "bandung"
    },
    {
        nama: "tataa",
        umur: 17,
        alamat: "bandung"
    },
    {
        nama: "nugroho",
        umur: 17,
        alamat: "bandung"
    },
];
console.log(users);
```
Cara menambahkan data ke array dengan menggunakan ``map``
```javascript
let data = users.map((el) =>{
    console.log(el.nama);
    el.status = "aktif"
    return el;
});
console.log(data);
```
Akses data dengan menggunakan index
```javascript
console.log(users[0].nama);
console.log(users[1]['nama']);
```
## Recursive Function
Recursive function artian sederhanannya adalah function yang mengeksekusi diri sendiri, nah jika tidak ada kondisi khusus, maka bisa membuat eksekusi kode terus berulang dan tak pernah berhenti.Recursive digunakan untuk mengganti perulangan biasa.

Looping recursive dapat digunakan pada saat tertentu contohnya dengan menghitung faktorial.Base case merupakan titik paling kecil atau berhenti sedangkan recursive case adalah titik memanggil function itu sendiri.

```javascript
function faktorialFor(n){
    let hasil = 1
    for (let i = n; i>=1; i--){
        console.log(i);
        hasil = hasil * i
    }
    return hasil
}
console.log(faktorialFor(5));
```
```javascript
function faktorial (n){
    if (n== 1){
        return 1
    }else{
    return n * faktorial(n-1)
    
    }
}
console.log(faktorial(3));

```

### Modules
Javascript modules adalah cara untuk memisahkan kode ke file yang berbeda yang bertujuan untuk memudahkan mengelola kode kemudian agar kode tidak menumpuk pada 1 file.

- Export yaitu mengirim data keluar dan dapat melakukan banyak export.kata kunci export ditangkap oleh import
- import memasukan data kedalam

Cara penulisanya:

- tambahkan type= "module" pada script di index.html
- siapkan script ke 2 dan seterusnya
- lakukan import 

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
    <!--file yang ada disini cuma bisa import-->
    <script src="./indonesia.js" type="module"></script>
</body>
</html>
```

```javascript
import entertaiment,{motor as motorJepang, sayHello, smartPhoneJepang} from"./jepang.js"
import {gadget} from './amerika.js'
//jika yang default tanpa kurung kurawal
console.log(entertaiment);
console.log(motorJepang);
console.log(smartPhoneJepang);
console.log(gadget);
motorJepang.splice(1,1)
console.log(motorJepang);

sayHello()

let pakaian = ["batik", "tas", "sepatu"]
export{pakaian}
```
```javascript
 let motor = ["suzuki", "yamaha", "honda", "kawasaki"]
 let smartphone = ["samsung", "nokia", "lenovo", "lg"]

export {motor, smartphone as smartPhoneJepang}

//alternative
//export {motor,smartphone}
//export default cuma bisa 1 saja yang di export
let entertaiment = ["anime","manga", "wibu", "dorama"]
export default entertaiment

export function sayHello(){
    console.log("halloo");
}

//import { pakaian } from "./indonesia.js";
//console.log(pakaian);

import { gadget } from "./amerika.js"
console.log(gadget);
```
## Asynchronous
Synchronous adalah yang paling umum dan mudah di mengerti. Setiap perintah di eksekusi satu persatu sesuai urutan kode yang anda tuliskan.Asynchronous hasil eksekusi atau output tidak selalu berdasarkan urutan kode, tetapi berdasarkan waktu proses. Eksekusi dengan asynchronous tidak akan membloking atau menunggu suatu perintah sampai selesai. Daripada menunggu, asynchronous akan mengeksekusi perintah selanjutnya.

Javascript memiliki sifat singel-tread, non-blocking, asyncronous
non-blocking artinya jika suatu proses terlalu lama makan akan mengijinkan lainya untuk berproses
bloking maka jika data sedang diproses maka lainnya harus menunggu
singel tread yaitu hanya memiliki 1 jalur sehingga harus menunggu jalanya baris perbaris program.
multi tread yaitu memiliki banyak jalur
syncronous yaitu proses penyelesaian secara berurutan
asyncronous proses penyelesaian yang dapat didahului ketika proses awal lama.

```javascript
console.log("A");
//butuh proses lama
callback ->function yang dijadikan sebagai argumen
setTimeout(() =>{
   console.log("B");
},1000)
console.log("C");
```
```javascript
let nontonPromise = new Promise((resolve,reject) =>{
    if(true){
   resolve ("nonton terpenuhi")//berhasil
    }
   reject ("gagal")
})
//untuk menampilkan berhasil
console.log("A");

//nontonPromise
.then(result =>{
    console.log(result);
    return `${result} bareng doi`
})
.then((result) =>{
    console.log(result);
})
//untuk menampilkan gagal
.catch((err)=>{
console.log(err);
})
console.log("C");

```
Promises
```javascript
let nonton = ((kondisi)=>{
    return new Promise((resolve, reject)=>{
        if (kondisi == "jalan"){
            resolve("nonton terpenuhi")
        }
        reject("batal nonton")
    })
})
nonton("jalan")
.then(result =>{
    console.log((result));
})
.catch(err => {
    console.log(err);
})
```
## Web storage
Web storage adalah salah satu Web API  yang dapat menyimpan data secara local pada sisi client.

Macam-macam web storage pada sisi client

- Cache dalam web browser adalah teknologi yang digunakan untuk menyimpan atau asset berupa data, gambar dan dokumen.
- Cookie sebagian kecil dari data yang dikirim dari suatu situs web dan disimpan dalam komputer pengguna oleh web browser contohnya menyompan login informasi, menyimpan configurasi website.
- Session Storage adalah penyimpanan pada sisi client yang digunakan untuk menyimpan data selama web-browser atau halaman web belum ditutup atau keluar.

Mendeklarasikan suatu nilai
```javascript
sessionStorage.setItem('variabel ', 'value ');
```
Mengambil data
```javascript
sessionStorage.getItem('variabel ');
```
Menghapus data
```javascript
sessionStorage.removeItem('variabel ');
```
Menghapus semua session storage
```javascript
sessionStorage.clear();
```
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
    <form action="" class="container">
        <input type="text" placeholder="Hari ini saya akan">
        <ul id="list-container">
            <li>Makan</li>
            <li>Writing</li>
        </ul>
    </form>
    <script src="script.js"></script>
</body>
</html>
```

```javascript
document.querySelector('form').addEventListener('submit', (ev)=>{
    ev.preventDefault();
    const userInput = document.querySelector("input").value
    //simpan ke local storage
    const li = document.createElement('li');
    li.innerText = userInput;

    const container = document.querySelector("#list-container");
    container.appendChild(li);
});
```
