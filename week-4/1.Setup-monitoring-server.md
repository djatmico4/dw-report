# **SETUP MONITORING SERVER**

1. Buat server baru di multipass.
2. Di sini aya menggunakan ansisble untuk instalasi node exporter ke banyak server. <br><br>

## Install Node Exporter di Server

1. Pertama-tama siapkan install node-exporter tiap server disini saya menggunakkan ansible.
2. untuk konfigurasi instalasi node-exporter seperti berikut; <br>
   ![confignodeyaml](assets/images-setup-monitoring-server/confignodeyaml.png) <br>
   ![installnode-exporter](assets/images-setup-monitoring-server/install%20node-exporter.png) <br>

   - Berikut adalah hasilnya; <br>
   ![node1](assets/images-setup-monitoring-server/node1.png) <br>
   ![node2](assets/images-setup-monitoring-server/node2.png) <br>
   ![node3](assets/images-setup-monitoring-server/node3.png) <br>
   ![node4](assets/images-setup-monitoring-server/node4.png) <br><br>


## Install Prometheus di Monitoring Server

1. Di sini saya juga menggunakan ansible.
2. Untuk konfigurasi instalasi grafana dan promethus seperti ini; <br>
   ![configpromyaml](assets/images-setup-monitoring-server/configpromyaml.png)  
   ![configpromgrafyaml](assets/images-setup-monitoring-server/configpromgrafyaml.png) <br>

3. Jalankan ansible playbooknya. <br>
   ![ansiblepromgraf](assets/images-setup-monitoring-server/ansiblepromgraf.png) <br>

4. Siapkan reverse proxy untuk prometheus dan grafana. <br>
   ![reverseprom](assets/images-setup-monitoring-server/reverseprom.png) <br>
   ![reversegraf](assets/images-setup-monitoring-server/reversegraf.png) <br>

5. Kemudian buka browser dan akses domain tersebut. Hasilnya sebagai berikut. <br>   
   ![result](assets/images-setup-monitoring-server/result.png) <br>
   ![result2](assets/images-setup-monitoring-server/result2.png)  
   