---
title: "Belajar Visualisasi Data"
subtitle: ""
date: 2024-03-09T15:41:10+07:00
lastmod: 2024-03-09T15:41:10+07:00
authors: [Afrando]
description: "Pada artikel kali ini kita akan mengenal beberapa bentuk dari visualisasi data."

tags: ["Machine Learning"]
categories: []
series: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: "/img/posts/visualisasi-data/visualisasi-data.png"
featuredImagePreview: ""

code:
  copy: true
math:
  enable: false
lightgallery: false
license: ""
---

Dalam era informasi yang kaya akan data, kemampuan untuk memahami dan menginterpretasikan informasi menjadi kunci dalam pengambilan keputusan yang efektif. <!--more--> Di sinilah pentingnya visualisasi data menjadi semakin terasa. Visualisasi data bukan hanya tentang grafik dan diagram yang menarik, tetapi juga tentang kemampuan untuk merangkum kompleksitas informasi menjadi gambaran yang jelas dan mudah dipahami.

# Media Visualisasi Data
Tahukah kalian macam - macam bentuk media yang digunakan dalam visualisasi data? berikut ini penjelasannya:

## Tabel
Pastinya kalian pernah menyusun data ke dalam sebuah baris dan kolom, maka selamat, kalian telah berhasil membuat sebuah tabel.  
Jadi, tabel merupakan salah satu bentuk dari media visualisasi data yang sederhana dan sering kita temukan. Data yang ada di dalam tabel biasanya dikategorikan dalam **baris** atau **kolom** tertentu yang kemudian dapat di urutkan dengan mudah, contohnya di urutkan secara menaik (_Ascending_) atau menurun (_Descending_). Hal tersebut memudahkan kita untuk menyusun data sesuai dengan perintah yang diinginkan. Contoh studi kasusnya, bayangkan kalian memiliki data sayur - sayuran seperti, sawi (50 ikat), kangkung (35 ikat), bayam (25 ikat), selada (10 ikat). Bagaimana kalian mencatatnya supaya lebih mudah dibaca? salah satu caranya adalah bisa dengan membuat tabel seperti berikut:  
| Nama Sayur | Jumlah |
| ---------- | ------ |
| Sawi       | 50 |
| Kangkung   | 35 |
| Bayam      | 25 |
| Selada     | 10 |
| **Total**  | 120|

Setelah diurutkan secara _ascending_ berdasarkan nama sayur sebagai berikut:  

| Nama Sayur | Jumlah |
| ---------- | ------ |
| Bayam      | 25 |
| Kangkung   | 35 |
| Sawi       | 50 |
| Selada     | 10 |
| **Total**  | 120|

Dari tabel di atas, kita dapat membaca data sayur - sayuran dengan lebih efektif dan mengetahui jumlah total sayur. Dari data tersebut kita juga dapat mengurutkan dari jumlah sayur yang paling banyak, paling sedikit, atau mengurutkan nama sayur berdasarkan abjad.  
Terdapat beberapa aturan dasar dalam penulisan tabel yaitu sebagai berikut:  
- **Penulisan Judul**  
Dalam menulis judul pastikan sudah mencakup isi dari tabel yang di buat. Usahakan menggunakan font yang jelas dan mudah dibaca. Sehingga, pembaca akan dapat dengan mudah memahami tabel apa yang tersaji.  

- **Simpel**  
_Simplicity is a must_ (Kesederhanaan adalah suatu keharusan). Jangan terlalu berlebihan dalam mendesain sebuah tabel. Akibatnya pembaca tidak fokus pada data yang disajikan. Penulisan variabel di dalamnya juga singkat saja.

- **Penjelasan Simbol**  
Apabila dalam tabel terdapat simbol atau istilah tertentu, pastikan untuk dapat menjelaskannya pada catatan kaki tabel tersebut.

- **Penekanan**  
Penekanan yang dimaksud adalah cara kita memfokuskan perhatian pembaca pada pokok data. Misal, dalam penulisan tabel di atas, nama sayur menggunakan warna background biru gelap supaya pembaca bisa dengan mudah membedakan nama sayur dan jumlah sayur. Jika suatu data ada dalam kategori yang sama dan dapat dijumlahkan, maka kalian dapat menyertakan total di akhir datanya seperti pada contoh tabel di atas.

- **Sumber Tabel**  
Apabila tabel yang di sajikan bukan milik kalian, maka sertakan sumber di catatan kaki tabel tersebut.

## Diagram
Saya rasa kita semua sudah tidak asing dengan kata Diagram. Sebenarnya apa itu diagram?  
**Diagram** merupakan sebuah representasi data yang digambarkan dalam bentuk grafik. Jika kalian memiliki sebuah data yang ingin diproyeksikan dalam bentuk diagram, berikut beberapa tipe diagram yang bisa kalian coba gunakan.

### Diagram Batang
Apakah kalian pernah membuat diagram batang?  
Jadi, Diagram batang merupakan salah satu jenis grafik yang hampir sering kita jumpai dalam visualisasi data. Mengapa demikian, karena diagram ini dapat menunjukkan perbandingan angka pada kategori tertentu. Jumlah elemen batang dari diagram ini sebaiknya tidak terlalu banyak supaya label dari data tersebut masih bisa terbaca atau tidak terpotong.  
Pada diagram batang terdapat dua sumbu, _sumbu X_ pada diagram batang menunjukkan kategori data sedangkan _sumbu Y_ menunjukkan skala nilai dari data dalam satuan ukuran tertentu. Pastikan pada sumbu Y nilai awalnya adalah 0 supaya diagram kalian terlihat akurat dan mengurangi kesalahpahaman dalam mengartikan data.  

Selain itu, perhatikan pula penulisan label diagram. Hindari penulisan label secara vertikal maupun diagonal supaya tidak menyulitkan pembaca. Unsur warna juga penting dalam penyajian data diagram. Usahakan menggunakan warna yang konsisten supaya mudah dipahami. Berikut contoh dari diagram batang **Perbandingan Pengeluaran Bulanan**:  

{{< echarts >}}
{
  "title": {
    "text": "",
    "subtext": "2024"
  },
  "tooltip": {
    "trigger": "axis",
    "axisPointer": {
      "type": "shadow"
    }
  },
  "legend": {
    "data": ["Minggu 1", "Minggu 2", "Minggu 3", "Minggu 4"]
  },
  "xAxis": {
    "type": "category",
    "data": ["Januari", "Februari", "Maret", "April", "Mei", "Juni"]
  },
  "yAxis": {
    "type": "value"
  },
  "series": [
    {
      "name": "Minggu 1",
      "data": [500000, 300000, 550000, 180000, 500000, 300000],
      "type": "bar",
      "color": "#5470c6"
    },
    {
      "name": "Minggu 2",
      "data": [260000, 500000, 500000, 260000, 760000, 280000],
      "type": "bar",
      "color": "#91cc75"
    },
    {
      "name": "Minggu 3",
      "data": [700000, 260000, 500000, 500000, 950000, 950000],
      "type": "bar",
      "color": "#fac858"
    },
    {
      "name": "Minggu 4",
      "data": [1000000, 760000, 950000, 760000, 1000000, 760000],
      "type": "bar",
      "color": "#ee6666"
    }
  ]
}
{{< /echarts >}}

### Diagram Garis
Diagram garis biasanya menyajikan perubahan data dalam periode waktu tertentu. Secara umum, **diagram garis** digunakan untuk melihat perkembangan data tertentu yang berlangsung secara terus menerus atau berkelanjutan. Contoh dari data yang bisa digambarkan dalam diagram garis seperti, perkembangan jumlah penduduk selama 10 tahun terakhir. Dalam proses penggambaran diagram garis diperlukan _sumbu mendatar_ atau **X** dan _sumbu tegak_ atau **Y**.  
Sumbu X berfungsi untuk menunjukkan **interval waktu** sedangkan sumbu Y menunjukkan **kuantitas** atau nilai dari data tersebut seperti total penjualan, biaya yang dikeluarkan, jumlah pendapatan, dan lain sebagainya.  
Kemudian, buat tanda titik koordinat yang menunjukkan nilai data berdasarkan waktunya. Setelah semua data ditandai dengan titik koordinat, maka selanjutnya buatlah garis yang menghubungkan titik - titik tersebut. Dari penarikan garis tersebut kita bisa melihat pola perkembangan datanya cenderung naik, stabil, atau turun.  
**Contoh Studi Kasus**  
Ada sebuah toko buku dan ingin melihat perkembangan penjualan tahun 2023 yang lalu. Terdapat tabel seperti berikut:  
| Bulan | Jumlah |
| ---------- | ------ |
| Januari       | 150 |
| Februari   | 130 |
| Maret      | 180 |
| April     | 190 |
| Mei     | 250 |
| Juni     | 200 |
| Juli     | 230 |
| Agustus     | 250 |
| September     | 280 |
| Oktober     | 290 |
| November     | 300 |
| Desember     | 350 |
| **Total**  | 2800 |

Untuk mempermudah melihat perkembangan data, maka kita dapat membuat data dalam tabel tersebut menjadi sebuah diagram garis berikut ini:  
**Diagram Garis Penjualan Buku Tahun 2023**
{{< echarts >}}
{
  "title": {
    "text": "",
    "subtext": "Jumlah Penjualan per Bulan"
  },
  "tooltip": {
    "trigger": "axis"
  },
  "legend": {
    "data": ["Jumlah Penjualan"]
  },
  "xAxis": {
    "type": "category",
    "data": ["Januari", "Februari", "Maret", "April", "Mei", "Juni", "Juli", "Agustus", "September", "Oktober", "November", "Desember"]
  },
  "yAxis": {
    "type": "value"
  },
  "series": [
    {
      "name": "Jumlah Penjualan",
      "data": [150, 130, 180, 190, 250, 200, 230, 250, 280, 290, 300, 350],
      "type": "line",
      "smooth": true
    }
  ]
}
{{< /echarts >}}

Dari data tersebut, kita dapat melihat tren penjualan buku pada toko yang cenderung naik pada tahun 2023. Walaupun pada bulan Januari sampai Juni sedikit tidak stabil karena terjadi kenaikan dan penurunan, namun pada bulan Juni sampai Desember penjualan cenderung naik. Nah, dengan menggunakan diagram garis data tersebut lebih mudah dibaca, bukan?

### Diagram Lingkaran
Apakah kalian pernah membuat diagram lingkaran sebelumnya?  
Diagram lingkaran mirip seperti sebuah makanan **pizza** yang diiris dengan porsi tertentu. pada konteks data, irisan pizza tersebut menggambarkan persentase data nilai atau kuantitas. Apabila irisan tersebut dijumlahkan nilainya, maka seharusnya akan menghasilkan **100 persen** atau **360 derajat.**  
Diagram lingkaran biasanya sering digunakan oleh perusahaan atau dunia pendidikan untuk merepresentasikan data. Diagram lingkaran tidak hanya menunjukkan jumlah relatif dari kuantitas suatu data satu sama lain, namun dapat menunjukkan keseluruhan data dan kuantitas sebuah kategori data itu sendiri relatif **vis a vis** atau berhubungan dengan keseluruhan data yang ada.  
Untuk memperjelas pemahaman tentang diagram lingkaran, berikut terdapat contoh survei terhadap mahasiswa yang memiliki hobi sepak bola, basket, dan bulu tangkis untuk pelatihan menghadapi lomba tingkat nasional.  

|  Hobi | Jumlah |
| ---------- | ------ |
| Sepak Bola | 17 |
| Basket   | 3 |
| Bulu Tangkis | 5 |
| Lainnya     | 10 |
| **Total**  | 35 |

Apabila data tabel di atas digambarkan dengan diagram lingkaran, berikut hasilnya:

{{< echarts >}}
{
  "title": {
    "text": "Survei Hobi Siswa",
    "subtext": "Distribusi Jumlah Orang dengan Hobi Berbeda",
    "left": "center"
  },
  "tooltip": {
    "trigger": "item",
    "formatter": "{a} <br/>{b} : {c} ({d}%)"
  },
  "legend": {
    "orient": "vertical",
    "left": "left",
    "data": ["Sepak Bola", "Basket", "Bulu Tangkis", "Lainnya"]
  },
  "series": [
    {
      "name": "Jumlah",
      "type": "pie",
      "radius": "55%",
      "center": ["50%", "60%"],
      "data": [
        {"value": 17, "name": "Sepak Bola"},
        {"value": 3, "name": "Basket"},
        {"value": 5, "name": "Bulu Tangkis"},
        {"value": 10, "name": "Lainnya"}
      ],
      "emphasis": {
        "itemStyle": {
          "shadowBlur": 10,
          "shadowOffsetX": 0,
          "shadowColor": "rgba(0, 0, 0, 0.5)"
        }
      }
    }
  ]
}
{{< /echarts >}}

Dari 35 siswa dalam satu kelas, sepak bola paling digemari dibandingkan dengan hobi lainnya. Basket dan bulu tangkis masing - masing sebanyak 8,57% dan 14,29%. Sedangkan 28,57% atau sama dengan 10 orang siswa lainnya memiliki hobi lainnya seperti bermain musik, jalan - jalan, dan membaca novel.  
Terdapat rumus untuk menjadikan jumlah data ke dalam bentuk persen, berikut ini perhitungan rumus diagram lingkaran dalam bentuk persen dan derajat.

|  **Dalam bentuk Persen**  (jumlah data dalam kategori tertentu / Total data keseluruhan) X 100 |
| -------------------------------------------------------------------- |

|  **Dalam bentuk Derajat**  (jumlah data dalam kategori tertentu / Total data keseluruhan) X 360 |
| -------------------------------------------------------------------- |

Terdapat beberapa aturan dasar yang perlu diperhatikan dalam pembuatan diagram lingkaran, diantaranya:  
- Pastikan terdapat judul pada diagram lingkaran.
- Jika membuat diagram dalam satuan persen maka pastikan jumlah total datanya adalah 100%, sedangkan untuk satuan derajat totalnya adalah 360 derajat.
- Penulisan label juga penting untuk penanda dari suatu data, bisa menunjukkan kategori data, nilai, ataupun keduanya.
- Buat warna masing - masing irisan berbeda untuk membedakan datanya.
- Usahakan data yang di gambarkan dalam diagram maksimal 5 irisan supaya tidak menyulitkan pembaca.