---
layout: post
title: "Menjaga privasi dan keamanan dalam berinternet"
tags: 
    - computer
    - blog
    - security
    - privacy

category: post
comments: true
published: true
---

Mungkin isu ini sangat sensitif sekarang ini, terlebih dengan kasus Cambridge Analytica dan beberapa jebolnya masalah privasi dan keamanan di internet.

Pasti pernah mengalami ketika sedang chat atau ngobrol dengan teman, pasangan, bahas tentang sesuatu, tiba-tiba kita disugihi iklan yang mirip atau mendekati dengan apa yang kita sedang bahas, menakutkan? yup, pernah mengalami ini dan sempat nanya-nanya apa ini disadap ya?

<!--more-->

Mungkin saja, mungkin juga tidak, karena zaman sekarang *marketing tools* sudah sangat kompleks, canggih, rumit dan moderen, dengan ditambah dengan *artificial intelligent*(A.I), mereka dapat menerka apa yang sedang kita lakukan di internet, iya, gerak-gerik kita bisa diawasi, karena sebenarnya ponsel, komputer kita memiliki semacam sidik jari, yang unik, yang mana misalkan kita meninggalkan ‘jejak’, maka tools marketing itu akan mengikuti kita dari mana saja, saking canggihnya kita sampai berpikir kalau kita disadap.

Ambil skenario misalkan pada januari sedang googling susu untuk ibu hamil, obat-obatan, vitamin dan lain-lain, di sini iklan akan menampilkan berbagai variasi dari obat-obat, vitamin, supplemen ibu hamil, kemudian diakhir-akhir kehamilan, misalkan kita juga mencari baju bayi, sedari awal sudah dibuntuti dan mengetahui perjalanan/histori pencarian kita tersebut. dari hamil kemudian melahirkan akan diikuti.

Dan tentunya akan menerka anak lahir kapan, umur berapa sekarang, dan hal itu masuk ke proses belajar mesin pencari.

Beberapa cara yang saya lakukan sebagai bentuk pencegahan, yaitu dengan melakukan hal-hal di bawah ini.

#### Mengganti _search engine_
Untuk meminimalisir hal tersebut, kita bisa memulai dengan hal yang tidak terlalu rumit dulu, sudah sekitar sebulanan ini beralih dari Google ke [DuckDuckGo](https://duckduckgo.com/),  mesin pencari alternatif, sejauh ini tidak ada masalah, apa yang dicari juga diketemukan, dan sama sekali *gak* melihat perbedaannya dengan Google, dan mengganti settingan mesin pencari di browser dari yang tadi nya Google ke [DuckDuckGo](https://duckduckgo.com/) secara *default*.

#### Menggunakan browser yang fokus pada privasi
Kemudian gunakan browser yang lebih pro ke menjaga privasi, antara lain [Firefox](https://www.mozilla.org/en-US/firefox/new/), [Brave](https://brave.com/). saat ini menggunakan 2 browser tersebut, baik di komputer, maupun di ponsel, karena masalah privasi dan kedua browser ini menjunjung privasi.

#### Menggunakan browser extension
Selain menggunakan browser yang fokus ke privasi, install juga *extension* yang dibuat memang untuk privasi, extension browser yang sering dipakai

- [Ublock origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
- [EFF privacy badger](https://www.eff.org/privacybadger)
- [Privacy Possum](https://addons.mozilla.org/en-US/firefox/addon/privacy-possum/)
- [SmartHTTPS](https://addons.mozilla.org/en-US/firefox/addon/smart-https-revived/)
- [Disconnect](https://addons.mozilla.org/en-US/firefox/addon/disconnect/)
- [HTTPS Everywhere](https://addons.mozilla.org/en-US/firefox/addon/https-everywhere/)

Browser Extension di atas juga tersedia untuk Brave (karena Brave berasal dari kode sumber yang sama dengan Google Chrome).

Langkah selanjutnya agak lebih teknikal, untuk settingan di atas bisa lumayan cukup untuk perlindungan dasar, untuk *kalo* mau lebih bisa gunakan beberapa *tools*.

#### Encrypted DNS resolver
Sederhananya, jika kita meminta satu nama website, misalkan detik.com, handphone/komputer akan bertanya ke ISP/Operator yang kita gunakan (misalkan biznet, indosat, telkomsel dll) berapa IP address-nya, dari sini ISP/Operator akan mencari IP dari website tersebut dan mencatat permintaan kita ke website tersebut, dan sudah pasti detik.com juga memanggil resource yang lain, bisa berupa gambar, scripts, dan yang pasti iklan-iklannya yang kadang bikin sakit mata.

Dengan menggunakan encrypted dns resolver, request domain yang kita lakukan tersebut dienkrip, dan juga request kita tidak tercatat di ISP/Operator, tetapi melalui resolver ini, selain itu, memiliki fitur tambahan, yaitu blocking iklan, *tracking*, malware dan juga domain-domain yang terindikasi phising.

Ada banyak penyedia enkripsi DNS ini, artikel yang bagus dari [Lifehacker](https://lifehacker.com/how-to-boost-your-internet-security-with-dnscrypt-510386189), di sini dijelaskn guna dan mekanisme enkripsi DNS.

Untuk pribadi, saya menggunakan [doh.tiar.app](https://doh.tiar.app/), service yang dibangun oleh [teman](https://github.com/pengelana/blocklist/), mendukung [DNSCrypt](https://en.wikipedia.org/wiki/DNSCrypt), [DoH](https://en.wikipedia.org/wiki/DNS_over_HTTPS), [DoT](https://en.wikipedia.org/wiki/DNS_over_TLS).

Untuk implementasi enkripsi DNS ini di smartphone dan komputer, saya pribadi menggunakan aplikasi-aplikasi berikut
- Android, menggunakan [Intra app](https://play.google.com/store/apps/details) dengan settingan [tiar.app](https://github.com/pengelana/blocklist/wiki/DNS-over-HTTPS-(DoH)#android)
- iOS, menggunakan [Morhill DoH Switcher](https://itunes.apple.com/us/app/morhill-doh-switcher/id1451319401), [petunjuk penggunaan untuk iOS](https://github.com/pengelana/blocklist/wiki/DNS-over-HTTPS-(DoH)#morhill-doh-switcher)
- MacOS menggunakan [Morhill DoH Switcher](https://apps.apple.com/id/app/morhill-doh-switcher/id1456779899?mt=12), petunjuk [penggunaan hampir sama dengan iOS](https://github.com/pengelana/blocklist/wiki/DNS-over-HTTPS-(DoH)#morhill-doh-switcher)
- Windows (saya *gak* pakai), bisa menggunakan [simpelDNSCrypt](https://simplednscrypt.org/)

Dan pastikan ikuti cara penggunaannya untuk [masing-masing OS](https://github.com/pengelana/blocklist/wiki).
