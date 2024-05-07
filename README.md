# Tutorial 10 (Timer)

**Prasetyo Adi Wijonarko**<br>
**2206830246**<br>
**Pemrograman Lanjut A / DEE**<br>


## 1.2. Understanding how it works

![alt text](/image/Timer-1.jpg)

Berdasarkan hasil eksekusi program, output yang pertama muncul adalah "Adi's Komputer: hey hey!" setelah itu muncul perintah yang ada pada spawner. Hal ini disebabkan karena kode diletakkan sebelum `drop(spawner)` dan `executor.run()`. Baru setelahnya ketika executor dijalankan, maka output "Adi's Komputer: howdy!". Kemudian, setelah waktu tertentu (dalam kasus ini, 2 detik), output "Adi's Komputer: done!" akan muncul. Jadi, Program tetap berjalan tanpa terblokir saat menunggu tugas asinkronus selesai dieksekusi, dan output sesuai dengan urutan dan waktu eksekusi yang ditentukan dalam program.

## 1.3. Multiple Spawn and removing drop
![alt text](/image/Timer-2.jpg)
![alt text](/image/Timer-3.jpg)
![alt text](/image/Timer-4.jpg)

Berdasarkan hasil eksekusi, ketika multiple spawn dijalankan, semua task yang dispawn akan berjalan bersamaan, diikuti oleh timer 2 detik sebelum semua task menampilkan output "done!". Karena sifat asinkronus setiap task yang dieksekusi oleh executor, urutan munculnya output dapat bervariasi. Perbedaan terlihat saat drop(spawner) dihapus dan ditambahkan lagi. Saat dihapus, spawner tetap aktif meskipun semua task sudah ditambahkan, sehingga executor tetap menerima task baru untuk dijalankan, menjadikan program tidak akan berhenti. Namun, ketika drop(spawner) digunakan, executor mengetahui bahwa tidak akan ada lagi task baru, sehingga dapat berhenti setelah semua task selesai dieksekusi. Pada lampiran, urutan print done juga bisa berbeda karena setiap task memiliki waktu tunggu yang sama, bergantung kepada bagaimana executor menjadwalkan task-task tersebut secara asinkron dan konkuren.