# Writing and PresentationTest Week 5
## React
React js adalah sebuah library javascript yang biasa digunakan untuk membangun UI pada suatu website atau aplikasi web.Mengapa kita menggunakan react karena dengan menggunakan react dapat membuat aplikasi web menjadi lebih cepat walaupun harus memproses banyak data sekaligus.Terdapat dua fitur tambahan yang menjadi keunggulan react yaitu JSX dan virtual DOM.

- JSX adalah extension syntax JavaScript yang memungkinkan Anda untuk memodifikasi Document Object Model (DOM) dengan kode bergaya HTML.JSX hanya bisa memiliki 1 elemen parent.Pada JSX atribut class diganti dengan className.
- Virtual DOM adalah salinan dari DOM yang ingin dipdate.

Cara menggunakan react:

- Pertama install node js
- masuk ke terminal kemudian ketikan ``create-react-app``
- kemudian masuk ke folder yang dibuat dengan ``cd directori``
- jalankan file dengan ``npm start``
## React Components
Component memungkinkan membagi User Interface (UI) menjadi bagian-bagian yang independen dan dapat digunakan kembali, dan memikirkan setiap bagian secara terpisah.

Component pada react dibagi menjadi 2 yaitu:

- Component class
```javascropt
class Welcome extends React.Component {
  render() {
    return <h1>Halo, {this.props.name}</h1>;
  }
}
```
- Component function
Cara termudah mendefinisikan Component adalah dengan menulis Function Javascript
```javascript
function Welcome(props) {

  return <h1>Hello, {props.name}</h1>;

}
```
Dengan menggunakan fungsi ini komponen react dapat menerima sebuah Props atau argumen object dengan data dan dikembalikan sebuah element react.
Kedua komponen tersebut memiliki fitur tambahan yaitu:

- Merender sebuah komponen

Props adalah ketika sebuah element react yang dibuat pengguna mengoper atribut JSX ke dalam komponen sebagai objek tunggal.
```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="world" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```
- Menyusun komponen
Pada komponen ini dapat menuju ke komponen lainnya dan dapat menggunakan abstraksi dari komponen yang sama seperti sebuah tombol,form,dialog,tampilan.
```javascript
function Welcome(props) {
  return <h1>Halo, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}
export default Welcome;
```
- Mengekstrasi komponen

Untuk memisahkan komponen menjadi ke bentuk lebih kecil
```javascript
function Avatar(props) {
  return (
    <img className="Avatar"
      src={props.user.avatarUrl}
      alt={props.user.name}
    />
  );
}
```
React komponen memiliki Kelebihan

- Declarative
- Component-based
- Learn Once,write anywhere

Stateful Componen dan Stateless Component

Stateful components adalah komponen yang menggunakan state. Sedangkan Stateless adalah komponen yang tidak menggunakan state.

State dan props
State adalah sebuah properti atau variabel yang didefinisikan di dalam sebuah class atau merupakan data lokal, sedangkan props adalah properti atau variabel yang berasal dari luar class atau class parent.Props adalah suatu cara untuk mengirim dan mengakses data dari komponent lain secara langsung.
```javascript
import PropTypes from "prop-types";
const MyComponent  = ({ name, status }) => {
    return(
        <>
<h1>Hello, {name}</h1>
<p>Status transaksi: {status}</p>
</>
);
```
```javascript
function App() {
  const[isLogin, setIsLogin] = useState(false);
  return (
    <>
    {!isLogin && <button onClick={() => setIsLogin(true)}>Login</button>}
    <br />
    {isLogin? <Counter/> :<span>Login dulu</span>}
      {isLogin && <ListUser/>}
      <MovieCard/>
      <MyComponent/>
    </>
  );
}
```
## React Hooks
Hooks merupakan fitur baru di React 16.8. Fitur ini memungkinkan Anda menggunakan state dan fitur React lainnya tanpa menuliskan sebuah kelas.

beberapa react hooks yang umum di gunakan, yaitu:

- useState di gunakan untuk membuat state di function komponen.Fungsi useState akan mereturn pasangan nilai dari state dan fungsi untuk mengubah state tersebut dalam bentuk sebuah array
```javascript
import { useState } from "react";

const Counter= () =>{
    const [count, setCount]= useState(0)

    const increment = () =>{
        console.log("increment");
        setCount(count+1)
    }

```
- useEffect digunakan untuk menambahkan side effect ke function komponen.useEffect hooks akan menerima dua parameter, yaitu sebuah callback dan sebuah array.Array di parameter kedua ini, bisa di isi atau bisa juga dikosongkan.
useEffect akan di jalankan setiap kali item di dalam array tersebut berubah.
```javascript
const ListDigimon = () =>{
    const [isLoading, setIsLoading] = useState(true)
    const [digimons, setDigimons] = useState([])

    console.log("List Digimon dipanggil");

    useEffect(()=> {
        console.log("List Digimon sudah di mount");
        axios("https://digimon-api.vercel.app/api/digimon")
        .then(res => {
            setDigimons(res.data)
            setIsLoading(false)
    })
    },[]);

    console.log(digimons);
```
- useRef umunnya digunakan untuk mengakses DOM node dalam sebuah komponen.
Misal kita mau mengakses element input, maka kita bisa menambahkan ref ke element inputnya.
- useMemo fungsinya adalah agar component di render jika ada perubahan state atau props.React hooks useMemo digunakan untuk mengoptimalkan performance sebuah function.
- useCallback digunakan untuk mencegah render child komponen yang tidak di perlukan.

## React From
Biasanya kita membuat form menggunakan file html.Nah kita juga bisa membuat form dengan react dan menggunakan tag html didalamnya.menggunakan state untuk mendeklarasikan variabelnya kemudian dengan tag onSubmit dan onChange untuk membuat tombol dapat bekerja di react serta even.target.value untuk mengisikan data pada variable dan ditampilkan dengan fungsi e.preventDefault
```javascript
import { useState } from "react";
import axios from "axios";

const Form = () => {
    const [name,setName] = useState("");
    const [address, setAddress] = useState("");
    const [program, setProgram] = useState("");
    const [data,setData] = useState({})

    // console.log(name, address);
    const handleSubmit= (e) =>{
        e.preventDefault();
        // setData({name,address,program})
        // setName("");
        // setAddress("");
        // setProgram("");
        axios.post("",{
            name,
            address,
            program,
        })
        .then(()=>{

            setData({name,address,program})
            setName("");
            setAddress("");
            setProgram("");
        })
        .catch(()=>{
            console.log(err);
        })
        // alert(`Nama:${name}, Address: ${address}`)
    }
    console.log(data);
    return (
        <>
        <form action="" onSubmit={handleSubmit}>

            <label htmlFor="name">Name</label>
            <input type="text" value={name} onChange={(e)=> setName(e.target.value)}/>
            <label htmlFor="address">Address</label>
            <input type="text" value={address} onChange={(e) => setAddress(e.target.value)}/>
            <label htmlFor="option">program</label>
            <select value={program} onChange={(e) => setProgram(e.target.value)}>
                <option value="">Pilih program</option>
                <option value="KM">KM</option>
                <option value="SIC">SIC</option>
                <option value="KM">KM</option>
                <option value="Ammn">Ammn</option>
            </select>
            <button type="submit">Submit</button>
        </form>
        <br />
        <h2>Name:{data.name}</h2>
        <h2>Address:{data.address}</h2>
        <h2>Program:{data.program}</h2>
        </>
    )
}

export default Form;
```
