# **AWS - SERVER FOR APPLICATION**
## Making Server for Application

1. Lakukan remote untuk masuk ke server.
   
        ssh djat@frontend
    ![ssh](assets/images-aws-server-for-app/ssh.png) <br>

    - Lakukan update dan upgrade.
    ![update-upgrade](assets/images-aws-server-for-app/update-upgrade.png) <br>

2. Install nvm.

        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
    ![install-nvm](assets/images-aws-server-for-app/install-nvm.png) <br>

    - Install `NodeJS versi 10.x`
  
            nvm install 10
    ![install-nvm-2](assets/images-aws-server-for-app/install-nvm-2.png) <br>

3. Clone aplikasi `https://github.com/sgnd/dumbflix-frontend.git`

        git clone https://github.com/sgnd/dumbflix-frontend.git
    ![clone-app](assets/images-aws-server-for-app/clone-app.png) <br>

    - Ubah nama folder.
    ![changename](assets/images-aws-server-for-app/changename.png) <br>

4. Install dependencies yang diperlukan.

        npm install
    ![npminstall](assets/images-aws-server-for-app/npminstall.png) <br>

5. Install pm2.
   
        npm install -g pm2
    ![pm2install](assets/images-aws-server-for-app/pm2install.png) <br>

    - Start applikasi.
  
            pm2 start ecosystem.config.js
    ![pm2start](assets/images-install-app/pm2start.png) <br>
    ![result](assets/images-aws-server-for-app/result.png) <br>