# **AWS - CREATE AND SETUP SERVER**
## **Create and Setup Server on AWS** <br><br>
## **Server untuk reverse proxy**

1. Login terlebih dahulu ke dalam AWS Educate.
2. Go to classrom.
3. Pilih `AWS console`, lalu pergi ke alamat link yang dituju.
   ![console](assets/images-aws-create&setup-server/console.png) <br>

4. Di dalam dashboard atau `AWS management console`, pilih `Launch a virtual machine`.
   ![launcmachine](assets/images-aws-create&setup-server/launchmachine.png) <br>

5. Pada `Step 1: Choose an Amazon Machine Image (AMI)`, pilih Ubuntu Server 18.x OS.
   ![chooseserver](assets/images-aws-create&setup-server/chooseserver.png) <br>

6. Step 2, pilih instance type sesuai kebutuhan, `next`.
   ![instancetype](assets/images-aws-create&setup-server/instancetype.png) <br>

7. Step 3, klik pada `Auto assign public IP` pilih `disable`, lalu `next`.
   ![step-3](assets/images-aws-create&setup-server/step-3.png) <br>

8. Step 4, isikan storage sesuai kebutuhan, klik `next`.
   ![step-4](assets/images-aws-create&setup-server/step-4.png) <br>

9. Step 5, biarkan saja default, pilih `next`.
    ![step-5](assets/images-aws-create&setup-server/step-5.png) <br>

10. Step 6 security group, pilih `create a new security group` tentukan type sesuai keinginan, di sini kita pilih SSH, HTTP, dan HTTPS, lalu klik `review and launch`.
    ![step6](assets/images-aws-create&setup-server/step-6.png) <br>

11. Step 7, review instance launch. Review konfigurasi yang sudah dibuat, klik `launch`.
    ![step-7](assets/images-aws-create&setup-server/step-7.png) <br>

12. Masuk ke Elastic IPs yang berada di sidebar console bagian network & security.
    ![elasticip](assets/images-aws-create&setup-server/elasticip.png) <br>

13. Pilih `Allocate ip address`, biarkan default saja, lalau `allocate`. AWS akan mengalokasikan sebuah IP yang dapat digunakan.
    ![allocateip](assets/images-aws-create&setup-server/allocateip.png) <br>

14. Pada tombol `Actions`, pilih `Associate ellastic IP address`, lalu pilih instancenya. Klik `Associate`
    ![associateip](assets/images-aws-create&setup-server/associateip.png) <br>

15. Masuk ke instances, lalu refresh.
    ![refresh-instances](assets/images-aws-create&setup-server/refresh-instance.png) <br>

16. Buka terminal, pindah ke directory `Downloads` serta ubah hak akses pada key pair.

        cd Downloads/
        chmod 400 bootcamp.pem
    ![chmod](assets/images-aws-create&setup-server/chmod.png) <br>

17. Server bisa diakses melalui SSH menggunakan IP public tadi.

        ssh -i bootcamp.pem ubuntu@ip-public
    ![sshserver](assets/images-aws-create&setup-server/sshserver.png) <br>

    - Jangan lupa untuk update dan upgrade agar lebih aman.
    ![update-upgrade](assets/images-aws-create&setup-server/update-upgrade.png) <br><br>


## **Server untuk reverse proxy**

1. Login terlebih dahulu ke dalam AWS Educate.
2. Go to classrom.
3. Di dalam dashboard atau `AWS management console`, pilih `Launch a virtual machine`.
   ![launcmachine](assets/images-aws-create&setup-server/launchmachine.png) <br>

4. Pada `Step 1: Choose an Amazon Machine Image (AMI)`, pilih Ubuntu Server 18.x OS.
   ![chooseserver](assets/images-aws-create&setup-server/chooseserver.png) <br>

5. Step 2, pilih instance type sesuai kebutuhan, `next`.
   ![instancetype](assets/images-aws-create&setup-server/instancetype.png) <br>

6. Step 3, klik pada `Auto assign public IP` pilih `disable`, lalu `next`.
   ![step-3](assets/images-aws-create&setup-server/step-3.png) <br>

7. Step 4, isikan storage sesuai kebutuhan, klik `next`.
   ![step-4](assets/images-aws-create&setup-server/step-4.png) <br>

8. Step 5, biarkan saja default, pilih `next`.
    ![step-5](assets/images-aws-create&setup-server/step-5.png) <br>

9. Step 6, setup security group. Pilih `All traffic` lalu `review and launch`.
    ![step6](assets/images-aws-create&setup-server/step6.png) <br>

10. Step 7, review konfigurasi yang sudah dibuat, kemudian `launch`.
    ![step7](assets/images-aws-create&setup-server/step7.png) <br>

    - Gunakan key pair yang sama pada reverse proxy yang sudah didownload tadi, lalu `launch instance`.
    ![step7-2](assets/images-aws-create&setup-server/step7-2.png) <br>

11. Masuk ke Elastic IPs yang berada di sidebar console bagian network & security. Allocate dan associate untuk mendapatkan IP address.
    ![allocateip-app](assets/images-aws-create&setup-server/allocateip-app.png) <br>

    - Masuk instances dan refresh.
    ![refresh-instance-app](assets/images-aws-create&setup-server/refresh-instance-app.png) <br>
    
12. Buka terminal, pindah ke directory `Downloads` lalu lakukan remote.

        cd Downloads/
        ssh -i bootcamp.pem ubuntu@ip-public
    ![sshserver-app](assets/images-aws-create&setup-server/sshserver-app.png) <br>

    - Jangan lupa update dan upgrade agar lebih aman.
    ![]