# **Repository**
## Create Own Repository for fe & be

1. Clone aplikasi fe & be dari `git@github.com:sgnd/dumbflix-frontend.git` dan `git@github.com:sgnd/dumbflix-backend.git`. <br>

        git clone git@github.com:sgnd/dumbflix-frontend.git
   ![clonefe&be](assets/images-repo/clonefe&be.png) <br>

2. Ganti git remote untuk repository sendiri. Lakukan hal ini untuk fe & be.
   
        git remote add origin git@github.com:sgnd/dumbflix-frontend.git
   ![gitremote](assets/images-repo/gitremote.png) <br>

3. Membuat branch development dan production. Lakukan hal ini untuk fe & be.

        git branch -M development
        git branch production
    ![gitbranch](assets/images-repo/gitbranch.png) <br>

4. Push ke dalam repositorty sendiri. Lakukan hal ini untuk fe & be.
   
        git push -u origin development
    ![gitpush](assets/images-repo/gitpush.png)