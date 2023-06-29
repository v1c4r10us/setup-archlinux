# Intro
This repo is about instruction for setup an ArchLinux lightweigth on a new server or localmachine

# Features
+ LightDM
+ i3
+ NetworkManager
+ TigerVNC
+ yay

# Instructions

1. Install archlinux on your server via archinstall 
2. Install lightdm
```bash
$ sudo pacman -S lightdm lightdm-slick-greeter
```
3. Install i3 and other components
```bash
$ sudo pacman -S i3 alacritty rofi picom scrot feh git
```
4. Install xorg
```bash
$ sudo pacman -S xorg xorg-server
```
5. Configure greeter: Edit /etc/lightdm/lightdm.conf
```bash
[Seat:*]
greeter-session=lightdm-slick-greeter
```
6. Enable lightdm service
```bash
$ sudo systemctl enable lightdm.service
```
7. Configure i3: Use file on i3/config
```bash
$ cp i3/config ~/.config/i3/config
```
8. Configure GUI remote access by VNC
```bash
$ sudo pacman -S tigervnc
```
9. Create a password for VNC server:
```bash
$ vncpasswd
```
10. Configure VNC server: Use file vnc/config
```bash
$ cp vnc/config ~/.vnc/config
```
11. Manage VNC sessions: Edit file in path /etc/tigervnc/vncserver.users
```bash
:1=<your-user>
```
12. Install yay helper
```bash
$ git clone https://aur.archlinux.org/yay.git
$ cd yay
$ makepkg -si
```
13. Configure alacritty terminal: Use file alacritty/alacritty.yml
```bash
$ cp alacritty/alacritty.yml ~/.config/alacritty/alacritty.yml
```
14. Optional: Copy wallpapers of wallpapers/ia.png and wallpapers/sunsetbg.jpg
```bash
$ cp wallpapers/ia.png ~/Pictures/ia.png
$ cp wallpapers/sunsetbg.jpg ~/Pictures/sunsetbg.jpg
```
