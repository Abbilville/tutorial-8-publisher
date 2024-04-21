# Tutorial-8
---
#### Nama: Abbilhaidar Farras Zulfikar
#### NPM: 2206026012
#### Kelas: Adpro A
---
### Refleksi
1. **How many data your publisher program will send to the message broker in one run?** <br>
Program publisher akan mengirimkan lima data ke message brocker dalam satu kali eksekusi. Hal ini karena ada lima panggilan metode publish_event, masing-masing mengirimkan sebuah UserCreatedEventMessage ke message brocker.<br>

2. **what guest:guest@localhost:5672 means? what is the first quest, and what is the second guest, and what is localhost:5672 is for?** <br>
URL <code>amqp://guest:guest@localhost:5672</code> sama di kedua program subscriber dan publisher. Ini berarti bahwa baik subscriber maupun publisher terhubung ke server AMQP (Advanced Message Queuing Protocol) yang sama menggunakan kredensial yang sama (nama pengguna: "guest", sandi: "guest"), dan server berjalan pada localhost dengan port 5672.

![alt text](assets/image/image1.png) <br><br>

Screenshot terminal Subscriber <br>
![alt text](assets/image/image2.png) <br><br>

Screenshot terminal subscriber dimana telah berhasil menerima 5 event message broker dari publisher <br>
![alt text](assets/image/image3.png) <br><br>