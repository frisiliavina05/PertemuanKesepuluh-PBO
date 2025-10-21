# Penerapan Konsep OOP dalam Sistem CRUD Berbasis CSV
Praktikum ke 10 ini merupakan implementasi sederhana dari proses upload dan pembacaan file CSV menggunakan bahasa pemrograman Java dengan antarmuka Java Swing. Tujuan utama dari praktikum ini adalah untuk memahami cara pengolahan data eksternal berformat CSV agar dapat dibaca, diinterpretasikan, dan ditampilkan secara interaktif melalui komponen JTable. Dalam implementasinya, sistem ini tidak melibatkan proses CRUD berbasis database, melainkan berfokus pada pengelolaan data langsung dari file CSV untuk ditampilkan ke dalam aplikasi secara dinamis.

# File CSV
File CSV (Comma-Separated Values) adalah salah satu format penyimpanan data berbasis teks yang umum digunakan untuk merepresentasikan data dalam bentuk baris dan kolom seperti tabel. Setiap elemen data pada satu baris dipisahkan oleh tanda khusus yang disebut delimiter, yang berfungsi sebagai pembatas antar nilai. <br>
Meskipun disebut Comma-Separated Values, kenyataannya tidak semua file CSV menggunakan tanda koma (,) sebagai pemisah. Pada beberapa pengaturan regional, seperti Indonesia dan negara-negara Eropa, delimiter yang digunakan justru berupa titik koma (;). Hal ini terjadi karena dalam pengaturan regional tersebut, tanda koma berfungsi sebagai pemisah desimal dalam angka (misalnya 3,14), sehingga untuk menghindari benturan dalam penyimpanan data numerik, aplikasi seperti Excel secara otomatis menggunakan titik koma sebagai pembatas antar kolom. <br>
Contoh : <br>
   KR020;Don't Go;EXO;2013
   KR018;Paradise;Treasure;2025
   KO011;Somebody;DO;2023
   KR100;Hello;Chen;2020
   KO095;Peaches;Kai;2022


