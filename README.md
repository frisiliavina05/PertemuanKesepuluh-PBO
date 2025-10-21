# Penerapan Konsep OOP dalam Sistem CRUD Berbasis CSV
Praktikum ke 10 ini merupakan implementasi sederhana dari proses upload dan pembacaan file CSV menggunakan bahasa pemrograman Java dengan antarmuka Java Swing. Tujuan utama dari praktikum ini adalah untuk memahami cara pengolahan data eksternal berformat CSV agar dapat dibaca, diinterpretasikan, dan ditampilkan secara interaktif melalui komponen JTable. Dalam implementasinya, sistem ini tidak melibatkan proses CRUD berbasis database, melainkan berfokus pada pengelolaan data langsung dari file CSV untuk ditampilkan ke dalam aplikasi secara dinamis.

# File CSV
File CSV (Comma-Separated Values) adalah salah satu format penyimpanan data berbasis teks yang umum digunakan untuk merepresentasikan data dalam bentuk baris dan kolom seperti tabel. Setiap elemen data pada satu baris dipisahkan oleh tanda khusus yang disebut delimiter, yang berfungsi sebagai pembatas antar nilai. 

<br> Meskipun disebut Comma-Separated Values, kenyataannya tidak semua file CSV menggunakan tanda koma (,) sebagai pemisah. Pada beberapa pengaturan regional, seperti Indonesia dan negara-negara Eropa, delimiter yang digunakan justru berupa titik koma (;). Hal ini terjadi karena dalam pengaturan regional tersebut, tanda koma berfungsi sebagai pemisah desimal dalam angka (misalnya 3,14), sehingga untuk menghindari benturan dalam penyimpanan data numerik, aplikasi seperti Excel secara otomatis menggunakan titik koma sebagai pembatas antar kolom. 

<br> Contoh : 
 ``` 
KR020;Don't Go;EXO;2013 
KR018;Paradise;Treasure;2025
KO011;Somebody;DO;2023
KR100;Hello;Chen;2020
KO095;Peaches;Kai;2022
```

<br> Memahami perbedaan penggunaan delimiter dalam file CSV merupakan hal yang sangat penting agar program Java dapat memproses data dengan benar. Kesalahan dalam menentukan jenis delimiter dapat menyebabkan data tidak terbaca sesuai dengan kolom aslinya, sehingga struktur tabel menjadi tidak teratur dan informasi yang ditampilkan pun bisa keliru.

# Konsep Pembacaan File CSV pada Java
Pada Java, pembacaan file CSV dapat dilakukan dengan menggunakan BufferedReader, yang berfungsi untuk membaca isi file secara bertahap, baris demi baris. Setiap baris yang diperoleh kemudian dipisahkan menjadi beberapa elemen data sesuai dengan delimiter yang digunakan (seperti ; atau ,) dengan bantuan metode split().

    try (BufferedReader br = new BufferedReader(new FileReader(filePilihan))) {
                Class.forName(driver);
                conn = DriverManager.getConnection(koneksi, user, password);
                String baris;
                String pemisah = ";";

                while ((baris = br.readLine()) != null) {
                    String[] data = baris.split(pemisah);
                    
Data yang telah dibaca dari file biasanya disimpan sementara dalam struktur seperti ArrayList atau DefaultTableModel, sebelum akhirnya ditampilkan ke komponen JTable agar dapat dilihat dalam bentuk tabel yang terstruktur.

    String id = data[0];
                    String judul = data[1];
                    String artis = data[2];
                    int tahun = Integer.parseInt(data[3]);

                    if (!id.isEmpty() && !judul.isEmpty() && !artis.isEmpty()) {
                        String sql = "INSERT INTO musik (id, judul, artis, tahun) VALUES (?,?,?,?)";
                        pstmt = conn.prepareStatement(sql);
                        pstmt.setString(1, id);
                        pstmt.setString(2, judul);
                        pstmt.setString(3, artis);
                        pstmt.setInt(4, tahun);

                        pstmt.executeUpdate();

# Komponen JFileChooser pada Java Swing
JFileChooser adalah komponen bawaan dari Java Swing yang digunakan untuk menampilkan jendela dialog pemilihan file secara interaktif. Melalui komponen ini, pengguna dapat memilih file secara langsung dari tampilan file explorer, sehingga tidak perlu lagi menuliskan lokasi atau path file secara manual.

# Alur Proses Upload CSV
<br> 1. Pengguna menekan tombol Upload untuk menampilkan dialog JFileChooser.
<br> 2. File CSV dipilih dari penyimpanan lokal.
<br> 3. Program membaca isi file menggunakan BufferedReader atau pustaka seperti OpenCSV.
<br> 4. Data yang telah dibaca dimasukkan ke dalam DefaultTableModel.
<br> 5. Komponen JTable kemudian menampilkan data tersebut pada antarmuka aplikasi


