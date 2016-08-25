![Raspberry Display Chart](https://cloud.githubusercontent.com/assets/51700/17963298/300d1f0a-6ab5-11e6-9b9b-b9a6e4f14844.jpg)

##INSTALL

sudo apt-get install matchbox x11-xserver-utils unclutter midori

vi presentation.sh  

    #!/bin/sh  
    unclutter &  
    matchbox-window-manager & :  
    xset -dpms  
    xset s off  
    while true; do  
    /usr/bin/midori -e Fullscreen -a /home/pi/chart.html  
    done  

chmod 755 presentation.sh

sudo vi /etc/rc.local  
    
    su -l pi -c "xinit /home/pi/presentation.sh"

sudo dpkg-reconfigure x11-common  
set to "anybody"