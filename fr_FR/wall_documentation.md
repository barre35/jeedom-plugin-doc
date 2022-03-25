Description
===

Plugin pour configurer  un Raspberry PI equipé d'un écran tactile pour interragir avec votre jeedom.

Construction
===

### Assemblage du matériel

![step-1](https://barre35.github.io/jeedom-plugin-wall/assets/images/poe.jpg)

TODO ...

### Installation des outils sur votre PC

Télécharger Win32DiskImager : https://sourceforge.net/projects/win32diskimager/files/latest/download

Télécharger Putty : https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

### Création de la carte SD

Télécharger et installer l'image Raspbian Buster Lite : https://downloads.raspberrypi.org/raspbian_lite_latest

Créer un fichier nommé "ssh" sur la carte SD

### Customiser l'OS du raspberry

Mettre la carte dans e raspberry pi et démarrer

Se connecter en ssh au raspberry (longin pi / mdp raspberry)

Ajouter la ligne suivante dans le fichier /boot/config.txt

> lcd_rotate=2

Mettre à jour l'OS

> sudo apt update
> sudo apt upgrade

Installer le server X et le navigateur chrome

> sudo apt-get install xserver-xorg-video-all xserver-xorg-input-all xserver-xorg-core xinit x11-xserver-utils lightdm chromium-browser unclutter

Modifier le démarrage avec le boot en desktop/cli et autologin

> sudo raspi-config

Ajouter un fichier .Xsession

>\#!/bin/sh
>xset -dpms
>xset s 120
>unclutter &
>chromium-browser 127.0.0.1 --kiosk --window-position=0,0 --window-size=800,480 --start-fullscreen --incognito --noerrdialogs --disable-translate --no-first-run--fast --fast-start --disable-infobars --disk-cache-dir=/dev/null

Installer nginx

>sudo apt install nginx

Créer le fichier setup.sh

>\#!/bin/sh
>
>date > setup.log
>
>echo JEEDOM IP IS $1 > setup.log
>
>echo DELETE OLD RELEASE >> setup.log>
>
>rm Wall.zip
>rm -R Wall
>
>echo GET NEW RELEASE >> setup.log
>
>wget http://$1/plugins/wall/Wall.zip
>
>echo INSTALL NEW RELEASE >> setup.log
>
>sudo rm -R /var/www/html
>unzip Wall.zip
>sudo mv Wall /var/www/html
>
>echo CONFIGURE NEW RELEASE >> setup.log
>
>sudo echo "{  \"jeedom\": { \"key\": \"$2\", \"timer\": \"$3\" }, \"wall\": { \"key\": \"$4\", \"dashboard\": \"$5\" } }" > /var/www/html/assets/boot.json
>
>echo SUCCESS INSTALL >> setup.log
>
>echo "###SUCCESS###"

puis chmod 777 setup.sh

Créer le fichier  reboot.sh

>\#!/bin/sh
>
>date > reboot.log
>
>echo "###SUCCESS###"
>
>sleep 5
>
>sudo reboot

chmod 777 reboot.sh

Ajouter la conf proxy à nginx (en remplacant par votre ip jeedom) dans le fichier /etc/nginx/sites-enabled/default

>location /api/ {
>    proxy_pass http://192.168.1.110/;
>}

Aller sur jeedom et configurer votre wall

Installer et rebooter le wall à partir de jeedom

Installation 
===


Configuration
===


Utilisation
===


Pour aller plus loin
===

Penser à noter le plugin sur le market et faites part de vos remarques, demandes d'évolutions et bugs sur le forum [https://community.jeedom.com/tag/plugin-wall](https://community.jeedom.com/tag/plugin-wall)

