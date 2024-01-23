##### **added and commited but cannot push problem**
![problem](problem_images/stagged_cimmited_but_cannot_pushed.PNG)
> **Solution:*`I deleted the whole directory with the files and recreate a directory and files. This solves the issue.`***

##### **[rejected] error: failed to push some refs to 'https://github.com/abs-sayem/deep_learning.git'**
```python
To https://github.com/abs-sayem/deep_learning.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/abs-sayem/deep_learning.git'
```
**Solution**
* pull changes from the remote:
```python
    git pull origin main
```
* This command fetches the changes and merges them into your local branch. If there are conflicts, Git will prompt you to resolve them