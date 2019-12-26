# Post-install process
Assuming base install with git on top
## zsh + theme
* pacman -S zsh 
* chsh
* git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
* **echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>! ~/.zshrc**
## Rank mirrors
*pacman-contrib*
* sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup
* sudo rankmirrors -n 10 /etc/pacman.d/mirrorlist.backup > /etc/pacman.d/mirrorlist
## Xorg + i3
* sudo pacman -S i3 xorg xorg-xinit
* echo "exec i3" > ~/.xinitrc
## Lightdm
=> *virtualbox mandatory ?*
* sudo pacman -S lightdm lightdm-webkit-theme-litarvan
* systemctl enable lightdm
* vim /etc/lightdm/lightdm.conf
    * *update [Seat:\*] greeter-session=lightdm-webkit2-greeter*
* vim /etc/lightdm/lightdm-webkit2-greeter.conf
    * *update [greeter] webkit_theme = litarvan*
## Terminal
* sudo pacman -S termite
## Applications
* sudo pacman -S firefox mpv thunar
* yay keeweb ufetch
