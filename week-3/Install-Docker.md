# **INSTALL DOCKER**
## Install Docker di Server Frontend dan Backend

1. Pertama, login terlebih dahulu ke server frontend dan backend.
2. Update dan Upgrade sistem. <br>
   ![loginandupdate](assets/images-install-docker/loginandupdate.png) <br>
   
3. Perbarui apt untuk memungkinkan dapat menggunakan repositori melalui HTTPS.

        sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    ![setuprepo](assets/images-install-docker/setuprepo.png) <br>

4. Tambahkan Official GPG key docker. 
   
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ![gpgdocker](assets/images-install-docker/gpgdocker.png) <br>

    - Gunakan perintah berikut untuk mengatur repositori yang stabil. Bisa menggunakan stable atau nightly.

            echo \ "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
        ![addrepodocker](assets/images-install-docker/addrepodocker.png) <br>

5. Lakukan update sistem.
6. Install docker.

        sudo apt-get install docker-ce docker-ce-cli containerd.io
    ![installdocker](assets/images-install-docker/installdocker.png) <br>

7. Cek versi docker dan pastikan sudah berjalan. <br>
   ![statusdocker](assets/images-install-docker/statusdocker.png) <br>

8. Install juga docker pada server backend, cara instalasinya sama, ikuti langkah 1-7. <br>
   ![installdocker2](assets/images-install-docker/installdocker2.png) <br><br>

## Sign Up & Log In to Docker Hub

1. Masuk ke web [hub docker](https://hub.docker.com/).
2. Kemudian silakan daftar / sign up. <br>
    ![logindocker](assets/images-install-docker/logindocker.png) <br>

3. Login ke server frontend, lalu login docker menggunakan akun hub docker yang telah dibuat sebelumnya.

        docker login
    ![logindockerterminal](assets/images-install-docker/logindockerterminal.png)