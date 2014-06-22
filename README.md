arch-dm-cache-rootfs
====================

HowTo:

* build package
* install package
* add your dmsetup lines to /etc/dm-cachetab

    --
    dmsetup create ssd_back --table '0 1563133952 cache /dev/sda2 /dev/sda3 /dev/md0 512 1 writeback default 0'
    --

* add dm-cache to HOOKS in /etc/mkinitcpio.conf

    --
    HOOKS="base udev autodetect modconf keyboard block mdadm dm-cache btrfs filesystems"
    --

* update inird ->

    mkinitcpio -p linux

* enable dm-cache.service

    systemctl enable dm-cache

* reboot
