# Adding a Public SSH Key
The main purpose of this key is to make you able to clone the git repositories in anothr pc and to maintain form both pc.
> [NB] Everytime you shoud pull the updates made either any of your pc. Use `git pull` before making any changes in your repository.
---

## Check SSH Folder and Keys
- **Open Terminal / CMD / Powershell (in root directory)**
- Check if there is already any **`.ssh`** folder and keys:
    ```cmd
        ls
    ```
- If **`.ssh`** folder is there, enter into it:
    ```cmd
        cd .ssh
    ```
- Then use `ls` to check the ssh keys. If there are any keys, they will appear as public and private key pair.

## Generate SSH Keys
- If there is no ssh keys already generated or you need new ssh key:
- To generate new ssh key: (place your git email)
    ```cmd
        ssh-keygen -o -t rsa -C gitexample@gmail.com
    ```
- It will generate the keys. Just keep pressing enter to generate keys in default location and escape passphrasing.
- Use `ls` to check the generated key. It will show `id_rsa.pub` file.
- To open the key in VS Code:
    ```cmd
        code id_rsa.pub
    ```
- It will open the file in VS Code and you can see the key there.

## Add SSH Key to GitHub Account
- Go to GitHub Account --> **Setting** --> **SSH and GPG keys** --> **New SSH Key**
- Place and title and paste the key and hit Add SSH key

**`Now you can clone repositories locally using ssh link and maintain them.`**

---

# Config SSH Key for Multiple Git Account

## Start OpenSSH Authentication Agent
- Search for **services** in windows search and open it.
- Find **OpenSSH Authetication Agent Properties** and open it by double click.
- Set Startup type to **Automatic**, then click **Start**.
- **Apply** then **Ok** and close the window.

## Generate SSH Key for 1st Account
Open **Git Bash** and follow the following steps:
#### Create a SSH Key:
    ```cmd
        ssh-keygen
    ```
- It will create two files: `id-rsa` and `id_rsa.pub` if don't existed. `ls` to see the files in the **.ssh/** directory.
#### See and Copy the key:
    ```cmd
        cat id_rsa.pub
    ```
- This will show key associated key with the `id_rsa.pub` file. Copy the key.
#### Add SSH Key to GitHub Account
- Go to GitHub Account --> **Setting** --> **SSH and GPG keys** --> **New SSH Key**
- Place and title and paste the key and hit Add SSH key

> Now check cloning git repository using ssh link, make changes and try pushing the changes. This should perfectly work for account one.