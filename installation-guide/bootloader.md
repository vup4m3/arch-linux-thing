# Boot Loader

##  Add Window to grub

```console
$ mkdir -p /mnt/windows
$ mount /dev/sda1 /mnt/windows
$ grub-mkconfig -o /boot/grub/grub.cfg
```