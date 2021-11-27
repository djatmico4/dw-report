# **DEPLOYMENT BACKEND APP**

1. Login ke server backend.
2. Clone aplikasi dari https://github.com/sgnd/dumbflix-backend.git
   
        git clone https://github.com/sgnd/dumbflix-backend.git
    ![clone](assets/images-deployment-for-backend-app/clone.png) <br>

    - Buka file `README.md ` di dalam folder backend.
    ![readmebackend](assets/images-deployment-for-backend-app/readmebackend.png) <br>

3. Jalankan requirements nya.
   - Install node.js 10.x
   - Import database dumbflix.sql dengan sequlize
   - Copy .env.example to .env
   - Deploy dumbflix-backend with port 5000 <br><br>
  
    ![npm](assets/images-deployment-for-backend-app/npm.png) <br>
    ![cpenv](assets/images-deployment-for-backend-app/cpenv.png) <br>

   - Change config/config.json to your database
    ![config](assets/images-deployment-for-backend-app/config.png) <br>

4. Lakukan secure copy untuk database `dumbflix.sql` dari server backend ke dalam server database.

        scp -r dumbflix.sql host@ip:<tujuan>
    ![scp](assets/images-deployment-for-backend-app/scp.png) <br>
    ![scp2](assets/images-deployment-for-backend-app/scp2.png) <br><br>

## Import Database Dengan Sequelize

1. Install sequelize pada backend.

        npm install --save-dev sequelize-cli -g
    ![instsequelize](assets/images-deployment-for-backend-app/instsequelize.png) <br>

2. Migrate database.

        sequelize db:migrate
    ![sequelize](assets/images-deployment-for-backend-app/sequelize.png) <br>

3. Jalankan backend app dengan pm2
   ![run](assets/images-deployment-for-backend-app/run.png) <br>

