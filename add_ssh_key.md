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
- Place a title, paste the key and hit Add SSH key

**`Now you can clone repositories locally using ssh link and maintain them.`**

---

# Config SSH Key for Multiple Git Account

## Start OpenSSH Authentication Agent
- Search for **services** in windows search and open it.
- Find **OpenSSH Authetication Agent Properties** and open it by double click.
- Set Startup type to **Automatic**, then click **Start**.
- **Apply** then **Ok** and close the window.

## Generate and Add SSH Key for 1st Account
Open **Git Bash** and follow the following steps: (All the files will be created in **.ssh** folder).

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
- Place a title, paste the key and hit Add SSH key

#### Create and Configure a config File
```cmd
    notepad config
```
- This will create a `config.txt` file and open it. Add the information in the config file:
    ```code
        #Accouont1
        Host github.com
          HostName github.com
          IdentityFile ~/.ssh/id_rsa
    ```
- Save the file and Rename the `config.txt` file to `config`.
    ```cmd
        mv config.txt config
    ```
- This will rename the config.txt file to config file. (config file doesn't have any extension)

> Now check cloning git repository using ssh link, make changes and try pushing the changes. This should perfectly work for account one.

---

## Generate and Add SSH Key for 2nd Account
[NB] This section is slightly tricky in `key generation` and `repository clonning`. Read the instructions carefully.

#### Create a new SSH Key:
- In Git Bash (of course):
    ```cmd
        ssh-keygen -f acc2_id_rsa
    ```
- It will also create two files: `acc2_id-rsa` and `acc2_id_rsa.pub` if don't existed. `ls` to see the files in the **.ssh/** directory.
- `This time we have to give the file name.` Otherwise it will try to generate another key in the same name previously created for the 1st account and ask us to replace first one.

#### See and Copy the key:
```cmd
    cat acc2_id_rsa.pub
```
- This will show key associated key with the `acc2_id_rsa.pub` file. Copy the key.

#### Add SSH Key to GitHub Account
- Go to GitHub Account --> **Setting** --> **SSH and GPG keys** --> **New SSH Key**
- Place a title, paste the key and hit Add SSH key

#### Update the Config File
- Open the config file:
    ```cmd
        notepad config
    ```
- Add the 2nd account information in the config file:
    ```code
        #Accouont2
        Host github.com-aac2
          HostName github.com
          IdentityFile ~/.ssh/acc2_id_rsa
    ```

#### Cloning Repository from 2nd Account [Important]
- While cloning any repository from 2nd account the link is like -
    ```link
        git@github.com:acc_name/repo_name.git
    ```
- We have to change the host name `github.com` to `github.com-aac2`, like -
    ```link
        git@github.com-acc2:acc_name/repo_name.git
    ```
- **We have to maintain this change everytime we clone any repo from 2nd account.**

---