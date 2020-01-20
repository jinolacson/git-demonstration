
1. Navigate to `.ssh` folder.
```
cd ~/.ssh 
```

2. Generate key using your company email.
```
ssh-keygen -t rsa -C "jino.lacson@boom.camp"
```

3. Enter 
```
Enter file in which to save the key (/home/jino/.ssh/id_rsa): [Enter]
Enter passphrase (empty for no passphrase): [Enter] 
Enter same passphrase again: [Enter] 
```

4. Check of `id_rsa  id_rsa.pub` if genereated successfully
```
ls 
output : id_rsa  id_rsa.pub  known_hosts
```

5. Paste your generated `id_rsa.pub` under.
```
https://[gitlab-hostname]/profile/keys
```

and click `save`

6. Clone with *ssh* `git@` over `https://`.

example: 

```
git clone git@dev.perfectpitchtech.com:boomcamp/handraiser.git
```

7. Done, you should able to push and pull without asking git credentials.

