# **SETUP DATABASES**
## Buat Instance Baru Untuk Backend

1. Login ke AWS, pilih EC2.
2. Masuk ke instance, pilih `Launch instances`
3. Buat instances baru untuk database.
   ![step1](assets/images-setup-databases/step1.png) <br>
   ![step2](assets/images-setup-databases/step2.png) <br>
   ![step3](assets/images-setup-databases/step3.png) <br>
   ![step4](assets/images-setup-databases/step4.png) <br>
   ![step5](assets/images-setup-databases/step5.png) <br>
   ![step6](assets/images-setup-databases/step6.png) <br>
   ![step7](assets/images-setup-databases/step7-2.png) <br>
   ![tep7-2](assets/images-setup-databases/step7-2.png) <br>
   ![step8](assets/images-setup-databases/step8.png) <br>
   ![step9](assets/images-setup-databases/step9.png) <br>
   ![step10](assets/images-setup-databases/step10.png) <br><br>

## Install Database

1. Login ke server database.
2. Lakukan update and upgrade terlebih dahulu.
   ![update-upgrade](assets/images-setup-databases/update-upgrade.png) <br>

3. Install mysql-server, lalu cek apakah sudah jalan.

        sudo apt install myql-server
        sudo systemctl status mysql
    ![mysqlserver](assets/images-setup-databases/mysqlserver.png) <br>
    ![statusmysql](assets/images-setup-databases/statusmysql.png) <br>

4. Konfigurasi keamanan database.
   
        sudo mysql_secure_installation
    ![securemysql](assets/images-setup-databases/securemysql.png) <br><br>

## Remote Database Dari Klien

1. Buka folder `/etc/mysql/mysql.conf.d`, lalu edit file `mysqld.cnf`

        sudo nano mysqld.cnf
    ![mysqlconf](assets/images-setup-databases/mysqlconf.png) <br>
    ![mysqlconf2](assets/images-setup-databases/mysqlconf2.png) <br>

   - Restart mysql service dengan perintah `sudo systemctl restart mysql`. <br><br>
  

2. Memberi akses ke host.
3. Membuat login tanpa sudo.
   
        sudo mysql -uroot
    ![newuser](assets/images-setup-databases/newuser.png) <br>

    - Membuat user baru dan grant database.
    ![newuser2](assets/images-setup-databases/newuser2.png) <br>