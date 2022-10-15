# Writing and presentation test week 4
## Asynchronous 
Javascript memiliki sifat singel-tread, non-blocking, asyncronous
non-blocking artinya jika suatu proses terlalu lama makan akan mengijinkan lainya untuk berproses
bloking maka jika data sedang diproses maka lainnya harus menunggu
singel tread yaitu hanya memiliki 1 jalur sehingga harus menunggu jalanya baris perbaris program.
multi tread yaitu memiliki banyak jalur
syncronous yaitu proses penyelesaian secara berurutan
asyncronous proses penyelesaian yang dapat didahului ketika proses awal lama.

### Javascript asynchrounous
- callback mengembalikan suatu nilai
- promises ketika kondisi memenuhi maka akan menjalankan then berdasar resolve ketika salah masuk ke catch berdasarkan perintah reject
- Async/Await merupakan sebuah syntax khusus yang digunakan untuk menangani Promise agar penulisan code lebih efisien dan rapih.

Contoh Program

```javascript
let nonton = ((kondisi)=>{
    return new Promise((resolve, reject)=>{
        if (kondisi == "jalan"){
            resolve("nonton terpenuhi")
        }
        reject("batal nonton")
    })
})
```
Menjalankan kode promise dapat menggunakan 2 cara

- Promise
```javascript
nama promise.then().catch()
nonton("jalan")
.then(result =>{
    console.log((result));
})
.catch(err => {
    console.log(err);
})
```
- async await
```javascript
asyncNonton()
async function asyncNonton(){
    try{
        let result = await nonton()
        console.log(result);
    }catch (error){
        console.log(error);
    }
}
```
### Fetch
- Promise
```javascript
fetch("https://digimon-api.vercel.app/api/digimon")
.then(result =>{
    console.log(result);
    return result.json()
})
.then(result =>{
    console.log(result);
})
```
- Aysnc await
```javascript
let containerDigimon = document.getElementById("list-digimon")
let digimons = []
let getDataDigigmon = async () =>{
    let response =await fetch("https://digimon-api.vercel.app/api/digimon")
    let digimons = await response.json()

    digimons.forEach(item =>{
        console.log(item);
        containerDigimon.innerHTML += 
        `<div>
        <img src="${item.img}" width = "100">
        <h3>${item.name}</h3>
        </div>`
    })

}
getDataDigigmon()
```
## Git dan Github lanjutan
Git adalah tools untuk para developer yang befungsi sebagai version control system untuk mengembangkan atau berkolaborasi untuk membuat aplikasi yang dapat mengelola code program yang akan ditambahkan atau diganti.Version Control System adalah sebuah kategori software yang membantu sebuah tim software mengelola perubahan pada source code. Version control system mencatat semua modifikasi yang dilakukan ke kode di sebuah database khusus.

Untuk berkolaboradi dapat menggunakan beberapa perintah git seperti dibawah ini

- Git init untuk membuat repositori baru
- git add untuk menambahkan file ke index
- git clone untuk chechout repositori
- git commit untuk melakukan commit pada perubahan yang telah dilakukan
- git push untuk mengirimkan perubahan ke master
- git checkout untuk membuat branch atau berpindah branch
- git remote membuat terhubung dengan remote repositori
- git branch membuat dan menghapus branch
- git pull menggabungkan perubahan
- git merge menggabungkan sebuah branch ke branch aktif

## Responsive Web Design
Responsive web  design adalah tampilan website yang menyesuaikan dengan device pengguna dan dapat menyesuaikan ukuran layar pengguna serta semua aspek web tersebut dari interface,image,font dan vidio akan menyesuaikan ukuranya supaya nyaman digunakan di device berbeda.

Syarat website responsive

- Layout dan tata letak
- Media
- Typography

Cara membuat tampilan website responsive

- Menambahkan viewport pada html untuk membuat berukuran sesuai device
- Menggunakan max-width untuk mengatur gambar
- merubah nilai pada css menggunakan rem yang mengacu nilai root html dan em yang mengacu nilai parent terdekat
- menggunakan ukuran vh dan vw yang akan mengacu pada ukutan viuwport
- menggunakan nilai persen(%)yang mengacu pada nilai parentnya
- menggunakan media dan breakpoin.Media query merupakan modul CSS3 yang berguna membuat layout kita responsive dengan menyesuaikan tampilan berdasarkan ukuran layar perangkat.Media query merupakan modul CSS3 yang berguna membuat layout kita responsive dengan menyesuaikan tampilan berdasarkan ukuran layar perangkat

## Bootstrap 
Boostrap adalah framework HTML, CSS, dan JavaScript yang berfungsi untuk mendesain website responsive dengan cepat dan mudah.Diciptakan pada tahun 2011 oleh Mark Otto dan Jacob Thornton dari Twitter

Kegunaan Boostrap

- Membuat website mobile friendly
- memudahkan resize gambar
- menambahkan halaman tanpa ribet
- membuat website interaktif

Cara konfigurasi bootstrap
Membuat tag boostrap di head html dengan href dan pada href diisi link bootstrap online.Menggunakan bootstrap dapat mengelompokan beberapa properti seperti button yaitu btn-primary.btn-success.

Layout pada Bootstrap

- Breakpoin pada bootstrap ada 5 yaitu sm,md,lg,xl,xxl
- setiap breakpoin memiliki 12 komponen yang menampung container hingga dapat digunakan dengan baik.

Containers adalah blok bangunan dasar Bootstrap yang berisi, melapisi, dan menyelaraskan konten Anda dalam perangkat atau area pandang tertentu.elemen tata letak paling dasar di Bootstrap dan diperlukan saat menggunakan sistem grid default

Bootstrap grid system menggunakan serangkaian wadah, baris, dan kolom untuk menata dan menyelaraskan konten. Itu dibangun dengan flexbox dan sepenuhnya responsif.

Contoh grid system
```html
<div class="container">
  <div class="row">
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
  </div>
</div>

```

