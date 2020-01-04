# 安裝指南

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

### 有線網路

```console
# pacman -S dhcpcd
# pacman -S networkmanager
# systemctl NetworkManager.service
```

## 開機程式

```console
# pacman -S grub efibootmgr
# grub-install --target=x86_64-efi --efi-directory=/efi --bootloader-id=GRUB
# grub-mkconfig -o /boot/grub/grub.cfg
```
