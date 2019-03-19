# GRUB2 File Manager 
 ![](https://img.shields.io/github/license/a1ive/grub2-filemanager.svg?style=flat) ![](https://img.shields.io/github/downloads/a1ive/grub2-filemanager/total.svg?style=flat) ![](https://img.shields.io/github/release/a1ive/grub2-filemanager.svg?style=flat) 

## 预览 

![preview.png](https://github.com/a1ive/grub2-filemanager/raw/gh-pages/preview.png)

## 功能 
1. 启动 efi,iso,img,Linux kernel,Multiboot kernel 文件
2. 挂载 iso,img,tar,gz,xz 查看内容 
3. 查看文本文件内容, 支持 GBK/UTF-8 编码 
4. 浏览 jpg,png,tga 图片 
5. 加载 GRUB 2,Syslinux 菜单 
6. 执行 Lua 脚本 

## 下载 
[Releases](https://github.com/a1ive/grub2-filemanager/releases) 

## 构建 
### Linux 
```shell
git clone https://github.com/a1ive/grub2-filemanager.git
cd grub2-filemanager
wget -O legacy/ntboot/NTBOOT.MOD/NTBOOT.NT6 https://github.com/a1ive/grub2-filemanager/raw/binfiles/NTBOOT.NT6
wget -O legacy/ntboot/NTBOOT.MOD/NTBOOT.PE1 https://github.com/a1ive/grub2-filemanager/raw/binfiles/NTBOOT.PE1
wget -O legacy/wimboot https://github.com/a1ive/grub2-filemanager/raw/binfiles/wimboot
./build.sh
```

## 启动 
**不要使用 memdisk 加载 grubfm.iso !**  
### GRUB4DOS 
```
map --mem /grubfm.iso (0xff)
map --hook
chainloader (0xff)
```
### GRUB 2
```
if [ "${grub_platform}" = "pc" ]; then
  linux /loadfm  
  initrd /grubfm.iso  
else
  chainloader /grubfm.efi
fi
```
### rEFInd 
```
loader /grubfm.efi
```
### Systemd-boot 
```
efi /grubfm.efi
```

## 支持的发行版列表 
*    4MLinux
*    Acronis True Image
*    Android-x86(6.0+)
*    antiX
*    Apricity OS
*    Antergos
*    Arch Linux(FAT32 only)
*    ArchBang
*    Archboot
*    Backbox
*    BlackArch
*    Bodhi
*    Calculate Linux
*    CDlinux
*    CentOS(FAT32 only)
*    Clonezilla
*    CyanogenMod (LineageOS)
*    DBAN(Legacy-BIOS only)
*    Debian Live
*    Debian/kFreeBSD
*    Deepin
*    Devuan Live
*    elementaryOS
*    Elive
*    ExTiX
*    Fedora(FAT32 only)
*    FreeBSD(bootonly ISO, Legacy-BIOS only)
*    FreeDOS(Legacy-BIOS only)
*    FreeNAS
*    Gentoo
*    GParted Live
*    grml
*    HelenOS(Legacy-BIOS only)
*    IPFire
*    Knoppix
*    Kali Linux
*    KaOS
*    KDE-neon
*    KolibriOS(Legacy-BIOS only)
*    Linux Lite
*    LinuxMint
*    Lubuntu
*    Manjaro
*    Memtest86
*    MiniTool Partition Wizard
*    MX Linux
*    NetBSD(Legacy-BIOS only)
*    OpenBSD(Legacy-BIOS only)
*    OpenSUSE
*    OpenSUSE Tumbleweed
*    OpenMandriva
*    Parted Magic
*    PCLinuxOS
*    Peppermint
*    pfSense
*    PhoenixOS
*    PIXEL
*    Plop Linux Live
*    Porteus
*    Q4OS
*    Redcore Linux
*    RemixOS(3.0+)
*    siduction
*    Slackware
*    Slax
*    Slitaz(Legacy-BIOS only)
*    SmartOS(Legacy-BIOS only)
*    Solus
*    Super Grub2 Disk
*    System Rescue CD
*    Tails
*    Ubuntu
*    Void Linux
*    Wifislax/Wifislax64
*    Wifiway
*    Windows PE(Legacy-BIOS only)
*    Xubuntu
*    ZorinOS

## 源码 
*	[GRUB2 File Manager](https://github.com/a1ive/grub2-filemanager)  
*	[GRUB2 MOD](https://github.com/a1ive/grub2-mod) 

## 相似项目 
*	[Multiboot USB](http://mbusb.aguslr.com/) 
*	[grub-iso-boot](https://github.com/Jimmy-Z/grub-iso-boot) 
*	[grub-iso-multiboot](https://github.com/mpolitzer/grub-iso-multiboot) 
*	[GLIM](https://github.com/thias/glim) 
*	[Easy2Boot](http://www.easy2boot.com/) 
*	[GRUB2 File Explorer](http://bbs.wuyou.net/forum.php?mod=viewthread&tid=320715) 
*	[RUN](http://bbs.wuyou.net/forum.php?mod=viewthread&tid=191301) 
*	[G4D AUTOMENU](http://bbs.wuyou.net/forum.php?mod=viewthread&tid=203607) 
