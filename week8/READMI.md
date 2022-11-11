# Writing And Presentation Test Week 8
## React Context
Context adalah suatu cara untuk mengoper data melalui diagram komponen tanpa harus memlakukan props secara manual disetiap tingkat.

Pada aplikasi react jika tidak menggunakan Context maka ketika ingin memproses suatu data mengkaruskan data dioper dari parent ke childnya dengan props.Karena dengan cara tersebut terlalu rumit kemudian react menciptakan context untuk menggunakan data tanpa harus mengoper props secara explisit melalui tingkatan diagram.

Context dirancang untuk berbagi data secara global untuk dapat digunakan oleh komponen react lainnya.
Jika hanya ingin menghindari mengoper beberapa props melalui banyak tingkatan, komposisi komponen seringkali menjadi solusi yang lebih sederhana daripada context.Dapat juga mengoper suatu childern atau memiliki beberapa slot terpisah untuk childern.
```javascript
  function Page(props) {
  const user = props.user;
  const content = <Feed user={user} />;
  const topBar = (
    <NavigationBar>
      <Link href={user.permalink}>
        <Avatar user={user} size={props.avatarSize} />
      </Link>
    </NavigationBar>
  );
  return (
    <PageLayout
      topBar={topBar}
      content={content}
    />
  );
}
```
## Context API

Context API merupakan sebuah cara untuk membuat global state yang nanti bisa digunakan di semua level komponen tanpa harus mengirim props ke lower level component secara manual. Context API ini merupakan alternatif dari props drilling. Props drilling sendiri adalah cara mempassing props dari grandparent ke parent ke child ke grandchild dan seterusnya.
```javascript
const MyContext = React.createContext(defaultValue);
```
Argumen default value hanya digunakan ketika memiliki provider yang cocok pada diagram.

## Context provider

```javascript
<MyContext.Provider value={/* beberapa nilai */}>
```
Objek context memiliki sebuah komponen yaitu Provider react yang berfungsi agar suatu komponen dapat menerima perubahan Context yaitu dengan cara memerima props value untuk dioper ke komponen yang keturunan Provider.Sebuah Provider dapat dihubungkan ke banyak consumer.Cara perubahan ditentukan dapat menyebabkan beberapa masalah 

## Class.contextType

Terdapat properti contextType pada kelas diberikan objek context yang dibuat oleh react.context() dengan itu dapat menggunakan tipe context this.context.Hanya bisa menerima satu context menggunakan API ini.

## Context.Consumer
```javascript
<MyContext.Consumer>
  {value => /* render sesuatu berdasarkan nilai *context*-nya */}
</MyContext.Consumer>
```
Komponen React yang menerima perubahan context. Ini memungkinkan Anda menerima context di dalam komponen fungsi.Jika tidak menggunakan provider untuk context argumen value akan sama dengan defaultValue yang diteruskan ke createContext().

## Context displayName
Objeck context menerima properti string dan reaxt menentukan apa yang harus ditampilkan untuk context tersebut.

## React Testing
Cara kita untuk memastikan kode react yang kita tulis sesuai dengan harapan awal dibuatnya program tersebut.Testing dibagi menjadi dua yaitu manual dan automatic.Contoh sederhana testing manual adalah dengan menggunakan console log pada javascript kemudian automatic menggunakan jest atau react testing library 

- Jest adalah test runner pada JavaScript yang memungkinkan Anda mengakses DOM melalui jsdom. Sementara jsdom hanyalah perkiraan cara kerja browser, seringkali cukup baik mengetes komponen pada React. Jest memberikan kecepatan iterasi yang bagus dikombinasikan dengan fitur-fitur yang powerful seperti mocking modules dan timers sehingga Anda dapat memiliki kontrol lebih pada kode yang dijalankan.
- React Testing Library adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya. Pendekatan ini membuat refactoring menjadi mudah dan juga mendorong Anda untuk menerapkan best practices untuk aksesbilitas. Mungkin tidak memberikan cara untuk me-render secara “dangkal” pada sebuah komponen tanpa anak, test runner seperti Jest yang memungkinkan Anda melakukan mocking.

Pengujian dengan function component

- persiapan menggunakan render pohon react ke sebuah element DOM yang terhubung ke dokumen
- act memastikan semua pembaharuan yang berhubungan dengan unit sudah diproses DOM.
- rendering merupakan pengujian apakah komponen dengan props dirender dengan benar.
- pengambilan data
- modul-modul
- event
- pengatur waktu
- pengujian snapshot
- multiple render

Penggunaan testing

- Seperti halnya setiap proyek JavaScript, Anda memerlukan lingkungan NPM (pastikan untuk menginstal Node di sistem Anda). Buat folder baru dan inisialisasi proyek dengan:
``mkdir getting-started-with-jest && cd $_
npm init -y ``
- install jest ``npm i jest --save-dev ``
- Mari kita juga mengonfigurasi skrip NPM untuk menjalankan pengujian kita dari baris perintah. Buka package.json dan konfigurasikan skrip bernama test untuk menjalankan Jest: 

```javascript
 "scripts": {
    "test": "jest"
  },
```
