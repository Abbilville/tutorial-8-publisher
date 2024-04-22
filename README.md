# Tutorial-8
---
#### Nama: Abbilhaidar Farras Zulfikar
#### NPM: 2206026012
#### Kelas: Adpro A
---
### Refleksi
1. **How many data your publisher program will send to the message broker in one run?** <br>
Program publisher akan mengirimkan lima data ke message brocker dalam satu kali eksekusi. Hal ini karena ada lima panggilan metode publish_event, masing-masing mengirimkan sebuah UserCreatedEventMessage ke message brocker.<br>

2. **The url of: <code>amqp://guest:guest@localhost:5672</code> is the same as in the subscriber program, what does it mean?** <br>
URL <code>amqp://guest:guest@localhost:5672</code> sama di kedua program subscriber dan publisher. Ini berarti bahwa baik subscriber maupun publisher terhubung ke server AMQP (Advanced Message Queuing Protocol) yang sama menggunakan kredensial yang sama (nama pengguna: "guest", sandi: "guest"), dan server berjalan pada localhost dengan port 5672.

Screenshot interface RabbitMQ ketika baru login
![alt text](assets/image/image1.png) <br><br>

Screenshot terminal subscriber dimana telah berhasil menerima 5 event message broker dari publisher <br>
![alt text](assets/image/image2.png) <br><br>

Screenshoot terminal publisher dimana telah berhasil menjalankan <code>cargo run</code> untuk mengirim 5 event memalui message brocker yang kemudian akan diproses oleh subscriber <br>
![alt text](assets/image/image3.png) <br><br>

Screenshot interface RabbitMQ dimana ada spike pada message rates yang disebabkan karena saya menjalankan publisher berkali-kali. Spike pada chart menandakan bahwa saya telah menjalankan program publisher dengan <code>cargo run</code> <br>
![alt text](assets/image/image4.png) <br><br>

Ada beberapa perbaikan yang dapat dilakukan pada kode ini: <br>
1. Saat ini, hasil dari <code>publish_event</code> diabaikan dengan _ =. Lebih baik menangani potensi kesalahan ini dengan benar.
2. Metode <code>publish_event</code> dipanggil beberapa kali dengan argumen yang serupa. Ini bisa direfactor menjadi loop atau fungsi untuk mengurangi duplikasi kode.
3. String koneksi dan nama event dikodekan secara langsung. Lebih baik memindahkan ini ke dalam file konfigurasi atau environment variables.
