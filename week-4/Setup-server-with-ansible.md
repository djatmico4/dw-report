# **SETUP SERVER WITH ANSIBLE**

## **Requirements**
- Buatlah repository di github untuk menyimpan file-file ansible.

## **Install Ansible in Ubuntu**

1. Konfigurasi PPA.

        sudo apt update
        sudo apt install software-properties-common
        sudo add-apt-repository --yes --update ppa:ansible/ansible

2. Kemudian install apt ansible. <br>
   ![installansible](assets/images-setup-server-ansible/installansible.png) <br>

## **Define Host Server**

1. Buat directory ansible dan buat hosts untuk menyimpan konfigurasi host. <br>
   ![ansiblehosts](assets/images-setup-server-ansible/ansiblehosts.png) <br>
   ![ansiblehosts2](assets/images-setup-server-ansible/ansiblehosts2.png) <br>

2. Kemudian cek ping dengan perintah berikut.

        ansible all -m ping
    ![cekping](assets/images-setup-server-ansible/cekping.png) <br>

## **Setup User**

1. Disini saya menggunakkan ansible-playbook.
2. Siapkan konfigurasi untuk membuat user. <br>
   ![createuser](assets/images-setup-server-ansible/createuser.png) <br>


## **Setup Nginx**

1. Siapkan konfigurasi untuk nginx dan kemudian jalankan `ansible-playbook nginx.yml`. <br>
   ![confignginx](assets/images-setup-server-ansible/confignginx.png) <br>
   ![runnginxyml](assets/images-setup-server-ansible/runnginxyml.png) <br>

2. Buka browser dan jalankan. <br>
   ![resultnginx](assets/images-setup-server-ansible/resultnginx.png) <br>
   

## **Setup CICD**

1. Siapkan konfigurasi untuk jenkins dan kemudian jalankan `nsible-playbook jenkins.yml`. <br>
   ![jenkinsyml](assets/images-setup-server-ansible/jenkinsyml.png) <br>
   ![resultjenkins](assets/images-setup-server-ansible/resultjenkins.png) <br>
   
## **Setup Database**

1. Siapkan konfigurasi untuk database dan kemudian jalankan `ansible-playbook database.yml`. <br>
   ![databaseyml](assets/images-setup-server-ansible/databaseyml.png) <br>

## **Setup Backend**

1. siapkan konfigurasi untuk backend dan kemudian jalankan `ansible-playbook backend.yml`. <br>
   ![backendyml](assets/images-setup-server-ansible/backendyml.png) <br>
   ![resultbackend](assets/images-setup-server-ansible/resultbackend.png) <br>

## **Setup Frontend**

1. siapkan konfigurasi untuk frontend dan kemudian jalankan `ansible-playbook frontend.yml`. <br>
   ![frontendyml](assets/images-setup-server-ansible/frontendyml.png) <br>
   ![resultfrontend](assets/images-setup-server-ansible/resultfrontend.png) 
