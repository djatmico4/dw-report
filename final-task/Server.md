# **SERVER**
## Membuat Server di AWS

1. Login ke AWS lalu browse VPC. <br>
   ![openvpc](assets/images-server/openvpc.png) <br>

2. Buat vpc. Isikan nama dan IPV4 CIDR seperti pada gambar. 10.0.0.0/16 adalah sebagai primary CIDR block pada vpc kita <br>
   ![vpcsettings](assets/images-server/vpcsettings.png) <br>
   ![createvpc](assets/images-server/createvpc.png) <br>

3. Buatlah subnet untuk public dan private. <br>
   ![publicsubnet](assets/images-server/publicsubnet.png) <br>
   ![privatesubnet](assets/images-server/privatesubnet.png) <br>

   - Arahkan subnet associations sesuai dengan route tablesnya. <br>
   ![subnetassociation](assets/images-server/subnetassociation.png) <br>
   ![subnetassociation2](assets/images-server/subnetassociation2.png) <br>

4. Buat internet gateway yang berfungsi untuk menghubungkan VPC ke internet. <br>
   ![igw](assets/images-server/igw.png) <br>

5. Attach igw ke vpc yang sudah dibuat tadi. <br>
   ![attach](assets/images-server/attach.png) <br>

6. Ganti nama default route menjadi “Public Route”. Pada route table, arahkan route target ke internet gateway yang telah kita attach di VPC tadi dengan destinasi 0.0.0.0/0 (All IP). <br>
   ![editroute](assets/images-server/editroute.png) <br>

7. Buat instance untuk nginx. <br>
   ![step1](assets/images-server/step1.png) <br>
   ![step2](assets/images-server/step2.png) <br>
   ![step3](assets/images-server/step3.png) <br>
   ![step4](assets/images-server/step4.png) <br>
   ![step5](assets/images-server/step5.png) <br>
   ![step6](assets/images-server/step6.png) <br>
   ![step7](assets/images-server/step7.png) <br>

8. Membuat elastic IP yang kita nanti attach ke public server/nginx. <br>
   ![elasticip](assets/images-server/elasticip.png) <br>

   - Kita harus stop source/destination check pada instance public server jika kita ingin membuat NAT Instance.
   ![sourcedestination](assets/images-server/sourcedestination.png) <br>

9. Buat private route. Setelah itu pergi ke route tables dan edit Private Route dengan target dari instances public server yang telah dibuat. Hal ini agar private instances bisa mengakses internet lewat NAT instance ini. <br>
    ![editroute2](assets/images-server/editroute2.png) <br>

10. Buatlah private server sebanyak kebutuhan. Di sini saya membuat untuk fe, be, db, ci/cd, monitoring. Atur security group ke all traffic.
11. Login ke nginx. <br>
    ![chmod](assets/images-server/chmod.png) <br>
    ![loginpublicserver](assets/images-server/loginpublicserver.png) <br>

12. Enable fitur ipv4 forwading pada kernel dan gunakan NAT untuk membolehkan private subnet mengakses outside world.
    ![enablefituripv4](assets/images-server/enablefituripv4.png) <br>

13. Agar tidak menggunakan key pair saat login SSH, ubah file sshd_config pada /etc/ssh dengan mengganti Password Authentication menjadi Yes. <br>
    ![configssh](assets/images-server/configssh.png) <br>

14. Tambahkan username baru dan beri akses sudo ke user baru tersebut. Jangan lupa untuk restart SSH. <br>
    ![adduser](assets/images-server/adduser.png) <br>

15. Copy key pair ke public server dengan scp dan arahkan pada direktori /home/mico. <br>
    ![scppem](assets/images-server/scppem.png) <br>

16. Login ke private server dari public server dengan key pair. Hal ini karena Password Authentication di private server belum disetting, jadi masih perlu key pair. <br>
    ![loginprivateserver](assets/images-server/loginserverprivate.png) <br>