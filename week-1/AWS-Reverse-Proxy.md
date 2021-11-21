# **AWS - REVERSE PROXY**
## Make A Reverse Proxy

1. Lakukan remote untuk masuk ke server.

        ssh dody@gateway
    ![ssh](assets/images-aws-reverse-proxy/ssh.png) <br>

    - Lakukan update dan upgrade.
    ![update-upgrade](assets/images-aws-reverse-proxy/update-upgrade.png) <br>

2. Install nginx.

        sudo apt install nginx -y
    ![install-nginx](assets/images-aws-reverse-proxy/install-nginx.png) <br>

    - Cek status `Nginx`
    ![status-nginx](assets/images-aws-reverse-proxy/status-nginx.png) <br>

3. Buat directory baru dan ubah hak aksesnya.

        sudo mkdir /etc/nginx/frontend
        sudo chown -R dody:dody /etc/nginx/frontend
    ![mkdir](assets/images-aws-reverse-proxy/mkdir.png) <br>

4. Buat file config pada directory `frontend`.
    
        nano dumbflix-conf
    ![dumbflix-conf](assets/images-aws-reverse-proxy/dumbflix-conf.png) <br>

    - Cek validasi dan reload.
    ![validasi](assets/images-aws-reverse-proxy/validasi.png) <br>

    - Masukan config yang sudah dibuat ke dalam `/etc/nginx/nginx.conf`.
    ![include](assets/images-aws-reverse-proxy/include.png) <br>

    - Lakukan validasi dan reload nginx.
    ![validasi-2](assets/images-aws-reverse-proxy/validasi-2.png) <br>

5. Jalankan di browser
   ![result](assets/images-aws-reverse-proxy/result.png)

