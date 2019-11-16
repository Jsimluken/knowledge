## Bash shortcut
- [blog](https://blog.ssdnodes.com/blog/cheatsheet-bash-shortcuts/)
## Change directory name to English from Japanese
 ```
 LANG=C xdg-user-dirs-gtk-update
 ```

## Generate ssh key
```
ssh-keygen -t rsa -b 4096
# copy pub key to "authorized_keys" file
```
## Tor!!
```
sudo apt install tor //for ubuntu
sudo systemctl start tor //デフォルトのサービスに
```
## Check logs
``` 
journalctl -ex
```

## Systemd
 [qiita](https://qiita.com/DQNEO/items/0b5d0bc5d3cf407cb7ff): How to setup daemon
