pada sesi ini, saya akan melakukan migrasi data dari server primary ke server standby menggunakan metode replikasi master-slave untuk pengaplikasian migrasi data near zero downtime.
hal ini penting dilakukan untuk memigrasi data critical. hal yang dibutuhkan saat memigrasi data menggunakan metode rpelikasi master-slave:
- menyediakan 1 server primary dan server standby
- menggunakan tools xtrabackup
- mengaktifkan binar log + gtid (global transaction identifier), gtid menjadi dasar yang penting untuk replikasi modern, pemulihan, dan failover.
metode ini berupa metode kelanjutan dari backup & recovery pitr menggunakan xtrabackup + binary log.


1. konfigurasi mysql.cnf pada source server dan replica server
   - sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf
     <img width="1283" height="110" alt="Screenshot (287)" src="https://github.com/user-attachments/assets/9f76c599-a9c9-4be3-98ec-1122cdc5fe45" /> <img width="943" height="126" alt="Screenshot (286)" src="https://github.com/user-attachments/assets/fff24534-8ffa-4789-bec3-05399b0cdcc6" />

3. restart mysql services di kedua server

4. cek status konfigurasi di dalam database server
   <img width="1116" height="581" alt="Screenshot (290)" src="https://github.com/user-attachments/assets/ae8716ce-b737-464e-9af2-b3944df6354c" /> <img width="1229" height="620" alt="Screenshot (291)" src="https://github.com/user-attachments/assets/724cf3c0-b210-47bc-9609-fc0fb8bbd18e" />





