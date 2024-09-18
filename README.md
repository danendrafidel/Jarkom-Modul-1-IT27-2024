# Jarkom-Modul-1-IT27-2024

## IT 27

| No  | Nama Anggota          | NRP        |
| --- | --------------------- | ---------- |
| 1   | Danendra Fidel Khansa | 5027231063 |
| 2   | Farida Qurrotu A'yuna | 5027231015 |

### Pegawai Negeri Sebelah

  Langkah Penyelesaian:

  1. Gunakan filter TCP pada Wireshark untuk mencari file pns.csv.
  2. Setelah file ditemukan, lakukan filter 
  3. Lanjut pada paket-paket yang berkaitan.
  4. Flag ditemukan

### Illegal Breakthrough

  Langkah Penyelesaian:

  1. Filter http.response pada Wireshark.
  2. Cari paket dengan IP belakang 207.
  3. Lakukan pencarian lebih lanjut pada paket yang mengandung kata kunci "found".
  4. Jawaban soal dan tools yang digunakan, yaitu ffuf-v2.1.0-dev, ditemukan di dalam paket yang berkaitan.
  5. Flag ditemukan

### Rizzset

  Langkah Penyelesaian :

  1. Filter paket DNS pada Wireshark, kemudian temukan IP terkait di bagian pojok kanan bawah.
  2. Clone repository JARM dengan perintah berikut:
  ```py
  git clone https://github.com/armory/jarm.git
  cd jarm
  pip install -r requirements.txt
  ```
  3. Jalankan perintah berikut untuk melakukan JARM fingerprinting terhadap domain target:
  ```py
  python jarm.py www.its.ac.id
  ```
  4. Hasil fingerprint ditemukan
  5. Muncul Flag

### Stegography

   Langkah Penyelesaian :

   1. Gunakan filter frame contains "png" pada Wireshark.
   2. Ekspor objek dan simpan gambar terkait.
   3. Gunakan script reversed.py yang sudah dimodifikasi untuk mendekripsi pesan di dalam gambar.
   4. Dari gambar ATP, EH, dan KJK, hasil yang ditemukan adalah frasa "pahlawan keamanan siber."
   5. Flag ditemukan

### InneRCE

  Langkah Penyelesaian :

  1. Filter frame contains "shel" untuk mencari file yang berhubungan dengan webshell.
  2. Fokus pada timestamp 2024-09-16 13:18:05.
  3. Cari hostname pada pojok kanan untuk file upload.php_server-app dan upload webshell dengan nama idzoyyshell.php.
  4. Jalankan command whoami sebagai command pertama.
  5. Cari paket yang berisi echo dan decode string berikut:
```
cGxzIHJhdGUgc29hbCBpbmkK
```
  6. Hasil decoding: "pls rate soal ini".
  7. Flag ditemukan

### Gajah Terbang (Server Record)

  Langkah Penyelesaian:
  1. Gunakan filter tcp.port == 5432 untuk PostgreSQL dan tcp.port == 6969 untuk mengecek port lain.
  2. Temukan Debian pada salah satu file melalui filter tcp.options -> tcp.stream eq 9.
  3. Pada file yang sama, di pojok kiri atas, temukan credentials untuk user s1gm4 dan nama database sigmaskibidigyatrizzzz.
  4. Lakukan penghitungan manual jumlah pengguna dalam database, ditemukan ada 4 pengguna.
  5. Temukan email admin jojohermawan@gmail.com, dan dekripsi hash password yang menghasilkan admin1234.
  6. Flag ditemukan

### Pegawai Negeri Sebelah

1. Mencari di kolom find packet details "password"
2. Mencari yang memiliki format nama, password, jabatan
  ![image](https://github.com/user-attachments/assets/2b7ce85f-a6d6-4e96-9a3a-02105df6465d)
3. Cari jawaban yang ada di stream tersebut berdasarkan pertanyaan pada terminal
   ![image](https://github.com/user-attachments/assets/d93b4b6a-3f57-497a-98e6-aee098f5f7be)
4. Dan ketemu Flagnya
   ![Screenshot (145)](https://github.com/user-attachments/assets/70769ff5-c9a7-4dc1-bda2-7b92d9b654ef)

### EZ

1. Mencari dengan scrolling dan menemukan file yang berisi jawaban dari pertanyaan nc nya
   ![image](https://github.com/user-attachments/assets/89bf524c-52ed-47b5-9945-30cc461362b8)
2. Melihat port berapa yang digunakan oleh stream tersebut
   ![image](https://github.com/user-attachments/assets/9e3ed6a8-821b-41fa-80df-bf11652934ec)
3. Setelah selesai menjawab pertanyaan nc, maka ketemu Flagnya
   ![Screenshot (146)](https://github.com/user-attachments/assets/93664775-dec1-4db6-a97b-35efd85a8a68)

### FTP Login

1. Mencari strem yang Login Successful, karena pertanyannya yang berhasil login
   ![Screenshot (161)](https://github.com/user-attachments/assets/a387bae2-ed99-43c9-8780-18fa03522a3c)
2. Setelah menjawab semua maka ketemu Flagnya
   ![Screenshot (156)](https://github.com/user-attachments/assets/31c77d30-d760-482c-beaa-1e17f8ed1344)

    ![Screenshot 2024-09-18 221534](https://github.com/user-attachments/assets/f35700f4-f506-4570-b2f4-49be94970c1c)

### Packet Barrage

1. Dari data pada soal illegal, stream yang dipilih menggunakan IP 172.21.80.1 dan 172.21.88.207. Lalu saya mencoba memasukkan  dan ternyata benar
   ![image](https://github.com/user-attachments/assets/2240c06b-c345-48b5-832e-19a72b1963e2)
2. Lalu saya mencoba memasukkan angka 1917 sebagai port untuk menjawab dikarenakan mencoba angka-angka yang ada pada stream
3. Untuk nama file dan isi file yang disisipkan attacker, saya melihat dalam isi stream tersebut
   ![Screenshot (163)](https://github.com/user-attachments/assets/c6ec9b41-992e-42b2-a26f-e8d327949cea)
4. Dan ketemulah Flagnya
   ![image](https://github.com/user-attachments/assets/7d43236d-552e-4f7d-aefe-fd80f4d8cc3d)

### Surprise

1. Mencari stream yang login succesfull pada file ftp login
   ![image](https://github.com/user-attachments/assets/0251fcb1-c7da-49b6-a3b2-5ab525f49a22)
2. Lalu menjawab dengan jenis FTP yang digunakan dalam file stream tersebut
   ![image](https://github.com/user-attachments/assets/9e3d754a-6d36-407b-83ec-0520d21e5507)
3. Dilanjutkan menjawab nama file extension yang ada di dalam dile streamnya
   ![image](https://github.com/user-attachments/assets/6e0f48ed-95a2-48ea-bf77-2d670ada481a)
4. Lalu file di compile dan ketemulah Flagnya
   ![Screenshot (160)](https://github.com/user-attachments/assets/fe857501-d662-4cf9-a5f5-478930e12b5c)

    ![image](https://github.com/user-attachments/assets/060921d8-60be-4e96-acc9-1c8cdb73d567)

### Malicious

1. Mencari dengan format http.request.method == "GET" dikarenakan get menunjukkan berapa kali attacker mencoba untuk mendapatkan informasi dari server dan mendapatkan strem ini
   ![Screenshot (169)](https://github.com/user-attachments/assets/31aa19df-95d3-4a35-a45b-a12e8a4bf634)

   ![Screenshot (170)](https://github.com/user-attachments/assets/d224a6dc-fb2d-4c3a-a6e3-5d4b07f7af49)
3. Untuk endpointnya saya melihat pada info stream yang menunjukkan /index.php
   ![image](https://github.com/user-attachments/assets/27cd5182-411e-48db-a962-630c7aaa017c)
4. Saya menemukan bahwa stream ini menunjukkan bahwa attacker berhasil masuk sehingga saya mencoba memasukkan length dengan angka 153 dan ternyata berhasil
   ![image](https://github.com/user-attachments/assets/4ec98380-4837-4a50-bcf7-25cff5d23017)

   ![image](https://github.com/user-attachments/assets/ea10d2ac-6538-406f-bbaa-be5710ae6e37)
5. Pada stream selanjutnya ditemukan bahwa ada indikasi yang menunjukkan bahwa isi stream tersebut mengandung jawaban dari pertanyaan tersebut. Dan isi stream tersebut harus diubah dahulu karena masih berbentuk kode ASCII
   ![image](https://github.com/user-attachments/assets/014cf942-1f19-42ff-9a93-93ac89ae5a64)
6. Setelah menjawab maka ketemulah Flagnya
   ![image](https://github.com/user-attachments/assets/b84c3afc-2ef5-4c76-ae99-146b109481ff)





