---
title: "Memahami Arsitektur Monolithic & Microservices: Perbandingan, Kelebihan dan kekurangannya"
subtitle: ""
date: 2024-03-08T03:39:32+07:00
lastmod: 2024-03-08T03:39:32+07:00
authors: [Afrando]
description: "Memahami dua arsitektur pemrograman yang sering digunakan serta mengenal kelebihan dan kekurangan dari masing masing arsitektur."

tags: ["Microservices"]
categories: []
series: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImagePreview: ""
featuredImage: "/img/posts/microservices/arsitektur-micro-mono.png"

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->
Dalam dunia pengembangan perangkat lunak, pemilihan arsitektur aplikasi menjadi langkah krusial yang akan memengaruhi kinerja, skalabilitas, dan fleksibilitas sebuah sistem. Dua pendekatan utama yang sering dibahas adalah Monolithic dan Microservices. Dalam artikel ini, kita akan memperbandingkan kedua arsitektur ini, melihat kelebihan, kekurangan, serta situasi yang tepat untuk menerapkan masing-masing.

# Pengenalan Monolithic Arsitektur
**Monolithic Arsitektur** ialah cara membuat atau membangun aplikasi yang dimana komponen / modul yang berbeda digabungkan menjadi satu program atau 1 codebase.

## Contoh Diagram Aplikasi Monolithic

{{< mermaid >}}flowchart LR;
    A[Client Web / Mobile App] --> B(Load Balancer)
    B --> APLIKASI
    subgraph APLIKASI
        D>Catalog]
        E{{Order}}
        F[/Payment/]
    end
    APLIKASI --> G[(Database)]
    style A fill:#ffe28f,color:#000
    style B fill:grey,color:#000
    style D fill:#9bbbf3,color:black
    style E fill:#ad9dd1,color:black
    style F fill:#a76485,color:black
    style APLIKASI fill:#d4e6ce,color:#000
    style G fill:#e5c9d4,color:#000
{{< /mermaid >}}

**Penjelasan**  
Diagram tersebut menggambarkan bagaimana aplikasi monolithic beroperasi. Client (pengguna) terhubung ke aplikasi melalui load balancer. Aplikasi ini memiliki tiga fitur utama (Catalog, Order, Payment) yang berinteraksi dengan database untuk menyimpan dan mengambil data. Ini adalah pendekatan yang umum digunakan dalam pengembangan aplikasi sebelum adanya arsitektur microservices yang lebih modern.
## Kelebihan Aplikasi Monolithic
1. Mudah untuk di develop.
2. Simple untuk di deploy.
3. Simple untuk di scale secara vertikal.
4. Gampang untuk di test.

## Kekurangan Aplikasi Monolithic
1. Mengintimidasi programmer baru.
2. Overloaded IDE.
3. Ketika deploy, berarti kita mendeploy seluruh code / seluruh aplikasi.
4. Susah ketika mau scale terlebih secara horizontal.
5. Ketika ada error, maka 1 aplikasi akan terpengaruh bahkan mati.
6. Susah untuk mengadopsi teknologi baru.

{{< admonition tip "apa itu scale?" false >}}
**"Scaling"** dalam konteks pengembangan aplikasi merujuk pada kemampuan aplikasi untuk menangani pertumbuhan beban kerja atau traffic. Ada dua cara umum untuk melakukan scaling: scaling vertikal (vertical scaling) dan scaling horizontal (horizontal scaling).  
**Scale Vertikal**: Meningkatkan spesifikasi seperti kapasitas (RAM, CPU) pada satu instance atau node aplikasi.  
**Scale Horizontal**: Menambahkan lebih banyak instance atau node ke dalam aplikasi untuk mendistribusikan beban kerja.
{{< /admonition >}}

# Pengenalan Microservices Arsitektur
**Microservices arsitektur** ialah sebuah arsitektur aplikasi yang dibangun dari kumpulan service - service kecil yang saling terhubung.

## Contoh Diagram Aplikasi Microservices

{{< mermaid >}}flowchart LR;
    subgraph APLIKASI
        D>Catalog] --> db1[(Database)] 
        E(Order) --> db2[(Database)]
        F[/Payment/] --> db3[(Database)]
    end
    style D fill:#9bbbf3,color:black
    style E fill:#ad9dd1,color:black
    style F fill:#a76485,color:black
    style APLIKASI fill:#fff,color:#000
    style db1 fill:grey,color:white
    style db2 fill:grey,color:white
    style db3 fill:gray,color:white
{{< /mermaid >}}

**Penjelasan**  
Dalam arsitektur microservices pada diagram di atas, setiap layanan (Catalog, Order, dan Payment) memiliki tugasnya sendiri dan terpisah, memungkinkan aplikasi untuk lebih modular dan mudah di-maintain. Masing-masing layanan memiliki akses ke database yang khusus untuk fungsinya sendiri. Hal ini memungkinkan pengembang untuk mengubah, memperbarui, atau memperbaiki satu layanan tanpa memengaruhi layanan lainnya. Arsitektur ini membantu dalam pengembangan aplikasi yang lebih fleksibel, scalable, dan dapat dikembangkan oleh tim yang terpisah secara bersamaan.

## Kelebihan Aplikasi Microservices
1. Mudah untuk di pahami bagi developer karena 1 service biasanya berukuran kecil.
2. Ketika ada service yang error maka tidak akan berimbas pada service lain.
3. Better Deploy, karena masing - masing service bisa di deploy secara independent.
4. Better Testability, karena service berukuran kecil maka mudah untuk di test.
5. Ringan untuk IDE.
6. Mudah untuk mengadopsi teknologi baru.
7. Mudah untuk scaling secara independent untuk masing - masing service.

## Kekurangan Aplikasi Microservices
1. Testing yang melibatkan interaksi antar service menjadi susah.
2. Tidak mudah mengimplementasikan sebuah fitur / request, yang melibatkan service lain, karena harus di diskusikan secara hati - hati bersama tim.
3. Tidak mudah untuk menghandle jumlah service yang banyak.

## Monolithic VS Microservices

{{< mermaid >}}flowchart LR;
    subgraph Perbandingan
      subgraph Monolithic
        A>Catalog]
        B[/Order/]
        C{{Payment}}
      end
      title[dengan]
      subgraph Microservices
        D>Catalog]
        E[/Order/]
        F{{Payment}}
      end
    end
    style Perbandingan fill:#fff,color:black
    style Microservices fill:#fff,color:#000
    style Monolithic fill:#fff,color:#000,stroke:black
    style title fill:#fff,color:#000,stroke:none
    style A fill:#88bd71,color:white
    style D fill:#88bd71,color:white
    style B fill:#f09834,color:white
    style E fill:#f09834,color:white
    style C fill:#c60000,color:white
    style F fill:#c60000,color:white
    
{{< /mermaid >}}

## Perbandingan
### Monolithic
1. Sebuah aplikasi besar yang biasanya hanya 1 codebase.
2. Sedikit susah untuk scaling berdasarkan kebutuhan.
3. Umumnya hanya mempunyai 1 database.
4. Susah untuk mengganti teknologi yang telah di pakai.
5. Deploy berarti merilis keseluruhan source code.

### Microservices 
1. Dibangun dari service - service kecil yang di buat berdasarkan domain bisnis.
2. Mudah untuk scaling berdasarkan kebutuhan.
3. Masing - masing service mempunyai database tersendiri.
4. Mudah untuk mengadopsi teknologi baru.
5. Deploy hanya pada service - service yang di ubah saja.

## Kesimpulan
Monolithic Arsitektur cocok untuk aplikasi sederhana dengan pengembangan yang mudah, namun kurang fleksibel dalam skalabilitas dan adopsi teknologi baru. Sementara itu, Microservices lebih baik untuk aplikasi kompleks yang membutuhkan skalabilitas tinggi, meskipun memerlukan manajemen yang kompleks. Pemilihan antara keduanya harus didasarkan pada kebutuhan aplikasi dan tim pengembang.


