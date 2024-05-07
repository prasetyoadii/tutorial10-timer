# Tutorial 10 (Timer)

**Prasetyo Adi Wijonarko**<br>
**2206830246**<br>
**Pemrograman Lanjut A / DEE**<br>


## 1.2. Understanding how it works

![alt text](/image/Timer-1.jpg)

Berdasarkan hasil eksekusi program, output yang pertama muncul adalah "Adi's Komputer: hey hey!" setelah itu muncul perintah yang ada pada spawner. Hal ini disebabkan karena kode diletakkan sebelum `drop(spawner)` dan `executor.run()`. Baru setelahnya ketika executor dijalankan, maka output "Adi's Komputer: howdy!". Kemudian, setelah waktu tertentu (dalam kasus ini, 2 detik), output "Adi's Komputer: done!" akan muncul. Jadi, Program tetap berjalan tanpa terblokir saat menunggu tugas asinkronus selesai dieksekusi, dan output sesuai dengan urutan dan waktu eksekusi yang ditentukan dalam program.