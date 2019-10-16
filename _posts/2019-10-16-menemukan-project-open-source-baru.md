---
layout: post
title: "Menemukan project Open Source"
tags: 
    - development
    - blog
    - software
    - brew
    - github

category: [software]
comments: true
published: true
---

![](/images/posts/software-opensource.png "github + brew")

[Why Software Eating the World](https://a16z.com/2011/08/20/why-software-is-eating-the-world/), essay yang ditulis oleh Marc Adreessen, *software* atau perangkat lunak menjadi hal yang tak terlihat tapi ada, orang menggunakan *software* sebagai kebutuhan, di komputernya, *smartphone*-nya, terlepas jenisnya apa, software ini bisa untuk *end-user*, atau untuk tipe *enterprise*.

*Open source* adalah salah satu proyek penggerak tersebarnya *software* ini ke hampir semua lini, untuk memudahkan pekerjaan kita sehari-hari, ada [Libre office](https://www.libreoffice.org/) yang merupakan salah satu proyek open source yang besar untuk yang perlu untuk mengetik laporan misalkan, atau mungkin yang tidak disadari, Linux, yang merupakan sistem operasi yang merupakan dasar dari Android yang dipakai sehari-hari.

<!--more-->

Untuk penggunaan di komputer, karena saya sendiri dibidang IT, tentunya software (perangkat lunak) merupakan bagian penting, dan hampir setiap hari menggunakan produk *software* open source, ada tools yang untuk mengecek kinerja sistem, ada yang untuk mengetes API, bahkan sistem operasi server adalah produk dari open source, dan lainnya.

Beberapa *tools* yang dipakai terkadang ‘ditemukan’ tidak disengaja, ada yang ditemukan melalui artikel, kemudian kalau sedang *browsing* di [Github ke bagian explore](https://github.com/explore), dan karena menggunakan MacOS, dan menggunakan aplikasi brew, sering juga juga menemukan tools/aplikasi open source baru di sini, tidak dengan cara browsing ke [websitenya](https://brew.sh/), tapi melalui command line.

![macos iterm2 and brew](/images/posts/iterm-brew.jpg "iterm + brew")

Contoh di atas adalah ketika mencoba install satu software, dan brew menampilkan informasi update software-software yang tersedia, dari sini kadang menemukan hal baru, tools baru, framework baru, kadang nama project open source berpengaruh supaya lebih catchy.

Kalau menemukan project yang membuat penasaran, tinggal cari infonya melalui command line lagi, misalkan 
```
dedenf@elementium ~ $ brew info homebank
homebank: stable 5.2.8 (bottled)
Manage your personal accounts at home
http://homebank.free.fr
Not installed
From: https://github.com/Homebrew/homebrew-core/blob/master/Formula/homebank.rb
==> Dependencies
Build: intltool ✘, pkg-config ✔
Required: adwaita-icon-theme ✘, fontconfig ✔, freetype ✔, gettext ✔, gtk+3 ✘, hicolor-icon-theme ✘, libofx ✘, libsoup ✘
==> Analytics
install: 268 (30 days), 547 (90 days), 1,958 (365 days)
install_on_request: 240 (30 days), 498 (90 days), 1,745 (365 days)
build_error: 0 (30 days)
```

Kunjungi websitenya, cek cocok atau tidak, suka dengan UI-nya misalkan, kalau mau ngetest tinggal install `brew [cask] install package_name`, beres, dan kita bisa mulai menggunakan software tersebut.

Untuk project open source biasanya kode di-host di Github atau layanan SCM lainnya, dan untuk melihat apakah project ini banyak menggunakan juga bisa lihat aktivitas dari kontribusi kode yang dikirimkan, banyaknya *commit* yang dilakukan, baik dari penciptanya, maupun dari komunitasnya (ini bisa jadi bahasan lain).

Sumber lain:
- [Hacker News](https://news.ycombinator.com/)
- [Lobster](https://lobste.rs/)