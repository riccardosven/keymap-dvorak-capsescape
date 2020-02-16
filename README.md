# keymap-dvorak-capsescape
A dvorak keymap with capslock mapped to escape to be used in virtual terminals

To use the keymap put `KEYMAP=dvorak-capsescape` in `/etc/vconsole.conf`
```
# echo 'KEYMAP=dvorak-capsescape' > /etc/vconsole.conf
```
alternatively, using `localectl`
```
# localectl --no-convert set-keymap dvorak-capsescape
```
