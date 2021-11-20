# **VMWARE - INSTALL APPLICATION**
## Make Server For Application on VMWare

1. Jalankan VMWare yang telah terinstall OS Ubuntu server.   
2. Login dan lakukan update dan upgrade terlebih dahulu dengan perintah ;

        sudo apt update -y && sudo apt upgrade -y
    ![sudo](assets/images-install-app/sudo.png) <br>

3. Lakukan ssh, anggap VMWare sebagai server.

        ssh djatmico@192.168.67.100
    ![ssh](assets/images-install-app/ssh.png) <br>

    - Ubah atau tambahkan user terlebih dahulu.

            sudo adduser djat
    ![adduser](assets/images-install-app/adduser.png) <br>

    - Beri hak akses sudo pada user baru dan pindah user tersebut.

            sudo usermod -aG sudo djat
            sudo su - djat
        ![usermod](assets/images-install-app/usermod.png)<br>

4. Kita clone dahulu aplikasi yang akan kita pakai.

        git clone https://github.com/sgnd/dumbflix-frontend.git
    ![clone](assets/images-install-app/clone.png) <br>

5. Kemudian install aplikasi Node.JS versi 10.x, dengan perintah berikut ;

         curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
    ![installnode](assets/images-install-app/instalnode.png) <br>

   - Jalankan `exec bash` dan cek versi nvm nya.

            exec bash
            nvm -v
        ![execbash](assets/images-install-app/execbash.png) <br>

    - Kemudian install node, konfirmasi hasil instalasinya.

            nvm install 10
            nvm use 10
            node -v
            npm -v
        ![donenode](assets/images-install-app/donenode.png) <br>

    - Lakukan npm install terlebih dahulu.

            npm install
        ![npm](assets/images-install-app/npm.png) <br>

    - Cek script apa yang akan dijalankan.

            cat package.json
        ![script](assets/images-install-app/script.png) <br>

    - Jalankan aplikasi.

            npm run start
        ![npmstart](assets/images-install-app/npmstart.png) <br>
        ![dumbflix](assets/images-install-app/dumbflix.png) <br><br>

# Deploy Apps by Nginx and Reverse Proxy

1. Install `nginx` terlebih dahulu apabila belum menginstallnya.
2. Install `pm2` agar aplikasi bisa tetap berjalan di background.
    
        npm install -g pm2
    ![pm2install](assets/images-install-app/pm2install.png) <br>

3. Bikin file ecosystem di pm2 untuk menggenerate config.
   
        pm2 init simple
    ![ecos](assets/images-install-app/ecos.png) <br>

    - Selanjutnya konfigurasi file ecosystem tadi.

            nano ecosystem.config.js
        ![configecos](assets/images-install-app/configecos.png) <br>

    - Run pm2.

            pm2 start ecosystem.config.js
        ![pm2start](assets/images-install-app/pm2start.png) <br>

    - Cek log.

            pm2 logs 0 --lines 200
        ![log](assets/images-install-app/log.png) <br>
        ![dumbflix](assets/images-install-app/dumbflix.png) <br>

4. Buat folder di dalam directory `/etc/nginx/`. Lalu beri izin user agar tidak perlu menggunakan `sudo` untuk merubah isi folder.

        sudo mkdir dumbflix
        sudo chown -R djat:djat dumbflix
    ![chown](assets/images-install-app/chown.png) <br>

5. Pindah ke directory `dumbflix` dan buat konfigurasi untuk reverse proxy.

        cd dumbflix/
        nano dumbflix.id
    ![dumbflixconf](assets/images-install-app/dumbflixconf.png) <br>
    ![dumbflixconf-2](assets/images-install-app/dumbflixconf-2.png) <br>

6. Validasi config dan reload `nginx`.

        sudo nginx -t
        sudo systemctl reload nginx
    ![reloadnginx](assets/images-install-app/reloadnginx.png) <br>

7. Masukkan folder yang berisi config ke dalam `nginx.conf` agar config yang sudah dibuat terbaca oleh `nginx`.

        sudo nano nginx.conf
    ![includeconf](assets/images-install-app/includeconf.png) <br>

    - Jangan lupa validasi dan reload `nginx` <br><br>

8. Setting hosts di `/etc/hosts`.

        sudo nano /etc/hosts
    ![hosts](assets/images-install-app/hosts.png) <br>

9. Jalankan di browser,  berikut hasilnya ;
    ![result](assets/images-install-app/result.png)

