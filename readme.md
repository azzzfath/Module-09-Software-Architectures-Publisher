# Dokumentasi Publisher - MODUL 9

## Pertanyaan Refleksi

### 1. How much data your publisher program will send to the message broker in one run?
Program *publisher* akan mengirimkan **5 buah data/event** secara berurutan ke *message broker* dalam satu kali jalan. Hal ini terlihat dari adanya 5 kali pemanggilan fungsi `p.publish_event` di dalam fungsi `main` untuk *user* yang berbeda-beda.

### 2. The url of: "amqp://guest:guest@localhost:5672" is the same as in the subscriber program, what does it mean?
Penggunaan URL yang sama berarti bahwa program *publisher* dan *subscriber* **terhubung ke instance *message broker* (RabbitMQ) yang sama**. Agar *subscriber* dapat menerima pesan yang dikirim oleh *publisher*, keduanya harus berkomunikasi melalui protokol (AMQP), server (`localhost`), port (`5672`), dan kredensial (`guest:guest`) yang persis sama.

### Make it work!
![Screenshot Console](Screenshot.png)
**Penjelasan:** Saat `publisher` dijalankan, program tersebut mengirimkan 5 antrean event ke RabbitMQ. Di sisi lain, program `subscriber` yang sedang berjalan (dan terus mendengarkan) langsung menerima dan memproses kelima pesan tersebut secara berurutan.