# install manjaro KDE on lenovo thinkpad x1 carbon(gen6)

## Specs
- X1 Carbon 6th Gen
- core intel i7-8550U processor
- 16GB RAM
- 256GB SSD

## Linux
- manjaro KDE

## 設定
**設定 mirror server**
```
sudo pacman-mirrors --country Taiwan
```

**更新簽名**
```
sudo pacman -Sy manjaro-keyring manjaro-system
```

**有事沒事更新一下**
```
sudo pacman -Syyu
```

**安裝 yay**
```
sudo pacman -S base-devel
sudo pacman -S yay
```

**休眠模式調整** 

/etc/default/grub -> GRUB_CMDLINE_LINUX_DEFAULT 加這行 acpi.ec_no_wakeup=1

/etc/systemd/logind.conf 取消註解 HandleLidSwitch=suspend

螢幕蓋上會進入 suspend 模式

**terminal**
- https://gist.github.com/yovko/becf16eecd3a1f69a4e320a95689249e
```
pacman build zsh-theme-powerlevel10k-git
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc

# restart konsole
p10k configure
```

**安裝中文輸入法**

原本想用 Hime 但不支援 wayland 所以只好改用 ibus


---
# install manjaro GNOME on lenovo thinkpad x1 carbon(gen6)

## Specs
- X1 Carbon 6th Gen
- core intel i7-8550U processor
- 16GB RAM
- 256GB SSD

## Linux
- manjaro GNOME

## others
**安裝中文輸入法**  
https://notes.wadeism.net/post/manjaro-gnome-install-hime-boshiamy/
- 沒辦法打ㄤ (已解決，把 keyboard layout 改為 us 即可)

**鍵盤位置調整 swap caps and ctrl**  
https://ithelp.ithome.com.tw/articles/10195361
```
sudo pacman -S xorg-setxkbmap
setxkbmap -option ctrl:swapcaps
```
**休眠模式**
/etc/default/grub -> GRUB_CMDLINE_LINUX_DEFAULT 加這行 acpi.ec_no_wakeup=1

/etc/systemd/logind.conf 取消註解 HandleLidSwitch=suspend

螢幕蓋上會進入 suspend 模式

**ArcMenu+dash to panel 設定畫面**

## review
- Wifi ok
- Audio ok
- monitor:
  - 外接螢幕無法獨立設定 scale
- trackpoint: ok
- trackpad: window system wayland fine、但 x1 只有頁面捲動手勢能用
- fn 鍵: ok

## tmp
Thunderbolt BIOS Assist Mode Enabled

## resource
https://wiki.archlinux.org/title/Lenovo_ThinkPad_X1_Carbon_(Gen_6)
