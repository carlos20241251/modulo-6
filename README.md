# modulo-6
practica I
 sudo apt update
   sudo apt install gnupg2 -y

crear y configurar llave
gpg2 --full-generate-key
contraseña
gpg2 --list-keys
crear directorio y archivo
cd /Desktop
mkdir prueba
cd prueba
 sudo nano clave.txt
Este es el contenido secreto
ctrl x
sudo gpg2 -e -r "carlos" clave.txt
ls 
cat clave.txt
sudo gpg2 -d clave.txt.gpg > clave_decifrado.txt
ls
cat clave_decifrado
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
PRACTICA II
erificar la web the apache y activar CMD
http://localhost

despues el servicio 
sudo systemctl status apache  vsftpd ssh

para ver los servicios habilitados
sudo iptables -L    sudo iptables -L INPUT -n --line-numbers

sudo ufw stop si esta activo 

bloquear trafico
 sudo iptables -A INPUT -p tcp --dport 80 -j DROP

despues ir ala web v=y verificar que ha sido 
parado 

despues 
sudo iptables -A INPUT -p tcp --dport 22 -j DROP
sudo iptables -A INPUT -p tcp --dport 21 -j DROP

verificar los puertos nueva mente 
sudo iptables -L
  para haceder al puerto 22  desde CMD 
SSH lavoe@192.168.10x.xx 
contraseña

despues activar los servicios

sudo iptables -D INPUT -p tcp --dport 22/80/21 -j DROP 
sudo iptables -L
verificar la web y ssh en el CMD 

despues 

sudo ufw status  / sudo ufw enable 

sudo ufw deny 80
sudo ufw deny 22
sudo ufw deny 21
verificar ssh en  y web nuevamente 
para permitir nuevamente 
despues sudo ufw allow 80
despues sudo ufw allow 21
despues sudo ufw allow 22v
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
PRACTICA IV
sudo apt install openssh-server
sudo systemctl status ssh
sudo systemctl start ssh
sudo systemctl restart ssh
sudo apt install libpam-google-authenticator

abrir  
google-authenticator  en el telepone 

 
scanear el codigo QR 
en mi caso ya esta configurado 
proveer el codigo 
luego darle a si  a toda la configuracion 
luego de configurarlo 

sudo nano /etc/pam.d/sshd
ir a la ultima linea  y 
poner auth required pam_google_authenticator.so que es para 
despues ir a sudo nano/etc/sshd_config 
buscar Kbdinteractiveauthenticacion  y poner yes al final 
ctrl o ctrl x


