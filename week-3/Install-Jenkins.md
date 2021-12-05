# **INSTALL JENKINS**
## Buat AWS Instance

1. Login ke akun AWS.
2. Buat instance baru untuk jenkins.
3. Login ke ke instance jenkins vis SSH.
4. Update dan upgrade sistem
5. Install Jenkins LTS. 

## Install Jenkins 

1. Install java terlebih dahulu.
   
        sudo apt install openjdk-8-jdk

   - Tambahkan apt repository jenkins 
  
            wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -

   - Eksekusi kode berikut ;
  
            sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

   - Update sistem. <br>
  ![step1](assets/images-install-jenkins/step1.png) <br>

2. Install jenkins. <br>
   ![isntalljenkins](assets/images-install-jenkins/installjenkins.png) <br>

3. Buka browser dan arahkan ke `ip-address-server:8080`. <br>
   ![openbrowserip](assets/images-install-jenkins/openbrowserip.png) <br>

4. Masukkan initial admin password, bisa dilihat di 
   
        sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ![password](assets/images-install-jenkins/password.png) <br>

    - Masukan password ke dalam browser tadi. <br><br>
  
5. Pilih jenis instalasi plugin jenkins(pilih yang suggested plugins) dan tunggu proses instalasi plugin selesai.
6. Buat admin jenkins, simpan dan lanjut.
   ![addadmin](assets/images-install-jenkins/addadmin.png) <br>

7. Konfigurasi jenkins URL. Save and finish.
   ![jenkinsurl](assets/images-install-jenkins/jenkinsurl.png) <br>

8. Tampilan dashboard jenkins.
   ![dashboardjenkins](assets/images-install-jenkins/dashboardjenkins.png) <br><br>


## Reverse Domain for Jenkins

1. Pertama login ke akun cloudflare.
   - Pilih akun `sugandaletter@outlook.com` dan domain `onlinecamp.id`.
   - Masuk ke menu DNS.
   - Add record untuk `jenkins jenkins.dody.onlinecamp.id`
   - save. <br>
  ![reversejenkins](assets/images-install-jenkins/reversejenkins.png) <br>

2. Kemudian kita setup reverse proxy untuk jenkins.
   - Login ke server gateway.
   - Masuk ke folder nginx `/etc/nginx/`
   - Buat konfigurasi file `jenkins.dody.onlinecamp.id` <br>
  ![configreversejenkins](assets/images-install-jenkins/configreversejenkins.png) <br>
  ![configreversejenkins2](assets/images-install-jenkins/configreversejenkins2.png) <br>

  - Lakukan validasi dan reload nginx.

3. Buka browser dan arahkan ke `jenkins.dody.onlinecamp.id` <br>
   ![result](assets/images-install-jenkins/result.png) <br>