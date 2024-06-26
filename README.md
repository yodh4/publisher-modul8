1. How many data your publlsher program will send to the message broker in one run?

    program `publisher` akan mengirim 5 data dalam bentuk `UserCreatedEventMessage` yang saling berbeda kepada message broker setiap kalo program di-run.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

    `publisher` dan `subscriber` memiliki url yang sama menandakan karena kedua program ini menggunakan protokol AMQP untuk berkomunikasi melalui message broker yang sama sehingga kedua program dapat saling mengirim dan memproses data

![RabbitMQ](image1.png)
Tampilan RabbitMQ saat diakses melalui `localhost:5672/`
<br></br>

![RabbitMQ-connection](image2.png)
![terminal](terminal.png)
Pada gambar tersebut terlihat terdapat angka 1 pada bagian Connections, angka tersebut menandakan terdapat 1 subscriber yang terhubung ke message broker RabbitMQ. Selain itu, pada gambar terminal terlihat saat program `publisher` di-run maka akan muncul pesan pada terminal `subscriber`, hal ini terjadi karena program `publisher` akan mengirim 5 data ke message broker dan `subscriber` yang terhubung ke message broker yang sama akan menerima data tersebut.
<br></br>

![RabbitMQ-msgrate](spike.png)
Pada chart tersebut terlihat perubahan grafik yang ditampilkan pada bagian message rates, hal ini dipengaruhi oleh frekuensi `publisher` dalam mengirim data. Jika `publisher` mengirim data secara terus menerus maka grafiknya akan terus naik dan saat `publisher` berhenti mengirim data maka graiknya akan turun perlahan lahan hingga akhirnya menjadi datar.
<br></br>

![RabbitMQ-slow](slow.png)
Karena program subscriber berjalan lebih lambat dari sebelumnya maka akan terjadi antrean messages sebelum akhirnya diterima oleh subscriber. Angka terakhir yang saya dapatkan pada chart queued messages bernilai sekitar 20 yang menunjukan terdapat sekitar 20 messages yang masih ada pada antrian sebelum diterima oleh subsriber.
