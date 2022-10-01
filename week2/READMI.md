# Writing and Presentation Test week 2
## Javascript Scope dan function

Scope adalah konsep dalam flow data variable kemudian menentukan suatu variable dapat diakses menggunakan scope atau tidak.

Scope dibagi menjadi tiga yaitu:

- Global scope adalah kode yang cakupanya di seluruh file javascript sehingga bisa diakses oleh semua fungsi yang ada di dalam file javascript.Agar dapat digunakan perlu menuliskan didasar atau root dari file javascript.
```javascript
let makanan = 'bakso'
function greeting(){
    return makanan;
}
console.log(makanan)
````
- Local scope atau function scope adalah cakupan kode yang dapat diakses dari dalam fungsi itu saja tetapitidak dapat diakses diluar fungsi tersebut.
```javascript

function greeting(){
    let makanan = 'bakso'
    return makanan;
}
console.log(greeting())//bakso
console.log(makanan)//index.js:7 Uncaught ReferenceError: makanan is not defined

```
- Block scope adalah cakupan kode yang hanya terbatas pada block kode saja.Block kode adalah area yang ada diantara kurung kurawal.

### Function
function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan task.Fungsi merupakan sebuah objek karena memiliki properti dan method.

4 cara membuat fungsi di javascript

- Menggunakan cara biasa
```javascript
function namaFungsi(){
    console.log("Hello world")
}
```
- Membuat fungsi dengan ekspresi
```javascript
let namaFungsi = function(){
    console.log("Hello world")
}
```
- Membuat fungsi dengan tanda panah
```javascript
let namaFungsi =()=>{
    console.log("Hello world")
}
```
- Membuat fungsi dengan konstruktor
```javascript
let namaFungsi = new Function('console.log("Hello World");');
```
Cara memanggil dan eksekusi fungsi

Cara memanggil fungsi dengan cara menuliskan nama fungsinya seperti ``namaFungsi()``
```javascript
function halo(){
    console.log("Hello world")
}
//memanggil fungsi
halo()
```
Parameter dan argumen

Parameter adalah variabel yang menyimpan nilai untuk diproses didalam fungsi sedangkan argumen adalah nilai yang digunakan saat memanggil function.
```javascript
function perkalian(a, b){
    return a * b
}
```
## Data Type Built in Prototype & Method
Tipe data adalah sebuah pengelompokan data untuk memberitahu compiler atau interpreter bagaimana programer ingin mengolah data tersebut.

Ada 6 tipe data di javascript

- String yaitu setiap karakter yang dibungkus dengan kutip satu (‘) atau kutip dua (“) dianggap sebagai string oleh JavaScript
- Number yaitu angka pada tipe data javascript 
- Null
- Undefined
- object(non-primitif)

Perbedaan primitif dan non-primitif

Tipe data primitif memiliki sifat immutable dan tidak memiliki properties sementara tipe data non-primitif bersifat mrtable dan memiliki propertis.

Jenis-jenis method array

- Join()
- reverse()
- Sort()
- Splice()
- Push dan pop()
- Shift dan unshift()
- toString()

## HTML DOM
javascript DOM (Document Object Model) adalah interface yang memungkinkan developer untuk memanipulasi konten ,struktur dan style pada suatu web.

Strukrut object dan definisinya

- Element HTML sebagai objek
- Propertis dan event elemen HTML
- method elemen HTML

cara mengakses element tertentu dengan DOM

- Memanggil tag HTML dengan menggunakan ID 
```javascript
let title = document.getElementById("title")
```
- Memanggil tag HTML dengan Class name
```javascript
let list = document.getElementsByClassName("list")
```
- Memanggil tag HTML menggunakan query selectoor
```javascript
let listQuery = document.querySelector(".list")
let itemQueryAll = document.querySelectorAll(".item")
```
- Mengambil tag HTML dari parent dan sibling
```javascript
let itemQueryP = document.querySelector(".item")
console.log(itemQueryP)

//ambil parentnya
console.log(itemQueryP.parentElement);
console.log(itemQueryP.closest(".list"))
//sibling
console.log(itemQueryP.previousElementSiblingc)
console.log(itemQueryP.nextElementSibling);
```
- Memanipulasi content HTML dengan innerhtml
```javascript
let app = document.getElementById("app")
console.log(app)

app.innerHTML = "<h1>Hallo</h1>"
```
- Memanipulasi content HTML dengan innertext
```javascript
let app = document.getElementById("app")
console.log(app)
app.innerText = "<h1>juga</h1>"
```
- Memanipulasi content HTML dengan appen dan appenChild
```javascript
let p = document.createElement("p")
p.innerText = "ini adalah paragraf"
app.append(p)

let p2= document.createElement("p")
p2.innerText= "paragraf 2"
app.appendChild(p2)
```
- Menghapus elemen html dengan remove
```javascript
let end = document.getElementById("end")
end.remove()
```
- mengubah style menggunakan DOM
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #tess{
            width: 100px;
            height: 20px;
            background-color: aqua;
        }
    </style>
</head>
<body>
    <div id="tess"></div>
    <div id="app"></div>
    <div id="end">
        <a href="google.com" class="link">Google</a>
    </div>
    <script src="index.js"></script>
</body>
</html>
```
```javascript
console.log(link.attributes)
console.log(link.getAttribute("href"));
link.setAttribute("id" ,"google")

link.style.color = "black"
link.style.border = "1px solid black"
link.style.padding = "5px 20px"
link.style.backgroundColor = "aqua"
```
HTML DOM juga dapat digunakan dengan HTML event sebagai berikut

- Mouse click
- Page click
- Mouse move
- Input field change

Menggunakan DOM untuk halaman login
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
    <div class="container">
        <form id="sign-in">
            <h1>Sign-in</h1>

            <div class="field">
                <label for="username">username</label>
                <input type="text" id="username" name="username">
            </div>
            <div class="field">
                <label for="password">password</label>
                <input type="password" id="password" name="password">
            </div>
            <button type="submit">login</button>
        </form>
    </div>
    <script src="login.js"></script>
</body>
</html>
```
```javascript
let loginForm = document.querySelector("#sign-in")

loginForm.addEventListener("submit", (event) =>{
    event.preventDefault()
    console.log("ini dari form yang di submit")
})
```
DOM Event merupakan objek untuk membantu interaksi dengan document HTML.

- Ketika mengklik mouse
- ketika halaman web dimuat
- ketika gambar dimuat
