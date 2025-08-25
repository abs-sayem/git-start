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