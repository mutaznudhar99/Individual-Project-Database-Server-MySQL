sebelum melakukan instalasi & konfigurasi database MySQL Server pada level OS Ubuntu, pastikan OS sudah terinstall dan terkonfigurasi pada OS di desktop menggunakan virtual machine.



1. Update operasi sistem ubuntu
   - dilakukan untuk memperbarui dan menginstall repository index pada system
     <img width="744" height="224" alt="Screenshot (133)" src="https://github.com/user-attachments/assets/a1c7d1a7-007b-4a65-a455-9717dbbd5d74" />
     
     sudo apt list --upgradable
     
     <img width="1058" height="149" alt="Screenshot (134)" src="https://github.com/user-attachments/assets/b8d4a0f6-4994-4e13-b6f2-9641d1d204d2" />

     sudo apt upgrade

     <img width="1660" height="265" alt="Screenshot (135)" src="https://github.com/user-attachments/assets/e370cc77-619d-4fbb-b6e0-ccd031af1b7f" />


2. Mencari MySQL Package yang tersedia di dalam operasi sistem

      apt-cache search mysql-server
      <img width="1042" height="195" alt="Screenshot (137)" src="https://github.com/user-attachments/assets/b394efd1-c021-4c19-860e-44b1a25591a5" />

      apt info -a mysql-server-versi
      <img width="1106" height="202" alt="Screenshot (138)" src="https://github.com/user-attachments/assets/d9ac6516-2446-4ed6-b803-132827e74916" />





     
     
   

    
