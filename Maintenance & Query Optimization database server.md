pada sesi kali ini, saya akan melakukan maintenance database server untuk mengembalikan database server ke performa terbaiknya yang memungkinkan penerapan ini bisa dilakukan pada level enterprise. 



1. melakukan cek table untuk melakukan integritas pada struktur table. memastikan table tidak ada masalah atau korupsi.
   <img width="1215" height="395" alt="Screenshot (318)" src="https://github.com/user-attachments/assets/4589bd5f-4d67-45d6-9318-78650b8aee6e" />


2. melakukan analisis table untuk memastikan optimizer selalu memiliki statistik index yang akurat terutama setelah operasi data besar seperti proses DML.
   <img width="1094" height="267" alt="Screenshot (319)" src="https://github.com/user-attachments/assets/2d4df3d6-994e-4283-8686-981f6e847e90" />
   <img width="954" height="343" alt="Screenshot (321)" src="https://github.com/user-attachments/assets/c74c593e-6570-4515-8e12-caa4a712cfcf" />
   - cardinality : semakin angkanya menyamai atau mendekati jumlah baris data yang ada, melakukan optimizer akan mengambil keputusan yang tepat saat merencanakan eksekusi query statement.
   - visible : jika (yes) indeks tersebut bisa digunakan untuk kebutuhan query optimizer


3. membuat perencanaan eksekusi query statement untuk mengoptimalkan rencana eksekusi yang lebih efisien tanpa menjalankan query statement tersebut.
   <img width="1309" height="569" alt="Screenshot (326)" src="https://github.com/user-attachments/assets/353f35f9-845a-4dce-a214-e08a2b2cd277" />



4. membuat index untuk mengoptimalkan perencanaan eksekusi query statement yang masih memindai full table menjadi pemindaian index. fungsinya mengambil data menjadi lebih cepat tanpa perlu memindai seluruh isi
   baris data yang ada.
   <img width="1648" height="403" alt="Screenshot (327)" src="https://github.com/user-attachments/assets/ce41035e-1b1f-4d8c-8a3a-58c2323bde0e" />
   - actual-time : 0.0293 > 0.0276
   - scan-rows : 10 > 5
   penggunaan index ini akan terlihat jelas efektifitasnya pada table yange memiliki jumlah baris yang besar. 


   
   
   

   
   


   
