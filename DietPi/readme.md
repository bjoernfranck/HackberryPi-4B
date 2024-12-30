## DietPi installation on HackberryPi-4B

### 1. **Preparation**
- **Hardware:**
  - HackberryPi Zero 4B 2GB RAM / 4GB RAM / 8GB RAM (mine is the 8GB RAM Version)
  - microSD card at least 4 GB, preferably 8 GB or more (I use a 128GB microSD Card)
  - Power supply for the HackberryPi (recommended)
  - microSD card reader (if your computer doesn’t have a built-in card reader)
  - Optional: Keyboard, mouse

- **Software:**
  - Rufus (a Windows tool to create bootable USB or SD cards)
  - DietPi image (for the Raspberry Pi 4B)
  - Some time and patience

### 2. **Download DietPi Image**
1. Visit the [official DietPi website](https://dietpi.com/).
2. Go to the **Download** section, choose the **Raspberry** section and than the **Raspberry Pi 2/3/4/Zero 2** version.
3. Download the **DietPi image** for the Raspberry Pi (make sure it’s for the Raspberry Pi 4B).

### 3. **Download and Install Rufus**
1. Download **Rufus** from the [official Rufus website](https://rufus.ie/).
2. Install Rufus on your computer if you haven’t already.

### 4. **Prepare the microSD Card**
1. Insert the microSD card your computer using a card reader.
2. Open Rufus.

### 5. **Write DietPi to the microSD Card**
1. In Rufus, select your microSD card as the target drive.
2. Click **Select** and find the DietPi image you downloaded earlier (it should be a .img.yz file).
3. Make sure under "Partition Scheme" it’s set to **MBR**, and under "File System" it’s set to **Large FAT32**.
4. Click **Start** to write the image to the microSD card. Wait until the process is completed.

### 6. **Set Up the Raspberry Pi**

**Important**


1. Download this ZIP. [config-display_driver.zip](https://github.com/bjoernfranck/HackberryPi-4B/blob/main/DietPi/config-display_driver.zip)
Simply use the two files and it works. There are two files in the ZIP. (hyperpixel4.dto and config.txt)
Copy this two files on the mircoSD hyperpixel4.dtbo to `/boot/overlays/` and config.txt to SD root folder. 

2. Than, safely remove the microSD card from your computer and insert it into the HackberryPi.
3. Connect the HackberryPi to power, and optionally to a keyboard / mouse.
4. The HackberryPi should now boot from the SD card and start DietPi.

### 7. **Initial Configuration of DietPi**
1. After DietPi boots up, you will be prompted to set up basic settings such as language and keyboard layout.
2. Connect the HackberryPi to the internet (Use the `dietpi-config` menu to connect Wi-Fi (either via Wi-Fi or using a USB-to-Ethernet adapter).
3. Perform the initial update of DietPi if prompted.

### 8. **Install Software on DietPi**
DietPi provides a lightweight menu system to install additional software like web servers, databases, media servers, and more.

You can configure this using the **DietPi-Software** menu:
```bash
dietpi-software
```

### 9. **All Done!**
DietPi is now running on your Hackberry-4B!

## **Additional setup**
### HDMI-Port
The HackberryPi has a mini-HDMI port on its top side, allowing you to connect it to an additional screen. You can use the commands below to turn the display on or off.
```bash
vcgencmd display_power 0
vcgencmd display_power 1
```
### For GUI (Xfce)
You can xfce install in the `dietpi-software` menu (see 8.)
A package must be installed for the GUI.
I only tested Xfce!
```bash
sudo apt install dbus-x11
```
Start the GUI
```bash
startx
```

### Change font size in terminal
```bash
sudo dpkg-reconfigure console-setup
```
