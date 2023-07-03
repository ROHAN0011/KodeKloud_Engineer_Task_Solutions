[Open two terminals and switch to root on jump_host itself]

{{{{{ Terminal 1 }}}}}

Open vi editor and add puppet infront of last 3 lines
```
vi /etc/hosts
```
After that,
```
puppetserver ca list --all
```
```
cat /etc/hosts
```


{{{{{ Terminal 2 }}}}}

[Login to given app server as per task and switch to root]
Remove jump_host line and add last two 3 lines from Terminal 1 (which we got using cat /etc/hosts)
```
vi /etc/hosts
```
```
ping puppet
```
```
systemctl restart puppet
```
```
systemctl status puppet
```

{{{{{ Terminal 1 }}}}}
```
puppetserver ca list --all
```
```
puppetserver ca sign --all
```


{{{{{ Terminal 2 }}}}}

Validation
```
puppet agent -t
```
