# SAMBA and Raspberry PI

## Install Samba

In the terminal:

    sudo apt install samba samba-common-bin

## Config
Open with your favorite text editor:
    
    sudo nano /etc/samba/smb.conf
    
And add this to the end:

    [Documents]
    comment = Share Directory
    path = /home/pi/Documents
    browseable = Yes
    writeable = Yes
    only guest = no
    create mask = 0644
    directory mask = 0755
    public = no

Save and exit.
## Create a new user for SAMBA

    sudo smbpasswd -a pi
      
Input a new user and password, in my case i used "pi".

## Test config
Test out the Samba configuration file with testparm. Enter
the following:
    
    testparm

## Test SAMBA
In the address bar of your file browser type \\\ip-raspberrypi and enter your user and pass.
For example on Windows 10.
(https://github.com/EduardoAule/SAMBA-Raspberry-PI/blob/master/samba.png)
![samba-windows](https://raw.githubusercontent.com/EduardoAule/SAMBA-RaspberryPI/master/samba.png)
