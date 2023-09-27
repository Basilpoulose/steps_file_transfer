#**Setting up Raspberry Pi and Transferring Files via SSHFS**

### Raspberry Pi Setup
 - Use Raspberry Pi Imager tool to write the Raspberry Pi OS Lite image to the microSD card.
 - Before Flashing:
	 - Enable SSH.
	 - Configure Wi-Fi for your respective network.

### Mounting a USB Drive on Local System 
 
#### Mounting a USB Drive on RPi
 - Install "pmount"
 - Find the drive location using:
	 -     lsblk
 - Mount the Pendrive
	 -     pmount  /dev/sda1

#### Unmounting a USB Drive on RPi
     pumount /dev/sda1
    
#### Mounting USB Drive on to Local System: Ubuntu
    
 - Create a Local Directory
	 -      mkdir pi_mount
 - Mounting Pendrive from Raspberry Pi
	 -     sshfs pidata@192.168.0.103:/media/sda1/ /home/local/pi_mount

#### Unmounting USB Drive from the Local Device(Ubuntu)
      pumount ~/pi_moun
 
### Mounting RPi on Windows via CMD
   - Mounting RPi with net use
	 -     net use X: \\sshfs.r\pidata@192.168.0.103
 - Unmounting RPi 
	 -     net use X: /delete