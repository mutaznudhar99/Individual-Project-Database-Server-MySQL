pada sesi ini, saya akan melakukan backup & restore pada server yang berbeda, melakukan backup dan restore point in time recovery pada server yang berbeda, dan migrasi data menggunakan metode replikasi master-slave menggunakan percona xtrabackup, binary log, dan gtid. 

kenapa saya memilih menggunakan percona xtrbackup dibandingkan dengan mysql enterprise backup:
- percona xtrabackup merupakan tools backup open source dibandingkan mysql backup yang berbayar
- cocok untuk backup fisik data yang menyimpan data besar
- sangat cepat dan andal untuk membackup dan restore file data
- non blocking saat melakukan backup, artinya backup bisa berjalan di saat database aktif (hot backup)
- terintegrasi dengan incremental backup, parallel backup, compressed file backup, dan sebagainya.




1. saya akan membuat 1 schema pada database server sebagai contoh, yang berisikan 1 table dan 5 baris data untuk melakukan restore data ke server yang berbeda.

   - menampilkan schema sebelum membuat schema baru
     <img width="803" height="218" alt="Screenshot (168)" src="https://github.com/user-attachments/assets/c7976a42-d017-488d-9965-2c887ee4c5ca" />


   - membuat schema baru yang berisikan 1 tabel dan 5 baris data
     <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/215ec4e6-a26f-4c60-95f8-bc0d53a96851" />
     <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8199da47-174e-42bf-96b6-c27234e278a3" />


   - menampilkan schema baru dan tabel yang ada pada schema 
     <img width="948" height="235" alt="Screenshot (176)" src="https://github.com/user-attachments/assets/8b50d5bf-cd91-4bd5-a089-2bfb4a75932b" />
     <img width="907" height="147" alt="Screenshot (174)" src="https://github.com/user-attachments/assets/57b24600-fb6b-4c46-90c2-6452260e6e79" />




2. cek ukuran file data dan schema untuk monitoring dan memanajemen ruang tempat backup data dan server restore yang berbeda.

   

   

