arch-dm-cache-rootfs
====================

HowTo:

* build package
* install package
* add dm-cache to HOOKS in /etc/mkinitcpio.conf

    HOOKS="base udev autodetect modconf keyboard block mdadm dm-cache btrfs filesystems"

* update inird ->

    mkinitcpio -p linux

* create your dm-cache 

    man lvmcache

* reboot

