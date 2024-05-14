# Zeek_Install_Instructions
Installation Instructions for Zeek Sensors

apt update -y 
apt upgrade -y 

apt install curl gnupg2 wget -y 

curl -fsSL https://download.opensuse.org/repositories/security:zeek/xUbuntu_22.04/Release.key | gpg --dearmor | tee /etc/apt/trusted.gpg.d/security_zeek.gpg 
 
echo 'deb http://download.opensuse.org/repositories/security:/zeek/xUbuntu_22.04/ /' | tee /etc/apt/sources.list.d/security:zeek.list 

apt update -y 
apt install zeek 

#Choose local only 
#Keep default mail name 
 
echo "export PATH=$PATH:/opt/zeek/bin" >> ~/.bashrc 
source ~/.bashrc 

#Run 
zeek --version  

#To see current version and validate Zeek installed correctly 

nano /opt/zeek/etc/networks.cfg 

10.0.0.0/8          Private IP space 
172.16.0.0/12       Private IP space 
192.168.0.0/16      Private IP space 

nano /opt/zeek/etc/node.cfg 
