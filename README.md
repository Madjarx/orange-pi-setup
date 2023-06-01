# Set up Orange PI lts 3 like a G tutorial

### step 1
Make sure you have the following before proceeding. 

Hardware
1. Orange Pi Lts 3 and 5V3A usbC power source (higher amps ok, lower amps not ok)
2. hdmi cord and display
3. usb keyboard
4. MicroSD card (8GB limit for flashing boot/root to eMMC)
5. MicroSD reader 
Software
1. https://www.balena.io/etcher (for flashing SD)
2. https://drive.google.com/file/d/1SoSmoQ9Tu-XrTWLkrtnj5ep612A1m_qv/view?usp=share_link (Ubuntu Jammy image)

### step 2
Set up shit so we can then set up more shit

1. Download image and extract to desktop
2. insert MicroSD into your SD readed 
3. install/Run balenaEtcher and select .img file in extracted Ubuntu Jammy folder
4. Select your SD card as "select drive" (should suggest). Flash and wait.
5. Remove SD card and insert into pi sd hole
6. connect keyboard and display to pi then power. (connecting power will boot pi)

### step 3
Set up ssh cause bet ur ass we gonna need google

1. Login to root with "root" and password is "orangepi"
2. run command `nmcli device status` and get ur interface name (probably wlan0)
3. scan for networks with command `nmcli device wifi list ifname wlan0` and find yours.
(yours may have two entries with same name but different bssid, use second one down if this is true)
4. connect with `nmcli device wifi connect your_bssid password your_password bssid your_bssid` and wait for confirmation
(if fails, try first entrie's bssid)
5. run command `ip addr show wlan0` or your interface name and copy ip
6. go back to normal computer and something like `ssh root@ip` then enter password "orangepi"

### step 4
Set up scale test to make sure shit works




