# Writing and Presentation Test Week 7
## Prop Types
PropsTypes adalah pengecekan atau validasi terhadap data yang dikirim menggunakan props apakah sudah sesuai atau tidak sehingga kedepanya tidak menyebabkan error akibat salah mengisikan data.PropTypes mengirimkan berbagai jenis validator yang dapat digunakan untuk memastikan bahwa data yang diterima valid.

Contoh Prop Types
```javascript
import propTypes from "prop-types"
const StudentInfo = ({name, age}) =>{
    return(
        <>
        <h2>{name}</h2>
        <h2>{age + 5}</h2>
        </>
    )
}
StudentInfo.propTypes = {
// tipe data string
    name: propTypes.string,
// tipe data number
    age : propTypes.number,
```
PropTypes mengirimkan berbagai jenis validator yang dapat digunakan untuk memastikan bahwa data yang diterima valid.Padacode diatas menggunakan Propstypes .string dan .number yaitu ketika nilai yang dikirimkan tidak sesuai maka akan muncul peringatan di konsol javascript itulah fungsi Propstypes untuk mengecek suatu nilai data apakah sesuai dengan yang kita imputkan.

Contoh validator yang sudah disediakan:
```javascript
StudentInfo.propTypes = {
// tipe data string
    name: propTypes.string,
// tipe data number
    age : propTypes.number,
//tipe data bebas
name: propTypes.any.isRequired,//isrequired data harus ada
//memberikan obsi untuk tipe data
age: propTypes.oneOfType([propTypes.string,propTypes.number])
//tipe data array
data: propTypes.array,
//cek data value dari props
data: propTypes.arrayOf(propTypes.number)
//array dengan berbagai data dikasil pilihan
data: propTypes.arrayOf(
    propTypes.oneOfType([propTypes.number, propTypes.string])
)
//tipe data object
info: propTypes.object
// cek nilai object
info: propTypes.shape({

    hobby: propTypes.string,
    class: propTypes.number,
})
//cek nilai key dari object jumlah harus sama dengan yang ditampilkan
info: propTypes.exact({
    hobby: propTypes.string,
     class: propTypes.number,
}).isRequired,
 }
```
PropsTypes.element dapat menentukan hanya menerima satu komponen anak yang dapat dikirimkan ke komponen lain.Nilai default props dapat didefinisikan dengan menambahkan properti khusus defaultProps.

## React Router
Routing  adalah proses pemetaan antara sebuah URL ke dalam sebuah halaman yang terdapat konten / UI (User Interface) sesuai dengan URL yang dituju.Kita harus menginstall terlebih dahulu sebelum digunakan kemudian mengimport pada bagian main atau index dan menambahkan library yaitu react router.

Tahapan penggunaan React Router 

- Install react router ``$ npm install react-router-dom@6``
- Mengimport BrowserRouter dari react-router
```javascript
import * as React from "react";
import * as ReactDOM from "react-dom";
import { BrowserRouter } from "react-router-dom";
import "./index.css";
import App from "./App";
import * as serviceWorker from "./serviceWorker";

ReactDOM.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
  document.getElementById("root")
);
```
- Kemudian kita dapat menggunakan react route ke file yang diinginkan dengan dibungkus tag ``<Routes>`` dan menggunakan ``<Route patch>`` untuk memasukan alamat yang dituju.
```javascript
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import {Routes, Route, Link} from 'react-router-dom'
import './App.css'
import HomePage from './pages/HomePage'
import AboutPage from './pages/AboutPage'
import DetailPage from './pages/DetailPage'
import AboutStudent from './pages/AboutStudent'
import AboutTeacher from './pages/AboutTeacher'
import AboutSchool from './pages/AboutSchool'

function App() {

  return (
    <>
    <nav>
      <Link to={"/"}>Home |</Link>
      <Link to={"/about"}>About</Link>
    </nav>
    <Routes>
    <Route path='/' element={<HomePage/>}/>
    <Route path='/detail/:id' element={<DetailPage/>}/>
    <Route path='/about' element={<AboutPage/>}>
      <Route path='student' element={<AboutStudent/>}/>
      <Route path='teacher' element={<AboutTeacher/>}/>
      <Route index element={<AboutSchool/>}/>
    </Route>
    </Routes>
    </>
  )
}

export default App

```
- Dapat juga membuat link dengan tag ``<Link>`` di file yang berbeda
```javascript
import {Outlet,Link} from 'react-router-dom'
const AboutPage = ()=>{
    return(
        <>
        <Outlet/>
        <Link to={"student"}>About Student |</Link>
        <Link to={"teacher"}>About Teacher</Link>
        </>
    )
}
export default AboutPage;
```
- jikan ingin menampilkan tampilan home pertama kali muncul maka pada pathnya diberi ``/`` dan untuk file yang dingin ditampilkan pertama menggunakan ``index``

- Membuat navigasi menggunakan Link
```javascript
import { Route, Routes, Link } from "react-router-dom"
import { Home } from "./Home"
import { BookList } from "./BookList"

export function App() {
  return (
    <>
      <nav>
        <ul>
          <li><Link to="/">Home</Link></li>
          <li><Link to="/books">Books</Link></li>
        </ul>
      </nav>

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/books" element={<BookList />} />
      </Routes>
    </>
  )
}
```
- Dynamic routing
```javascript
<Routes>
    <Route path='/' element={<HomePage/>}/>
    <Route path='/detail/:id' element={<DetailPage/>}/>
</Routes>
```
- Routing priority yaitu mengakses bagian tertentu dalam sebuah halaman
```javascript
<Route path='/about' element={<AboutPage/>}>
      <Route path='student' element={<AboutStudent/>}/>
      <Route path='teacher' element={<AboutTeacher/>}/>
      <Route index element={<AboutSchool/>}/>
    </Route>
```
- Nested routing adalah mengakses child dari halaman tertentu
```javascript
function App() {
  return (
    <>
      <nav>
        <Link to={"/"}>home</Link>
        <Link to={"/about"}>about</Link>
        <Link to={"/product"}>product</Link>
        <Link to={"/product/detail/xx"}>detail</Link>
        <Link to={"/buku/penerbit/erlanga"}>erlanga</Link>
        <Link to={"/product/merk/asus"}>asus</Link>
      </nav>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<AboutPage />} />
        <Route path="/product">
          <Route path="" element={<Product />} />
          <Route path="detail/:id" element={<ProductDetail />} />
          <Route path="new">
            <Route path="phone" element={<ProductNewPhone />} />
            <Route path="laptop" element={<ProductNewLaptop />} />
          </Route>
```
## React Redux
react redux yang merupakan aplikasi state manajement untuk memusatkan state agar dapat diakses oleh semua komponen secara langsung.State management adalah cara untuk memfasilitasi komunikasi dan berbagai data lintas komponen. State management menciptakan struktur data yang nyata untuk mewakili keadaan aplikasi Anda yang dapat Anda gunakan untuk membaca dan menulis.React redux berfungsi untuk melakukan perubahan state yang dibutuhkan oleh setiap fungsional yang ada di suatu aplikasi.Redux dibuat pada tahun 2015 oleh Dan Abramov dan Andrew Clark.

Cara install redux

- ``npm install react-redux``

Komponen redux dan cara kerjanya

- Action merupakan suatu event, di mana ia adalah satu-satunya cara Anda dapat mengirim data dari aplikasi Anda ke Redux Store. Data tersebut pun dapat berasal dari interaksi pengguna, panggilan API (API request), atau bisa juga pengiriman formulir. Action ini pun dikirim menggunakan metode ‘store.dispatch ()’.Action merupakan objek JavaScript biasa dan harus memiliki tipe properti (property type).
```javascript
export const INCREMENT = "INCREMENT"
export const DECREMENT = "DECREMENT"

export function increment (){
    return{

        type: INCREMENT
    }
}

export function decrement(){

    return{
        type: DECREMENT
    }
}
```
- Reducer adalah fungsi murni yang mengambil status aplikasi saat ini. Reducer juga berfungsi untuk melakukan tindakan,dan mengembalikan status baru (new state). Status ini disimpan sebagai objek, dan menentukan bagaimana status aplikasi berubah sebagai respons terhadap tindakan yang dikirim.
```javascript
import { INCREMENT,DECREMENT } from "../action/KeranjangAction"

const inisitialState ={
    count:0,
}

const KeranjangReducer = (state = inisitialState, action)=>{
    switch (action.type) {
        case INCREMENT:
            return{
                count: state.count+1
            }
            case DECREMENT:
                return{
                    count: state.count-1
                }
        default: return state
    }
}

export default KeranjangReducer;
```
- Store berfungsi untuk menyimpan status aplikasi. Sangat disarankan untuk hanya menyimpan satu store di aplikasi Redux apa pun. Anda dapat mengakses status yang disimpan, mengupdate status, dan mendaftarkan atau membatalkan pendaftaran listener melalui metode helper.
```javascript
import {combineReducers, createStore} from "redux"
import KeranjangReducer from "../reducer/keranjangReducer";
import todoReducer from "../reducer/TodoReducer";


const allReducer = combineReducers({

    counter: KeranjangReducer,
    todo: todoReducer
})
const store = createStore(allReducer)

export default store;
```
Redux Thunk adalah middleware yang memungkinkan Anda memanggil pembuat aksi yang mengembalikan fungsi sebagai ganti objek aksi. Fungsi itu menerima metode pengiriman penyimpanan, yang kemudian digunakan untuk mengirim aksi sinkron di dalam isi fungsi setelah operasi asinkron selesai.

- install redux thunk ``npm install redux-thunk@2.3.0``
- Terapkan middleware saat membuat penyimpanan aplikasi menggunakan ``applyMiddleware`` 
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import './index.css';
import rootReducer from './reducers';
import App from './App';
import * as serviceWorker from './serviceWorker';

const store = createStore(rootReducer, applyMiddleware(thunk));

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```
- Menggunakan Redux thunk untuk membuat todo list
```javascript
import { connect } from 'react-redux';
import { addTodo } from '../actions';
import NewTodo from '../components/NewTodo';

const mapDispatchToProps = dispatch => {
  return {
    onAddTodo: todo => {
      dispatch(addTodo(todo));
    }
  };
};

export default connect(
  null,
  mapDispatchToProps
)(NewTodo);
```
- Selain menerima status fungsi yang dikembalikan oleh asinkron dengan reduk juga menggunakan metode ``getState``yang juga berfungsi membatasiaplikasi dengan fungsi tertentu.
