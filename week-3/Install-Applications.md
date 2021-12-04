# **INSTALL APPLICATIONS**

1. Kita akan membuat container dengan docker compose. Pertama-tama login ke server frontend & backend. <br>
   ![loginfe](assets/images-install-app/loginfe.png) <br>
   ![loginbe](assets/images-install-app/loginbe.png) <br>

2. Install docker compose (masing-masing di fe & be).

        sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

        sudo chmod +x /usr/local/bin/docker-compose
        
        docker-compose --version
    ![installdockercompose](assets/images-install-app/installdockercompose.png) <br>
    ![installdockercompose2](assets/images-install-app/installdockercompose2.png) <br>

3. Kemudian buat sebuah file docker-compose.yml dan ketikan perintah berikut di dalamnya (masing-masing di fe & be).
   
        nano docker-compose.yml
    ![composeyml](assets/images-install-app/composeyml.png) <br>
    ![composeyml2](assets/images-install-app/composeyml2.png) <br>

4. Lalu untuk membuat sebuah container ketikkan perintah berikut (masing-masing di fe & be) ;
   
        docker-compose up -d
    ![dockercompose](assets/images-install-app/dockercompose.png) <br>
    ![dockercompose2](assets/images-install-app/dockercompose2.png) <br>

5. Periksa apakah contianer sudah berjalan.

        docker ps
    ![dockerps](assets/images-install-app/dockerps.png) <br>
    ![dockerps2](assets/images-install-app/dockerps2.png) <br>

6. Periksa di browser apakah apps berjalan dengan baik dengan memasukan `ip:port`. <br>
   ![result](assets/images-install-app/result.png) <br>
   ![result2](assets/images-install-app/result2.png)