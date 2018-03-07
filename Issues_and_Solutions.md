# Issues and Fixes - ALL TESTED on Ubuntu 16.04 and Windows 10

### OPERATION SYSTEMS
#### 1) Faulty Disc During Installation
- Solution: Change Live USB, Test RAM, or Hardware Issue

#### 2) Cannot boot into Windows after dual boot installation
- Solution: https://askubuntu.com/questions/435160/cant-boot-windows-7-after-installing-ubuntu

#### 3) DUAL BOOT Windows 10 & Ubuntu. Shrink/Resize Windows partion. Error: no such partion. Entering rescue mode. grub rescue>
___Method 1___ (Tested):

__Step 1:__
- Need a bootable Live CD Ubuntu drive. Enter Trying Ubuntu mode
- Start a terminal to install [Boot-Repair](https://help.ubuntu.com/community/Boot-Repair):

```
sudo add-apt-repository ppa:yannubuntu/boot-repair
sudo apt-get update
sudo apt-get install -y boot-repair && boot-repair
```
- Launch boot-repair on terminal, type: `boot-repair` > Choose __Recommended repair__
- Grub should be fixed after repair. Reboot. The GRUB menu should show up after Reboot, but there is Ubuntu option only, no Windows.
- Boot into Ubuntu for next step.

__Step 2:__
- After access to Ubuntu again, start a new terminal.
- Type: `sudo update-grub`
- Grub update with recognition of Windows existence. Wait for the update to finish. Reboot.
- Windows option should show up in Grub menu after reboot

#### 4) Modifying GRUB. Edit GRUB menu time. Make changes. Copy from top answer from [here](https://askubuntu.com/questions/281119/how-do-you-run-update-grub)

___Phase 1 - Note: don't use a Live CD.___

- In your Ubuntu open a terminal (press Ctrl+Alt+T at the same time)
- Type `gksu gedit /etc/default/grub`
- This will run text-editor gedit, if you're using another one just type the name of it instead of gedit.
- Make the changes you would like to make and save them.
Close gedit.
- Your terminal should still be open.
In the terminal type `sudo update-grub`, wait for the update to finish.
- Reboot your computer.

___Phase 2 - After you have logged into your system___

- Open a terminal again (Ctrl+Alt+T).
- Type in the terminal gksu gedit /etc/default/grub
- To see the grub-menu at boot time,
comment or remove the following line: `GRUB_HIDDEN_TIMEOUT=0`
- To comment, add # at the beginning of this line, the result will be `#GRUB_HIDDEN_TIMEOUT=0`
Save the file.
- Again in the terminal run `sudo update-grub`.

#### 5) Login screen freezed after a few cursor blinking after update.
- Access recover mode: Choose __Advanced Ubuntu__ at Grub, then choose __Recovery Mode__ option at latest kernel.
- Choose __update grub__, __dpkg__, __enable network__, then access __root__
- Try to install packages in this [solution](https://askubuntu.com/questions/91543/apt-get-update-fails-to-fetch-files-temporary-failure-resolving-error).
- If having issue with __Unable to fetch packages__ error, try temporary fix [here](https://askubuntu.com/questions/91543/apt-get-update-fails-to-fetch-files-temporary-failure-resolving-error) with:
`echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null`

### IT & APPLICATIONS
#### 1) Fix corrupted USB drive with Window Diskpart. Format USB drive after using as bootable drive.
- https://www.youtube.com/watch?v=KWUM6iwPKvA

#### 2) Install .deb file in Linux:
- https://unix.stackexchange.com/questions/159094/how-to-install-a-deb-file-by-dpkg-i-or-by-apt

#### 3) Installation for Deep Learning (Tensorflow)
- https://medium.com/@vivek.yadav/deep-learning-setup-for-ubuntu-16-04-tensorflow-1-2-keras-opencv3-python3-cuda8-and-cudnn5-1-324438dd46f0
