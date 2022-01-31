---
layout: post
title: "Menggunakan plugins di Netlify"
tags: 
    - writing
    - development
        
category: [geeking]
comments: true
published: true
page_type: 
image:
    teaser: "/images/posts/dylan-hunter-CkoFNi1YXY0-unsplash.jpg"
    feature: "/images/posts/dylan-hunter-CkoFNi1YXY0-unsplash.jpg"
    author: "Dylan Hunter"
    creditlink: "https://unsplash.com/photos/CkoFNi1YXY0"
    url: false
---

Saya pengguna [Netlify](https://netlify.com/?utm_source=dedenf.com) yang lumayan sudah lama, meski masih di tier gratisan *hehe*, dan karena masih dalam batas wajar penggunaannya, jadi masih cukup quota yang saya miliki, dan juga dengan optimasi sana sini, yang mana penggunaan bandwidth menjadi lebih ringan.

Sempat membuat [postingan yang dikhususkan untuk Netlify](/2020/11/thank-you-netlify).

Sekarang kita akan menggali lebih jauh dengan [Netlify](https://netlify.com/?utm_source=dedenf.com) Plugins, penggunaan Plugins ini bisa dimasukkan menjadi bagian dari pipeline ketika kita hendak *build* website yang dideploy, sayang menggunakan [*static site generator*](https://jamstack.org/generators/) (SSG), [Jekyll](https://jekyllrb.com/), dan [Netlify](https://netlify.com/?utm_source=dedenf.com) mendukung SSG ini *out-of-the-box*.

<!--more-->

Untuk mendefinisikan *plugins* dan konfigurasi lainnya, [Netlify](https://netlify.com/?utm_source=dedenf.com) memiliki file [konfigurasi bernama netlify.toml](https://docs.netlify.com/configure-builds/file-based-configuration/), di sini banyak yang bisa dikonfigurasikan, bisa dilihat di [halaman dokumentasinya](https://docs.netlify.com/configure-builds/file-based-configuration/).

#### Persiapan

Karena saya pengguna macOS, jadi mungkin ini akan lebih spesifik macOS, untuk memulai, pastikan sudah [install Homebrew](https://brew.sh/), dan install paket `netlify-cli`.

```shell
$ brew install netlify-cli
```

Dengan ini akan menginstall aplikasi `netlify-cli` yang akan kita gunakan untuk melakukan build dan deploy di Netlifty.

#### Netlify.toml

Didalam file konfigurasi ini, saya mencantumkan nilai

```toml
[[headers]]
  for = "/*"
  [headers.values]
    Cache-Control = "max-age=3600"
    Strict-Transport-Security = "max-age=63072000; includeSubDomains; preload"

[[plugins]]
package = "netlify-plugin-checklinks"

[[plugins]]
package = "netlify-plugin-image-optim"
```

di bagian `[[plugins]]`, saya menambahkan [plugins di netlify](https://docs.netlify.com/configure-builds/build-plugins/#install-a-plugin), untuk daftar plugins yang ada di Netlify bisa dilihat di panel dashboard masing-masing dan bisa install plugins yang sesuai dengan kebutuhan.

Untuk saya sendiri saya install plugis bernama 
- netlify-plugin-checklinks
- netlify-plugin-image-optim

Dua plugins ini untuk mengecek tautan yang ada di blog seputar finansial, jika ada bad links yang berujung pada `404`, dari sisi SEO ini tidak bagus, dan mungkin akan menurunkan kredibilitas, dan juga install plugins untuk mengoptimasi gambar, yang mana bisa menghemat bandwidth yang dikirim ke pembaca blog [seputarfinansial.com](https://seputarfinansial.com/), dan tentunya, halaman bisa tampil lebih cepat.

#### Build

Langkah selanjutnya adalah build, dengan menggunakan perintah `netlify build`, Netlify akan memulai men-generate halaman, sesuai dengan SSG yang kita miliki.

```shell
$ netlify build
```

![](/images/posts/netlify-build.png)

Dari sini, Netlify akan melakukan *task* yang sudah didefinisikan di dalam file `netlify.toml`, termasuk plugins yang sudah kita masukkan, dan plugins ini akan dieksekusi didalam events `onPostBuild`.

Jika ada yang gagal dalam proses pengecekan links

![](/images/posts/netlify-failed-links.png)

Dan jika semua lulus dalam pengecekan 

![](/images/posts/netlify-checklinks.png)

Kemudian yang kedua menjalankan optimasi gambar dengan bantuan imgOptim 

![](/images/posts/netlify-img-optim.png)

Dan proses build selesai
![](/images/posts/build-complete.png)

Di sini proses pengecekan dengan dua plugins itu selesai, di halaman plugins bisa dicoba-coba untuk penggunaan plugins yang cocok untuk website, dan perlu diingat, karena Netlify menggunakan build time dalam layanannya, dan masing-masing tier di Netlify memiliki jatah build time, proses build ini akan mengkonsumsi jatah tersebut.

Untuk kasus saya, build menghabiskan sekitar 1 menit 33.3s, dan jumlah itu yang akan mengurangi jatah saya (karena masih free tier) sebesar 300 menit build time, kalau mau menambah build time, biasanya untuk website yang lebi kompleks dan besar akan menbutuhkan waktu lebih lama juga, dan upgrade ke pengguna yang berbayar lebih disarankan.

