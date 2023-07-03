[Open two terminals and switch to root on jump_host itself]

{Terminal 1}

Open vi editor and add puppet infront of last 3 lines
```
vi /etc/hosts
```
After that,
```
puppetserver ca list --all
```
{Terminal 2}

[Login to given app server as per task and switch to root]
