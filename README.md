# What?

# Installation
`yaourt -S mkinitcpio-overlayfs`

# Configuration
To enable the hook you need to edit the configuration file `/etc/mkinitcpio.conf`. With this you can customize your ramdisk with additional modules, scripts, files and what not.

However, after a clean Arch Linux installation you will find a line which looks like this:
```
HOOKS=(base udev autodetect modconf block filesystems keyboard fsck)
```

Just put `overlayfs` at the right time / position you want to run it, like below. In this example it will be executed last.
```
HOOKS=(base udev autodetect modconf block filesystems keyboard fsck overlayfs)
```

Finally run the following command to rebuild your ramdisk.
```
mkinitcpio -P
```
