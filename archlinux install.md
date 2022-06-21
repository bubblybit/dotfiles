---
category: linux
tags: ['install', 'partition', 'package']
---

1) create gpt filetable and partition using #fdisk
| partition | size | partitioning      |
| --------- | ---- | ----------------- |
| sda1      | 1M   | BIOS Boot         |
| sda2      | 8G   | swap              |
| sda3      | * | Linux filesystem|
2) mkfs.ext4 sda3
3) mount everything

> mount /dev/sda3 /mnt
mkswap /dev/sda2
swapon /dev/sda2

4) install pacstrap...

https://wiki.archlinux.org/title/Installation_guide

### grub bootloader
> pacman -S grub
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg

### packages
```javascript
pulseaudio
pulseaudio-alsa
networkmanager
bash-completion
xorg xorg-xinit
i3-gaps
i3status
i3lock
nvidia nvidia-utils lib32-nvidia-utils nvidia-settings
man-pages
lightdm
lightdm-gtk-greeter
thunar
thunar-volman
thunar-archive-plugin
bluez
bluez-utils
blueman
rofi
xface-terminal
```

### startup
include startup applets into i3-config


### scripts
- i3exit.sh https://raw.githubusercontent.com/arcolinux/arcolinux-i3wm/master/etc/skel/.config/i3/scripts/i3exit.sh

# References
https://wiki.archlinux.org/title/Installation_guide

https://wiki.archlinux.org/title/General_recommendations






