# **AWS - SSL CONFIGURATION**
## Generate API Key

1. Pertama, login dan masuk ke dalam dashboard `cloudflare`.
2. Pada sidebar kiri, klik `My Profile`, lalu klik `API Tokens`.
   ![dashboard](assets/images-aws-ssl-config/dashboard.png) <br>
   ![api](assets/images-aws-ssl-config/api.png) <br>

3. Pada bagian `Global API Key`, klik `view`, lalu akan muncul kotak dialog.
   ![api-key](assets/images-aws-ssl-config/api-key.png) <br>

4. Masukkan password untuk mendapatkan key.
5. Copy dan simpan api key.
   ![copy-key](assets/images-aws-ssl-config/copy-key.png) <br>

6. Buka terminal dan masuk ke ddalam server.
7. Buatlah folder dan di dalamnya buat file untuk menyimpan api key cloudflare.
   ![folder-api](assets/images-aws-ssl-config/folder-api.png) <br>
   ![save-api](assets/images-aws-ssl-config/save-api.png) <br>

8. Berikan hak akses pada folder dan file.
   ![hakakses](assets/images-aws-ssl-config/hakakses.png) <br><br>

## Install Cerbot dan Cloudflare DNS Authenticator Plugin

1. Update snap sudo snap install core; sudo refresh core.
2. Install certbot sudo snap install --classic certbot.
   ![install-certbot](assets/images-aws-ssl-config/install-certbot.png) <br>

3. Link certbot dari /snap/bin/certbot ke /usr/bin/certbot.
    
        sudo ln -s /snap/bin/certbot /usr/bin/certbot
    ![prepare-certbot](assets/images-aws-ssl-config/prepare-certbot.png) <br>
        
4. Generate SSL sudo certbot.
   
        sudo certbot --nginx
    ![generate](assets/images-aws-ssl-config/generate.png) <br>

    - Masukkan e-mail address.
    - Kemudian `Terms of Agreement`.
    - Pilih nama website yang akan dipakaikan HTTPS.
    - Tunggu sampai request berhasil.
    ![hasil-generate](assets/images-aws-ssl-config/hasil-generate.png) <br>

5. Untuk mengeceknya, masuk ke directory `/etc/nginx/frontend/`
6. Lalu cek isi dari confignya.
   
        cat dody.onlinecamp.id
    ![cek-config](assets/images-aws-ssl-config/cek-config.png) <br>

7. Lakukan validasi dan reload `nginx`
   ![validasi-reload](assets/images-aws-ssl-config/validasi-reload.png) <br>

8. Jalankan di browser.
   ![done](assets/images-aws-ssl-config/done.png) <br>