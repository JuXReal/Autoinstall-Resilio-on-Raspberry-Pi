# Autoinstall-Resilio-on-Raspberry-Pi

You dont have to search for a installer... is easy :-)

Just follow these steps

#1.Create a folder

sudo mkdir    /opt/resilio/
sudo mkdir -p /opt/resilio/bin
sudo mkdir /opt/resilio/app_files

#2.Change Directory
cd /opt/resilio/bin

#3.Get the stuff
sudo wget https://download-cdn.resilio.com/stable/linux-arm/resilio-sync_arm.tar.gz

#4.Extract
sudo tar -xvf resilio-sync_arm.tar.gz

#5.Houskeeping (cleanup) -> you have to be in the folder :-)
sudo rm -f *.gz

#6.Start Resilio
sudo ./rslsync --webui.listen 0.0.0.0:8888

#7.Autostart via Crontab

Crontab -e 

#8.Add this line
@reboot sudo ./rslsync --webui.listen 0.0.0.0:8888



Thats it. You dont need a script :-)
