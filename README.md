1. How many data your publlsher program will send to the message broker in one run?

    program `publisher` akan mengirim 5 data dalam bentuk `UserCreatedEventMessage` yang saling berbeda kepada message broker setiap kalo program di-run.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

    `publisher` dan `subscriber` memiliki url yang sama menandakan karena kedua program ini menggunakan protokol AMQP untuk berkomunikasi melalui message broker yang sama sehingga kedua program dapat saling mengirim dan memproses data