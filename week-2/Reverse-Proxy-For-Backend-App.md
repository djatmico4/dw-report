# **REVERSE PROXY FOR BACKEND APP**

1. Login ke server gateway terlebih dahulu.
2. Laakukan update and upgrade.
3. Install `Nginx`.
   ![installnginx](assets/images-reverse-proxy-for-backend-app/installnginx.png) <br>

4. Masuk ke folder /etc/nginx/dumbflix
5. Kemudian buat file config untuk backend app `api.dody.onlinecamp.id`

        cd /etc/nginx/dumbflix
        nano api.dody.onlinecamp.id
    ![folderdumbflix](assets/images-reverse-proxy-for-backend-app/folderdumbflix.png) <br>

    - Arahkan proxy_pass ke ip private server backend.
    ![config](assets/images-reverse-proxy-for-backend-app/config.png) <br>

    - Save.
    - Lakukan validasi config dan reload `nginx`.


            sudo nginx -t
            sudo systemctl reload nginx