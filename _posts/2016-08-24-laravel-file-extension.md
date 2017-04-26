---
title: Extensi file Virtual di Laravel
layout: post
tags:
    - laravel
    - php

description : menggunakan route sebagai cara untuk mendapatkan extension file virtual
---

Kasus ini terjadi karena hendak menggunakan Facebook dynamic ads, untuk memenuhi syarat yang ditulis di [dokumentasi facebook marketing](https://developers.facebook.com/docs/marketing-api/dynamic-product-ads/product-catalog), dibutuhkan file XML sebagai data feeding ke marketing funnel feed.

dalam percobaan pertama, hasil response yang digunakan adalah dengan menambahkan `Content-Type` dioutput, tapi ini tidak cukup, facebook feed fetcher tidak support hal ini, diharuskan berupa ektensi file. memang ada cara bagaimana untuk membuat file feed ini dengan menggunakan facebook Ads SDK, tetapi hal ini mengharuskan kita untuk meng-_update_ `composer.json`, dan menambahkan library-nya.

ada cara yang lebih mudah, yaitu dengan menggunakan `routes.php`, dan mendeklarasikan ekstensi file (entah itu pdf, xml, csv dan lainnya),

<script src="https://gist.github.com/dedenf/56c9a236e5f6ae04c516a88895448ed9.js"></script>

dengan menggunakan entry routes di atas, kita memiliki kemudahan dalam men-_generate_ file, berikut extensinya, di sini, akan terbuat url `https://www.example.com/products/feed/baju.xml`

ini mirip dengan yang dulu pernah diimplementasikan di codeigniter.

dengan cara ini kita bisa dengan mudah menggunakan extensi file semau kita, tanpa perlu ada aktual file-nya, dengan didukung oleh content-type dari hasil output kita.
