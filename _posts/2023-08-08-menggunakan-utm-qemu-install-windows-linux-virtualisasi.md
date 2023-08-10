---
layout: post
title: "Menggunakan QEMU (UTM) virtualisasi untuk install Windows 11 (dan OS lain)"
tags: 
    - geeking
        
category: [geeking]
comments: true
published: true
page_type: false
image:
    teaser: "/images/posts/utm-qemu.jpg"
    feature: "/images/posts/utm-qemu.jpg"
    author: "Deden"
    creditlink: "https://dedenf.com"
    url: false
---

Akhir-akhir ini saya sedang belajar beberapa hal yang sayangnya hanya ada di Windows aplikasi tersebut, sebagai pengguna macOS, tentunya bikin ribet yang begini-begini, dan jalan satu-satunya untuk bisa menjalankan windows di macOS ya dengan menggunakan virtualisasi.

VIrtualisasi bukan hal yang istimewa memang, dan banyak sekali aplikasi yang menyediakan kemampuan ini, dari yang gratis sampai yang berbayar.

<!--more-->

Sebelumnya saya menggunakan [Parallels Desktop](https://www.parallels.com/), setelah dilihat sekarang, harganya lumayan mahal ternyata, dan kemudian ada juga solusi dari VMWare, [VMWare Fusion](https://www.vmware.com/products/fusion.html), dan tentunya ada yang gratis seperti [VirtualBox](https://www.virtualbox.org/) dan juga [QEMU](https://www.qemu.org/).

Karena lagi cekak, jadi saya ambil yang Virtualbox awalnya, hanya saja ini terbentur dengan arsitektur Macbook yang saya pakai saat ini, menggunakan [Apple Silicon](https://en.m.wikipedia.org/wiki/MacBook_Pro_(Apple_silicon)) M1, dengan arsitektur Arm64 ini agak sulit karena aplikasi yang mungkin dulu jalan di Macbook dengan prosesor intel tidak semuanya bisa jalan, salah satunya Virtualbox ini, meski katanya ada versi development, tapi ini bisa jadi masih belum stabil, kemudian pilihan beralih ke QEMU.

[QEMU](https://www.qemu.org/) ini project opensource yang sudah lama, dan ada dihampir semua sistem operasi, dan [UTM](https://mac.getutm.app/) adalah aplikasi macOS yang bisa digunakan untuk virtualisasi.

## Instalasi

Biasanya saya menggunakan `homebrew` untuk instalasi, jadi tinggal `brew install qemu`, tapi dengan menggunakan command line tidak intuitive, dan saya menggunakan aplikasi desktop bernama [UTM](https://getutm.app/), kerennya ini bisa menjalankan OS lain di macOS dan juga di iOS!

Instalasi UTM bisa dilakukan dengan download `.dmg` di websitenya, atau bisa install via `homebrew` juga bisa.

```jsx
❯ brew install utm --force
==> Downloading https://github.com/utmapp/UTM/releases/download/v4.3.5/UTM.dmg
Already downloaded: /Users/ditd21065/Library/Caches/Homebrew/downloads/37ac22c59647a26a7e9457ba59358553f63552f3d003edc2fc12d4f299c9c970--UTM.dmg
==> Installing Cask utm
...
==> Linking Binary 'utmctl' to '/opt/homebrew/bin/utmctl'
🍺  utm was successfully installed!
```

### Download Windows 11

Selanjutnya bisa mengunduh WIndows 11, tetapi karena saya menggunakan Apple Silicon M1, jadi membutuhkan Windows 11 yang menggunakan arsitektur Arm64, dan ini bisa dilakukan dengan mengunduh file `.iso` yang memang dikhususkan untuk itu, untuk parallels desktop, meski yang didownload untuk arsitektur bukan Arm64, masih bisa dilakukan instalasi, untuk yang mau download `.iso` [bisa diambil di sini](https://www.microsoft.com/software-download/windows11).

Untuk Apple Silicon ini, saya mengunduh `.iso` windows dengan menggunakan aplikasi [CrystalFetch](https://github.com/TuringSoftware/CrystalFetch/), hal ini juga sama dijelaskan di [dokumentasi UTM](https://docs.getutm.app/guides/windows/).

![crystalfetch](/images/posts/utm-crystalfetch.png)

Masalah yang mungkin muncul, proses pengunduhan file iso tidak lancar, seperti yang pernah saya alami menggunakan CrystalFetch, sehingga saya menggunakan proses unduh yang berbeda, lebih ke manual, dengan menggunakan script dari project UUPs, script tersebut bisa diunduh di website ini [https://uupdump.net/](https://uupdump.net/d).

Di website tersebut akan dibuat semacam kustomisasi paket yang ada, dengan menggunakan aplikasi `aria2c`, dengan melakukan perintah ini:

```jsx
$ sh uup_download_macos.sh
```

Perintah di atas, akan melakukan download paket-paket yang dibutuhkan untuk membuat file iso windows yang dibutuhkan.

```jsx
Download Results:
gid   |stat|avg speed  |path/URI
======+====+===========+=======================================================
aecd5b|OK  |       0B/s|UUPs/Microsoft-Windows-Foundation-Package.ESD
d741ec|OK  |       0B/s|UUPs/Microsoft-Windows-Wallpaper-Content-Extended-FoD-Package-arm64.cab
90d714|OK  |       0B/s|UUPs/Microsoft-Windows-Not-Supported-On-LTSB-Package.ESD
418f0e|OK  |       0B/s|UUPs/Microsoft-Windows-StepsRecorder-Package-arm64.x86.cab
3771d2|OK  |       0B/s|UUPs/Microsoft-Windows-Not-Supported-On-LTSB-arm64arm-Package.ESD
e3d606|OK  |       0B/s|UUPs/Microsoft-Windows-Notepad-System-FoD-Package-arm64.x86.cab
9483e3|OK  |       0B/s|UUPs/Microsoft-Windows-PowerShell-ISE-FOD-Package-arm64.x86.cab
910ff9|OK  |       0B/s|UUPs/Microsoft-Windows-LanguageFeatures-OCR-en-us-Package-arm64.cab
30a361|OK  |       0B/s|UUPs/Microsoft-Windows-StepsRecorder-Package-arm64.arm.cab
18713d|OK  |       0B/s|UUPs/Microsoft-Windows-StepsRecorder-Package-arm64.cab
fbb2c7|OK  |       0B/s|UUPs/Microsoft-Windows-Notepad-System-FoD-Package-arm64.arm.cab
541e04|OK  |       0B/s|UUPs/Microsoft-Windows-Notepad-System-FoD-Package-arm64.cab
f9a5fe|OK  |       0B/s|UUPs/Microsoft-Windows-InternetExplorer-Optional-Package-arm64.cab
e75451|OK  |       0B/s|UUPs/Microsoft-Windows-WMIC-FoD-Package-arm64.x86.cab
...
```

Selanjutnya setelah paket-paket tersebut didownload, proses ini akan membuat folder bernama UUPs dengan isi file seperti ini:

```jsx
❯ ls -1 UUPs
45323232-df65-4eed-9461-71d7796a7446.AggregatedMetadata.cab
DesktopDeployment.cab
Microsoft-OneCore-ApplicationModel-Sync-Desktop-FOD-Package-arm64.cab
Microsoft-Windows-CHPE-Binaries-arm64x86-Package.ESD
Microsoft-Windows-Client-Desktop-Required-Package.ESD
Microsoft-Windows-Client-Desktop-Required-WOW64-Package.ESD
Microsoft-Windows-Client-Desktop-Required-arm64arm-Package.ESD
Microsoft-Windows-Client-Features-Package.ESD
Microsoft-Windows-Client-Features-WOW64-Package.ESD
Microsoft-Windows-Client-Features-arm64arm-Package.ESD
...
```

Agak repot memang, tapi seru!

Selanjutnya kita membuat file `.iso` dari file-file di atas tersebut, dengan tools converter yang memang dikhususkan untuk hal ini, lakukan perintah ini relative ke folder `UUPs` berada.

```jsx
❯ ./convert.sh <DIR UUPS>
UUP Converter v0.7.2
Note: This script does not and cannot support the integration of updates.
Use the Windows version of the converter to integrate updates.

CAB -> ESD: Microsoft-Windows-LanguageFeatures-Speech-en-us-Package-arm64
CAB -> ESD: Microsoft-Windows-WMIC-FoD-Package-arm64
CAB -> ESD: Microsoft-Windows-MediaPlayer-Package-arm64
CAB -> ESD: Microsoft-Windows-LanguageFeatures-TextToSpeech-en-us-Package-arm64
...
Creating ISO structure...
Applying image 1 ("Windows Setup Media") from "/Users/blabla/UUPs/professional_en-us.esd" to directory "ISODIR"
Extracting file data: 247 MiB of 247 MiB (100%) done
Done applying WIM image.
...
Total translation table size: 2048
Total rockridge attributes bytes: 0
Total directory bytes: 0
Path table size(bytes): 10
Max brk space used 0
2165663 extents written (4229 MB)
Done.
```

Sesudah ini, file `.iso` telah dibuat, dan siap untuk kita install di UTM.

## Instalasi Windows 11

Untuk proses awal, silakan tambahkan Guest OS yang akan diinstall di macOS, di sini saya memilih pilihan Windows dan kemudian memuat file iso yang sudah saya buat sebelumnya.

Sayangnya ini saya tidak sempat melakukan tangkapan layar, lupa, tapi untuk instalasi Windows 11 ini (saya pakai Windows 11 pro), mudah sekali, tinggal klak klik sampai akhir, dan tunggu hingga selesai prosesnya.

Sesudah itu, kita bisa masuk ke dalam desktop Windows 11, dan melakukan tasks di sana.

![Windows Desktop](/images/posts/utm-desktop.jpg)

Untuk bisa menggunakan fasilitas jaringan dan juga layar yang lebih baik dari instalasi default, bisa dilakukan install Windows OS tools, yang mana

## Instalasi OS lain (linux dan OS lain)

Untuk kebutuhan pekerjaan, saya juga melakukan instalasi OS GNU/Linux distro Kali Linux, untuk instalasi linux hampir sama prosesnya dengan Windows di UTM, muat file iso dan lakukan instalasi selanjutnya seperti yang tertera di layar.

Tetapi terkadang ada masalah untuk instalasi Linux di UTM ini, terkadang layar menjadi gelap dan tidak ada lanjutan untuk instalasinya, untuk memitigasi issue ini, bisa dengan langkah ini

1. Buka edit VM yang sudah ada
2. Di bagian `Devices`, tambahkan device baru, tipe serial

Setelah lakukan itu, dan melakukan instalasi lagi, akan muncul 2 layar, hal ini normal, lakukan instalasi di layar yang sekiranya nyaman, hasilnya sama saja, kemudian lakukan instalasi seperti biasa.

![Desktop Kali Linux](/images/posts/utm-linux-kali.jpg)

UTM juga bisa digunakan untuk instalasi macOS sebagai guest OS, ya mungkin ada kebutuhan untuk membuat development atau kebutuhan lain.

Jadi selama ada installernya, iso atau format lain, bisa diinstall di UTM, sejauh ini masih berjalan dengan baik, dan bahkan saya sempat install Windows XP, cuman buat nostalgia aja sih.

## Kesimpulan

Untuk kebutuhan pengguna komputer sehari-hari, menggunakan UTM untuk kebutuhan virtualisasi OS lain, sangat berguna, dan juga memudahkan, kita tidak perlu install aplikasi yang bisa membuat berat sistem, atau mungkin membeli aplikasi yang bisa melakukan hal yang sama dengan cara yang gratis.