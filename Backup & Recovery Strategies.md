pada sesi ini, saya akan melakukan backup & restore pada server yang berbeda, melakukan backup dan restore point in time recovery pada server yang berbeda, dan migrasi data menggunakan metode replikasi master-slave menggunakan percona xtrabackup, binary log, dan gtid. 

kenapa saya memilih menggunakan percona xtrbackup dibandingkan dengan mysql enterprise backup:
- percona xtrabackup merupakan tools backup open source dibandingkan mysql backup yang berbayar
- cocok untuk backup fisik data yang menyimpan data besar
- sangat cepat dan andal untuk membackup dan restore file data
- non blocking saat melakukan backup, artinya backup bisa berjalan di saat database aktif (hot backup)
- terintegrasi dengan incremental backup, parallel backup, compressed file backup, dan sebagainya.







1. sebelum melakukan backup fisik data, hal yang perlu saya lakukan adalah cek size file data dan cek size database pada server.

   - sudo -

