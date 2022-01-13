# **VMWARE  SETUP NETWORK**
## Change Network from NAT to Bridge & Make The IP To Be Static

1. Pertama bukalah aplikasi VMWare, pilih `Edit virtual machine settings`. <br>
   ![open](assets/images-setting-network/openvm.png) <br>

2. Pilih `network adapter`, lalu di kolom sebelah kanan pilih `Bridge`. <br>
   ![custom-hardware](assets/images-setting-network/customize-hardware.png) <br>

3. Untuk setting IP address menjadi static, buka dan jalankan ubuntu server. <br>
   ![start-ubuntu](assets/images-setting-network/start-ubuntu.png) <br>

4. Update dan upgrade terlebih dahulu dengan perintah ;

        sudo apt update -y && sudo apt upgrade -y
    ![sudo](assets/images-setting-network/sudo.png) <br>

5. Pindah ke directory `/etc/netplan/` dan edit file .yaml di dalamnya, kemudian apply. <br>

        cd /etc/netplan/
        sudo nano 00-installer-config.yaml
    ![sudo-nano](assets/images-setting-network/sudo-nano.png) <br>
    ![configyaml](assets/images-setting-network/configyaml.png) <br>
    ![netplanapply](assets/images-setting-network/netplanapply.png) <br>

6. Test konkesi menggunakan ping. <br>
   
         ping google.com
   ![ping](assets/images-setting-network/ping.png) <br>