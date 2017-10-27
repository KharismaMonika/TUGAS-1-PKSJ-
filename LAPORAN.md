# LAPORAN TUGAS 1
 OLEH 
- 5114100092    KHARISMA MONIKA
- 5114100131    Michael Dave
- 5114100081    M. Luqmanul Hakim

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

* ### VIRTUAL BOX

Oracle VM VirtualBox adalah perangkat lunak virtualisasi, yang dapat digunakan untuk mengeksekusi sistem operasi “tambahan” di dalam sistem operasi “utama”. Sebagai contoh, jika seseorang mempunyai sistem operasi MS Windows yang terpasang di komputernya, maka seseorang tersebut dapat pula menjalankan sistem operasi lain yang diinginkan di dalam sistem operasi MS Windows tersebut. Fungsi ini sangat penting jika seseorang ingin melakukan ujicoba dan simulasi instalasi suatu sistem tanpa harus kehilangan sistem yang ada. Aplikasi dengan fungsi sejenis VirtualBox lainnya adalah VMware dan Microsoft Virtual PC. Sistem operasi yang dapat menjalankannya antara lain Linux, Mac OS X, Windows XP, Windows Vista, Windows 7, Windows 8, Solaris, dan OpenSolaris

* ### SERVER
Pengertian server adalah sebuah sistem komputer yang menyediakan jenis layanan tertentu dalam sebuah jaringan komputer. Terkadang istilah server disebut sebagai web server. Namun umumnya orang lebih suka menyebutnya sebagai ‘server’ saja. Sebuah server didukung dengan prosesor yang bersifat scalable dan RAM yang besar, juga dilengkapi dengan sistem operasi khusus. Sistem operasi ini berbeda dengan sistem operasi yang biasanya. Jika kita biasa menggunakan sistem operasi windows, MacOS dll, maka sistem operasi dari server ini mungkin berbeda. Sistem Operasi dari server adalah sistem operasi jaringan atau network operating system. Server juga bertugas untuk menjalankan software administratif. Yakni software yang mengontrol akses terhadap jaringan dan sumber daya yang terdapat di dalamnya. Hal ini termasuk file atau alat pencetak (printer), dan memberikan akses kepada workstation anggota jaringan. Di dalam sistem operasi server, umumnya terdapat berbagai macam service yang menggunakan arsitektur klien/server. Contoh dari service yang diberikan oleh server ini antara lain Mail Server, DHCP Server, HTTP Server, DNS Server , FTP Server dan lain lain.

* ### UBUNTU SERVER

Ubuntu server adalah ubuntu yang didesain untuk di install di server. Perbedaan mendasar, di Ubuntu Server tidak tersedia GUI. Jika anda menggunakan ubuntu server artinya anda harus bekerja dengan perintah perintah di layar hitam yang sering disebut konsole. Jika anda datang dari windows, maka tampilan ubuntu server seperti DOS. Bagi orang awam pemakai desktop, jelas tidak ada manfaatnya, tapi bagi admin jaringan, warnet, kantor, server dan perusahaan webhosting, ubuntu server merupakan solusi mudah dan free untuk membangun layanan seperti file sharing , printer sharing atau webhosting. 

Ubuntu server walaupun hanya menggunakan CLI (Coomand line interface) tidaklah sesusah yang dikira karena sudah banyak tutorial dan help bawaan dari perintah itu sendiri. Yang dibutuhkan adalah kemauan membaca manual dan belajar bahasa inggris.

* ### UBUNTU DEKSTOP
ubuntu dekstop adalah sistem operasi ubuntu dengan GUI (Graphic User Interface)

* ### KALI LINUX
Kali Linux adalah keluarga sistem Debian yang didesign untuk digital forensik dan testing penetrasi sistem. Banyak dari package pada Kali Linux dikembangkan dari repositori Debian. Kali Linux juga memiliki project untuk dikembangkan pada perangkat Android bernama Kali Linux NetHunter. 

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

* ### MEDUSA

Medusa juga merupakan password cracking alat yang mirip dengan THC Hydra. Ini klaim menjadi alat paralel cepat, modular dan masuk kasar memaksa. Mendukung HTTP, FTP, CVS, AFP, IMAP, MS SQL, MYSQL, NCP, NNTP, POP3, PostgreSQL, pcAnywhere, rlogin, SMB, rsh, SMTP, SNMP, SSH, SVN, VNC, VmAuthd dan Telnet. Sementara retak password, tuan rumah, username dan password dapat menjadi masukan yang fleksibel saat melakukan serangan.

Medusa adalah alat baris perintah, sehingga Anda perlu belajar perintah sebelum menggunakan alat. Efisiensi alat tergantung pada konektivitas jaringan. Pada sistem lokal, dapat menguji 2000 password per menit.

Dengan alat ini, Anda juga dapat melakukan serangan paralel. Misalkan Anda ingin memecahkan password dari account email beberapa secara bersamaan. Anda dapat menentukan daftar nama bersama dengan daftar password.

* ### FAIL2BAN

Fail2Ban adalah kerangka kerja perangkat lunak pencegahan intrusi yang melindungi server komputer dari serangan brute force. Ditulis dalam bahasa pemrograman Python, ia dapat berjalan pada sistem POSIX yang memiliki antarmuka ke sistem kontrol paket atau firewall yang terpasang secara lokal, misalnya iptables atau TCP Wrapper.

___

## IMPLEMENTASI
* ### INTALASI UBUNTU SERVER

 1.	Download Ubuntu Server pada https://www.ubuntu.com/download/server/thank-you?country=ID&version=16.04.3&architecture=amd64
 2. Buka VirtualBox
 3.	Klik New kemudian isikan nama, type, versi
 4.	Atur Ram . Sesuaikan pengaturan ram dengan spesifikasi hardware yang kita pakai, semakin besar ram yang kita alokasikan untuk virtual ubuntu server ini maka akan semakin cepat pula proses instalasi dan kinerjanya. Namun yang harus diingat adalah tidak boleh menghabiskan resource ram yang kita miliki. Semisal ram pada pc kita 6 gb kita bisa mengalokasikan 2 gb untuk virtual ubuntu server ini
 5.	Selanjutnya mensetting DISK DRIVE sebagai penyimpanan file system virtualisasi Ubuntu server. Pilih create a virtual hard disk now untuk membuat virtual penyimpanan
 6.	di bagian Storage on physical hard disk pilh Dynamically Allocated. Karena dengan begitu kita dapat lebih fleksibel dalam menggunakan virtual ruang penyimpanan
 7.	Mengatur tempat penyimpanan virtual ubuntu server dan kapasitas penyimpanan
 8.	Jalankan konfigurasi VirtualBox yang sebelumnya sudah di buat , kemudian masukan image iso ubuntu server 
 9.	Setelah image iso sudah di masukan kemudian klik start untuk memulai proses instalasi
 10.	Memilih bahasa
 11.	Klik install ubuntu server
 12.	Memilih bahasa yang gunakan saat proses intallasi
 13.	memilih lokasi, ini bertujuan untuk menentukan waktu pada ubuntu server
 14.	pilih benua atau wilayah asia karna Indonesia berada di asia tenggara
 15.	Pilih negara indonesia
 16.	Pilih United states
 17.	Deteksi keyboard yang kita gunakan, pilih no karna nantinya kita akan memasukan type keyboard secara manual
 18.	Pilih English (US). ini adalah keyboard yang umum digunakan oleh semua orang.
 19.	Pilih kembali English (us)
 20.	Masukan Hostname untuk system, masukan hostname tanpa spasi kemudian klik Continue
 21.	Masukan nama untuk user baru
 22.	Masukan username untuk user baru
 23.	Masukan password untuk user baru
 24.	Masukan ulang password untuk akun baru
 25.	Enkripsi directory home | system akan mengekripsi home jika kondisi anda belum masuk ke dalam system dan akan membuka enkripsi jika kita sudah masuk ke dalam system. Pilih no
 26.	Konfigurasi waktu | jika terdapat informasi pada layar yang menampilkan bahwa zona waktu anda adalah asia/Jakarta maka sudah benar. Kemudian pilih yes
 27.	Melakukan pertisi hardisk
 28.	Memilih disk yang akan di partisi
 29.	Klik yes
 30.	Masukan ukuran disk yang akan di gunakan untuk menginstall ubuntu server
 31.	Jika sudah selesai mengatur partisi disk, selanjutnya akan terdapat informasi pertisi yang sudah kita buat dan kemudian jika sudah yakin dengan partisi tersebut dan disk akan di format maka klik yes
 32.	Mengatur pembaruan pada system ubuntu server pilih no automatic update
 33.	Memilih software yang akan di pasang pada ubuntu server
 34.	Install GRUB boot | Klik yes
 35.	Jika instalasi telah selesai klik continue dan Virtualbox akan terestar kemudian coba login ke dalam sistem
 36.	Masukan username dan password yang sebelumnya telah di buat saat proses instalasi

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
 20.	Pada tampilan terlihat alokasi hardisk yang tersedia, yaitu 8.5GB. klik pada baris tersebut lalu klik tombol “+” untuk membuat partisi baru.
 21.	Berikut kita membuat partisi untuk swap, dengan alokasi 1GB. Klik “OK” untuk melanjutkan.
 22.	Partisi swap berhasil dibuat, klik “free space” lagi dan klik tombol “+” untuk membuat partisi baru lagi.
 23.	Selanjutnya kita membuat partisi dengan format Ext4 yang akan digunakan sebagai root folder “/” sebesar 7.5GB. Root folder “/” akan berisikan filesystem dan direktori home. Klik “OK” untuk lanjut.
 24.	Hasil akhir partisi akan sebagai berikut.
 25.	Anda juga dapat memisahkan direktori home anda dengan partisi lain dari root folder.
 26.	Ketika akan menyimpan perubahan partisi. klik “Continue” untuk lanjut.
 27.	Pilih zona waktu yang anda inginkan dengan klik pada peta, lalu klik “Continue”.
 28.	Pilih layout keyboard yang sesuai dengan keyboard anda, lalu klik “Continue”.
 29.	Isikan detail user yang akan digunakan pertama kali, lalu klik “Continue”.
 30.	Silakan tunggu sampai proses instalasi selesai.

* ### INSTALASI KALI LINUX
 1.	Download Kali Linux pada https://www.kali.org/downloads
 2.	Buat Virtual Machine yang baru, Isikan Nama virtual machine, type : Linux, Version : Debian 64/32-bit, isikan jumlah alokasi memory pada contoh ini sebesar 1 GB / 1024 MB
 3.	Membuat virtual hard disk
 4.	Memilih tipe file hard disk. Ada banyak tipe Harddisk virtual, disini kita menggunakan VDI yaitu tipe standard yang digunakan VirtualBox,
 5.	Tentukan kapasitas harddisk minimum untuk kali Linux 20GB
 6.	Dynamically Allocated, hanya menggunakan alokasi harddisk yang terpakai. Sedangkan Fixed size akan mengalokasikan harddisk sesuai yang anda buat. Misalkan anda membuat harddisk dengan kapasitas 50GB, sedangkan yang terpakai hanya 20GB. Pada dynamic, harddisk real anda akan berkurang kapasitasnya 50GB, sedangkan pada Fixed, akan berkurang 20GB.
 7.	Pilih create dan Virtual Machine list anda bertambah
 8.	Jalankan VM dan untuk proses pertama anda diminta memasukan file .iso yang sudah didownload
 9.	Tunggu hingga muncul pilihan instalasi
10.	Pilih Graphical Instal
11.	Pilih Bahasa
12.	Pilih Lokasi
13.	Pilih Kombinasi Lokasi dan Bahasa
14.	Pilih Type Keyboard
15.	Buat nama server (kosongi jika tidak ada)
16.	Buat nama hostname
17.	Buat nama domain
18.	Buat password untuk 'root' system
19.	Pilih pembagian waktu, lalu continue
20.	Pilih Guided-use entire disk and set up LVM
21.	Pilih disk yang akan dipartisi
22. Pilih All files in one partition (recommended), lalu continue
23. Pilih Yes lalu continue
24. Pilih finish lalu continue
25. Pilih Yes lalu continue, tunggu hingga proses selesai. Setelah selesai pilih mirror network, lalu jika tidak menggunakan proxy, kosongkan kolom proxy, tekan continue
26. Jika mirror network gagal, tidak perlu menggunakan mirror network, pilih yes, lalu continue
27. Tunggu hingga proses selesai, dan muncul dialog instalasi GRUB, pilih yes lalu continue
28. Pilih device, lalu continue, tunggu hingga proses selesai
29. Pilih continue, instalasi telah selesai

* ### INSTALASI SSH SERVER
Pada ubuntu server : 
 1. Ketikkan " sudo apt-get install openssh-server "
 
  ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/install%20open%20ssh.PNG "Instalasi SSH Server")
 

 2. Masukkan password
 
* ### INSTALASI HYDRA
Pada Ubuntu desktop :
 1. sudo apt-get install hydra-gtk
 
  ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/d662e77a60e4e042de428c2b23b7696d6b7aa5e1/SCREENSHOOT/install%20hydra%20gtk.PNG "Instalasi Hydra")
  
 2. Masukkan password

Pada Kali Linux Hydra sudah terinstall

* ### INSTALASI NCRACK
Pada Ubuntu desktop :
 1. wget https://nmap.org/ncrack/dist/ncrack-0.5.tar.gz
 2. tar -xvzf ncrack-0.5.tar.gz
 3. cd ncrack-0.5
 4. /configure
 5. make
 6. make install
 
 Pada Kali Linux Ncrack sudah terinstall

* ### MEMBUAT DAN DOWNLOAD DICTIONARY PASSWORD
 1. Dictionary 1: membuat sendiri file txt berisi 5 list password
 2. Dictionary 2 : download list password berisi 100 list password
Dalam hal ini sengaja digunakan list password yang sedikit karena untuk mempersingkat waktu penetrasi.

* ### INSTALASI FAIL2 BAND
 1. Ketikkan perintah pada terminal "sudo apt-get update"
 2. Ketikkan perintah untuk download "sudo apt-get install fail2ban"

* ### MENGANTI KONFIGURASI PADA SSH
 1. Mengganti port
 2. Mengubah bandtime
 
___

## HASIL UJI COBA
* ### Uji Penetrasi 1 : menggunakan hydra + username: risma + dictionary 1 + tanpa fail2ban
 1. Memasukkan IP Target pada hydra
 
  ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji%20penetrasi1_1.PNG "IP Target")
 
 2. Memasukkan Username = risma,  Password Dictionary 1
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi1_2.PNG "Dictionary 1")
 
 3. Output penetrasi 1 pada hydra. Sukses Mendapatkan Password
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi1_3.PNG "Success")
 
 4. Output pada server, menunjukkan terdapat IP yang mencoba masuk ke dalam sistem.
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi1_4%20ketika%20dilihat%20dr%20sisi%20server.PNG "Server")
 
* ### Uji Penetrasi 2 : menggunakan hydra + username: risma +  dictionary 2 + tanpa fail2ban

 1. Penetrasi menggunakan dictionary 2
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi2_1%20dict.PNG "Dictionary 2")
 
 2. Output pada hydra
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi2_2%20output%20hydra.PNG "Uji 2 sukses")
 
 3. Output pada server
 
  ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi2_3%20tampilan%20di%20server.PNG "Uji 2 Server") 
 
* ### Uji Penetrasi 3 : menggunakan ncrack + username: michael2 + dictionary 1 + tanpa fail2ban
1. Hasil uji coba :

![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi3_1.png "Uji Coba 3") 

* ### Uji Penetrasi 4 : menggunakan ncrack + username: michael2 + dictionary 2 + tanpa fail2ban
 1. Hasil Uji Coba :
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi4_1.png "Uji Coba 4")
 
* ### Uji Penetrasi 5 : menggunakan hydra + username: michael2 +  dictionary 1 + dengan fail2ban setting default
 1. Hasil Uji coba, koneksi ditolak, sehingga SSH gagal
 ![alt text](https://github.com/KharismaMonika/TUGAS-1 PKSJ-/blob/5800e1e26901235c3a30c1bf527e22efa44c297f/SCREENSHOOT/uji_penetrasi5_1.png "Uji Coba 5")
 
 2. Ketika dicek pada server, ternyata IP kena firewall dengan iptables yang dibuat oleh fail2ban
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/5800e1e26901235c3a30c1bf527e22efa44c297f/SCREENSHOOT/uji_penetrasi5_2.png "iptables")
 
* ### Uji Penetrasi 6 : menggunakan hydra + username: michael2 +  dictionary 2 + dengan fail2ban setting default

 1. Hasil Uji Coba:SSH gagal karena terkena firewall fail2ban
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/5800e1e26901235c3a30c1bf527e22efa44c297f/SCREENSHOOT/uji_penetrasi6_1.png "Uji 6")

* ### Uji Penetrasi 7 : menggunakan ncrack + username: michael2 +  dictionary 1 + dengan fail2ban setting default
 1. Hasil Uji Coba : tidak mendapatkan password dengan mencoba dalam 6 detik
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi7_1.png "Uji Coba 7")
 
* ### Uji Penetrasi 8 : menggunakan ncrack + username: michael2 +  dictionary 2 + dengan fail2ban setting default

 1. Hasil Uji Coba : tidak mendapatkan password dengan mencoba dalam 6 detik
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi8_1.png "Uji Coba 8")
 
* ### Uji Penetrasi 9 : menggunakan medusa + dictionary 1 + tanpa fail2ban

 1. Hasil Uji Coba : mendapatkan password pada percobaan ke 10
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi9_1.png "Uji Coba 9a")
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi9_2.png "Uji Coba 9b")

* ### Uji Penetrasi 10 : menggunakan medusa + dictionary 2 + tanpa fail2ban

 1. Hasil Uji Coba : mendapatkan password pada percobaan ke 100
 
 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi10_1.png "Uji Coba 10")

* ### Uji Penetrasi 11 : menggunakan medusa + dictionary 1 + dengan fail2ban setting default

 1. Hasil Uji Coba : tidak mendapatkan password karena koneksi ditolak

 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi11_1.png "Uji Coba 11")

* ### Uji Penetrasi 12 : menggunakan medusa + dictionary 2 + dengan fail2ban setting default

 1. Hasil Uji Coba : tidak mendapatkan password karena koneksi ditolak

 ![alt text]( https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi12_1.png "Uji Coba 12")

* ### Uji Penetrasi 13 : dictionary 2 + dengan fail2ban setting port diganti dengan port 222
uji coba dilakukan dengan menggunakan ncrack dan mengganti port SSH menjadi 222
 1.  Hasil Uji Coba:
 Uji coba menunjukkan bahwa password berhasil didapatkan, karena fail2ban hanya melindungi port 22,
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi7_2.png "Uji Coba 13")
 
 2. Ketika mencoba kembali menggunakan port 22
 
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/uji_penetrasi7_3.png "Uji Coba 13")
 
* ### Uji Penetrasi 14 : dictionary 2 + dengan fail2ban setting baned time

 1. Bantime pada fail2ban diubah menjadi 60
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/bantime_60.png "Uji Coba 14")

 2. Hasilnya adalah waktu pencarian yang meningkat
 ![alt text](https://github.com/KharismaMonika/TUGAS-1-PKSJ-/blob/master/SCREENSHOOT/hasil_bantime_60.png "Uji Coba 14")

___

## PENUTUP
* ### KESIMPULAN
 1. Untuk mengamankan SSH dapat menggunakan Fail2ban dengan settingan default tetapi tidak menutup kemungkinan user password tetap dapat ditemukan
 2. Untuk lebih aman dapat mengganti port, settingan default menggunakan port 22 yang telah umum diketahui. Namun port yang terbuka dapat diketahui oleh attacker dengan nmap
 3. Dapat menambah waktu baned (bantime) atau mengecilkan max retries pada settingan fail2ban sehingga menambah waktu yang dibutuhkan attacker untuk melakukan pencarian password

 
* ### SARAN
 1. Dilakukan konfigurasi advance pada fail2ban agar ssh lebih aman, dengan setting action pembentukan iptables
 2. Mengubah keamanan ssh dengan tidak menggunakan password untuk autentikasi tetapi  menggunakan key based authentication (RSAKey)
 3. Buat sebuah kombinasi password yang unik sehingga tidak mudah dilakukan brute force attack

