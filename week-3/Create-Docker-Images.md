# **CREATE DOCKER IMAGES**
## Membuat Docker Images Untuk Frontend

1. Login ke server frontend dan backend.
2. Download images node js, dengan menjalankan perintah 
   
        docker pull node:14.18.1-alpine
    ![dockerpull](assets/images-create-docker-images/dockerpull.png) <br>
    ![dockerpull2](assets/images-create-docker-images/dockerpull2.png) <br>

3. Masuk ke dalam folder dumbflix-frontend.
4. Buat docker file 
   
        sudo nano Dockerfile
    ![dockerfile](assets/images-create-docker-images/dockerfile.png) <br>

- Lakukan hal yang sama di server backend.
    ![dockerfile2](assets/images-create-docker-images/dockerfile2.png) <br>

5. Buat docker image frontend danb backend app.
   
        docker build -t nama-file:tag
    ![dockerbuild](assets/images-create-docker-images/dockerbuild.png) <br>
    ![dockerbuild2](assets/images-create-docker-images/dockerbuild2.png) <br>

6. Buat container dari image frontend dan backend.
   
        docker container create --name nama-container -p 3131:3000 nama-images:tag
    ![dockercontainer](assets/images-create-docker-images/dockercontainer.png) <br>

        docker container create --name nama-container -p 5151:5000 nama-images:tag
    ![dockercontainer2](assets/images-create-docker-images/dockercontainer2.png) <br>

7. Push images ke reposiroty docker hub.

        docker push nama-images:tag
    ![dockerpush](assets/images-create-docker-images/dockerpush.png) <br>
    ![dockerpush2](assets/images-create-docker-images/dockerpush2.png) <br>
    
8. Kemudian kita bisa cek di akun docker hub kita, apakah sudah berhasil atau belum. <br>
    ![result](assets/images-create-docker-images/result.png)