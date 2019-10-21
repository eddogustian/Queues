<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

Anda pasti bertanya-tanya, apa yang diperlukan untuk memproses pekerjaan selanjutnya? Jangan khawatir—itu adalah apa yang akan kita bahas pada bagian berikutnya.

Queue Worker
Pekerjaan queue worker Laravel adalah untuk memproses pekerjaan yang ter-queue untuk diproses. Sebenarnya, ada perintah artisan yang membantu kita untuk memulai proses queue worker.


$php artisan queue:work


Segera setelah anda menjalankan perintah, ini memproses pekerjaan yang tertunda. Dalam kasus kita, ini seharusnya memproses pekerjaan ProcessImageThumbnails yang ter-queue ketika pengguna meng-upload gambar sebelumnya.


$php artisan queue:work


[YYYY-MM-DD HHMMSS] Processing: App\Jobs\ProcessImageThumbnails
[YYYY-MM-DD HHMMSS] Processed:  App\Jobs\ProcessImageThumbnails


Anda akan sadar bahwa ketika anda memulai queue worker, itu akan terus berjalan sampai anda menghentikannya secara manual atau menutup terminal. Pada kenyataannya, ini menunggu pekerjaan berikutnya untuk diproses. Segera ada pekerjaan baru dalam queue, ini akan diproses segera jika queue worker berjalan.

Tentu saja, kami tidak dapat tetap berjalan seperti ini, jadi kita perlu menemukan cara agar queue worker menjalankannya secara permanen di latar belakang.

Untuk menolong kita, ada beberapa alat manajemen proses diluar sana yang dapat anda pilih. Untuk beberapa nama, berikut daftarnya:

Circus
daemontools
Monit
Supervisor
Upstart

Anda harus memilih alat yang membuat anda nyaman dengan mengelola Laravel queue worker. Pada dasarnya, kita ingin memastikan bahwa queue worker harus berjalan tanpa batas waktu sehingga segera memproses pekerjaan queue.

Jadi itu adalah Queue API di penyelesaian Anda. Anda dapat menggunakannya dalam pengembangan hari-ke-hari anda untuk menunda tugas-tugas yang memakan waktu untuk kemajuan pengalaman pengguna akhir.




