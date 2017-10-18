# LAPORAN TUGAS 1
 OLEH 
- 5114100092    KHARISMA MONIKA
- 5114100131    Michael Dave

___

## PENDAHULUAN
### LATAR BELAKANG
Sebuah sistem pasti memiliki aturan untuk memasuki sistem. Salah satu aturan adalah menggunakan autentikasi. Autentikasi yang digunakan biasanya menggunakan username dan password. Namun menggunakan authentikasi belum dapat mengamankan sebuah sistem. Sistem dapat diserang dengan menggunakan percobaan memasukkan password yang mungkin. Salah satu algoritma untuk membobol password sistem adalah dengan menggunakan brute force attack. Tools yang dapat digunakan untuk melakukan brute force attack adalah Hydra dan Ncrack.

Namun permasalahan tersebut dapat diatasi dengan mengamankan sistem. Salah satu tools yang dapat digunakan adalah Fail2ban. Fail2ban dapat mengamankan sistem dengan cara memblock IP yang mencoba untuk masuk berkali-kali. 

Dalam uji coba ini, dilakukan penetrasi menggunakan bruteforce attack menggunakan dictionary dan melakukan pencegahan dengan menggunakan fail2ban.

### TUJUAN
 1 Melakukan implementasi SSH Brute Force Attack pada server.
 
 2 Melakukan implementasi Fail2ban untuk mengamankan server.
### MANFAAT
* Menerapkan ilmu pengetahuan yang dipelajari mengenai keamanan server.

___

## DASAR TEORI
* ### PENETRASI

Testing Penetrasi merupakan metode yang digunakan untuk mengevaluasi keamanan sistem atau jaringan komputer dengan melakukan sebuah simulasi penyerangan. Penetration testing merupakan seni dari pengujian sistem aplikasi web yang sedang berjalan, tanpa mengetahui apa yang dikerjakan di dalam (inner workings) aplikasi web itu sendiri. Seorang penguji berperan sebagai penyerang (attacker) dan berusaha untuk menemukan dan mengeksploitasi bagian dari aplikasi web yang memiliki sifat mudah diserang (vulnerabilities).

* ### SERVER
Pengertian server adalah sebuah sistem komputer yang menyediakan jenis layanan tertentu dalam sebuah jaringan komputer. Terkadang istilah server disebut sebagai web server. Namun umumnya orang lebih suka menyebutnya sebagai ‘server’ saja. Sebuah server didukung dengan prosesor yang bersifat scalable dan RAM yang besar, juga dilengkapi dengan sistem operasi khusus. Sistem operasi ini berbeda dengan sistem operasi yang biasanya. Jika kita biasa menggunakan sistem operasi windows, MacOS dll, maka sistem operasi dari server ini mungkin berbeda. Sistem Operasi dari server adalah sistem operasi jaringan atau network operating system. Server juga bertugas untuk menjalankan software administratif. Yakni software yang mengontrol akses terhadap jaringan dan sumber daya yang terdapat di dalamnya. Hal ini termasuk file atau alat pencetak (printer), dan memberikan akses kepada workstation anggota jaringan. Di dalam sistem operasi server, umumnya terdapat berbagai macam service yang menggunakan arsitektur klien/server. Contoh dari service yang diberikan oleh server ini antara lain Mail Server, DHCP Server, HTTP Server, DNS Server , FTP Server dan lain lain.

* ### UBUNTU SERVER

Ubuntu server adalah ubuntu yang didesain untuk di install di server. Perbedaan mendasar, di Ubuntu Server tidak tersedia GUI. Jika anda menggunakan ubuntu server artinya anda harus bekerja dengan perintah perintah di layar hitam yang sering disebut konsole. Jika anda datang dari windows, maka tampilan ubuntu server seperti DOS. Bagi orang awam pemakai desktop, jelas tidak ada manfaatnya, tapi bagi admin jaringan, warnet, kantor, server dan perusahaan webhosting, ubuntu server merupakan solusi mudah dan free untuk membangun layanan seperti file sharing , printer sharing atau webhosting. 

Ubuntu server walaupun hanya menggunakan CLI (Coomand line interface) tidaklah sesusah yang dikira karena sudah banyak tutorial dan help bawaan dari perintah itu sendiri. Yang dibutuhkan adalah kemauan membaca manual dan belajar bahasa inggris.

* ### UBUNTU DEKSTOP


* ### SSH SERVER

SSH merupakan singkatan dari Secure Shell yang merupakan suatu aplikasi pengganti remote login,tak jauh berbeda dengan Rsh dan rlogin, dan merupakan suatu protocol jaringan,dengan adanya SSh ini kita dapat menukarkan data melalui saluran yang aman antara dua perangkat jaringan,protocol jaringan ini sering digunakan pada SO Linux dan Protokol yang diciptakan oleh Tatu Ylönen, seorang peneliti di Helsinki University of Technology, Finlandia  dirancang sebagai pengganti Telnet dan shell remote tak aman lainnya, yang mengirim informasi, terutama kata sandi, dalam bentuk teks sederhana yang membuatnya mudah untuk dicegat. Enkripsi yang digunakan oleh SSH menyediakan kerahasiaan dan integritas data melalui jaringan yang tidak aman seperti Internet.

Cara Kerja SSH Server Pada saat suatu client mencoba mengakses suatu linux server melalui SSH. SH daemon yang berjalan baik pada linux server maupun SSH client telah mempunyai pasangan public/private key yang masing-masing menjadi identitas SSH bagi keduanya.   

Berikut Tahapan-tahapannya / Proses Kerja SSH  : 
 1.	Client bind pada local port nomor besar dan melakukan koneksi ke port 22 pada server.
 
 2.	Client dan server setuju untuk menggunakan sesi SSH tertentu. Hal ini penting karena SSH v.1 dan v.2 tidak kompatibel. 

 3.	Client meminta public key dan host key milik server. 
 
 4.	Client dan server menyetujui algoritma enkripsi yang akan dipakai (misalnya TripleDES atau IDEA). 
 
 5.	Client membentuk suatu session key yang didapat dari client dan mengenkripsinya menggunakan public key milik server. 
 
 6.	Server men-decrypt session ky yang didapat dari client, meng-re-encrypt-nya dengan public key milik client, dan mengirimkannya kembali ke client untuk verifikasi.
 
 7.	Pemakai mengotentikasi dirinya ke server di dalam aliran data terenkripsi dalam session key tersebut. Sampai disini koneksi telah terbentuk, dan client dapat selanjutnya bekerja secara interaktif pada server atau mentransfer file ke atau dari server.

* ### BRUTE FORCE ATTACK

Menurut Wikipedia Serangan brutal (bahasa Inggris: Brute-force attack) adalah sebuah teknik serangan terhadap sebuah sistem keamanan komputer yang menggunakan percobaan terhadap semua kunci yang mungkin. Pendekatan ini pada awalnya merujuk pada sebuah program komputer yang mengandalkan kekuatan pemrosesan komputer dibandingkan kecerdasan manusia. Sebagai contoh, untuk menyelesaikan sebuah persamaan kuadrat seperti x²+7x-44=0, di mana x adalah sebuah integer, dengan menggunakan teknik serangan brute-force, penggunanya hanya dituntut untuk membuat program yang mencoba semua nilai integer yang mungkin untuk persamaan tersebut hingga nilai x sebagai jawabannya muncul. Istilah brute force sendiri dipopulerkan oleh Kenneth Thompson, dengan mottonya: "When in doubt, use bruteforce" (jika ragu, gunakan brute-force). 

Teknik yang paling banyak digunakan untuk memecahkan password, kunci, kode atau kombinasi. Cara kerja metode ini sangat sederhana yaitu mencoba semua kombinasi yang mungkin.
Sebuah password dapat dibongkar dengan menggunakan program yang disebut sebagai password cracker. Program password cracker adalah program yang mencoba membuka sebuah password yang telah terenkripsi dengan menggunakan sebuah algoritma tertentu dengan cara mencoba semua kemungkinan. Teknik ini sangatlah sederhana, tapi efektivitasnya luar biasa, dan tidak ada satu pun sistem yang aman dari serangan ini, meski teknik ini memakan waktu yang sangat lama, khususnya untuk password yang rumit.

Namun ini tidak berarti bahwa password cracker membutuhkan decrypt. Pada prakteknya, mereka kebayakan tidak melakukan itu. Umumnya, kita tidak dapat melakukan decrypt password-password yang sudah terenkripsi dengan algoritma yang kuat. Proses-proses enkripsi modern kebanyakan hanya memberikan satu jalan, di mana tidak ada proses pengembalian enkripsi. Namun, anda menggunakan tool-tool simulasi yang mempekerjakan algoritma yang sama yang digunakan untuk mengenkripsi password orisinal. Tool-tool tersebut membentuk analisis komparatif. Program password cracker tidak lain adalah mesin-mesin ulet. Ia akan mencoba kata demi kata dalam kecepatan tinggi. Mereka menganut "Azaz Keberuntungan", dengan harapan bahwa pada kesempatan tertentu mereka akan menemukan kata atau kalimat yang cocok. Teori ini mungkin tepat mengena pada anda yang terbiasa membuat password asal-asalan. Dan memang pada kenyataannya, password-password yang baik sulit untuk ditembus oleh program password cracker

* ### THC-HYDRA

Sebuah tools crack yang semakin unggul dalam hal exploit dan THC-Hydra salah satu yang sangat cepat meretas jaringan logon cracker yang mendukung banyak layanan yang berbeda. Lihat fitur dan layanan cakupan halaman - termasuk. perbandingan kecepatan terhadap ncrack dan medusa.

THC Hydra adalah jaringan logon alat password cracking cepat. Bila dibandingkan dengan alat sejenis lainnya, hal itu menunjukkan mengapa ia lebih cepat. Modul baru yang mudah untuk menginstal dalam perangkat. Anda dapat dengan mudah menambahkan modul dan meningkatkan fitur. Ini tersedia untuk Windows, Linux, Free BSD, Solaris dan OS X. Alat ini mendukung berbagai protokol jaringan. Saat ini mendukung Asterisk, AFP, Cisco AAA, Cisco auth, Cisco memungkinkan, CVS, Firebird, FTP, HTTP-FORMULIR-GET, HTTP-FORMULIR-POST, HTTP GET-, HTTP-HEAD, HTTP-proxy, HTTPS-form- GET, HTTPS-FORMULIR-POST, HTTPS-GET, HTTPS-HEAD, HTTP-Proxy, ICQ, IMAP, IRC, LDAP, MS-SQL, MYSQL, NCP, NNTP, Oracle Listener, Oracle SID, Oracle, PC-mana saja, PCNFS, POP3, POSTGRES, RDP, rexec, rlogin, rsh, SAP / R3, SIP, SMB, SMTP, SMTP Enum, SNMP, Socks5, SSH (v1 dan v2), Subversion, TeamSpeak (TS2), Telnet, VMware-Tupoksi , VNC dan XMPP.

* ### NCRACK

Ncrack adalah alat cracking otentikasi jaringan berkecepatan tinggi. Ini dibangun untuk membantu perusahaan mengamankan jaringan mereka dengan secara proaktif menguji semua host dan perangkat jaringan mereka dengan kata kunci yang buruk. Profesional keamanan juga mengandalkan Ncrack saat mengaudit klien mereka. Ncrack dirancang menggunakan pendekatan modular, sintaks baris perintah yang mirip dengan Nmap dan mesin dinamis yang dapat menyesuaikan perilakunya berdasarkan umpan balik jaringan. Ini memungkinkan dilakukannya audit berskala besar yang cepat namun dapat diandalkan dari beberapa host.

Fitur Ncrack mencakup antarmuka yang sangat fleksibel yang memberi pengguna kontrol penuh atas operasi jaringan, memungkinkan serangan bruteforcing yang sangat canggih, template waktu untuk kemudahan penggunaan, interaksi runtime yang mirip dengan Nmap dan banyak lagi. Protokol yang didukung meliputi RDP, SSH, HTTP (S), SMB, POP3 (S), VNC, FTP, SIP, Redis, PostgreSQL, MySQL, dan Telnet.

* ### FAIL2BAND

Fail2Ban adalah kerangka kerja perangkat lunak pencegahan intrusi yang melindungi server komputer dari serangan brute force. Ditulis dalam bahasa pemrograman Python, ia dapat berjalan pada sistem POSIX yang memiliki antarmuka ke sistem kontrol paket atau firewall yang terpasang secara lokal, misalnya iptables atau TCP Wrapper.

___

## IMPLEMENTASI
* ### INTALASI UBUNTU SERVER

 1.	Download Ubuntu Server pada https://www.ubuntu.com/download/server/thank-you?country=ID&version=16.04.3&architecture=amd64
 
* ### INSTALASI UBUNTU DEKSTOP
 1.	Download pada https://www.ubuntu.com/download
 2.	Membuat Virtual mesin dengan OS Ubuntu Dekstop 16.04. Mengisi nama virtual machine, type dan versi OS yang akan diinstall.
 3.	Mengatur ukuran memory RAM
 4.	Membuat virtual hard disk
 5.	Memilih tipe file hard disk. Ada banyak tipe Harddisk virtual, disini kita menggunakan VDI yaitu tipe standard yang digunakan VirtualBox,
 6.	Dynamically Allocated, hanya menggunakan alokasi harddisk yang terpakai. Sedangkan Fixed size akan mengalokasikan harddisk sesuai yang anda buat. Misalkan anda membuat harddisk dengan kapasitas 50GB, sedangkan yang terpakai hanya 20GB. Pada dynamic, harddisk real anda akan berkurang kapasitasnya 50GB, sedangkan pada Fixed, akan berkurang 20GB.
 7.	Tentukan nama harddisk virtual anda beserta ukurannya. Untuk Ubuntu saja, 8GB sudah cukup
 8.	Virtual Machine telah dibuat. Tinggal menambahkan file ISO Ubuntu untuk booting pertama kali. Klik Setting dan ikuti langkah selanjutnya.
 9.	Klik Storage.
 10.	Klik tombol CD disebelah Controller IDE.
 11.	Klik Choose disk untuk memilih file ISO Ubuntu.
 12.	Pilih file .iso Ubuntu, lalu klik open.
 13.	Klik OK.
 14.	Klik tombol start untuk booting menggunakan Ubuntu pada Virtual Machine yang telah kita buat.
 15.	Pilih bahasa yang akan digunakan pada Ubuntu.
 16.	Jika anda terhubung ke internet, dan ingin meng-install driver seperti graphic, Wifi, MP3 dan lainnya silakan centang pada pilihan kedua, jida tidak langsung klik “Continue”.
 17.	Memilih “Something else” untuk menentukan partisi dan alokasi sendiri.
 18.	Disini anda dapat melihat daftar harddisk. “/dev/sda” berarti harddisk pertama. Jika menghubungkan PC dengan 2 harddisk, maka akan tampil “dev/sdb”.
 19.	Klik harddisk yang akan di-install Ubuntu, lalu klik “newPartition Table” untuk membuat Partisi. Klik continue ketika muncul pesan konfirmasi untuk membuat partisi baru
 
* ### INSTALASI SSH SERVER
* ### INSTALASI HYDRA
* ### INSTALASI NCRACK
* ### MEMBUAT DAN DOWNLOAD DICTIONARY PASSWORD

___

## HASIL UJI COBA
* ### Uji Penetrasi 1 : menggunakan hydra + username: risma + dictionary 1 + tanpa fail2ban
* ### Uji Penetrasi 2 : menggunakan hydra + username: risma +  dictionary 2 + tanpa fail2ban
* ### Uji Penetrasi 3 : menggunakan ncrack + username: risma + dictionary 1 + tanpa fail2ban
* ### Uji Penetrasi 4 : menggunakan ncrack + username: risma + dictionary 2 + tanpa fail2ban
* ### Uji Penetrasi 5 : menggunakan hydra + username: risma +  dictionary 1 + dengan fail2ban
* ### Uji Penetrasi 6 : menggunakan hydra + username: risma +  dictionary 2 + dengan fail2ban
* ### Uji Penetrasi 7 : menggunakan ncrack + username: risma +  dictionary 1 + dengan fail2ban
* ### Uji Penetrasi 8 : menggunakan ncrack + username: risma +  dictionary 2 + dengan fail2ban

___

## PENUTUP
* ### KESIMPULAN
* ### SARAN

