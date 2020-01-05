# 安裝指南

## 確認主機板的開機模式

```console
ls /sys/firmware/efi/efivarsls
```

如果資料夾不存在，代表電腦以BIOS模式開啟，有東西代表UEFI。

## 網路

確認網路界面

```console
# ip link
```

### 無線網路

```console
# systemctl stop dhcp.service
# wifi-menu
```

確認網路連線

```console
# ping archlinux
```

## 更新系統時間

```console
# timedatectl set-ntp true
# timedatectl status
```

## 切割硬碟

[fdisk](https://blog.gtwang.org/linux/linux-add-format-mount-harddisk/)

[切割範例](https://wiki.archlinux.org/index.php/Partitioning#Example_layouts)

格式化硬碟

```console
# mkfs.fat -F32 /dev/[EFI]
# mkfs.ext4  /dev/[ROOT]
# mkswap /dev/[SWAP]
# swapon /dev/[SWAP]
```

## 安裝

```console
/etc/pacman.d/mirrorlist
```

留下離自己比較近的server

```console
# mount /dev/[ROOT] /mnt
# pacstrap /mnt base linux linux-firmware
```

## 配置系統

```console
# genfstab -U /mnt >> /mnt/etc/fstab
```

用*vim /mnt/etc/fstab* 來確認fstab

## Change root

```console
# arch-chroot /mnt
```

## Time zone

```console
# ln -sf /usr/share/zoneinfo/Aisia/Taipei /etc/localtime
# hwclock --systohc
```

## Localization

```console
# locale-gen
```

```console
vim /etc/locale.conf
```

```bash
LANG=en_US.UTF-8
```

## Network configuration

```console
# vim /etc/hostname
```

```bash
myhostname
```

```console
# vim /etc/hosts
```

```bash
127.0.0.1    localhost
::1                  localhost
127.0.1.1    myhostname.localdomain    myhostname
```

## Root password

```console
# passwd
```

## 使用者與群組

加入使用者

```bash
useradd -m USERNAME
passwd USERNAME
usermod -aG wheel,audio,video,optical,storage USERNAME
```

權限設置

```console
# pacman -S sudo
# visudo
```

移除註解

```bash
## Uncomment to allow members of group wheel to execute any command
 %wheel ALL=(ALL) ALL
```

## 網路設定

### 有線網路設定

```console
# pacman -S dhcpcd
# pacman -S networkmanager
# systemctl NetworkManager.service
```

### 無線網路設定

```console
# pacman -S netctl
# pacman -S dialog
# pacman -S networkmanager
# systemctl NetworkManager.service

```

## 開機程式

```console
# pacman -S grub efibootmgr
# grub-install --target=x86_64-efi --efi-directory=/efi --bootloader-id=GRUB
# grub-mkconfig -o /boot/grub/grub.cfg
```
