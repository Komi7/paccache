# paccache


```
sudo mkdir /etc/pacman.d/hooks
sudo nvim /etc/pacman.d/hooks/clean_package_cache.hook
```

Add the following lines:

```
[Trigger]
Operation = Upgrade
Operation = Install
Operation = Remove
Type = Package
Target = *
[Action]
Description = Cleaning pacman cache...
When = PostTransaction
Exec = /usr/bin/paccache -r
```
