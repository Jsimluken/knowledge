## Bash shortcut
- [blog](https://blog.ssdnodes.com/blog/cheatsheet-bash-shortcuts/)
## Change directory name to English from Japanese
 ```
 LANG=C xdg-user-dirs-gtk-update
 ```
## List HDDs
```
lsblk
```
## Get UUID
```
blkid
# Maybe it requires sudo
```

## Generate ssh key
```
ssh-keygen -t rsa -b 4096
# copy pub key to "authorized_keys" file
```
## Tor!!
```
sudo apt install tor //for ubuntu
sudo systemctl start tor //as default service
```
## Check logs
``` 
journalctl -ex
```

## Tar
```
tar -Jxvf hyper.tar.xz //for *.tar.xz
```

## Systemd
 [qiita](https://qiita.com/DQNEO/items/0b5d0bc5d3cf407cb7ff): How to setup daemon
