# Adeepts_Learning_Kit
This repository is my findings to improve Adeepts Learning Kit's Python Program for RFID Scanner.  
As per my experience below steps are required to be performed in order to run the RFID Scanner programme.    

1) Enabling the SPI : 

SPI is serial peripheral interface bus. It can be configured from RPidesktop : 
Menu->Preferences->Raspberry Pi Configuration->Interfaces->SPI->Enable 
Now reboot the Rpi as suggested in pop-up window.

To veryfy the SPI is enabled you can enter command ls /dev/spidev0.* which should return output as /dev/spidev0.0  /dev/spidev0.1

2) Installing Python-dev and SPI-py :

Enter command sudo apt-get install python-dev

Now install SPI-py software (Free Software) needs to be installed on Rpi using below command

git  clone https://github.com/lthiery/SPI-Py
cd SPI-Py
sudo python setup.py install

3) Enable Device Tree

The device tree is a data structure for describing hardware, which originated from Open Firmware. The data structure can hold any kind of data as internally it is a tree of named nodes and properties.
Device Tree can be enabled following below steps:

sudo nano/boot/config.txt

Now go to end of the file and add additional below line:

device_tree=on

4) Cablings and Connections:
 
 RF Scanner could be connected to the Rpi using the cablings as shown in RFID.docx.

5) Initialising the RFID Scanner

RFID Scanner could be started by executing below command.

$ sudo python Read.py

Now RFID scanner is activated and as soon as a RFID reader card/ring is brought in it's proximity the ID number will be sent to the Raspberry Pi terminal.


