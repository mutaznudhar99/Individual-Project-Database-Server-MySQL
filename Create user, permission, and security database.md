pada sesi kali ini, saya akan membuat role, permission, user, dan security database yang bisa diterapkan pada lingkungan enterprise untuk menjaga keamanan database server. kemudian mengaktifkan pgaudit untuk proses monitoring setiap user yang mengakses data.

dalam project testing ini, saya akan membuat user operasional yang dibagi menjadi user **read** and **writer**.


1. login ke dalam database menggunakan user 'root', karena server belum membuat user operasional lain.
   <img width="909" height="466" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/046f4352-73e7-4f3e-9c0e-e0891035346a" />


2. cek validasi password yang disetujui oleh server saat membuat user
   - memastikan password yang dibuat untuk user sesuai dengan keamanan database server

     <img width="921" height="126" alt="Screenshot (182)" src="https://github.com/user-attachments/assets/644d0afe-ac83-41ce-b60a-ef98c299c99b" />

   - membuat kemanan menggunakan autentifikasi plugin 
     
     <img width="986" height="287" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/a68f34af-a64b-4986-817c-bd4850c911c8" />
     - length : minimal karakter
     - mix_case_count : minimal 1 huruf besar dan 1 huruf kecil
     - number_count : minimal mempunyai 1 angka
     - special_char : minimal harus mempunyai 1 karakter khusus (@, #, dll)
     - cek_user_name : tidak boleh mengandung nama user


4. selanjutnya, membuat user operasional dengan role **user_reader** dan **user_writer** menggunakan validasi password yang disetujui oleh server.
   - memastikan user operasional yang login ke dalam database server seminimal mungkin diberikan izin hak akses.
   - merupakan security database level middle enterprise yang wajib saya terapkan untuk keamanan data.

     - user 'reporting' dengan role 'user_reader'
       <img width="1106" height="413" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/07319fc3-829f-4627-9169-efc9186c5b96" />

     - user 'transaction' dengan role 'user_writer'
       <img width="990" height="386" alt="Screenshot (158)" src="https://github.com/user-attachments/assets/cfb56c2e-4525-418f-9e70-084bd8201734" />
       - grant : memberikan izin kepada user untuk level tertentu
       - *.* : database.table
       - set default role : mengaktifkan peran secara default ketika user login
       - 'localhost' : digunakan untuk mengizinkan koneksi dari aplikasi yang berjalan di server fisik yang sama dengan database server
       - '%' : digunakan untuk mengizinkan koneksi dari ip atau nama host manapun di jaringan
       - specific ip : digunakan hanya untuk mengizinkan koneksi dari satu alamat ip yang ditentukan


5. Monitoring user exist/yang ada di dalam database server beserta dengan role dan autentifikasi security server.

   - menampilkan user yang ada di dalam server database
   - memastikan user yang dibuat memiliki autentifikasi security yang disetujui oleh database server
     <img width="921" height="323" alt="Screenshot (167)" src="https://github.com/user-attachments/assets/a17e7c36-0275-42ac-996d-ef2781ef902d" />

   - menampilan user beserta dengan role nya di dalam database server
     <img width="1014" height="387" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/fa005377-e973-413a-86b9-f7b610244edb" />
     - bisa dilakukan yang sama pada user/role yang terdaftar di dalam server


6. mengaktifkan pg_audit untuk mencatat setiap user yang login dan mengakses data pada database dan disimpan di dalam file logging.
   - install postgresql-versi-pgaudit

     <img width="1357" height="677" alt="Screenshot (504)" src="https://github.com/user-attachments/assets/0d3a8cb5-00f6-4e09-8f67-e8565b2393be" />


7. konfigurasi postgresql.conf dengan menambahkan parameter pgaudit

   <img width="1137" height="201" alt="Screenshot (518)" src="https://github.com/user-attachments/assets/7c99da5c-e6a7-459e-9dc5-a34bcb14f52f" />
   - all : mencatat semua tindakan yang dilakukan oleh user pada database server, proses audit paling berat(tidak rekomen)
   - log_line_prefix : mencatat dari mana asal user


8. membuat extension pgaudit pada database untuk mengaktifkan fitur audit

   <img width="564" height="230" alt="Screenshot (511)" src="https://github.com/user-attachments/assets/5547cd2e-f24f-4a76-bdc8-9b600b5a7dd2" />


9. konfigurasi pg_hba.conf untuk menerima akses ke database dari server luar

   <img width="1166" height="276" alt="Screenshot (514)" src="https://github.com/user-attachments/assets/7236d5b9-315f-4f2d-98f0-1193d12b4b82" />
   - trust : memberikan kepercayaan penuh pada user di luar server tanpa verifikasi apapun. dilakukan untuk testing akses database.


10. install postgresql-client-versi di server berbeda kemudian login ke dalam database server dan membuat database beserta table untuk bahan audit
    - sudo apt-get install postgresql-client-versi

      <img width="1229" height="414" alt="Screenshot (515)" src="https://github.com/user-attachments/assets/262b6114-bfcf-4d7c-8100-b4f28a73728f" />


11. login ke dalam database server dan melakukan read data pada server primary

    <img width="748" height="245" alt="Screenshot (516)" src="https://github.com/user-attachments/assets/ab4b54a0-e7de-441d-836c-c5df82f197f8" />


12. cek log file audit di server primary

    <img width="1694" height="322" alt="Screenshot (517)" src="https://github.com/user-attachments/assets/1d9f1553-fb97-4d96-8bd9-bd50cd16d65a" />





   



     
   
     
     
     



   


