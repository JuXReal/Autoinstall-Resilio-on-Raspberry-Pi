# Autoinstall-Resilio-on-Raspberry-Pi

You dont have to search for a installer... is easy :-)

#Create a folder
sudo mkdir -p /opt/resilio/bin

sudo mkdir /opt/resilio/app_files

#Change Directory
cd /opt/resilio/bin

#Get the stuff
sudo wget https://download-cdn.resilio.com/stable/linux-arm/resilio-sync_arm.tar.gz

#Extract
sudo tar -xvf resilio-sync_arm.tar.gz

#Houskeeping (cleanup) -> you have to be in the folder :-)
sudo rm -f *.gz

#Start Resilio
sudo ./rslsync --webui.listen 0.0.0.0:8888

#Autostart via Crontab

Crontab -e 

#Add this line
@reboot sudo ./rslsync --webui.listen 0.0.0.0:8888



Thats it. You dont need a script :-)
