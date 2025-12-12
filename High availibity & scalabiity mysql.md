pada sesi kali ini, saya akan melakukan high availibility database dan clustering terintegrasi menggunakan beberapa fitur native dari mysql atau disebut dengan innodb cluster mysql. hal ini bertujuan untuk:
- menyediakan ketersediaan database yang tinggi (HA)
- skalabilitas baca
- perpindahan peran secara otomatis (failover automatic)
- memastikan konsistensi data yang kuat

mysql innodb cluster menggabungkan beberapa komponen native, diantaranya:
- mysql group replication, yang terdiri dari beberapa server replikasi (minimal 3) 1 server primary/multi master primary dan beberapa node replika yang dijadikan dalam sebuah kelompok/group
- mysql shell, sebagai command line administrasi setiap server
- mysql router, sebagai penghubung/connection pooling antara client dengan node database server.

hal-hal yang perlu dipersiapkan sebelum melakukan clustering data.
- ruang disk yang cukup
- 1 server primary mysql + mysqlshell
- 1 server replica mysql + mysqlshell
- 1 server replica mysql + mysqlshell
- 1 server mysql router


1. memastikan instalasi database mysql server dan mysql shell sudah terinstall di setiap server.
   <img width="1181" height="112" alt="Screenshot (353)" src="https://github.com/user-attachments/assets/ccd4f504-9e4e-426d-8bc6-1c54dc92de82" />
   <img width="1136" height="98" alt="Screenshot (354)" src="https://github.com/user-attachments/assets/63e3d279-761c-48ad-aa45-a7a9b78e0f48" />
   <img width="1217" height="115" alt="Screenshot (355)" src="https://github.com/user-attachments/assets/ad8867a7-1c16-46cf-bfb3-c39efff9c993" />








