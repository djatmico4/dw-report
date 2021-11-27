# **INSTALLATION GIT & SSH KEY**
## Fork Repository backend apps
<br>

1. Login ke akun Github.
2. Buka repository backend apps yang akan di-fork, https://github.com/sgnd/dumbflix-backend.
3. Pada halaman repository backend apps, klik fork mpada pojok kanan atas, maka otomatis kita akan masuk ke repository akun github kita.
   ![fork](assets/images-install-git-and-ssh-key/fork.png) <br><br>

## Buat SSH key untuk Git
<br>

1. Buat sebuah server di AWS.
   ![step1](assets/images-install-git-and-ssh-key/step1.png) <br>
   ![step2](assets/images-install-git-and-ssh-key/step2.png) <br>
   ![step3](assets/images-install-git-and-ssh-key/step3.png) <br>
   ![step4](assets/images-install-git-and-ssh-key/step4.png) <br>
   ![step5](assets/images-install-git-and-ssh-key/step5.png) <br>
   ![step6](assets/images-install-git-and-ssh-key/step6.png) <br>
   ![step7](assets/images-install-git-and-ssh-key/step7.png) <br>
   ![step7-2](assets/images-install-git-and-ssh-key/step7-2.png) <br>
   ![step8](assets/images-install-git-and-ssh-key/step8.png) <br>
   ![step9](assets/images-install-git-and-ssh-key/step9.png) <br>

2. Masuk kedalam server yang sudah dibuat, yaitu server backend dengan key.
   ![loginserver](assets/images-install-git-and-ssh-key/loginserver.png) <br>

3. Lakukan update dan upgrade.

        sudo apt update -y && sudo apt upgrade -y
    ![update-upgrade](assets/images-install-git-and-ssh-key/update-upgrade.png) <br>

4. Cek apakah sudah terinstall git dan ssh.
   ![cekversion](assets/images-install-git-and-ssh-key/cekversion.png) <br>

5. Buatlah git config terlebih dahulu.

        git config --global user.name "<username>"
        git config --global user.email "<email>"
    ![gitconfig](assets/images-install-git-and-ssh-key/gitconfig.png) <br>

6. Buat folder untuk menyimpan ssh key.
   
        mkdir ssh-key
    ![foldersshkey](assets/images-install-git-and-ssh-key/foldersshkey.png) <br>

7. Generate ssh key di dalam foder yang telah dibuat. lalu Jalankan perintah berikut ;
8.  Masukkan nama file kemudian passphrase.

         ssh-keygen -t rsa -b 4096 -C "email".
    ![generatesshgit](assets/images-install-git-and-ssh-key/generatesshgit.png) <br>

9. Hal tersebut akan menghasilkan 2 key, git-ssh dan git-ssh.pub.
    ![hasilgenerate](assets/images-install-git-and-ssh-key/hasilgenerate.png) <br>

10. Tambahkan ssh key yang telah di generate tadi, ketikkan perintah ; 

         eval "$(ssh-agent -s)" 
         ssh-add git-ssh
      ![sshagent](assets/images-install-git-and-ssh-key/sshagent.png) <br>
   
11. Login ke GitHub.
12. Masuk ke settings, pada bagian `Account settings` klik `SSH dan GPG keys`.
13. Untuk menambahkan ssh key, copy isi data ssh key yang sudah dibuat tadi yang berekstensi `.pub` kemudian paste ke bagian `key` lalu `Add ssh key`.
    ![addsshkeytogithub](assets/images-install-git-and-ssh-key/addsshkeytogithub.png) <br>

14. Kemudian test koneksi ke github.

         ssh -T git@github.com
      ![teskoneksigithub](assets/images-install-git-and-ssh-key/teskonkesigithub.png) <br><br>

## Git pull, git commit, git push, and git merge

1. Pertama kita buat direktori baru untuk menyimpan perubahan inisiasi git di dalam direktori tersebut.

         mkdir <new-direktori>
         git init
      ![gitinit](assets/images-install-git-and-ssh-key/gitinit.png) <br>

   - Tambahkan file di dalamnya dan cek statusnya.

         cat > file (isi file)
         git add .
         git status
      ![gitadd](assets/images-install-git-and-ssh-key/gitadd.png) <br>

   - Lakukan commit.

         git commit -m "<isi pesan>"
      ![gitcommit](assets/images-install-git-and-ssh-key/gitcommit.png) <br>

   - Tambahkan branch baru, lalu pindah ke branch baru dan buat file baru juga.

         git branch <nama-branch>
         git checkout <branch-baru>
         cat > fle (isi file)
      ![gitbranch](assets/images-install-git-and-ssh-key/gitbranch.png) <br>

   - Lakukan add dan commit.
   - Pindah ke branch development (branch awal).
   - Lakukan merge.

         git mnerge <nama-branch>
      ![gitmerge](assets/images-install-git-and-ssh-key/gitmerge.png) <br>

   - Add git remote.
      ![addremote](assets/images-install-git-and-ssh-key/addremote.png) <br>

   - Jalankan git push & pull.
      ![gitpush](assets/images-install-git-and-ssh-key/gitpush.png) <br>
      ![gitpush2](assets/images-install-git-and-ssh-key/gitpush2.png) <br>



   