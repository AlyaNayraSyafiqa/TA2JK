# TA2JK

Link Youtube : https://youtu.be/ZN60YNRQlic

Penjelasan :
Bagian 1: Build the Topology and Initialize Devices
Pada tahap ini, perangkat jaringan berupa PC, Switch, dan Router dihubungkan sesuai topologi. Tujuannya adalah membuat jalur komunikasi fisik antara semua perangkat.
1. Menyambungkan perangkat
PC dihubungkan ke switch melalui port FastEthernet0/6.
Switch dihubungkan ke router melalui port GigabitEthernet0/0/1.
Hal ini memastikan PC dapat mengirim dan menerima data melalui switch dan router.
2. Menyalakan perangkat dan menginisialisasi
Semua perangkat dinyalakan dan di-reset ke konfigurasi default untuk menghindari konflik pengaturan lama.
3. Mengonfigurasi IP pada PC
PC-A: IP 192.168.1.3 /24, Default Gateway 192.168.1.1
PC-B: IP 192.168.0.3 /24, Default Gateway 192.168.0.1
Pada tahap ini, ping antar PC kemungkinan gagal karena router (gateway) belum dikonfigurasi, sehingga paket antar subnet tidak bisa diteruskan.

Bagian 2: Configure Devices and Verify Connectivity
A. Konfigurasi Router
1. Masuk ke router
Administrator masuk ke mode konfigurasi router melalui console agar dapat mengatur pengaturan dasar dan interface.
2. Pengaturan dasar router
Nama router diubah agar mudah dikenali.
DNS lookup dinonaktifkan agar salah ketik perintah tidak diterjemahkan ke nama host.
Password untuk masuk mode privileged dan akses console maupun VTY diatur untuk keamanan.
Semua password dienkripsi agar tidak terlihat sebagai teks biasa.
Banner MOTD ditambahkan untuk memberi peringatan terhadap akses tidak sah.
3. Konfigurasi interface router
Interface pertama dihubungkan ke PC-B dengan alamat IPv4 dan IPv6 sesuai subnet.
Interface kedua dihubungkan ke switch dengan alamat IPv4 dan IPv6 sesuai subnet.
Setiap interface diberi deskripsi agar memudahkan identifikasi perangkat yang terhubung.
Routing IPv6 diaktifkan sehingga paket IPv6 bisa diteruskan antar subnet.
Konfigurasi disimpan agar tetap berlaku setelah router dimatikan atau di-restart.
4. Verifikasi konektivitas
Setelah konfigurasi router selesai, ping dari PC-A ke PC-B dilakukan untuk memastikan paket antar subnet dapat berjalan. Ping berhasil menunjukkan router mampu merutekan paket.

B. Konfigurasi Switch
1. Masuk ke switch
Administrator masuk ke switch melalui console untuk melakukan pengaturan dasar.
2. Pengaturan dasar switch
Nama switch diubah agar mudah dikenali.
DNS lookup dinonaktifkan agar salah ketik perintah tidak diterjemahkan.
3. Konfigurasi VLAN dan IP
VLAN 1 diaktifkan dan diberi alamat IP agar switch dapat diakses dari jaringan.
Default gateway switch diarahkan ke router agar switch dapat mengirim paket ke subnet lain.
4. Simpan konfigurasi
Semua pengaturan disimpan agar tetap berlaku setelah switch dimatikan atau direstart.
5. Verifikasi konektivitas
Ping dari switch ke PC-B dilakukan untuk memastikan VLAN dan gateway berfungsi dengan benar.

Bagian 3: Display Device Information
A. Routing Table pada Router
IPv4 dan IPv6 routing table ditampilkan untuk memeriksa rute yang tersedia.
Kode “C” menunjukkan subnet langsung terhubung ke interface router.
Kode “L” menunjukkan alamat lokal interface router.
Rute yang ditampilkan memastikan router mengetahui subnet mana yang terhubung langsung dan siap merutekan paket antar subnet.

B. Informasi Interface Router
Status interface diperiksa untuk memastikan interface aktif dan protokol link berjalan.
MAC address dan alamat IP setiap interface dicatat sebagai identifikasi unik perangkat.
IPv6 link-local dan global address diperiksa untuk memastikan komunikasi IPv6 dapat berjalan.

C. Ringkasan Interface
Ringkasan interface router dan switch menampilkan status setiap port dan alamat IP yang digunakan.
Interface yang terhubung aktif (up/up), sementara port yang tidak digunakan akan terlihat down.

<img width="571" height="178" alt="image" src="https://github.com/user-attachments/assets/275ac03b-3ed5-49ea-a56c-b8975facc38e" />

Sebelum di konfigurasi
1. Ping dari PC-A ke PC-B, Switch dan Router
   ![Gambar WhatsApp 2025-11-05 pukul 22 34 20_2ee804a0](https://github.com/user-attachments/assets/f80d480c-35cf-4f55-87ec-588257bdc471)
3. Ping dari PC-B ke PC-A, Switch dan Router
   ![Gambar WhatsApp 2025-11-05 pukul 22 35 04_ee8563c1](https://github.com/user-attachments/assets/c576623f-45cf-4c99-8515-c32fdc21e922)
5. Ping dari Switch ke PC-A, PC-B dan Router
   ![Gambar WhatsApp 2025-11-05 pukul 22 37 32_3dcebf10](https://github.com/user-attachments/assets/bcf06ab6-c6c3-4d83-a063-89a1e794e7e1)
6. Ping dari Router ke PC-A, PC-B dan Switch
   ![Gambar WhatsApp 2025-11-05 pukul 22 37 32_c7e120dd](https://github.com/user-attachments/assets/bd837825-cddb-48ab-b4f8-fafb9e347db3)


Sudah dikonfigurasi
1, Ping dari Router ke PC-A, PC-B dan Switch
![Gambar WhatsApp 2025-11-05 pukul 22 31 07_a287381b](https://github.com/user-attachments/assets/015a7184-d3e3-4fad-8587-8e52253fd754)
2. Ping dari PC B Ke PC-A, Router dan Switch
![Gambar WhatsApp 2025-11-05 pukul 22 31 07_1a76f172](https://github.com/user-attachments/assets/79ae12fb-912f-44ce-8004-f83c90e9e664)
3.Ping dari Switch ke PC-A, PC-B dan Router
![Gambar WhatsApp 2025-11-05 pukul 22 32 13_32843e33](https://github.com/user-attachments/assets/d742cd88-d149-42d5-a155-ffaaed8ec2dc)
4. Ping dari PC-A ke  PC-B, Router dan Switch
![Gambar WhatsApp 2025-11-05 pukul 22 30 05_87eb4115](https://github.com/user-attachments/assets/691d0fa0-bdcb-4cbf-9b16-d54def1c9389)
![Gambar WhatsApp 2025-11-05 pukul 22 29 46_a87079bf](https://github.com/user-attachments/assets/d521c455-5119-40ae-aed6-72b26277fd2a)






