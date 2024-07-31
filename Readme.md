# Template Laravel Docker

Merupakan clone dan modifikasi dari repository https://github.com/hanieas/Docker-Laravel

Dalam project ini, Mariadb digunakan untuk menangani rdbms.

## Panduan ringkas
- Edit docker-compose.yml. Sesuaikan nama container dan port. Pastikan tidak ada konflik nama container dan port.
- Nama service aplikasi laravel, dalam contoh ini adalah larapphel, harus menjadi entry
parameter *fastcgi_pass* di file *nginx/conf.d/default.conf*.
- Buat folder mysql dan mysql/data di dalam root project untuk volume rdbms.
- Buat project laravel menggunakan composer. Nama folder aplikasi laravel, halam hal ini *project* harus sesuai dengan entry volume layanan nginx pada file *docker-compose.yml*.
- Ubah ownership __/var/www__ di dalam container aplikasi laravel, dalam contoh ini adalah *larapphel* mejadi milik __www-data__ sebelum container diaktifkan. Ubah kembali menjadi milik root untuk keperluan editing. 