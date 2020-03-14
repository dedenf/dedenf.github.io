---
layout: post
title: "PPP, framework untuk komunikasi dan manajemen project"
tags: 
    - "Self Development"
    - development
    - agile

category: [development]
comments: true
published: true
image:
    teaser: "/images/posts/sebastiaan-stam-D1QI9bx8KUM-unsplash.jpg"
    feature: "/images/posts/sebastiaan-stam-D1QI9bx8KUM-unsplash.jpg"
    author: "Sebastiaan Stam"
    creditlink: "https://unsplash.com/photos/D1QI9bx8KUM"
    url: false
---

Jurnaling merupakan salah satu hal yang bisa dilakukan dalam mendokumentasikan apa yang kita kerjakan atau update yang hendak kita sampaikan dalam satu project yang kita kerjakan, ada framework yang bisa dikerjakan yang menjadi compliment terhadap jurnaling, yaitu framework **PPP** (Progress, Problem, Plan, tidak selalu dalam urutan ini).

Dengan mendefinisikan,
1. **Progress**   
    Menceritakan progres atau apa yang sudah diraih dalam satu minggu misalkan (durasi bebas, bisa satu hari, minggu, bulan)
2. **Problem**   
    Menceritakan kendala yang dihadapi dalam mencapai progres itu, baik yang sudah dilalui atau yang sedang dilalui, belum selesai.
3. **Plan**   
    Rencana apa saja yang akan dikerjakan, diraih minggu depan (besok, bulan depan)

<!--more-->

Contoh implementasi, PPP saya gunakan ketika meng-update tim sendiri dan tim lain terkait dengan project yang sedang saya dan tim saya lakukan, sehingga bisa dimengerti oleh tim lain dan bisa bersinergi,

1. Progress
- Membuat *automation* (saat ini berhasil mengurangi *manual step* untuk *provisioning* dan *deployment*)
- Pods untuk tipe special project berhasil di*support*
- Implementasi NLB untuk beberapa service (yang lain menyusul).
- Membuat repo baru yang ditujukan untuk onboarding developer baru.

2. Problems
- *Alerting system* terkadang mengganggu, terlalu banyak alert malah cenderung diabaikan
- *Development workflow* untuk beberapa project terlalu rumit

3. Plans
- Melakukan housekeeping untuk data yang tidak dipakai
- Mengimplementasikan automation di beberapa project lain
- Tune up Alerting, mengurangi alerting yang tidak perlu
- Menyederhanakan *development workfolow*


Dengan melakukan hal ini, setidaknya untuk saya, selain bisa membuat jurnaling apa yang sudah dilakukan sehingga lebih bisa memiliki konteks dan ownership dalam project, juga bisa untuk meng-*update* tim lain apa yang sudah dikerjakan, dan jika ada tim lain yang bisa membantu atas *Problem* dan *Plan* kita, maka komunikasi dengan tim bisa terus terjaga, komunikasi yang baik adalah pilar dari project yang sukses dan berkesinambungan.