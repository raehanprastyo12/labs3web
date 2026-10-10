Berikut adalah penjelasan lengkap dan terstruktur untuk menjawab keempat pertanyaan tugas pada modul praktikum tersebut:

---

Praktikum 3: CSS Dasar

Tujuan
1. Mahasiswa mampu memahami konsep dasar CSS
2. Mahasiswa mampu memahami aturan penulisan pada CSS
3. Mahasiswa mampu memahami selector sebagai pengontrol CSS
4. Mahasiswa mampu membuat pengaturan CSS pada HTML


Pertanyaan dan Tugas
1. Lakukan eksperimen dengan mengubah dan menambah properti dan nilai pada kode CSS
dengan mengacu pada CSS Cheat Sheet yang diberikan pada file terpisah dari modul ini.
2. Apa perbedaan pendeklarasian CSS elemen h1 {...} dengan #intro h1 {...}? berikan
penjelasannya!
3. Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline
CSS pada elemen yang sama. Deklarasi manakah yang akan ditampilkan pada browser?
Berikan penjelasan dan contohnya!
4. Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector
tersebut terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada

browser? Berikan penjelasan dan contohnya! ( <p id="paragraf-1" class="text-
paragraf"> )


### **1. Eksperimen Properti dan Nilai CSS**

Langkah ini merupakan bentuk eksplorasi mandiri menggunakan properti tambahan dari *CSS Cheat Sheet*. Anda dapat mencoba menambahkan properti dekoratif pada file CSS Anda, seperti:

* `border-radius: 8px;` (untuk membuat sudut elemen menjadi melengkung)
* `box-shadow: 0 4px 8px rgba(0,0,0,0.1);` (untuk memberikan efek bayangan)
* `transition: all 0.3s ease;` (untuk memberikan efek transisi halus saat kursor diarahkan)

---

### **2. Perbedaan `h1 {...}` dengan `#intro h1 {...}**`

* **`h1 {...}` (Element Selector):**
Digunakan untuk menargetkan **seluruh** elemen tag `<h1>` yang ada di dalam dokumen HTML tanpa terkecuali.
* **`#intro h1 {...}` (Descendant Selector):**
Bersifat lebih spesifik. Aturan ini **hanya** berlaku untuk elemen tag `<h1>` yang berada **di dalam** elemen yang memiliki ID `intro` (`id="intro"`). Tag `<h1>` lain yang berada di luar kontainer `#intro` tidak akan terpengaruh.

---

### **3. Prioritas Deklarasi CSS (Internal vs Eksternal vs Inline)**

Jika elemen yang sama memiliki aturan CSS dari berbagai sumber, browser akan menentukan pemenangnya berdasarkan tingkat prioritas (spesifisitas):

1. **Inline CSS** (prioritas tertinggi)
2. **Internal CSS** dan **Eksternal CSS** (prioritas lebih rendah, ditentukan oleh urutan file dibaca — kode yang ditulis paling akhir akan menimpa kode sebelumnya).

* **Contoh:**
```html
<!-- Di CSS Internal/Eksternal -->
h1 { color: red; }

<!-- Di HTML (Inline CSS) -->
<h1 style="color: blue;">Judul Utama</h1>

```


**Hasil di Browser:** Teks akan berwarna **biru**, karena Inline CSS menimpa aturan dari Internal/Eksternal CSS.

---

### **4. Prioritas ID Selector vs Class Selector**

Jika sebuah elemen memiliki atribut ID dan Class secara bersamaan (`<p id="paragraf-1" class="text-paragraf">`), dan keduanya mengatur properti yang sama (misalnya warna teks), maka **ID Selector akan selalu menang**.

* **Alasan:**
Dalam hierarki CSS, tingkat spesifisitas ID (`#`) jauh lebih tinggi dibandingkan Class (`.`).
* **Contoh:**
```css
.text-paragraf {
    color: green; /* Kalah */
}
#paragraf-1 {
    color: red; /* Menang */
}

```


```html
<p id="paragraf-1" class="text-paragraf">Teks ini akan berwarna merah.</p>

```


**Hasil di Browser:** Paragraf akan berwarna **merah** karena ID selector memiliki bobot spesifisitas yang lebih kuat daripada class selector.
