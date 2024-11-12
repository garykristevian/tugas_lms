
# Aplikasi LMS Sederhana Menggunakan Django dan PostgreSQL

## Aplikasi LMS ini memiliki template minimal, hanya untuk tujuan edukasi di backend, dengan beberapa URL yang telah ditambahkan di `urls.py`.

## Aplikasi ini juga dapat dijalankan secara virtual menggunakan Docker, yang menjelaskan keberadaan `Dockerfile` dan `docker-compose.yml` di dalamnya.

### Cara Menjalankannya di Container Docker

1. Pastikan Docker terinstal di komputer Anda. Jika sudah, jalankan Docker Machine.
2. Unduh file zip dari proyek ini, lalu ekstrak di komputer Anda.
3. Sebaiknya unduh ekstensi Docker (oleh Microsoft) dan PostgreSQL (oleh Weijan Chen) jika Anda menggunakan VSCode sebagai IDE.
4. Buka terminal baru, lalu jalankan perintah berikut:
   - `docker-compose up -d --build`
5. Proses ini akan memakan beberapa menit hingga selesai.
6. Jika sudah berjalan, buka ekstensi Docker di VSCode untuk melihat container yang sedang aktif.
7. Klik kanan pada "docker-lms-django" dan pilih "Attach Shell" untuk membuka terminal Docker.
8. Sebelum menjalankan perintah apapun, hubungkan terlebih dahulu ke PostgreSQL.
9. Buka ekstensi PostgreSQL, kemudian buat koneksi baru.
10. Isi Nama Database, Pengguna Database, dan Kata Sandi sesuai dengan file `settings.py`. Anda dapat mencari file ini dan scroll ke bagian databases.
11. Setelah membuat koneksi, lanjutkan ke langkah berikutnya.
12. Jalankan perintah berikut:
    - `python manage.py makemigrations`
    - `python manage.py migrate`
13. Perintah-perintah tersebut akan melakukan migrasi untuk membuat tabel di PostgreSQL.
14. Untuk memeriksa tabel, gunakan lagi ekstensi PostgreSQL dan cek tabel seperti user, coursecontent, coursemember, course, dan comment.
15. Kemudian, buka terminal Docker dan jalankan perintah:
    - `python manage.py runserver 0.0.0.0:8000`
16. Untuk melihat data, cukup akses URL yang telah disetel di `urls.py`.
