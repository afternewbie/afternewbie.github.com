---
layout: post
title: format flashdisk dengan cfdisk di linux
description: memformat flashdisk dengan cfdisk melalui terminal
keywords: linux, format, flashdisk, terminal
---

Kali ini saya mau membagikan tips dasar untuk memformat flashdisk menggunakan CFdisk di linux. **Mengapa CFdisk gan ? kenapa bukan Gparted, kan lebih mudah tuh ?** Gini gan, saya jelasin dulu kenapa saya pake CFdisk.

Waktu itu saya pernah format flashdisk menggunakan Gparted gan, tapi setelah saya format, partisi yang ada didalam flashdisk itu jadi unllocated gan, dan tidak bisa di format lagi menggunakan Gparted. Jadi saya cari cara yang lebih ampuh, ya itu tadi menggunakan CFdisk gan. Udah itu aja penjelasan saya kenapa pake CFdisk.

**Kenapa tidak menggunakan Fdisk gan ?** Oke, ini pertanyaan bagus menurut saya. Saya tidak menggunakan Fdisk untuk tutorial kali ini karena saya mau agan-agan yang masih baru di dunia linux tidak kesulitan untuk memahami tutorial saya gan.

Oke, mari disimak caranya gan 😀

**Penjelasan :**  

 - /dev/sdb adalah tempat partisi flashdisk saya.

1\. Pilih Delete untuk menghapus partisi pada Flashdisk.

![][1]

2\. Pilih new untuk membuat ulang partisi.

![][2]

3\. Pilih Primary gan.

![][3]

4\. tekan tombol enter untuk jumlah maksimal kapasitas flashdisk.

![][4]

5\. Pilih Bootable, jika tidak dipilih bootable. maka tidak bisa melakukan "write" di flashdisk.

![][5]

6\. Pilih write agar settingan yg kita lakukan pada point diatas bisa terjadi.

![][6]

ketik yes, dan tekan tombol enter.

![][7]

7\. Pilih Quite gan untuk keluar dari CFdisk.

![][8]

8\. nah sekarang jalankan perintah "**lsblk**" untuk melihat partisi flashdisk yg baru kita buat.

![][9]

9\. Jalankan perintah "**mkfs.vfat -F32 /dev/sdb1**" di terminal. Sesuaikan dengan tempat partisi flashdisk agan. bisa saja punya agan /dev/sdc1 atau yg lainnya.

![][10]

10\. Nah sekarang jalankan perintah "**dosfslabel /dev/sdb1** **Arietux**" untuk membuat nama label pada flashdisk agan.


![][11]

Nah,, sekarang kita sudah selesai memformat flashdisk dengan menggunakan CFdisk.

Liat gambar dibawah untuk contoh flashdisk yg saya format.


![][12]

[1]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-30-08-AM.png
[2]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-30-45-AM.png
[3]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-31-04-AM.png
[4]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-31-20-AM.png
[5]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-31-37-AM.png
[6]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-31-48-AM.png
[7]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-32-57-AM.png
[8]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-33-13-AM.png
[9]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-33-40-AM.png
[10]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-34-22-AM.png
[11]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-35-17-AM.png
[12]: {{ site.baseurl }}/images/2013/03/Screenshot-03062013-10-36-23-AM.png