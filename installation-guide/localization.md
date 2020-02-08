# Localization /Traditional Chinese

## 字體

>下載思源體

```console
sudo pacman -S adobe-source-han-sans-tw-fonts adobe-source-han-sans-cn-fonts
```

>修改 /etc/locale.gen 文件，將需要的語系前面的註解 (# 符號)刪除。

```bash
zh_TW.UTF-8
zh_TW.Big5
```

>之後執行 locale-gen 指令即可。 

```console
# locale-gen
```

## 輸入法

>安裝fcitx

```console
# pacman -S fcitx fcitx-im fcitx-configtool fcitx-chewing
```

## 在圖形介面中啟用中文 locale

>如果是希望在圖形介面有中文環境的話，需要修改 `~/.xinitrc` 或 `~/.xprofile`，加入

```bash
#!/bin/bash
export LANG="zh_TW.UTF-8"
export LC_ALL=zh_TW.UTF-8
export XMODIFIERS="@im=fcitx"
export XMODIFIER="@im=fcitx"
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export DefaultIMModule=fcitx
export XMODIFIERS=@im=fcitx
export LC_CTYPE=zh_TW.UTF-8
fcitx &
```
